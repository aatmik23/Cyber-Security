
**Site map**: This sub-tab allows us to map out the web applications we are targeting in a tree structure. Every page that we visit while the is active will be displayed on the site map.

**Issue definitions**

The **Issue definitions** section provides an extensive list of web vulnerabilities, complete with descriptions and references. This resource can be valuable for referencing vulnerabilities in reports or assisting in describing a particular vulnerability that may have been identified during manual testing.

**Scope settings**:

Imagine you are testing this website:

http://example.com

While using the website, your browser might send requests to:

example.com

google.com

facebook.com

analytics.com

But you only care about:

example.com

So you tell Burp:

> **My scope = example.com**

Now Burp knows that **example.com is the target you're interested in**.


![](../../assets/Pasted%20image%2020260819210320.png)


