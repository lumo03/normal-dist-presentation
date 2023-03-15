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

# Aufgabe 1

Geben Sie Erwartungswert und Standardabweichung der Verteilungen an und begründen Sie jeweils, ob es sich um eine **valide** Normalverteilung handelt. Wenn dies zutrifft, geben Sie zusätzlich die Wahrscheinlichkeitsdichtefunktion $f(x)$ an.

- $\ {\displaystyle X\sim {\mathcal {N}}\left(0 ,4 \right)}$
- $\ {\displaystyle Y\sim {\mathcal {N}}\left(-4 ,16 \right)}$
- $\ {\displaystyle Z\sim {\mathcal {N}}\left(16, -4 \right)}$
- $\ {\displaystyle O\sim {\mathcal {N}}\left(2, 0 \right)}$

<v-click>

## Lösung:

</v-click>

<v-clicks>

- $X$ ist normalverteilt mit $\mu=0$ und $\sigma=2$; $f(x)= \frac{1}{\sqrt{8 \pi}} \cdot e^{-\frac{x^2}{8}}$
- $Y$ ist normalverteilt mit $\mu=-4$ und $\sigma=4$; $f(x)= \frac{1}{\sqrt{32 \pi}} \cdot e^{-\frac{1}{2} \cdot \left( \frac{x+4}{4} \right)^2}$
- $Z$ ist nicht normalverteilt, da für eine Normalverteilung $\sigma^2 > 0$ gelten muss
- $O$ ist nicht normalverteilt, da für eine Normalverteilung $\sigma^2 > 0$ gelten muss

</v-clicks>

---

<Graph />

---

# Graph - Eigenschaften

<br />

<v-clicks>

- Gaußsche Glockenkurve, deren Höhe und Breite von $\sigma$ abhängt
- Veränderung von $\mu$ verschiebt die Glockenkurve in x-Richtung
- $\mu$ ist die x-Koordinate des Hochpunkts
- Achsensymmetrie zur Geraden mit der Gleichung $x=\mu$
- → Symmetrie um Erwartungswert

</v-clicks>

---
layout: image

image: /sigma-intervalle3.png
---

---

# Sigma-Intervalle

<br />

$$ 
  \begin{aligned}
    P(\mu - 1 \cdot \sigma \leq x \leq \mu + 1 \cdot \sigma) \approx 68,3 \% \\ 
    P(\mu - 2 \cdot \sigma \leq x \leq \mu + 2 \cdot \sigma) \approx 95,5 \% \\ 
    P(\mu - 3 \cdot \sigma \leq x \leq \mu + 3 \cdot \sigma) \approx 99,7 \% 
  \end{aligned}
$$

<style>
  #image-div {
    display: flex;
    justify-content: center;
    width: 100%;
    height: 60%;
  }
  img {
    height: 100%;
  }
</style>

---

# Wichtige Formeln

<v-click>

$$ \mu = n \cdot p $$

</v-click>

<v-click>

$$ \sigma = \sqrt{\mu \cdot q} = \sqrt{n \cdot p \cdot q} = \sqrt{n \cdot p \cdot (1-p)} $$

</v-click>

<v-click>

$$ \sigma^2 = n \cdot p \cdot (1-p) $$

</v-click>