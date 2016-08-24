---
layout: slide
---

<section data-markdown><script type="text/template">
{% include logo.html %}

# wolfcrypt-py
### embalando segredos com Python

[Moisés Guimarães de Medeiros](https://github.com/moisesguimaraes)

27 de Agosto de 2016
</script></section>

<section data-markdown><script type="text/template">
{% include logo.html %}

# wolfSSL Inc.

Fundada em 2009

~ 20 funcionários

Seattle | Bozeman | Portland | Sacramento | Tokyo | João Pessoa

</script></section>

<section data-markdown><script type="text/template">
  # wolfcrypt
  ## wolfSSL Crypto Engine

  - Escrita em C, com foco em leveza e portabilidade.

  - Reconhecida pelo seu tamanho, velocidade e funcionalidades.

  - Amplamente utilizada no mercado de IoT.

  - Também disponível para desktop e cloud.
</script></section>

<section data-markdown data-background-image="{{ "/images/segredo.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### Quanto vale um segredo?
</script></section>

<section data-markdown data-background-image="{{ "/images/ancient.png" | prepend: site.baseurl }}"><script type="text/template">
  #### Como era antigamente?
</script></section>

<section data-markdown data-background-image="{{ "/images/citala.png" | prepend: site.baseurl }}"><script type="text/template">
  #### transposição
</script></section>

<section data-markdown data-background-image="{{ "/images/caesar.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### substituição
</script></section>

<section data-markdown data-background-image="{{ "/images/enigma.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### Como evoluiu?
</script></section>

<section data-markdown data-background-image="{{ "/images/enigma2.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### enigma
</script></section>

<section data-markdown data-background-image="{{ "/images/bombe.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### bombe
</script></section>

<section data-markdown data-background-image="{{ "/images/keyboard.jpg" | prepend: site.baseurl }}"><script type="text/template">
  #### Onde estamos?
</script></section>

<section data-markdown><script type="text/template">
  <img class="plain" width=25% src={{ "/images/whats.png" | prepend: site.baseurl }}>

  As mensagens que você enviar e as ligações que você fizer nesta conversa estão <spam class="fragment highlight-current-blue">protegidas com criptografia de ponta-a-ponta</spam>.
</script></section>

<section data-markdown><script type="text/template">
  # Confidencialidade

  <img class="plain" width=75% src={{ "/images/confidencialidade.png" | prepend: site.baseurl }}>

  protege contra acesso não autorizado
</script></section>

<section data-markdown><script type="text/template">
  # Integridade

  <img class="plain" width=95% src={{ "/images/integridade.png" | prepend: site.baseurl }}>

  garante que a mensagem não foi alterada
</script></section>

<section data-markdown><script type="text/template">
  # Autenticidade

  <img class="plain" width=50% src={{ "/images/autenticidade.png" | prepend: site.baseurl }}>

  verifica a identidade do remetente
</script></section>

<section data-markdown><script type="text/template">
  <img class="plain" width=45% src={{ "/images/algorithm.png" | prepend: site.baseurl }}>

  # Algoritmos de Criptografia
</script></section>

<section data-markdown><script type="text/template">
  # Chave Simétrica
  <img class="plain" width=90% src={{ "/images/simetrica.png" | prepend: site.baseurl }}>
</script></section>

<section data-markdown><script type="text/template">
  ## Modos de cifragem em bloco: ECB
  
  <img class="plain" width=90% src={{ "/images/ecb.svg" | prepend: site.baseurl }}>
</script></section>

<section data-markdown><script type="text/template">
  ## Modos de cifragem em bloco: ECB
  
  <img class="plain" src={{ "/images/tux.jpg" | prepend: site.baseurl }}>
  <img class="plain" src={{ "/images/tux-ecb.jpg" | prepend: site.baseurl }}>
  <img class="plain" src={{ "/images/tux-secure.jpg" | prepend: site.baseurl }}>
</script></section>

<section data-markdown><script type="text/template">
  ## Modos de cifragem em bloco: CBC
  
  <img class="plain" width=90% src={{ "/images/cbc.svg" | prepend: site.baseurl }}>
</script></section>

<section data-markdown><script type="text/template">
  ## Modos de cifragem em bloco: CRT
  
  <img class="plain" width=90% src={{ "/images/crt.svg" | prepend: site.baseurl }}>
</script></section>

<section>
<h2>Exemplo de Chave Simétrica</h2>

<pre><code class="python" data-trim data-noescape>
>>> from wolfcrypt.ciphers import Aes, MODE_CBC
>>> 
>>> cipher = Aes(b'0123456789abcdef', MODE_CBC, b'1234567890abcdef')
>>> 
>>> ciphertext = cipher.encrypt('now is the time ')
>>> ciphertext
b'\x95\x94\x92W_B\x81S,\xcc\x9dFw\xa23\xcb'
>>> 
>>> cipher.decrypt(ciphertext)
b'now is the time '
</code></pre>
</section>

<section data-markdown><script type="text/template">
  # Chave Assimétrica
  <img class="plain" width=90% src={{ "/images/assimetrica.png" | prepend: site.baseurl }}>
</script></section>

<section>
<h2>Exemplo de Chave Assimétrtica</h2>

<pre><code class="python" data-trim data-noescape>
>>> from wolfcrypt.ciphers import RsaPrivate, RsaPublic
>>> from wolfcrypt.utils import h2b
>>> 
>>> private = "3082025C02010002818100BC730EA849F374A2A9EF18A5DA559921F9C8ECB36D" \
...         + "48E53535757737ECD161905F3ED9E4D5DF94CAC1A9D719DA86C9E84DC4613682" \
...         + "FEABAD7E7725BB8D11A5BC623AA838CC39A20466B4F7F7F3AADA4D020EBB5E8D" \
...         + "6948DC77C9280E22E96BA426BA4CE8C1FD4A6F2B1FEF8AAEF69062E5641EEB2B" \
...         + "3C67C8DC2700F6916865A902030100010281801397EAE8387825A25C04CE0D40" \
...         + "7C31E5C470CD9B823B5809863B665FDC3190F14FD5DB15DDDED73B9593311831" \
...         + "0E5EA3D6A21A716E81481C4BCFDB8E7A866132DCFB55C1166D279224458BF1B8" \
...         + "48B14B1DACDEDADD8E2FC291FBA5A96EF83A6AF1FD5018EF9FE7C3CA78EA56D3" \
...         + "D3725B96DD4E064E3AC3D9BE72B66507074C01024100FA47D47A7C923C55EF81" \
...         + "F041302DA3CF8F1CE6872705700DDF9835D6F18B382F24B5D084B6794F712994" \
...         + "5AF0646AACE772C6ED4D59983E673AF3742CF9611769024100C0C1820D0CEBC6" \
...         + "2FDC92F99D821A31E9E9F74BF282871CEE166AD11D188270F3C0B62FF6F3F71D" \
...         + "F18623C84EEB8F568E8FF5BFF1F72BB5CC3DC657390C1B54410241009D7E05DE" \
...         + "EDF4B7B2FBFC304B551DE32F0147966905CD0E2E2CBD8363B6AB7CB76DCA5B64" \
...         + "A7CEBE86DF3B53DE61D21EEBA5F637EDACAB78D94CE755FBD71199C102401898" \
...         + "1829E61E2739702168AC0A2FA172C121869538C65890A0579CBAE3A7B115C8DE" \
...         + "F61BC2612376EFB09D1C44BE1343396717C89DCAFBF545648B38822CF2810240" \
...         + "3989E59C195530BAB7488C48140EF49F7E779743E1B419353123759C3B44AD69" \
...         + "1256EE0061641666D37C742B15B4A2FEBF086B1A5D3F9012B105863129DBD9E2"
>>> 
>>> prv = RsaPrivate(h2b(private))
>>> 
>>> public  = "30819F300D06092A864886F70D010101050003818D0030818902818100BC730E" \
...         + "A849F374A2A9EF18A5DA559921F9C8ECB36D48E53535757737ECD161905F3ED9" \
...         + "E4D5DF94CAC1A9D719DA86C9E84DC4613682FEABAD7E7725BB8D11A5BC623AA8" \
...         + "38CC39A20466B4F7F7F3AADA4D020EBB5E8D6948DC77C9280E22E96BA426BA4C" \
...         + "E8C1FD4A6F2B1FEF8AAEF69062E5641EEB2B3C67C8DC2700F6916865A90203010001"
>>> 
>>> pub = RsaPublic(h2b(public))
>>> 
>>> plaintext = b"Everyone gets Friday off."
>>> 
>>> ciphertext = pub.encrypt(plaintext)
>>> ciphertext 
b'e\xb7\xc2\xad\x0c\x04.\xefU8\x17QB\x852\x03\x01\xef\xbe=\xb4\xaf\xaf\x97\x9e4\x96\x9f\xc3\x8e\x87\x9a8o$.|_e\x1d\xa2yi?\x83\x18\xf9Yr|\x1fQ\x1a\x18\x1e\xab\xd17\xc5\x8c\xae\x08c)\xbc\nIr\x8d\xc3\x88\x7f\xde\x1f\x1a^lB\r\xf1\xc0\xfd0\xdeA\xf3\xd2\xe5q\x9a0\xee\xb4,\x97\x80\xa4|U;\xe6\x11\xf0\xc2Q\x987\xe1>F\xf5\x14\x186@G~(Q\xf2;\xcb\x05\xee\x88\x0b\xd8\xa7'
>>> 
>>> prv.decrypt(ciphertext)
b'Everyone gets Friday off.'
>>> 
>>> signature = prv.sign(plaintext)
>>> signature 
b'~\xc4\xe65\x15\xb17\x7fX\xaf,\xc2lw\xbd\x8f\t\x9d\xbf\xac\xdez\x90\xb4\x9f\x1aM\x88#Z\xea\xcb\xa6\xdb\x99\xf55\xd0\xfe|Mu\xb6\xb79(t\x81+h\xf2\xcd\x88v\xa8\xbaM\x86\xcfk\xe8\xf3\x0b\xb8\x8ew\xda>\xf8\xd5[H\xeaAh\xc6\xdaQlo]\xdd\xf8w\xe7#M-\x12f\xae,\xdd\xa6d FP<;R\xa2\x96hJ\xee_\x1fh\xaa\xc8\xdfAJ\xa5\xdd\x05\xc4\x89\x0c\xd7\xa0C\xb7u"U\x03'
>>> 
>>> pub.verify(signature)
b'Everyone gets Friday off.'
</code></pre>
</section>

<section data-markdown><script type="text/template">
  # Funções de Hash
  <img class="plain" width=90% src={{ "/images/hash.png" | prepend: site.baseurl }}>
</script></section>

<section data-markdown><script type="text/template">
  ## Propriedades de um bom Hash
  - Fácil de calcular
  - Inviável de forjar uma mensagem com um determinado resumo
  - Inviável de modificar a mensagem sem modificar o resumo
  - Inviável de encontrar duas mensagens com o mesmo resumo
</script></section>

<section data-markdown><script type="text/template">
  ## Funções de Hash

  <table>
  <tr>
    <th>Hash</th>
    <th>Tamanho</th>
    <th>Exemplo</th>
  </tr>

  <tr>
    <td>SHA-1</td>
    <td>160 bits</td>
    <td><code>a33d8d465abb7cc30958b47095528619<br/>
              83c28f02</code></td>
  </tr>

  <tr>
    <td>SHA-256</td>
    <td>256 bits</td>
    <td><code>2157db6d182dfce96fe8190e0117ea85<br/>
              38392658fdd9ae2d48268d4277d5dceb</code></td>
  </tr>

  <tr>
    <td>SHA-512</td>
    <td>512 bits</td>
    <td><code>58c489dc1286f484b17473cbd519346e<br/>
              5035640c27326ec7098e9b91d4c61e27<br/>
              26eaa5b76eeb921c6f0796d3a281f3b7<br/>
              dbbd3fa7e9c7e3f03d964795e2ba2f43</code></td>
  </tr>
  </table>
</script></section>

<section>
<h2>Exemplo de Hash</h2>

<pre><code class="python" data-trim data-noescape>
>>> from wolfcrypt.hashes import Sha256
>>> 
>>> s = Sha256()
>>> h.update("wolf")
>>> h.update("crypt")
>>> 
>>> s.digest()
b'\x96\xe0.{\x1c\xbc\xd6\xf1\x04\xfe\x1f\xdbFR\x02zU\x05\xb6\x86R\xb7\x00\x95\xc61\x8f\x9d\xce\r\x18D'
>>> 
>>> s.hexdigest()
b'96e02e7b1cbcd6f104fe1fdb4652027a5505b68652b70095c6318f9dce0d1844'
</code></pre>
</section>

<section data-markdown><script type="text/template">
  # HMAC
  <img class="plain" width=90% src={{ "/images/hmac.png" | prepend: site.baseurl }}>
</script></section>

<section>
<h2>Exemplo de HMAC</h2>

<pre><code class="python" data-trim data-noescape>
>>> from wolfcrypt.hashes import HmacSha256
>>> 
>>> h = HmacSha256('secret')
>>> h.update("wolf")
>>> h.update("crypt")
>>> 
>>> h.digest()
b'\x18\xbf*\t9\xa2o\xdf\\\xc8\xe0\xc2U\x94,\x8dY\x02;\x1c<Q\xdf\x8d\xdb\x863\xfb\xc1f#o'
>>> 
>>> h.hexdigest()
b'18bf2a0939a26fdf5cc8e0c255942c8d59023b1c3c51df8ddb8633fbc166236f'
</code></pre>
</section>

<section data-markdown><script type="text/template">
  <img class="plain" width=25% src={{ "/images/dice.png" | prepend: site.baseurl }}>

  # Números Aleatórios

</script></section>

<section>
<h2>Geração de Números Aleatórios</h2>

<pre><code class="python" data-trim data-noescape>
>>> from wolfcrypt.random import Random
>>> 
>>> r = Random()
>>> 
>>> b = r.byte()
>>> b
b'\x8c'
>>> 
>>> b16 = r.bytes(16)
>>> b16
b']\x93nk\x95\xbc@\xffX\xab\xdcB\xda\x11\xf7\x03'
</code></pre>
</section>

<section data-markdown><script type="text/template">

<img class="plain" width=20% src={{ "/images/gear.png" | prepend: site.baseurl }}>

# Instalação

<pre><code class="shell" data-trim data-noescape>
$ git clone https://github.com/wolfssl/wolfssl.git
$ 
$ cd wolfssl/
$ ./autogen.sh
$ ./configure --enable-sha512
$ make
$ sudo make install
$ 
$ sudo -H pip install wolfcrypt
</code></pre>
</script></section>

<section data-markdown><script type="text/template">
  <img class="plain" width=15% src={{ "/images/book.png" | prepend: site.baseurl }}>

  # Documentação completa

  [wolfssl.github.io/wolfcrypt-py](https://wolfssl.github.io/wolfcrypt-py/)
</script></section>

<section data-markdown><script type="text/template">

{% include logo.html %}

## Moisés Guimarães de Medeiros
### [moises@wolfssl.com](mailto:moises@wolfssl.com)
### +55 (83) 99986-5511
### [www.wolfssl.com](https://www.wolfssl.com)

</script></section>