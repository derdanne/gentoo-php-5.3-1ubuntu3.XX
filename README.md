# gentoo-php-5.3-1ubuntu3.XX
Ported PHP 5.3 from Ubuntu Precise - to have a PHP 5.3 with security fixes on Gentoo

# Description:
Since PHP 5.3 does not get any official security fixes, and we have some needs of a 
PHP 5.3 in production services, i ported the php package from Ubuntu Precise.

https://launchpad.net/ubuntu/precise/+source/php5

You can use this as a local Portage overlay in your Funtoo / Gentoo Setup. You have to 
unmask >=dev-lang/php-5.3.10-r17 and emerge =app-admin/eselect-php-r4

I use the following USE flags to compile the package, any other USE flags are not tested! 

USE="apache2 bcmath berkdb bzip2 cgi cli crypt ctype curl exif fileinfo filter ftp gd 
gdbm hash iconv intl ipv6 json mhash mysql mysqli nls pdo phar posix readline session 
simplexml soap ssl tidy tokenizer truetype unicode xml xmlreader xmlwriter zip zlib 
-calendar -cdb -cjk -curlwrappers -debug -embed -enchant (-firebird) -flatfile -fpm -gmp 
-imap -inifile -iodbc -kerberos -ldap -ldap-sasl -libedit -mssql -mysqlnd 
-oci8-instant-client -odbc -pcntl -postgres -qdbm -recode (-selinux) -sharedmem -snmp 
-sockets -spell -sqlite -sqlite2 (-sybase-ct) -sysvipc -threads -wddx -xmlrpc -xpm -xslt"

Feel free to test other USE flags as well and commit needed changes in a fork and do a pull
request.

Thanks for backporting security fixes till 2017 @Ubuntu Developers 
https://launchpad.net/~ubuntu-devel-discuss-lists and @Marc Deslauriers https://launchpad.net/~mdeslaur

