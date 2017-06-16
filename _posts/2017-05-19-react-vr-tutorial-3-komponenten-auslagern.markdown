---
layout: post
title: "ReactVR PART 3 - Komponenten auslagern"
date: 2017-05-19
description: "Komponenten einfach auslagern"
tags: [Virtual Reality, WebVR, ReactVR]
image: /assets/img/ReactVR/Tut3/reactVR3.jpg
comments: true
---


# **Komponenten auslagern**


Man kann Komponenten in anderen Dateien aulagern! **Wichtig ist dabei, dass der Path richtig referenziert wird!**

## Beispiel:

Ich möchte die Komponente **Rabe** in einer anderen Datei auslagern!

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

## **Schritte**:
##### 1.
Ich erstelle einen Ordner namens **components**, indem ich die Komponente "Rabe" auslagere.

![Hallo](/assets/img/ReactVR/Tut3/components.png)

Als nächstes erstelle ich in **components** die Datei **rabe.js**.



##### 2.
In **rabe.js** steht folgender Code:
{% highlight javascript %}
{% raw %}
import React from 'react';
import {
  asset,
  View,
  Image
} from 'react-vr';

export default class Rabe extends React.Component {
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

{% endraw %}
{% endhighlight %}

Wichtig:  
**export default** muss vor class stehen, denn wir wollen ja erreichen, dass die Komponente exportiert wird.

##### 3.
Zum Schluss importiere ich die Komponente Rabe aus dem Ordner components in **index.vr.js** mit:

**import Rabe from './components/rabe.js';** und verwende sie anschließend :)!

**index.vr.js:**
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

import Rabe from './components/rabe.js';

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

# Ergebnis:
![Ergebnis](/assets/img/ReactVR/Tut2/rabe.jpg)
