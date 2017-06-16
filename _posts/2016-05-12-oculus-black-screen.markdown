---
layout: post
title: "Oculus Rift Black-Screen"
date: 2016-12-05
description: "Ein Fehler des Betriebssystems"
tags: [Virtual Reality, Oculus Rift, Black-Screen]
image: /assets/img/ogDE.jpg
comments: true
---

# **Oculus Rift Black Screen gelöst[SOLVED]**

## **Hallo Community!**


Manche von euch haben das gleiche Problem wie ich bezüglich der Oculus Rift CV1: "Linsen anpassen" im Oculus Setup(im Englischen "Adjust your Lenses"). Man kann den Sound auf der Rift hören, aber sieht kein Bild und die Oculus Rift CV1 LED ist orange oder weiß.

Zuerst habe ich diese einfachen Möglichkeiten auf meinem Windows 8.1 probiert, ob sie meinen Fehler beheben würden:

+ Oculus Runtime deinstalliert und neu installiert
+ DisplayPort-HDMI Adapter gekauft(Bei mir hat es sich als Fehlinvestition herausgestellt)
+ HDMI ein- und ausstecken
+ USB Treiber neu installiert
+ NVIDIA Grafiktreiber Treiber für meine GTX 1060 deinstalliert und neu installiert
+ Mainboard Treiber installiert


**aber leider ohne Erfolg.**

Nach unzähligen gescheiterten Versuchen die Oculus Rift zum Laufen zu bringen, kam mir der Einfall, sich mit der Oculus Rift Funktionalität zu beschäftigen und siehe ICH HABE DEN FEHLER GEFUNDEN!


Ich bin so vorgegangen:

1) Geht zum **oculus-runtime** Ordner und wählt den Ordner **oculus-runtime** aus. Der Ordner liegt bei mir auf Computer --> Programme --> Oculus --> Support --> oculus-runtime.

![oculus-runtime](/assets/img/oculus-runtime.jpg)

2) Auf diesem Ordner wird zugegriffen, wenn man sich die Oculus Rift aufsetzt. In diesem Ordner ist eine exe namens DirectDisplayConfig, die für das Starten des Oculus Bildschirmes verantwortlich ist. Startet die DirectDisplayConfig.exe. Es sollte kurzzeitig ein Konsolenfenster erscheinen.

![directdisplayconfig](/assets/img/directdisplayconfig.jpg)

Wenn dieser Fehler auftaucht: **api-ms-win-crt-string-l1-1-0.dll is missing**, dann habt ihr das gleiche Problem wie ich kürzlich.

Dieser Fehler taucht auf, wenn ihr den Windows Treiber **api-ms-win-crt-string-l1-1-0.dll** nicht installiert habt. Normallerweise sollte sich dieser Treiber automatisch mit den Windows Updates auf das Betriebssystem installiert, aber manchmal hat er keine Lust drauf :).

## **Lösung:**

Ladet diesen Treiber von Microsoft herunter:
[https://support.microsoft.com/en-us/kb/2999226](https://support.microsoft.com/en-us/kb/2999226)

Wenn ihr den Treiber heruntergeladen und installiert habt, dann probiert eure Oculus aufzusetzen. Wenn sie funktioniert, dann wünsche ich viel Spaß in der virtuellen Welt :D.

Wenn euch dieser Beitrag geholfen hat, dann teilt diesen weiter. Vielleicht hilft es de Einen oder Anderem.

Ich entschuldige mich für meine sprachlichen Fehler, die in diesem Beitrag auftauchen.


Tags: Adjust your Lenses, Oculus Rift black screen, Oculus Rift orange led, Oculus Rift CV1 drivers, Oculus Rift display driver, Oculus Rift linsen anpassen, Oculus Rift schwarzer Bildschrim,
Oculus Rift kein Bild
