---
# try also 'default' to start simple
theme: apple-basic
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: "text-center"
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
exportFilename: "normal-dist-presentation"
# enable slide recording, can be boolean, 'dev' or 'build'
record: "build"
# favicon, can be a local file path or URL
favicon: "https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Mu_uc_lc.svg/100px-Mu_uc_lc.svg.png"
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

Eine **stetige Zufallsvariable $\boldsymbol{X}$** ist normalverteilt mit dem **_Erwartungswert_ $\boldsymbol{\mu}$** und der **_Varianz_ $\boldsymbol{\sigma^2}$**, wenn $X$ die folgende Wahrscheinlichkeitsdichte hat:

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

Gib jeweils jeweils begründet an, ob es sich um eine **valide** Normalverteilung handelt. Wenn dies zutreffen sollte, gib zusätzlich Erwartungswert, Standardabweichung und die Wahrscheinlichkeitsdichtefunktion $f(x)$ an.

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

# Standardnormalverteilung

<br />

<v-click>

$$\mu = 0\ \ \land\ \ \sigma=1$$

</v-click>

<v-click>

$$\ {\displaystyle X\sim {\mathcal {N}}\left(0 ,1 \right)}$$

</v-click>

<v-click>

$$\Phi(x) = \frac{1}{\sqrt{2\pi}} \cdot e^{-\frac{x^2}{2}}$$

</v-click>

---

<Graph />

---

# Graph - Eigenschaften

<div id="image-div">
  <img src="/graph-punkte.png" class="rounded shadow" />
</div>

<br />

<v-clicks>

- stetige Gaußsche Glockenkurve, deren Höhe und Breite von $\sigma$ abhängt
- Veränderung von $\mu$ verschiebt die Glockenkurve in x-Richtung
- $\mu$ ist die x-Koordinate des Hochpunkts
- Achsensymmetrie zur Geraden mit der Gleichung $x=\mu$
- → Symmetrie um Erwartungswert
- $\forall x \in \mathbb{R}: f(x) > 0$
- Wendestellen bei $x_1 = \mu - \sigma$ und $x_2 = \mu + \sigma$

</v-clicks>

<style>
  #image-div {
    display: flex;
    justify-content: center;
    width: 100%;
    height: 40%;
  }
  img {
    height: 100%;
  }
</style>

---

# Wahrscheinlichkeit

<div id="image-div">
  <img src="/normalverteilung-beispiel.png" class="rounded shadow" />
</div>

<br />

<div>

- Wahrscheinlichkeit entspricht Fläche unter dem Graphen
- Flächeinhalt beträgt insgesamt $1$ ($100 \%$)

</div>

<style>
  #image-div {
    display: flex;
    justify-content: center;
    width: 100%;
    height: 70%;
  }
  img {
    height: 100%;
  }
</style>

---

# Verteilungsfunktion

Eine Verteilungsfunktion beschreibt die Fläche, die die Dichtefunktion mit der
$x$-Achse einschließt. Sie wird daher mit einem Integral beschrieben:

$$ F(x)= \int _{-\infty }^{x}f(t)\ \mathrm {d} t = {\frac {1}{\sigma {\sqrt {2\pi }}}}\int _{-\infty }^{x}e^{-{\frac {1}{2}}\left({\frac {t-\mu }{\sigma }}\right)^{2}}\mathrm {d} t $$

<br />

$$ F(z_0) = P(X \leq z_0)$$

<br />

$$
P(z_1 \leq X \leq z_2) = F(z_2) - F(z_1)

---

# Inverse Normalverteilung

- $P(X \leq a)=P_0$ gegeben
- $a$ gesucht

- Berechnung:
  $$\begin{aligned}
    F(a) &= P_0\\
    {\frac {1}{\sigma {\sqrt {2\pi }}}}\int _{-\infty }^{a}e^{-{\frac {1}{2}}\left({\frac {t-\mu }{\sigma }}\right)^{2}}\mathrm {d} t &= P_0\\
    a &= ...\ \text{(nach a auflösen)}\\
    \text{OD}&\text{ER}\\
    a &= \text{invNorm}(P_0, \mu, \sigma)\ \text{(mit GTR)}\\
    (P_0 \in [0, 1];\ &\mu, \sigma \in \mathbb{R})
  \end{aligned}
$$

---

# Sigma-Intervalle

<div id="image-div">
  <img src="/sigma-intervalle.png" class="rounded shadow" />
</div>

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

---

# Normal-Approximation

- Die Werte einer diskreten Zufallsgröße können mithilfe von den entsprechenen Werten einer stetigen Normalverteilung approximiert werden
- Voraussetzungen:
  - $\sigma^2 > 9$ $(\sigma > 3)$
  - hohes $n$
- Stetigkeitskorrektur notwendig: $P_B(z_1 \leq X \leq z_2) = P_N(z_1-0.5 \leq X \leq z_2+0.5)$

---

<Aufgabe2 />

---

<Aufgabe2l />

---

# Aufgabe 3

Ein fairer Würfel wird $1000$ Mal geworfen. Man ist nun an der Wahrscheinlichkeit interessiert, dass zwischen $100$ und $150$ Mal die Sechs gewürfelt wird.

<ol class="list-upper-alpha">
  <li>Begründe, wieso man hier trotz des 6-seitigen Würfels von einem Bernoulli-Experiment sprechen kann.</li>
  <li>Begründe, wieso es sich hier um eine Binomialverteilung handelt und nicht um eine Normalverteilung.</li>
  <li>Berechne die exakte Wahrscheinlichkeit.</li>
  <li>Erkläre, ob hier die Bedingungen für die Normal-Approximation gegeben sind.</li>
  <li>Berechne die approximierte Wahrscheinlichkeit mithilfe der Normalverteilung.</li>
</ol>

---

<Aufgabe3l />
