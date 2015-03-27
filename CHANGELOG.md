##2015-03-27 - Release 5.3.10-1ubuntu3.17
###Summary

(https://launchpad.net/ubuntu/+source/php5/5.3.10-1ubuntu3.17)

php5 (5.3.10-1ubuntu3.17) precise-security; urgency=medium

  * SECURITY UPDATE: denial of service via recursion
    - debian/patches/CVE-2014-8117.patch: lower recursion limit in
      ext/fileinfo/libmagic/softmagic.c.
    - CVE-2014-8117
  * SECURITY UPDATE: denial of service or possible code execution in
    enchant
    - debian/patches/CVE-2014-9705.patch: handle position better in
      ext/enchant/enchant.c.
    - CVE-2014-9705
  * SECURITY UPDATE: arbitrary code execution via use after free in
    unserialize() with DateTime
    - debian/patches/CVE-2015-0273.patch: fix use after free in
      ext/date/php_date.c, added test to ext/date/tests/*.phpt.
    - CVE-2015-0273
  * SECURITY UPDATE: denial of service or possible code execution in phar
    - debian/patches/CVE-2015-2301.patch: fix use after free in
      ext/phar/phar_object.c.
    - CVE-2015-2301
 -- Marc Deslauriers <email address hidden>   Mon, 16 Mar 2015 13:59:27 -0400