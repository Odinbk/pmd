---
title: Security
summary: Rules that flag potential security flaws.
permalink: pmd_rules_java_security.html
folder: pmd/rules/java
sidebaractiveurl: /pmd_rules_java.html
editmepath: ../pmd-java/src/main/resources/category/java/security.xml
keywords: Security, InsecureCryptoIv, HardCodedCryptoKey
language: Java
---
## HardCodedCryptoKey

**Since:** PMD 6.3.0

**Priority:** Medium (3)

Do not use hard coded values for cryptographic operations. Please store keys outside of source code.

**This rule is defined by the following Java class:** [net.sourceforge.pmd.lang.java.rule.security.HardCodedCryptoKeyRule](https://github.com/pmd/pmd/blob/master/pmd-java/src/main/java/net/sourceforge/pmd/lang/java/rule/security/HardCodedCryptoKeyRule.java)

**Example(s):**

``` java
public class Foo {
    void good() {
		SecretKeySpec secretKeySpec = new SecretKeySpec(Properties.getKey(), "AES");		
    }

    void bad() {
		SecretKeySpec secretKeySpec = new SecretKeySpec("my secret here".getBytes(), "AES");
    }
}
```

**Use this rule by referencing it:**
``` xml
<rule ref="category/java/security.xml/HardCodedCryptoKey" />
```

## InsecureCryptoIv

**Since:** PMD 6.3.0

**Priority:** Medium (3)

Do not use hard coded initialization vector in cryptographic operations. Please use a randomly generated IV.

**This rule is defined by the following Java class:** [net.sourceforge.pmd.lang.java.rule.security.InsecureCryptoIvRule](https://github.com/pmd/pmd/blob/master/pmd-java/src/main/java/net/sourceforge/pmd/lang/java/rule/security/InsecureCryptoIvRule.java)

**Example(s):**

``` java
public class Foo {
    void good() {
        SecureRandom random = new SecureRandom();
        byte iv[] = new byte[16];
        random.nextBytes(bytes);
    }

    void bad() {
        byte[] iv = new byte[] { 00, 00, 00, 00, 00, 00, 00, 00, 00, 00, 00, 00, 00, 00, 00, 00, };
    }
    
    void alsoBad() {
        byte[] iv = "secret iv in here".getBytes();
    }
    
}
```

**Use this rule by referencing it:**
``` xml
<rule ref="category/java/security.xml/InsecureCryptoIv" />
```
