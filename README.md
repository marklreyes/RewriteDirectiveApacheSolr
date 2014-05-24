#Apply a Rewrite Directive to a Solr Instance#

After exposing the Solr endpoint with a reverse proxy, it’s important to note that it also exposes the Solr admin panel to the end-user. This is not desired.

![Flowchart of a RewriteRule directive that rests on website.com’s httpd.conf file.](http://blog.marklreyes.com/wp-content/uploads/2014/05/rewrite_rule.jpg)

##Problem##

  - Solr’s admin panel becomes exposed from the reverse proxy.
  
##Solution##

  - Perform a redirect to website.com’s homepage.
  - RewriteRule directive, [mod_rewrite – Apache HTTP Server](http://httpd.apache.org/docs/2.2/mod/mod_rewrite.html#rewriterule).

<pre>
<code>
RewriteRule ^/solr/$ / [R=301,L,DPI]
</code>
</pre>
