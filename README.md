# jasypt

Fork of http://svn.code.sf.net/p/jasypt/code/trunk, with some minor additions.

If necessary, re-build the project:

```
cd jasypt
mvn clean:clean install
```

Next, encrypt `hello world` text with `truth` password:

```
$ jasypt-dist/src/main/bin/encrypt.sh input="hello world" password="truth"

----ENVIRONMENT-----------------

Runtime: Oracle Corporation OpenJDK 64-Bit Server VM 25.191-b12



----ARGUMENTS-------------------

input: hello world
password: truth



----OUTPUT----------------------

D12otaM0aKTKe7aFlESXSJpBA2TQWho2
```

Then, decrypt it:

```
$ jasypt-dist/src/main/bin/decrypt.sh input="D12otaM0aKTKe7aFlESXSJpBA2TQWho2" password="truth"

----ENVIRONMENT-----------------

Runtime: Oracle Corporation OpenJDK 64-Bit Server VM 25.191-b12



----ARGUMENTS-------------------

input: D12otaM0aKTKe7aFlESXSJpBA2TQWho2
password: truth



----OUTPUT----------------------

hello world
```

Also, check algorithms:

```
$ jasypt-dist/src/main/bin/listAlgorithms.sh

DIGEST ALGORITHMS:   [MD2, MD5, SHA, SHA-224, SHA-256, SHA-384, SHA-512]

PBE ALGORITHMS:      [PBEWITHHMACSHA1ANDAES_128, PBEWITHHMACSHA1ANDAES_256, PBEWITHHMACSHA224ANDAES_128, PBEWITHHMACSHA224ANDAES_256, PBEWITHHMACSHA256ANDAES_128, PBEWITHHMACSHA256ANDAES_256, PBEWITHHMACSHA384ANDAES_128, PBEWITHHMACSHA384ANDAES_256, PBEWITHHMACSHA512ANDAES_128, PBEWITHHMACSHA512ANDAES_256, PBEWITHMD5ANDDES, PBEWITHMD5ANDTRIPLEDES, PBEWITHSHA1ANDDESEDE, PBEWITHSHA1ANDRC2_128, PBEWITHSHA1ANDRC2_40, PBEWITHSHA1ANDRC4_128, PBEWITHSHA1ANDRC4_40]
```

Relevant articles:
* https://apereo.atlassian.net/wiki/spaces/CASUM/pages/103261428/HOWTO+Use+Jasypt+to+encrypt+passwords+in+configuration+files
