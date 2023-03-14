---
# try also 'default' to start simple
theme: apple-basic
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
# enable presenter mode, can be boolean, 'dev' or 'build'
presenter: true
# enabled pdf downloading in SPA build, can also be a custom url
download: true
# filename of the export file
exportFilename: 'normal-dist-presentation'
---

# Die Normalverteilung

<br>

Eine Präsentation von Luis
<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
   <carbon:arrow-right class="inline"/>
  </span>
</div>

---

# Definition

Eine **stetige Zufallsvariable $\boldsymbol{X}$** ist normalverteilt mit dem ***Erwartungswert* $\boldsymbol{\mu}$** und der ***Varianz* $\boldsymbol{\sigma^2}$**, wenn $X$ die folgende Wahrscheinlichkeitsdichte hat:
$$
  \begin{aligned}
    f(x| \mu, \sigma^2) &= \frac{1}{\sqrt{2 \pi \sigma^2}}\, e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}\\ 
    \\ 
    f: \mathbb{R} &\rightarrow \mathbb{R}\\
    \mu &\in \mathbb{R}\\
    \sigma^2 \in \mathbb{R} &\land \sigma^2 > 0
  \end{aligned}
$$

<br />

Kennzeichnung, dass $X$ normalverteilt ist: $\ {\displaystyle X\sim {\mathcal {N}}\left(\mu ,\sigma ^{2}\right)}$

---

<Graph />