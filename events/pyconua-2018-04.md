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

{% include crypt/symmetric.html lang=en %}

<section data-markdown><script type="text/template">
  ## Block cipher modes: ECB
  
  <img class="plain" width=90% src={{ "/images/crypt/symmetric/ecb.svg" | prepend: site.baseurl }}>
</script></section>

<section data-markdown><script type="text/template">
  ## Block cipher modes: ECB
  
  <img class="plain" src={{ "/images/crypt/symmetric/tux.jpg" | prepend: site.baseurl }}>
  <img class="plain" src={{ "/images/crypt/symmetric/tux-ecb.jpg" | prepend: site.baseurl }}>
  <img class="plain" src={{ "/images/crypt/symmetric/tux-secure.jpg" | prepend: site.baseurl }}>
</script></section>

<section data-markdown><script type="text/template">
  ## Block cipher modes: CBC
  
  <img class="plain" width=90% src={{ "/images/crypt/symmetric/cbc.svg" | prepend: site.baseurl }}>
</script></section>

<section data-markdown><script type="text/template">
  ## Block cipher modes: CTR
  
  <img class="plain" width=90% src={{ "/images/crypt/symmetric/ctr.svg" | prepend: site.baseurl }}>
</script></section>

{% include asymmetric.html lang=en %}

{% include hash.html lang=en %}

<section data-markdown><script type="text/template">
  ## Properties of a good hash
  - Easy to calculate
  - Infeasible to guess the message from its hash
  - Infeasible to modify the message without modifying its hash
  - Infeasible to find two different messages with the same hash

</script></section>

<section data-markdown><script type="text/template">
  ## Hash functions

  <table>
    <thead>
      <tr>
        <th>Hash</th>
        <th>Size</th>
        <th>Example</th>
      </tr>
    </thead>
    <tbody>
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
    </tbody>
  </table>
</script></section>

<section data-markdown><script type="text/template">

## Moisés Guimarães de Medeiros
### [{{ site.email }}](mailto:{{ site.email }})
### [{{ site.url }}]({{ site.url }})
slides at {{ site.baseurl | prepend: site.url }}
</script></section>
