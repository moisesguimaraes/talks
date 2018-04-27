---
title: Understanding SSL/TLS with Python examples @ PyCon UA
layout: slide
---

<section data-markdown data-background-image="{{ "/images/bg/pyconua-cover.jpeg" | prepend: site.baseurl }}"><script type="text/template">
  ## Understanding SSL / TLS
  ## with Python examples

  <br><br><br><br><br><br><br><br><br><br>

  ### April 28, 2018
</script></section>

<section data-markdown data-transition="none"><script type="text/template">
  ## Who am I ?

  <div class="row">
    <div class="column">
      {% include img.html src="logos/avatar.png" width="90%" %}
    </div>
    <div class="column">
      <br><br><br><br>
      <h3>Moisés Guimarães</h3>
      <ul>
        <li>Software engineer&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</li>
        <li>Infosec specialist</li>
      </ul>
    </div>
  </div>
</script></section>
<!--
<section data-markdown data-transition="none"><script type="text/template">
  ## Who am I ?

  <div class="row">
    <div class="column">
      {% include img.html src="logos/avatulhu.png" width="90%" %}
    </div>
    <div class="column">
      <br><br><br><br>
      <h3>Moisés Guimarães</h3>
      <ul>
        <li>Software engineer&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</li>
        <li>Infosec specialist</li>
        <li>And many other things <font color="#00CC00">(;,;)</font></li>
      </ul>
    </div>
  </div>
</script></section>
-->
<section data-markdown data-transition="none"><script type="text/template">
  ## Where am I from ?

  <div class="row">
    <div class="column">
      {% include img.html src="logos/jampa.png" width="90%" %}
    </div>
    <div class="column">
      <br><br><br><br>
      <h2>🇧🇷 Brasil</h2>
      <h3>João Pessoa - PB</h3>
    </div>
  </div>
</script></section>
<!--
<section data-markdown data-transition="none"><script type="text/template">
  ## Where am I from ?

  <div class="row">
    <div class="column">
      {% include img.html src="logos/jampa-centro.png" width="90%" %}
    </div>
    <div class="column">
      <br><br><br><br>
      <h2>🇧🇷 Brasil</h2>
      <h3>João Pessoa - PB</h3>
    </div>
  </div>
</script></section>

<section data-markdown data-transition="none"><script type="text/template">
  ## Where am I from ?

  <div class="row">
    <div class="column">
      {% include img.html src="logos/jampa-praia.png" width="90%" %}
    </div>
    <div class="column">
      <br><br><br><br>
      <h2>🇧🇷 Brasil</h2>
      <h3>João Pessoa - PB</h3>
    </div>
  </div>
</script></section>
-->
<section data-markdown data-background-image="{{ "/images/bg/segredo.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### why are secrets important?
</script></section>

<section data-markdown data-background-image="{{ "/images/bg/ancient.png" | prepend: site.baseurl }}"><script type="text/template">
  #### in the beginning
</script></section>

<section data-markdown data-background-image="{{ "/images/bg/citala.png" | prepend: site.baseurl }}"><script type="text/template">
  #### transposition
</script></section>

<section data-markdown data-background-image="{{ "/images/bg/caesar.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### substitution
</script></section>

<section data-markdown data-background-image="{{ "/images/bg/keyboard.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### nowadays
</script></section>

<section data-markdown><script type="text/template">
  <img class="plain" width=25% src={{ "/images/logos/whats.png" | prepend: site.baseurl }}>

  Messages you send to this chat and calls

  are now secured with end-to-end encryption.
</script></section>

<section data-markdown><script type="text/template">
  <img class="plain" width=25% src={{ "/images/icons/column.png" | prepend: site.baseurl }}>
  <img class="plain" width=25% src={{ "/images/icons/column.png" | prepend: site.baseurl }}>
  <img class="plain" width=25% src={{ "/images/icons/column.png" | prepend: site.baseurl }}>

  # Pillars of safe communication
</script></section>

<section data-markdown><script type="text/template">
  # Confidentiality

  <img class="plain" width=75% src={{ "/images/crypt/abc/confidencialidade.png" | prepend: site.baseurl }}>

  protects against unauthorized access
  
