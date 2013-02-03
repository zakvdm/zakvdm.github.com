---
layout: post
title: Kanji stroke orders in Anki!
tags:
- kanji
- MovieMethod
- study methods
- anki
---
{% img right /images/posts/2012-11-05-kanji-stroke-order-diagrams-1-400.jpg 250 %}

Just a quick note for anyone studying kanji (especially if you're doing a variant of heisig). You can download a font which includes stroke orders [here](http://www.nihilist.org.uk/).

With a simple change to my Anki model, all my kanji cards now include stroke order diagrams. Nice!

If you're curious, here's how I changed the card:

###Back Template
Include something like:

``` html 
<span class="kanji">{{Kanji}}</span>
```
    

###Styling
Include the following css:

``` css
    .kanji {
      font-family: KanjiStrokeOrders;
      font-size: 150px;
      color: #e56727;
    }
```

This is for Anki 2.0 by the way, but you could do something similar with
earlier versions. The only really critical part is setting the font-family to
KanjiStrokeOrders.

