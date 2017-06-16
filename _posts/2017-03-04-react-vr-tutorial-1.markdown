---
layout: post
title: "ReactVR PART 1 - Erster Schritt zur VR-Webseite"
date: 2017-03-04
description: "Eine Einführung ins WebVR für neugierige Virtual Reality Einsteiger"
tags: [Virtual Reality, WebVR, ReactVR]
image: /assets/img/ReactVR/Tut1/reactVRTutorialEinfuerung.jpg
comments: true
---

# **ReactVR - Einführung**

## Hallo meine geehrten Leser!

Dieser Post ist eine Einführung zum Thema ReactVR und kann am Anfang kompliziert wirken :D. Keine Sorge! Ich werde weitere Tutorials schreiben und die einzelnen Sachverhalte besser erläutern.

Ich würde mich freuen, wenn ich Feedback bekommen könnte. Dankeschön!

## Installation
Wenn du ReactVR noch nicht installiert hast, dann gehe auf die
[offizielle Seite](https://facebookincubator.github.io/react-vr/docs/getting-started.html) und folge der Anleitung.

Nachdem du dein Projekt erstellt hast und einen lokalen Server mit **npm start** zum Laufen gebracht hast, können wir loslegen.

## Erklärung

**index.vr.js**:
{% highlight javascript %}
{% raw %}
import React from 'react';
import {
AppRegistry,
asset,
StyleSheet,
Pano,
Text,
View,
} from 'react-vr';

class ReactVR extends React.Component {
render() {
  return (
    <View>
      <Pano source={asset('chess-world.jpg')}/>
      <Text
        style={{
          backgroundColor:'blue',
          padding: 0.02,
          textAlign:'center',
          textAlignVertical:'center',
          fontSize: 0.8,
          layoutOrigin: [0.5, 0.5],
          transform: [{translate: [0, 0, -3]}],
        }}>
        hallo
      </Text>
    </View>
  );
}
};

AppRegistry.registerComponent('ReactVR', () => ReactVR);
{% endraw %}
{% endhighlight %}

ReactVR arbeitet mit Komponenten, die zusammen ein ganzes Programm bilden. Man kann sich eine Komponente als ein Werkzeug vorstellen, die Eigenschaten hat und einen Sinn erfüllt.
Beispielsweise ist **\<Text\>** eine Komponente, die nur für die Ausgabe von Strings(Text) zuständig ist. Die Eigenschaften sind textAlign, backgroundColor, fontSize ...

Mit **import** werden Komponenten importiert. Hier sind einpaar aufgelistet:
+ View - Ist ein Container für Elemente, der visuelle Eigenschaften hat
+ Pano - Ist für das Anzeigen des 360 Grad Bildes zuständig
+ Text - Wie schon oben erwähnt, zur Anzeige von Text

Jede React Komponente muss immer eine **render()** Funktion haben. Warum? Weil *render()* die Komponente visuell darstellt. Damit sie die Komponente darstellen kann, braucht sie einen Container wie **\<View\>**, der Unterkomponenten(Kinder) enthält.

{% highlight javascript %}
{% raw %}
render() {
  return (
    <View>
      <Pano source={asset('chess-world.jpg')}/>
      <Text
        style={{
          backgroundColor:'blue',
          padding: 0.02,
          textAlign:'center',
          textAlignVertical:'center',
          fontSize: 0.8,
          layoutOrigin: [0.5, 0.5],
          transform: [{translate: [0, 0, -3]}],
        }}>
        hallo
      </Text>
    </View>
  );
}
{% endraw %}
{% endhighlight %}

Über AppRegistry braucht man sich am Anfang keine Gedanken zu machen! Sie dient zur Ausführung der Komponente.
Mehr Informationen in der Doku:

[https://facebookincubator.github.io/react-vr/docs/appregistry.html]()

# Action!
Zeit den Code ein bisschen zu verändern :D!

Ändern wir beim Text das "hallo" zu "Hallo VR! :D". Die Hintergrundfarbe vom Text könnten wir grün färben.

{% highlight javascript %}
{% raw %}
render() {
  return (
    <View>
      <Pano source={asset('chess-world.jpg')}/>
      <Text
        style={{
          backgroundColor:'green',
          padding: 0.02,
          textAlign:'center',
          textAlignVertical:'center',
          fontSize: 0.8,
          layoutOrigin: [0.5, 0.5],
          transform: [{translate: [0, 0, -3]}],
        }}>
        Hallo VR! :D
      </Text>
    </View>
  );
}
{% endraw %}
{% endhighlight %}

## Ergebnis
![Ergebnis](/assets/img/ReactVR/Tut1/hallo_vr.jpg)