</script></section>

<section data-markdown><script type="text/template">
  # Integrity

  <img class="plain" width=95% src={{ "/images/crypt/abc/integridade.png" | prepend: site.baseurl }}>

  ensures that the message has not been changed
</script></section>

<section data-markdown><script type="text/template">
  # Authenticity

  <img class="plain" width=50% src={{ "/images/crypt/abc/autenticidade.png" | prepend: site.baseurl }}>

  verifies the sender's identity
</script></section>

<section data-markdown><script type="text/template">
  <img class="plain" width=45% src={{ "/images/icons/algorithm.png" | prepend: site.baseurl }}>

  # Cryptographic Algorithms
</script></section>

<section data-markdown><script type="text/template">
  # Symmetric Key
  
  <img class="plain" width=90% src="{{ "/images/crypt/symmetric/6.png" | prepend: site.baseurl }}">
</script></section>

<section data-markdown><script type="text/template">
  # Asymmetric Key
  
  <img class="plain" width=90% src="{{ "/images/crypt/asymmetric/encrypt6.png" | prepend: site.baseurl }}">
</script></section>

<section data-markdown><script type="text/template">
  # Asymmetric Key
  
  <img class="plain" width=90% src="{{ "/images/crypt/asymmetric/sign6.png" | prepend: site.baseurl }}">
</script></section>

<section data-markdown><script type="text/template">
  # Hash Functions
  
  <img class="plain" width=90% src="{{ "/images/crypt/hash/3.png" | prepend: site.baseurl }}">
</script></section>

<section data-markdown><script type="text/template">
  # Certificates

  <img class="plain" width=100% src={{ "/images/crypt/certificates/certchain.png" | prepend: site.baseurl }}>

</script></section>

<section>
<h2>Digital Certificate</h2>

<pre><code class="shell" data-trim data-noescape>
$ cat ca-digicert.pem

-----BEGIN CERTIFICATE-----
MIIDxTCCAq2gAwIBAgIQAqxcJmoLQJuPC3nyrkYldzANBgkqhkiG9w0BAQUFADBs
MQswCQYDVQQGEwJVUzEVMBMGA1UEChMMRGlnaUNlcnQgSW5jMRkwFwYDVQQLExB3
d3cuZGlnaWNlcnQuY29tMSswKQYDVQQDEyJEaWdpQ2VydCBIaWdoIEFzc3VyYW5j
ZSBFViBSb290IENBMB4XDTA2MTExMDAwMDAwMFoXDTMxMTExMDAwMDAwMFowbDEL
MAkGA1UEBhMCVVMxFTATBgNVBAoTDERpZ2lDZXJ0IEluYzEZMBcGA1UECxMQd3d3
LmRpZ2ljZXJ0LmNvbTErMCkGA1UEAxMiRGlnaUNlcnQgSGlnaCBBc3N1cmFuY2Ug
RVYgUm9vdCBDQTCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAMbM5XPm
+9S75S0tMqbf5YE/yc0lSbZxKsPVlDRnogocsF9ppkCxxLeyj9CYpKlBWTrT3JTW
PNt0OKRKzE0lgvdKpVMSOO7zSW1xkX5jtqumX8OkhPhPYlG++MXs2ziS4wblCJEM
xChBVfvLWokVfnHoNb9Ncgk9vjo4UFt3MRuNs8ckRZqnrG0AFFoEt7oT61EKmEFB
Ik5lYYeBQVCmeVyJ3hlKV9Uu5l0cUyx+mM0aBhakaHPQNAQTXKFx01p8VdteZOE3
hzBWBOURtCmAEvF5OYiiAhF8J2a3iLd48soKqDirCmTCv2ZdlYTBoSUeh10aUAsg
EsxBu24LUTi4S8sCAwEAAaNjMGEwDgYDVR0PAQH/BAQDAgGGMA8GA1UdEwEB/wQF
MAMBAf8wHQYDVR0OBBYEFLE+w2kD+L9HAdSYJhoIAu9jZCvDMB8GA1UdIwQYMBaA
FLE+w2kD+L9HAdSYJhoIAu9jZCvDMA0GCSqGSIb3DQEBBQUAA4IBAQAcGgaX3Nec
nzyIZgYIVyHbIUf4KmeqvxgydkAQV8GK83rZEWWONfqe/EW1ntlMMUu4kehDLI6z
eM7b41N5cdblIZQB2lWHmiRk9opmzN6cN82oNLFpmyPInngiK3BD41VHMWEZ71jF
hS9OMPagMRYjyOfiZRYzy78aG6A9+MpeizGLYAiJLQwGXFK3xPkKmNEVX58Svnw2
Yzi9RKR/5CYrCsSXaQ3pjOLAEFe4yHYSkVXySGnYvCoCWw9E1CAx2/S6cCZdkGCe
vEsXCS+0yx5DaMkHJ8HSXPfqIbloEpw8nL+e/IBcm2PN7EeqJSdnoDfzAIJ9VNep
+OkuE6N36B9K
-----END CERTIFICATE-----
</code></pre>
</section>

