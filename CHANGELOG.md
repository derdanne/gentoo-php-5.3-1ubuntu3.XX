##2016-10-03 - Release 5.3.10-1ubuntu3.25
###Summary

php5 (5.3.10-1ubuntu3.25) precise-security; urgency=medium

  * SECURITY UPDATE: denial of service or code execution via crafted
    serialized data
    - debian/patches/CVE-2016-7124-1.patch: destroy broken object when
      unserializing in ext/standard/var_unserializer.c*.
    - debian/patches/CVE-2016-7124-2.patch: improve fix in
      ext/standard/var_unserializer.c*, added test to
      ext/standard/tests/strings/bug72663_3.phpt.
    - CVE-2016-7124
  * SECURITY UPDATE: arbitrary-type session data injection
    - debian/patches/CVE-2016-7125.patch: consume data even if not storing
      in ext/session/session.c, added test to
      ext/session/tests/bug72681.phpt.
    - debian/patches/CVE-2016-7125-2.patch: remove unused label in
      ext/session/session.c.
    - CVE-2016-7125
  * SECURITY UPDATE: denial of service and possible code execution in
    imagegammacorrect function
    - debian/patches/CVE-2016-7127.patch: check gamma values in
      ext/gd/gd.c, added test to ext/gd/tests/bug72730.phpt.
    - CVE-2016-7127
  * SECURITY UPDATE: information disclosure via exif_process_IFD_in_TIFF
    - debian/patches/CVE-2016-7128.patch: properly handle thumbnails in
      ext/exif/exif.c.
    - CVE-2016-7128
  * SECURITY UPDATE: denial of service and possible code execution via
    invalid ISO 8601 time value
    - debian/patches/CVE-2016-7129.patch: properly handle strings in
      ext/wddx/wddx.c, added test to ext/wddx/tests/bug72749.phpt.
    - CVE-2016-7129
  * SECURITY UPDATE: denial of service and possible code execution via
    invalid base64 binary value
    - debian/patches/CVE-2016-7130.patch: properly handle string in
      ext/wddx/wddx.c, added test to ext/wddx/tests/bug72750.phpt.
    - CVE-2016-7130
  * SECURITY UPDATE: denial of service and possible code execution via
    malformed wddxPacket XML document
    - debian/patches/CVE-2016-7131.patch: added check to ext/wddx/wddx.c,
      added tests to ext/wddx/tests/bug72790.phpt,
      ext/wddx/tests/bug72799.phpt.
    - CVE-2016-7131
    - CVE-2016-7132
  * SECURITY UPDATE: denial of service and possible code execution via
    partially constructed object
    - debian/patches/CVE-2016-7411.patch: properly handle partial object in
      ext/standard/var_unserializer.*, added test to
      ext/standard/tests/serialize/bug73052.phpt.
    - CVE-2016-7411
  * SECURITY UPDATE: denial of service and possible code execution via
    crafted field metadata in MySQL driver
    - debian/patches/CVE-2016-7412.patch: validate field length in
      ext/mysqlnd/mysqlnd_wireprotocol.c.
    - CVE-2016-7412
  * SECURITY UPDATE: denial of service and possible code execution via
    malformed wddxPacket XML document
    - debian/patches/CVE-2016-7413.patch: fixed use-after-free in
      ext/wddx/wddx.c, added test to ext/wddx/tests/bug72860.phpt.
    - CVE-2016-7413
  * SECURITY UPDATE: denial of service and possible code execution via
    crafted PHAR archive
    - debian/patches/CVE-2016-7414.patch: validate signatures in
      ext/phar/util.c, ext/phar/zip.c.
    - CVE-2016-7414
  * SECURITY UPDATE: denial of service and possible code execution via
    MessageFormatter::formatMessage call with a long first argument
    - debian/patches/CVE-2016-7416.patch: added locale length check to
      ext/intl/msgformat/msgformat_format.c.
    - CVE-2016-7416
  * SECURITY UPDATE: denial of service or code execution via crafted
    serialized data
    - debian/patches/CVE-2016-7417.patch: added type check to
      ext/spl/spl_array.c.
    - CVE-2016-7417
  * SECURITY UPDATE: denial of service and possible code execution via
    malformed wddxPacket XML document
    - debian/patches/CVE-2016-7418.patch: fix out-of-bounds read in
      ext/wddx/wddx.c, added test to ext/wddx/tests/bug73065.phpt.
    - CVE-2016-7418

 -- Marc Deslauriers <email address hidden>  Mon, 03 Oct 2016 07:39:03 -0400

##2016-08-01 - Release 5.3.10-1ubuntu3.24
###Summary

