##2016-05-19 - Release 5.3.10-1ubuntu3.23
###Summary

php5 (5.3.10-1ubuntu3.23) precise-security; urgency=medium

  * SECURITY UPDATE: heap corruption in tar/zip/phar parser
    - debian/patches/CVE-2016-4342.patch: remove UMR when size is 0 in
      ext/phar/phar_object.c.
    - CVE-2016-4342
  * SECURITY UPDATE: uninitialized pointer in phar_make_dirstream()
    - debian/patches/CVE-2016-4343.patch: check lengths in
      ext/phar/dirstream.c, ext/phar/tar.c.
    - CVE-2016-4343
  * SECURITY UPDATE: bcpowmod accepts negative scale and corrupts _one_
    definition
    - debian/patches/CVE-2016-4537.patch: properly detect scale in
      ext/bcmath/bcmath.c, add test to ext/bcmath/tests/bug72093.phpt.
    - CVE-2016-4537
    - CVE-2016-4538
  * SECURITY UPDATE: xml_parse_into_struct segmentation fault
    - debian/patches/CVE-2016-4539.patch: check parser->level in
      ext/xml/xml.c, added test to ext/xml/tests/bug72099.phpt.
    - CVE-2016-4539
  * SECURITY UPDATE: out-of-bounds reads in zif_grapheme_stripos and
    zif_grapheme_strpos with negative offset
    - debian/patches/CVE-2016-4540.patch: check bounds in
      ext/intl/grapheme/grapheme_string.c, added test to
      ext/intl/tests/bug72061.phpt.
    - CVE-2016-4540
    - CVE-2016-4541
  * SECURITY UPDATE: out of bounds heap read access in exif header
    processing
    - debian/patches/CVE-2016-4542.patch: check sizes and length in
      ext/exif/exif.c.
    - CVE-2016-4542
    - CVE-2016-4543
    - CVE-2016-4544

 -- Marc Deslauriers <marc.deslauriers@ubuntu.com>  Thu, 19 May 2016 12:54:58 -0400

##2016-04-19 - Release 5.3.10-1ubuntu3.22
###Summary

(https://launchpad.net/ubuntu/+source/php5/5.3.10-1ubuntu3.22)

php5 (5.3.10-1ubuntu3.22) precise-security; urgency=medium

  * SECURITY UPDATE: directory traversal in ZipArchive::extractTo
    - debian/patches/CVE-2014-9767.patch: use proper path in
      ext/zip/php_zip.c, added test to ext/zip/tests/bug70350.phpt.
    - CVE-2014-9767
  * SECURITY UPDATE: type confusion issue in SoapClient
    - debian/patches/CVE-2015-8835.patch: check types in
      ext/soap/php_http.c.
    - CVE-2015-8835
    - CVE-2016-3185
  * SECURITY UPDATE: mysqlnd is vulnerable to BACKRONYM
    - debian/patches/CVE-2015-8838.patch: fix ssl handling in
      ext/mysqlnd/mysqlnd.c.
    - CVE-2015-8838
  * SECURITY UPDATE: stack overflow when decompressing tar archives
    - debian/patches/CVE-2016-2554.patch: handle non-terminated linknames
      in ext/phar/tar.c.
    - CVE-2016-2554
  * SECURITY UPDATE: use-after-free in WDDX
    - debian/patches/CVE-2016-3141.patch: fix stack in ext/wddx/wddx.c,
      added test to ext/wddx/tests/bug71587.phpt.
    - CVE-2016-3141
  * SECURITY UPDATE: out-of-Bound Read in phar_parse_zipfile()
    - debian/patches/CVE-2016-3142.patch: check bounds in ext/phar/zip.c.
    - CVE-2016-3142
  * SECURITY UPDATE: libxml_disable_entity_loader setting is shared between
    threads
    - debian/patches/bug64938.patch: enable entity loader in
      ext/libxml/libxml.c.
    - No CVE number
  * SECURITY UPDATE: openssl_random_pseudo_bytes() is not cryptographically
    secure
    - debian/patches/bug70014.patch: use RAND_bytes instead of deprecated
      RAND_pseudo_bytes in ext/openssl/openssl.c.
    - No CVE number
  * SECURITY UPDATE: buffer over-write in finfo_open with malformed magic
    file
    - debian/patches/bug71527.patch: properly calculate length in
      ext/fileinfo/libmagic/funcs.c, added test to
      ext/fileinfo/tests/bug71527.magic.
    - CVE number pending
  * SECURITY UPDATE: integer overflow in php_raw_url_encode
    - debian/patches/bug71798.patch: use size_t in ext/standard/url.c.
    - CVE number pending
  * SECURITY UPDATE: invalid memory write in phar on filename containing
    NULL
    - debian/patches/bug71860.patch: require valid paths in
      ext/phar/phar.c, ext/phar/phar_object.c.
    - CVE number pending
  * SECURITY UPDATE: invalid negative size in mbfl_strcut
    - debian/patches/bug71906.patch: fix length checks in
      ext/mbstring/libmbfl/mbfl/mbfilter.c.
    - CVE number pending

 -- Marc Deslauriers <marc.deslauriers@ubuntu.com>  Tue, 19 Apr 2016 16:55:56 -0400

##2015-10-27 - Release 5.3.10-1ubuntu3.21
###Summary

(https://launchpad.net/ubuntu/+source/php5/5.3.10-1ubuntu3.21)

php5 (5.3.10-1ubuntu3.21) precise-security; urgency=medium

  * SECURITY UPDATE: null pointer dereference in phar_get_fp_offset()
    - debian/patches/CVE-2015-7803.patch: check link in ext/phar/util.c.
    - CVE-2015-7803
  * SECURITY UPDATE: uninitialized pointer in phar_make_dirstream()
    - debian/patches/CVE-2015-7804.patch: check filename length in
      ext/phar/util.c, ext/phar/zip.c.
    - CVE-2015-7804

 -- Marc Deslauriers <marc.deslauriers@ubuntu.com>  Tue, 27 Oct 2015 16:59:36 -0400

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