<section>
<h2>Digital Certificate</h2>

<pre><code class="shell" data-trim data-noescape>
$ openssl x509 -in ca-digicert.pem -text

Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number:
            02:ac:5c:26:6a:0b:40:9b:8f:0b:79:f2:ae:46:25:77
        Signature Algorithm: sha1WithRSAEncryption
        Issuer: C=US, O=DigiCert Inc, OU=www.digicert.com, CN=DigiCert High Assurance EV Root CA
        Validity
            Not Before: Nov 10 00:00:00 2006 GMT
            Not After : Nov 10 00:00:00 2031 GMT
        Subject: C=US, O=DigiCert Inc, OU=www.digicert.com, CN=DigiCert High Assurance EV Root CA
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
            RSA Public Key: (2048 bit)
                Modulus (2048 bit):
                    00:c6:cc:e5:73:e6:fb:d4:bb:e5:2d:2d:32:a6:df:
                    e5:81:3f:c9:cd:25:49:b6:71:2a:c3:d5:94:34:67:
                    a2:0a:1c:b0:5f:69:a6:40:b1:c4:b7:b2:8f:d0:98:
                    a4:a9:41:59:3a:d3:dc:94:d6:3c:db:74:38:a4:4a:
                    cc:4d:25:82:f7:4a:a5:53:12:38:ee:f3:49:6d:71:
                    91:7e:63:b6:ab:a6:5f:c3:a4:84:f8:4f:62:51:be:
                    f8:c5:ec:db:38:92:e3:06:e5:08:91:0c:c4:28:41:
                    55:fb:cb:5a:89:15:7e:71:e8:35:bf:4d:72:09:3d:
                    be:3a:38:50:5b:77:31:1b:8d:b3:c7:24:45:9a:a7:
                    ac:6d:00:14:5a:04:b7:ba:13:eb:51:0a:98:41:41:
                    22:4e:65:61:87:81:41:50:a6:79:5c:89:de:19:4a:
                    57:d5:2e:e6:5d:1c:53:2c:7e:98:cd:1a:06:16:a4:
                    68:73:d0:34:04:13:5c:a1:71:d3:5a:7c:55:db:5e:
                    64:e1:37:87:30:56:04:e5:11:b4:29:80:12:f1:79:
                    39:88:a2:02:11:7c:27:66:b7:88:b7:78:f2:ca:0a:
                    a8:38:ab:0a:64:c2:bf:66:5d:95:84:c1:a1:25:1e:
                    87:5d:1a:50:0b:20:12:cc:41:bb:6e:0b:51:38:b8:
                    4b:cb
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Key Usage: critical
                Digital Signature, Certificate Sign, CRL Sign
            X509v3 Basic Constraints: critical
                CA:TRUE
            X509v3 Subject Key Identifier:
                B1:3E:C3:69:03:F8:BF:47:01:D4:98:26:1A:08:02:EF:63:64:2B:C3
            X509v3 Authority Key Identifier:
                keyid:B1:3E:C3:69:03:F8:BF:47:01:D4:98:26:1A:08:02:EF:63:64:2B:C3

    Signature Algorithm: sha1WithRSAEncryption
        1c:1a:06:97:dc:d7:9c:9f:3c:88:66:06:08:57:21:db:21:47:
        f8:2a:67:aa:bf:18:32:76:40:10:57:c1:8a:f3:7a:d9:11:65:
        8e:35:fa:9e:fc:45:b5:9e:d9:4c:31:4b:b8:91:e8:43:2c:8e:
        b3:78:ce:db:e3:53:79:71:d6:e5:21:94:01:da:55:87:9a:24:
        64:f6:8a:66:cc:de:9c:37:cd:a8:34:b1:69:9b:23:c8:9e:78:
        22:2b:70:43:e3:55:47:31:61:19:ef:58:c5:85:2f:4e:30:f6:
        a0:31:16:23:c8:e7:e2:65:16:33:cb:bf:1a:1b:a0:3d:f8:ca:
        5e:8b:31:8b:60:08:89:2d:0c:06:5c:52:b7:c4:f9:0a:98:d1:
        15:5f:9f:12:be:7c:36:63:38:bd:44:a4:7f:e4:26:2b:0a:c4:
        97:69:0d:e9:8c:e2:c0:10:57:b8:c8:76:12:91:55:f2:48:69:
        d8:bc:2a:02:5b:0f:44:d4:20:31:db:f4:ba:70:26:5d:90:60:
        9e:bc:4b:17:09:2f:b4:cb:1e:43:68:c9:07:27:c1:d2:5c:f7:
        ea:21:b9:68:12:9c:3c:9c:bf:9e:fc:80:5c:9b:63:cd:ec:47:
        aa:25:27:67:a0:37:f3:00:82:7d:54:d7:a9:f8:e9:2e:13:a3:
        77:e8:1f:4a
