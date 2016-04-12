# nginx-pagespeed-modsecurity
Nginx with pagespeed, mod security http2 and ngx_cache_purge

This is a script which will build an Nginx 1.9.14 RPM which includes
  * Googles, PageSpeed Module
  * Mod Security Module
  * http2 Enabled
  * ngx_cache_purge to be used by a wordpress plugin.

This script was written on and for a Centos 6.7 Server.

To use this script you need to create a new username and enable Sudo for it.

  <preadduser nginxbuild
  usermod -aG wheel nginxbuild
  su nginxbuild
  cd ~</pre>
  
Download and run the script using;

  wget https://raw.githubusercontent.com/karlgray/nginx-pagespeed-modsecurity/master/build.sh
  chmod +x build.sh
  ./build.sh

If all goes well you will end up with an RPM in ~/rpmbuild/RPMS/x86_64/nginx-1.9.14-1.el6.ngx.x86_64.rpm

Please report any issues you have if you use it.  Any use of this script is at your own risk.

Please do not use this script on a live server.

** To enable sudo on a Redhat server
Enter this command
 visudo

Line 105 will look like this;
 #  %wheel  ALL=(ALL)       ALL
Change it to look like this;
 %wheel  ALL=(ALL)       ALL

