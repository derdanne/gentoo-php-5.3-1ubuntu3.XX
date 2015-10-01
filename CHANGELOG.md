##2015-10-01 - Release 5.3.10-1ubuntu3.20
###Summary

(https://launchpad.net/ubuntu/+source/php5/5.3.10-1ubuntu3.20)

php5 (5.3.10-1ubuntu3.20) precise-security; urgency=medium

  * debian/patches/bug65481.patch: backport bugfix to get new
    var_push_dtor_no_addref function.
  * SECURITY UPDATE: phar segfault on invalid file
    - debian/patches/CVE-2015-5589-1.patch: check stream before closing in
      ext/phar/phar_object.c.
    - debian/patches/CVE-2015-5589-2.patch: add better checks in
      ext/phar/phar_object.c.
    - CVE-2015-5589
  * SECURITY UPDATE: phar buffer overflow in phar_fix_filepath
    - debian/patches/CVE-2015-5590.patch: properly handle path in
      ext/phar/phar.c.
    - CVE-2015-5590
  * SECURITY UPDATE: multiple use-after-free issues in unserialize()
    - debian/patches/CVE-2015-6831-1.patch: fix SPLArrayObject in
      ext/spl/spl_array.c, added test to ext/spl/tests/bug70166.phpt.
    - debian/patches/CVE-2015-6831-2.patch: fix SplObjectStorage in
      ext/spl/spl_observer.c.
    - CVE-2015-6831
  * SECURITY UPDATE: dangling pointer in the unserialization of ArrayObject
    items
    - debian/patches/CVE-2015-6832.patch: fix dangling pointer in
      ext/spl/spl_array.c.
    - CVE-2015-6832
  * SECURITY UPDATE: phar files extracted outside of destination dir
    - debian/patches/CVE-2015-6833-1.patch: limit extracted files to given
      directory in ext/phar/phar_object.c.
    - CVE-2015-6833
  * SECURITY UPDATE: multiple vulnerabilities in unserialize()
    - debian/patches/CVE-2015-6834-1.patch: fix use-after-free in
      ext/standard/var.c, ext/standard/var_unserializer.*.
    - debian/patches/CVE-2015-6834-2.patch: fix use-after-free in
      ext/spl/spl_observer.c.
    - CVE-2015-6834
  * SECURITY UPDATE: use after free in session deserializer
    - debian/patches/CVE-2015-6835-1.patch: fix use after free in
      ext/session/session.c, ext/standard/var_unserializer.*
      fixed tests in ext/session/tests/session_decode_error2.phpt,
      ext/session/tests/session_decode_variation3.phpt.
    - CVE-2015-6835
  * SECURITY UPDATE: SOAP serialize_function_call() type confusion
    - debian/patches/CVE-2015-6836.patch: check type in ext/soap/soap.c,
      added test to ext/soap/tests/bug70388.phpt.
    - CVE-2015-6836
  * SECURITY UPDATE: NULL pointer dereference in XSLTProcessor class
    - debian/patches/CVE-2015-6837-6838.patch: fix logic in
      ext/xsl/xsltprocessor.c.
    - CVE-2015-6837
    - CVE-2015-6838

 -- Marc Deslauriers <email address hidden>  Tue, 29 Sep 2015 12:51:49 -0400

##2015-07-02 - Release 5.3.10-1ubuntu3.19
###Summary

(https://launchpad.net/ubuntu/+source/php5/5.3.10-1ubuntu3.19)

php5 (5.3.10-1ubuntu3.19) precise-security; urgency=medium

  * SECURITY UPDATE: missing file path null byte checks
    - debian/patches/CVE-2015-3411.patch: add missing checks to
      ext/dom/document.c, ext/fileinfo/fileinfo.c, ext/gd/gd.c,
      ext/hash/hash.c, ext/pgsql/pgsql.c, ext/standard/streamsfuncs.c,
      ext/xmlwriter/php_xmlwriter.c, ext/zlib/zlib.c, add tests to
      ext/fileinfo/tests/finfo_file_basic.phpt,
      ext/hash/tests/hash_hmac_file_error.phpt,
      backport CHECK_NULL_PATH to Zend/zend_API.h.
    - CVE-2015-3411
    - CVE-2015-3412
  * SECURITY UPDATE: denial of service via crafted tar archive
    - debian/patches/CVE-2015-4021.patch: handle empty strings in
      ext/phar/tar.c.
    - CVE-2015-4021
  * SECURITY UPDATE: arbitrary code execution via ftp server long reply to
    a LIST command
    - debian/patches/CVE-2015-4022.patch: fix overflow in ext/ftp/ftp.c.
    - CVE-2015-4022
  * SECURITY UPDATE: denial of service via crafted form data
    - debian/patches/CVE-2015-4024.patch: use smart_str to assemble strings
      in main/rfc1867.c.
    - CVE-2015-4024
  * SECURITY UPDATE: more missing file path null byte checks
    - debian/patches/CVE-2015-4025.patch: add missing checks to
      ext/pcntl/pcntl.c, ext/standard/dir.c.
    - CVE-2015-4025
    - CVE-2015-4026
  * SECURITY UPDATE: arbitrary code execution via crafted serialized data
    with unexpected data type
    - debian/patches/CVE-2015-4147.patch: check variable types in
      ext/soap/php_encoding.c, ext/soap/php_http.c, ext/soap/soap.c.
    - CVE-2015-4147
    - CVE-2015-4148
    - CVE-2015-4600
    - CVE-2015-4601
  * SECURITY UPDATE: more missing file path null byte checks
    - debian/patches/CVE-2015-4598.patch: add missing checks to
      ext/dom/document.c, ext/gd/gd.c.
    - CVE-2015-4598
  * SECURITY UPDATE: denial of service or information leak via type
    confusion with crafted serialized data
    - debian/patches/CVE-2015-4599.patch: use proper types in
      ext/soap/soap.c.
    - CVE-2015-4599
  * SECURITY UPDATE: denial of service or information leak via type
    confusion with crafted serialized data
    - debian/patches/CVE-2015-4602.patch: check for proper type in
      ext/standard/incomplete_class.c.
    - CVE-2015-4602
  * SECURITY UPDATE: denial of service or information leak via type
    confusion with crafted serialized data
    - debian/patches/CVE-2015-4603.patch: check type in
      Zend/zend_exceptions.c, add test to
      ext/standard/tests/serialize/bug69152.phpt.
    - CVE-2015-4603
  * SECURITY UPDATE: arbitrary code execution via ftp server long reply to
    a LIST command
    - debian/patches/CVE-2015-4643.patch: prevent overflow check bypass in
      ext/ftp/ftp.c.
    - CVE-2015-4643
  * SECURITY UPDATE: denial of service via php_pgsql_meta_data
    - debian/patches/CVE-2015-4644.patch: check return value in
      ext/pgsql/pgsql.c, add test to ext/pgsql/pg_insert_002.phpt.
    - CVE-2015-4644
  * debian/patches/CVE-2015-2783-memleak.patch: fix memory leak introduced
    by CVE-2015-2783 security update.

 -- Marc Deslauriers <email address hidden>  Thu, 02 Jul 2015 07:42:32 -0400

##2015-04-17 - Release 5.3.10-1ubuntu3.18
###Summary

(https://launchpad.net/ubuntu/+source/php5/5.3.10-1ubuntu3.18)

php5 (5.3.10-1ubuntu3.18) precise-security; urgency=medium

  * SECURITY UPDATE: potential remote code execution vulnerability when
    used with the Apache 2.4 apache2handler
    - debian/patches/bug69218.patch: perform proper cleanup in
      sapi/apache2handler/sapi_apache2.c.
    - CVE number pending
  * SECURITY UPDATE: buffer overflow when parsing tar/zip/phar
    - debian/patches/bug69441.patch: check lengths in
      ext/phar/phar_internal.h.
    - CVE number pending
  * SECURITY UPDATE: heap overflow in regexp library
    - debian/patches/CVE-2015-2305.patch: check for overflow in
      ext/ereg/regex/regcomp.c.
    - CVE-2015-2305
  * SECURITY UPDATE: buffer overflow in unserialize when parsing Phar
    - debian/patches/CVE-2015-2783.patch: properly check lengths in
      ext/phar/phar.c, ext/phar/phar_internal.h.
    - CVE-2015-2783
  * SECURITY UPDATE: arbitrary code exection via process_nested_data
    use-after-free
    - debian/patches/CVE-2015-2787.patch: fix logic in
      ext/standard/var_unserializer.*.
    - CVE-2015-2787
 -- Marc Deslauriers <email address hidden>   Fri, 17 Apr 2015 06:25:37 -0400

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
