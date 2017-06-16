---
layout: post
title: "ReactVR PART 2 - Komponenten und Eigenschaften"
date: 2017-03-16
description: "Was kann man mit Komponenten machen? Das erfährst du hier! :)"
tags: [Virtual Reality, WebVR, ReactVR]
image: /assets/img/ReactVR/Tut2/reactVR2.jpg
comments: true
---

# **ReactVR Tutorial #2 - Komponenten und Eigenschaften**

## Hallo meine geehrten Leser!

In diesem Tutorial geht es um Komponenten und wir setzen beim Code vom ersten Tutorial fort. Ich würde mich freuen, wenn ich Feedback bekommen könnte. Dankeschön!

## Komponente
**React-VR arbeitet mit Komponenten**, wie im ersten Tutorial schon erklärt. Eine React-Komponente ist nichts anderes als eine Klasse, die mit React erstellt wurde.

Hier zwei Illustrationen:
{% highlight javascript %}
  {% raw %}
   var Rabe = React.createClass({

    });
 {% endraw %}
{% endhighlight %}
**ODER ES6 Syntax:**
{% highlight javascript %}
 class Rabe extends React.Component {

 }
{% endhighlight %}

Wie man oben sehen kann, ist die zweite Form eher zu bevorzugen, denn sie ist einfacher von der Syntax her.

Im obigen Code erstellen wir eine Klasse Rabe und wandeln sie in eine React Komponente um. Nun kann man sie Komponente nennen.

Damit die Komponente "Rabe" erst zeigen kann, was sie kann, muss in ihr eine bestimmte Funktion definiert werden - die **render()** Funktion. Sie ist für die Darstellung der Komponente wichtig, denn wir wollen ja einen Raben sehen.

Die **render()** Funktion muss immer mit **return** einen **Container** zurückliefern. Ein Container ist **View** zum Beispiel. Im View ist das Bild des Raben drinnen.

Ein Bild wird mit der vordefinierten Komponente **Image** dargestellt. Um die Komponente **Image** zu verwenden, sollten wir sie importieren:

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
    Image
    } from 'react-vr';
  {% endraw %}
{% endhighlight %}

Dieser müssen wir eine Bildquelle mit **source** übergeben. Die Funktion *asset* greift automatisch auf den Ordner *static_assets* zu, wo das Bild des Raben liegt.
Es ist ein guter Stil auch noch **width** und **height** festzulegen. Außerdem muss die Komponente eine Position in der Welt haben und die wird mit der Eigenschaft **transform** festgelegt. Mit der Eigenschaft **layoutOrigin** wird die linke untere Ecke des Textes auf die Position x = 0.5 und y = 0.5 festgelegt.

{% highlight javascript %}
  {% raw %}
  class Rabe extends React.Component {
    render() {
      return (
        <View>
          <Image source={asset('rabe.jpg') }
          style={{
            width: 1,
            height: 1,
            transform: [{translate: [0,0,-3]}],
            layoutOrigin: [0.5,0.5]
          }}
          />
        </View>
      );
    }
  }
 {% endraw %}
{% endhighlight %}

## Zusammenfassung
Zum Schluss entfernen wir die Text Komponente und fügen die Komponente Rabe ein. Hier der gesamte Code:

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
Image
} from 'react-vr';

class Rabe extends React.Component {
  render() {
    return (
      <View>
        <Image source={asset('rabe.jpg')}
        style={{
          width: 2,
          height: 1,
          transform: [{translate: [0, 0, -3]}],
          layoutOrigin: [0.5,0.5]
        }}/>
      </View>
    );
  }
}

class ReactVR extends React.Component {
render() {
  return (
    <View>
      <Pano source={asset('chess-world.jpg')}/>
      <Rabe />
    </View>
  );
}
};

AppRegistry.registerComponent('ReactVR', () => ReactVR);
{% endraw %}
{% endhighlight %}

## Ergebnis
![Ergebnis](/assets/img/ReactVR/Tut2/rabe.jpg)
