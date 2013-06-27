---
layout: post
title: "PDF-Dateien mit Ghostscript verkleinern"
description: "Mit einem kleinen Bash-Skript lassen sich schnell viele PDF-Dateien verarbeiten"
category: articles
tags: [Bash, Ghostscript, Notiz, PDF, Terminal]
lang: de
image:
  feature: texture-feature-05.jpg
---

Für das Reduzieren der Dateigröße bei PDF-Dateien bietet sich auf den Unixoiden Ghostscript an. Mit einem kleinen Bash-Skript lassen sich schnell viele PDF-Dateien in einer Stapelverarbeitung verarbeiten. Der Inhalt der Skriptdatei ist simpel:

{% highlight tcsh %}
for i in `ls *.pdf`
do
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dNOPAUSE -dQUIET \
-dBATCH -sOutputFile="$i".pdf "$i"
done
{% endhighlight %}

Nimmt man zusätzlich noch die GhostScript-Option -dPDFSETTINGS=/screen werden die erzeugten Dateien noch kleiner, aber auch ziemlich häßlich…
