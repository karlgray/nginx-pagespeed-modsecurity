# nginx-pagespeed-modsecurity
Nginx with pagespeed, mod security http2 and ngx_cache_purge

This is a script which will build an Nginx 1.9.14 RPM which includes
  * Googles, PageSpeed Module
  * Mod Security Module
  * http2 Enabled
  * ngx_cache_purge to be used by a wordpress plugin.

This script was written on and for a Centos 6.7 Server.

There are a few pre-requisites you need to install (as root)
 <pre>
 yum install vim wget httpd-devel libxml2-devel openssl-devel zlib-devel pcre-devel
</pre>
To use this script you need to create a new username and enable Sudo for it.
  <pre>
  adduser nginxbuild
  usermod -aG wheel nginxbuild
  passwd nginxbuild
  su nginxbuild
  cd ~</pre>

Download and run the script using;

<pre>
 wget https://raw.githubusercontent.com/karlgray/nginx-pagespeed-modsecurity/master/build.sh
 chmod +x build.sh
 ./build.sh
</pre>

If all goes well you will end up with an RPM in ~/rpmbuild/RPMS/x86_64/nginx-1.9.14-1.el6.ngx.x86_64.rpm

Please report any issues you have if you use it.  Any use of this script is at your own risk.

Please do not use this script on a live server.

To enable sudo on a Redhat server

Enter this command
<pre>
visudo
</pre>

Line 105 will look like this;
<pre>
#  %wheel  ALL=(ALL)       ALL
</pre>
Change it to look like this;
<pre>
%wheel  ALL=(ALL)       ALL
</pre>
