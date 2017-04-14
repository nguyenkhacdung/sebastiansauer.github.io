---
title: "Müncher Mietpreis: Übung zum p-Wert"
author: "Sebastian Sauer"
layout: post
tags: [teaching, stats, German]
date: "2016-12-21"
---

Sie möchten die Hypothese (H0) testen, dass der mittlere Mietpreis in München 16,28€ beträgt (wie der Münchner Merkur einmal behauptet hat). Dafür ziehen Sie eine Stichprobe der Größe n = 36. Gehen Sie von einer SD von 3€ in der Population aus (Menge aller Mietwohnungen in München). Alpha sei 5%. Der Mittelwert Ihrer Stichprobe ist 16,79€. Nehmen Sie als H1 die Hypothese, dass der wahre mittlere Mietpreis höher ist.

# Gesucht

1. Was ist der z-Wert des Stichprobenergebnisses?
2. Wie hoch ist die Wahrscheinlichkeit dieses Ergebnisses (oder noch extremerer), wenn die H0 gilt? Sprich: Was ist der p-Wert (2 Dezimalen)?
3. Verwerfen Sie die H0?

# Lösung

Wir fassen die gegebenen Informationen zusammen:

```r
mue = 16.28  # mue laut H0
xquer = 17.29
sdpop = 3
n = 36
```


Als erstes berechnen wir den SE, den wir im nächsten Schritt für den z-Wert benötigen:


```r
se = sdpop / sqrt(n)
se
```

```
## [1] 0.5
```


Wir berechnen den z-Wert:

```r
z = (xquer - mue) / se
z
```

```
## [1] 2.02
```

Der z-Wert ist: 2.02.

Und berechnen den p-Wert für `z`:


```r
p = 1 - pnorm(z)
```


... gerundet auf 2 Dezimalen:


```r
p = round(p, 2)
p
```

```
## [1] 0.02
```


Der p-Wert beträgt: 0.02.

Wenn p < 5% (.05) ist, verwerfen wir die H0; wir prüfen also als letzten Schritt, ob diese Bedingung erfüllt ist.


```r
p < .05
```

```
## [1] TRUE
```

Ja, wir verwerfen die H0 und nehmen die H1 an: Der mittlere Mietpreis in München ist höher als 16.28€.
