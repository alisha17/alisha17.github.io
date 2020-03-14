---
layout: post
title: Understanding LDAP terminologies
categories: [LDAP]
comments: true
author: alisha
image: assets/images/ldaptree.png
---

When I started to look into the Fedora’s 389 Directory Server, my first concern was understanding LDAP glossary!

I did a project of Single Sign-On and Password Authentication using LDAP as the database during my internship in the last year of undergraduation, 2+ years back (time literally flies!), but to be honest, I didn’t really understand much at that time.

(It’s better to get started with LDAP using Apache Directory Studio, it becomes easier to visualise things.)

<!-- ##What is LDAP?##


 -->
### What is DN? ###

**Consider: cn=Alisha, ou=People, dc=example, dc=google, dc=com**

This whole string is a DN (Distinguished Name). It is a series of comma-separated key/value pairs used to identify entries uniquely in the directory hierarchy. The DN is actually the entry's fully qualified name, i.e. it uniquely identifies an entry in the directory. DN should be read from right to left. The rightmost component is the root of the tree and the leftmost component is the leaf or the node you want to reach.


### What is RDN (Relative Distinguished Name)? ###

**Consider: uid=alisha, ou=People, dc=example, dc=com**

* uid=alisha and ou=People are RDN for dc=example, dc= com

**Consider: cn=maths, dc=example, dc=com**

* cn=maths is RDN for dc=example, dc=com

**Hence, RDN is how you name a 'singlular' object, whereas DN is the fully qualified path to an entry.**

Generally according to the convention, uid=&lt;name&gt; is the rdn for ou=Accounts, and cn=&lt;name&gt; for ou=Groups, but Active Directory uses CN=&lt;value&gt; for almost all rdns.


### What is directory hierarchy? ###

The data in LDAP is stored in the form of a hierarchical structure (called DIT, i.e, Directory Information Tree). It is just a tree with nodes and leafs, no rocket science!

Let’s understand this visually.

![ldap tree]({{ site.url }}/assets/ldaptree.png)


* The top of the tree is called the basedn (dc=example, dc=com).
* Each entry in the tree has one parent entry (object) and zero or more child entries (objects). Each child  entry (object) is a sibling of its parent's other child entries.
* Each entry is an instance of one or more objectClasses.
* Objectclasses contain zero or more attributes.
* Attributes have names and contain data.

So, coming back to our query "CN=Alisha,OU=People,DC=example,DC=google,DC=com"

It means “From the com domain component, find google Domain Component, and from this find example Domain Component. From the example Domain Component, find People Organisational Unit, and from this find an entry whose common name is Alisha.”


### What is DC (Domain Component)? ###

This refers to each component of the domain. For example, “example.google.com” would be written as DC=example,DC=google,DC=com.


### What is OU (Organizational Unit)? ###

This refers to the organizational unit (or sometimes the user group) that the user is part of, for example, a user might be a part of People group or Developer group. If the user is part of more than one group, it can be specified as OU= Developer, OU= Tester. (Many a times, developer might have to do all the testing by himself also, hence both of the groups!)


### What is CN (Common Name)? ###

This refers to the individual object (person's name; meeting room; recipe name; job title; etc.) for whom/which object you are querying.

For example,

```html
uid=alisha, ou=People, dc=example, dc=com
uid: alisha
cn: alisha
...
```

uid is equivalent to user id, so it is a unique user identifier (generally the "logon" name). cn is the "common name" so what I should be "called". (There is also displayName for applications to render too).

Hold on tight, more to come! :)