(https://launchpad.net/ubuntu/+source/php5/5.3.10-1ubuntu3.24)

php5 (5.3.10-1ubuntu3.24) precise-security; urgency=medium

  * SECURITY UPDATE: segfault in SplMinHeap::compare
    - debian/patches/CVE-2015-4116.patch: properly handle count in
      ext/spl/spl_heap.c, added test to ext/spl/tests/bug69737.phpt.
    - CVE-2015-4116
  * SECURITY UPDATE: denial of service via recursive method calls
    - debian/patches/CVE-2015-8873.patch: add limit to
      Zend/zend_exceptions.c, add tests to
      ext/standard/tests/serialize/bug69152.phpt,
      ext/standard/tests/serialize/bug69793.phpt,
      sapi/cli/tests/005.phpt.
    - CVE-2015-8873
  * SECURITY UPDATE: denial of service or code execution via crafted
    serialized data
    - debian/patches/CVE-2015-8876.patch: fix logic in
      Zend/zend_exceptions.c, added test to Zend/tests/bug70121.phpt.
    - CVE-2015-8876
  * SECURITY UPDATE: XSS in header() with Internet Explorer (LP: #1594041)
    - debian/patches/CVE-2015-8935.patch: update header handling to
      RFC 7230 in main/SAPI.c, added tests to
      ext/standard/tests/general_functions/bug60227_*.phpt.
    - CVE-2015-8935
  * SECURITY UPDATE: get_icu_value_internal out-of-bounds read
    - debian/patches/CVE-2016-5093.patch: add enough space in
      ext/intl/locale/locale_methods.c, added test to
      ext/intl/tests/bug72241.phpt.
    - CVE-2016-5093
  * SECURITY UPDATE: integer overflow in php_html_entities()
    - debian/patches/CVE-2016-5094.patch: don't create strings with lengths
      outside int range in ext/standard/html.c.
    - CVE-2016-5094
  * SECURITY UPDATE: string overflows in string add operations
    - debian/patches/CVE-2016-5095.patch: check for size overflow in
      Zend/zend_operators.c.
    - CVE-2016-5095
  * SECURITY UPDATE: int/size_t confusion in fread
    - debian/patches/CVE-2016-5096.patch: check string length in
      ext/standard/file.c, added test to
      ext/standard/tests/file/bug72114.phpt.
    - CVE-2016-5096
  * SECURITY UPDATE: memory leak and buffer overflow in FPM
    - debian/patches/CVE-2016-5114.patch: check buffer length in
      sapi/fpm/fpm/fpm_log.c.
    - CVE-2016-5114
  * SECURITY UPDATE: proxy request header vulnerability (httpoxy)
    - debian/patches/CVE-2016-5385.patch: only use HTTP_PROXY from the
      local environment in ext/standard/basic_functions.c, main/SAPI.c,
      main/php_variables.c.
    - CVE-2016-5385
  * SECURITY UPDATE: inadequate error handling in bzread()
    - debian/patches/CVE-2016-5399.patch: do not allow reading past error
      read in ext/bz2/bz2.c.
    - CVE-2016-5399
  * SECURITY UPDATE: integer overflows in mcrypt
    - debian/patches/CVE-2016-5769.patch: check for overflow in
      ext/mcrypt/mcrypt.c.
    - CVE-2016-5769
  * SECURITY UPDATE: double free corruption in wddx_deserialize
    - debian/patches/CVE-2016-5772.patch: prevent double-free in
      ext/wddx/wddx.c, added test to ext/wddx/tests/bug72340.phpt.
    - CVE-2016-5772
  * SECURITY UPDATE: buffer overflow in php_url_parse_ex()
    - debian/patches/CVE-2016-6288.patch: handle length in
      ext/standard/url.c.
    - CVE-2016-6288
  * SECURITY UPDATE: integer overflow in the virtual_file_ex function
    - debian/patches/CVE-2016-6289.patch: properly check path_length in
      Zend/zend_virtual_cwd.c.
    - CVE-2016-6289
  * SECURITY UPDATE: use after free in unserialize() with unexpected
    session deserialization
    - debian/patches/CVE-2016-6290.patch: destroy var_hash properly in
      ext/session/session.c, added test to ext/session/tests/bug72562.phpt.
    - CVE-2016-6290
  * SECURITY UPDATE: out of bounds read in exif_process_IFD_in_MAKERNOTE
    - debian/patches/CVE-2016-6291.patch: add more bounds checks to
      ext/exif/exif.c.
    - CVE-2016-6291
  * SECURITY UPDATE: locale_accept_from_http out-of-bounds access
    - debian/patches/CVE-2016-6294.patch: check length in
      ext/intl/locale/locale_methods.c, added test to
      ext/intl/tests/bug72533.phpt.
    - CVE-2016-6294
  * SECURITY UPDATE: heap buffer overflow in simplestring_addn
    - debian/patches/CVE-2016-6296.patch: prevent overflows in
      ext/xmlrpc/libxmlrpc/simplestring.*.
    - CVE-2016-6296
  * SECURITY UPDATE: integer overflow in php_stream_zip_opener
    - debian/patches/CVE-2016-6297.patch: use size_t in
      ext/zip/zip_stream.c.
    - CVE-2016-6297
  * debian/patches/fix_exif_tests.patch: fix exif test results after
    security changes.

 -- Marc Deslauriers <email address hidden>  Mon, 01 Aug 2016 13:27:52 -0400


##2016-05-19 - Release 5.3.10-1ubuntu3.23
###Summary

(https://launchpad.net/ubuntu/+source/php5/5.3.10-1ubuntu3.23)

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
