---
layout: slide

title: wolfcrypt-py @ EXPOTEC 2016
description: > # Esta apresentação contém conceitos básicos de criptografia clássica e moderna,
  e uma introdução à biblioteca wolfCrypt, engine de criptografia por trás da biblioteca wolfSSL
  responsável pela segurança de mais de 1 bilhão de aplicações e dispositivos. Utilizando exemplos
  na linguagem python com a API wolfcrypt-py, tentamos desmistificar um pouco da criptografia para
  público geral, assim como divulgar a ferramenta para desenvolvedores, aumentando o seu "arsenal
  digital".

theme: sky
transition: slide
---

<section data-markdown>
![logo]({{ "/images/logo.gif" | prepend: site.baseurl }})

# wolfcrypt-py
### embalando segredos com Python

[Moisés Guimarães de Medeiros](https://github.com/moisesguimaraes)

27 de Agosto de 2016
</section>

<section data-markdown>
## Overview

[reveal.js](https://github.com/hakimel/reveal.js/) enables you to create
beautiful interactive slide decks using HTML. This presentation will show you
how to integrate it with [Jekyll](http://jekyllrb.com/)
</section>

<section data-markdown>
## reveal.js

Clone reveal.js to your site's root folder:

```
git clone https://github.com/hakimel/reveal.js.git
```

Or, add it as your site's submodule:

```
git submodule add https://github.com/hakimel/reveal.js.git
```
</section>

<section data-markdown>
## Slide Layout

Create a layout file, call `slide.html` in `_layouts` folder. And use this gist
for the content of the file https://gist.github.com/luugiathuy/c07ac5608addadb642e5.

</section>

<section data-markdown>
## Slide

Now, in your page/post YAML front matter, use `slide` for the layout. You can
define *title*, *author*, *description* as well as the slide's *theme* and
*transition*:

```yaml
---
layout: slide
title: Jekyll&#58; Make presentation page with reveal.js
description: A presentation slide for how to use reveal.js in Jekyll
theme: black
transition: slide
---
```
</section>

<section data-markdown>
## Slide

Each slide is enclosed in a `&lt;section&gt;` tag:

```html
&lt;section data-markdown&gt;
## Overview

[reveal.js](https://github.com/hakimel/reveal.js/) enables you to create
beautiful interactive slide decks using HTML. This presentation will show you
how to integrate it with [Jekyll](http://jekyllrb.com/)
&lt;/section&gt;
```

</section>

<section data-markdown>
# THE END
</section>