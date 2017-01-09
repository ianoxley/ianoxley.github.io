---
date: '2008-06-07 08:01:05'
layout: post
slug: adding-custom-attributes-to-aspnet-site-map-files-to-improve-accessibility
status: publish
title: Adding Custom Attributes to ASP.NET Site Map Files to Improve Accessibility
wordpress_id: '20'
categories:
- accessibility
- asp.net
tags:
- accessibility
- asp.net
- sitemap
---

The Web.sitemap file was introduced in ASP.NET 2.0 and provides a really easy way to bind data to menus in your site. For example, given a Web.sitemap file containing this:
    
    <sitemap
        xmlns="http://schemas.microsoft.com/AspNet/SiteMap-File-1.0">
      <sitemapnode url="Default.aspx" title="Home"
            description="">
        <sitemapnode url="about.aspx" title="About"
            description="">
        <sitemapnode url="contact.aspx" title="Contact"
            description="">
      </sitemapnode>
    </sitemapnode>
    
We can bind this to a Repeater control using a SiteMapDataSource control to generate a list of links like so:
    
    <ul>
      <asp:SiteMapDataSource ID="siteMapData" runat="server"
            ShowStartingNode="false" />
      <asp:Repeater ID="menu" runat="server"
            DataSourceID="siteMapData">
        <ItemTemplate>
          <li>
            <a href="<%# Eval("url") %>"><%# Eval("title") %></a>
          </li>
        </ItemTemplate>
      </asp:Repeater>
    </ul>
    
This, unsurprisingly, renders the following HTML:
    
    <ul>
      <li>
        <a href="about.aspx">About</a>
      </li>
      <li>
        <a href="contact.aspx">Contact</a>
      </li>
    </ul>
    
Nothing you probably didn't know already. But to make our menu more accessible, we can utilise the empty description attribute that Visual Studio provides us with by default to add some text to render as a HTML title attribute on each link:
    
    <sitemap xmlns="http://schemas.microsoft.com/AspNet/SiteMap-File-1.0">
      <sitemapnode url="Default.aspx"
            title="Home" description="Return to homepage">
        <sitemapnode url="about.aspx"
            title="About" description="About company XYZ">
        <sitemapnode url="contact.aspx" title="Contact"
            description="How to get in touch with us">
      </sitemapnode>
    </sitemapnode>

Now we just need to tweak our code slightly:
    
    <ul>
      <asp:SiteMapDataSource ID="siteMapData" runat="server"
        ShowStartingNode="false" />
      <asp:Repeater ID="menu" runat="server"
            DataSourceID="siteMapData">
        <ItemTemplate>
          <li>
            <a href="<%# Eval("url") %>" title="<%# Eval("description") %>">
                <%# Eval("title") %></a></li>
        </ItemTemplate>
      </asp:Repeater>
    </ul>

Which will render:
    
    <ul>
      <li>
        <a title="About company XYZ" href="about.aspx">About</a>
      </li>
      <li>
        <a title="How to get in touch with us" href="contact.aspx">Contact</a>
      </li>
    </ul>

This will show the description text as a title when you mouseover each link. But we can take this a step further as the ASP.NET site map files support custom attributes. Lets add an access key so that users can navigate using their keyboard:
    
    <sitemap xmlns="http://schemas.microsoft.com/AspNet/SiteMap-File-1.0">
      <sitemapnode url="Default.aspx"
            title="Home" description="Return to homepage" accesskey="H">
        <sitemapnode url="about.aspx"
            title="About" description="About company XYZ" accesskey="A">
        <sitemapnode url="contact.aspx" title="Contact"
            description="How to get in touch with us" accesskey="C">
      </sitemapnode>
    </sitemapnode>

Custom attributes are accessed via an indexer e.g.
    
    // node is a SiteMapNode instance
    string innerText = node.Title; // accesses the Title property
    string shortcut = node["accessKey"]; // accesses the accessKey custom attribute

We can add this to our markup like this:
    
    <ul>
      <asp:SiteMapDataSource ID="siteMapData" runat="server"
          ShowStartingNode="false" />
      <asp:Repeater ID="menu" runat="server"
          DataSourceID="siteMapData">
        <ItemTemplate>
          <li>
            <a href="<%# Eval("url") %>" title="<%# Eval("description") %>"
                    accesskey="<%# Eval("[accessKey]") %>">
                <%# Eval("title") %></a>
          </li>
        </ItemTemplate>
      </asp:Repeater>
    </ul>

This will render the following HTML:
    
    <ul>
      <li>
        <a accesskey="A" title="About company XYZ" href="about.aspx">About</a>
      </li>
      <li>
        <a accesskey="C" title="How to get in touch with us" href="contact.aspx">Contact</a>
      </li>
    </ul>

If you fancy playing around with the above sample code please feel free to [download](http://www.strongasanox.co.uk/samples/CustomSiteMapAttributes.zip) it.

Hope you find this useful.