</code></pre>
</section>


<section data-markdown><script type="text/template">
  # SSL / TLS timeline

  <table>
      <tr style="color:gray;">
        <td>-</td>
        <td>SSL 1.0</td>
        <td>Netscape</td>
      </tr>
      <tr style="color:red;">
        <td>1995</td>
        <td>SSL 2.0</td>
        <td>Netscape</td>
      </tr>

      <tr style="color:red;">
        <td>1997</td>
        <td>SSL 3.0</td>
        <td>Netscape</td>
      </tr>
      <tr style="color:orange;">
        <td>1999</td>
        <td>TLS 1.0</td>
        <td>RFC 2246</td>
      </tr>
      <tr style="color:green;">
        <td>2006</td>
        <td>TLS 1.1</td>
        <td>RFC 4346</td>
      </tr>
      <tr style="color:green;">
        <td>2008</td>
        <td>TLS 1.2</td>
        <td>RFC 5246</td>
      </tr>
      <tr style="color:blue;">
        <td>2018</td>
        <td>TLS 1.3</td>
        <td>draft</td>
      </tr>
  </table>
</script></section>

<section>
<h1>handshake</h1>

<pre><code class="text" data-trim data-noescape style="font-size: 30px;">
  <div style="text-align:left;">>>> client hello</div>
  <div style="text-align:right;">server hello <<<</div>
  <div style="text-align:right;">certificate <<<</div>
  <div style="text-align:right;">server key exchange <<<</div>
  <div style="text-align:right;">server hello done <<<</div>
  <div style="text-align:left;">>>> client key exchange</div>
  <div style="text-align:left;">>>> change cipher spec</div>
  <div style="text-align:left;">>>> finished</div>
  <div style="text-align:right;">change cipher spec <<<</div>
  <div style="text-align:right;">finished <<<</div>
</code></pre>

</section>

<section data-markdown><script type="text/template">

# demo

</script></section>

<section data-markdown><script type="text/template">

## Moisés Guimarães de Medeiros
### [{{ site.email }}](mailto:{{ site.email }})
### [{{ site.url }}]({{ site.url }})
slides at {{ site.baseurl | prepend: site.url }}

</script></section>
