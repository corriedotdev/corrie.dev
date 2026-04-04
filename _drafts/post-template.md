---
layout: post
title: "[POST TITLE]"
excerpt: "[One sentence summary shown in post listings and meta tags.]"
categories: [Tech💡]
# Other category options: games👾, VR🥽, Research🔬
comments: true
image:
  feature: feature/poly.jpg
  # Path is relative to /img/ — e.g. feature/poly.jpg → /img/feature/poly.jpg
galleries:
 1:
   -
     - { url: '/img/yove-vr.png', alt: '[Image description]' }
     - { url: '/img/yove-vr.png', alt: '[Image description]' }
---

## Intro

[Opening paragraph — 2–3 sentences. What is this about and why does it matter to you?]

---

## [Section One Title]

[Body text. Keep it focused — one idea per section.]

> [Optional pullquote or key insight from this section.]

- [Bullet point one]
- [Bullet point two]
- [Bullet point three]

---

## [Section Two Title]

[Body text.]

### YouTube Embed

<iframe width="720" height="480" src="https://www.youtube.com/embed/5Bj4s9o4yYE" title="[Video title]" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen> </iframe>

---

## [Section Three Title]

[Body text.]

### Inline Video

<video id="videoElement" width="720" height="480" playsinline autoplay muted loop>
  <source src="{{ site.url }}/img/gallery/xr-interface.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

---

## [Section Four Title — Optional Code Example]

[Brief explanation of what the code does.]

{% highlight csharp %}
// [Code placeholder]
void Example() {
    Debug.Log("Replace this with real code.");
}
{% endhighlight %}

---

## [Section Five Title — Optional Tweet Embed]

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">[Tweet text placeholder] <a href="https://twitter.com/hashtag/unity?src=hash&amp;ref_src=twsrc%5Etfw">#unity</a></p>&mdash; Corrie (@corriedotdev) <a href="https://twitter.com/corriedotdev/status/1501587367823650816?ref_src=twsrc%5Etfw">March 9, 2022</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

---

## Further Reading

* [[Link title]](https://corrie.dev)
* [My Company](https://www.cjgstudio.com)

---

<a href="#" id="emailclick" onclick="replace_email()">My Email</a>

<script>
var email;

function add_mailto() {
  const elem = document.getElementById("emailclick");
  elem.href = `mailto:${email}`;
}

function replace_email() {
  const domain = "cjgstudio.com";
  const name = [16, 28, 1, 1, 26, 22];
  const xor_with = 115;
  let constructed = "";
  name.forEach(function(i) {
    constructed += String.fromCharCode(i ^ xor_with);
  })
  email = `${constructed}@${domain}`;
  const elem = document.getElementById("emailclick");
  elem.text = email;
  window.setTimeout(add_mailto, 100);
}
</script>
