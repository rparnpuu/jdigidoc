DigiDoc Java library
--------------------

JDigiDoc is a library for manipulating Estonian DDOC and BDOC
digital signature container files.

It offers the functionality for creating digitally signed files in
DDOC and BDOC formats, adding new signatures,
verifying signatures and adding confirmations in OCSP format.

DigiDoc documents are XML files based on the international standards XML-DSIG, ETSI TS 101 903 and others. 
DigiDoc documents and the JDigiDoc library implement a subset of XML-DSIG and ETSI TS 101 903.

### Build status
  * Travis - [![Build Status](https://travis-ci.org/open-eid/jdigidoc.png?branch=master)](https://travis-ci.org/open-eid/jdigidoc)
  * Coverity - [![Coverity status](https://scan.coverity.com/projects/931/badge.svg?flat=1)](https://scan.coverity.com/projects/931/)

Building with Maven
-------------------
1. Get Maven2 from http://maven.apache.org
2. Run
     mvn install

Some dependent jar-s like iaikPkcs11Wrapper.jar is not available from public Maven repos.
So you have to register by IAIK and download it and then install the file to your local
maven repo. For example:
mvn install:install-file -Dfile=iaikPkcs11Wrapper.jar -DgroupId=iaik.pkcs -DartifactId=iaikPkcs11Wrapper -Dversion=1.2.16 -Dpackaging=jar
Please see also maven install command syntax http://maven.apache.org/guides/mini/guide-3rd-party-jars-local.html

Generating API documentation
----------------------------
Run mvn javadoc:jar

Full documentation
----------------------------

For documentation please see in doc folder SK-JDD-PRG-GUIDE

Contact for assistance by email abi@id.ee or http://www.id.ee

Building with Ant
-------------------------

You need the following dependent librarys to build jdigidoc:

- commons-codec-1.6.jar - http://commons.apache.org/proper/commons-codec/download_codec.cgi
- commons-compress-1.3.jar - http://commons.apache.org/proper/commons-compress/download_compress.cgi
- bcmail-jdk15on-151.jar - http://www.bouncycastle.org/latest_releases.html
- bcpkix-jdk15on-151.jar - http://www.bouncycastle.org/latest_releases.html
- bcprov-jdk15on-151.jar - http://www.bouncycastle.org/latest_releases.html
- jakarta-log4j-1.2.6.jar - https://archive.apache.org/dist/jakarta/log4j/binaries/
- iaikPkcs11Wrapper.jar version 1.2.16 or higher - http://jce.iaik.tugraz.at/sic/Products/Core-Crypto-Toolkits/PKCS_11_Wrapper

Download them all to some directory and edit build.xml entry:

    <property name="lib.dir" location="${env.HOME}/libs/jdigidoc" />

to point to that directory.

To build jdigidoc library use:

    ant jar

This command also build esteidtestcerts.jar that contains additional CA certificates for
testing environments only.

To build a zip file with dependent libs for distribution use

    ant deplibs

## Support
Official builds are provided through official distribution point [installer.id.ee](https://installer.id.ee). If you want support, you need to be using official builds.

Source code is provided on "as is" terms with no warranty (see license for more information). Do not file Github issues with generic support requests.
