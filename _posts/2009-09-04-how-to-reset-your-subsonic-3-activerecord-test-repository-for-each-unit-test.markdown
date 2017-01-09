---
date: '2009-09-04 14:09:38'
layout: post
slug: how-to-reset-your-subsonic-3-activerecord-test-repository-for-each-unit-test
status: publish
title: How To Reset Your SubSonic 3 ActiveRecord Test Repository For Each Unit Test
wordpress_id: '171'
categories:
- asp.net
- c#
tags:
- asp.net
- subsonic
- unit testing
---

When writing unit tests with [SubSonic's new built-in testing for ActiveRecord](http://subsonicproject.com/docs/Using_ActiveRecord#Testing) don't forget that each time you call the **Setup()** method on your ActiveRecord object it adds records to any that have already been created. For example:
    
    [Test]
    public void Foo_Bar() {
        Foo.Setup(10);
        Assert.AreEqual(10, Foo.All().Count());
    }
    
    [Test]
    public void Bar_Foo() {
        Foo.Setup(10);
    
        // This will fail: Foo.All().Count() will return 20
        Assert.AreEqual(10, Foo.All().Count());
    }


To reset your test repositories you will need to call the **ResetTestRepo()** method prior to each test, which can be accomplished easily enough by adding the method call to your test's **[SetUp]** method:
    
    [SetUp]
    public void SetUp() {
        Foo.ResetTestRepo();
    }
    
    [Test]
    public void Foo_Bar() {
        Foo.Setup(10);
        Assert.AreEqual(10, Foo.All().Count());
    }
    
    [Test]
    public void Bar_Foo() {
        Foo.Setup(10);
    
        // Now Foo.All().Count() will return 10 and the test will pass
        Assert.AreEqual(10, Foo.All().Count());
    }

Hopefully this will save you a bit of time.
