---
title: react native start
date: 2018-07-19 07:38:10
tags: [react native]
---

#### react native start
[react native get started](https://facebook.github.io/react-native/docs/getting-started.html)

```bash
npm install -g create-react-native-app
create-react-native-app AwesomeProject
cd AwesomeProject
npm run ios
```

if you already installed ios simulation,your app will be running in ios simulation, 

file structure
```bash
localhost:AwesomeProject wu$ tree -I node_modules
.
├── App.js
├── App.test.js
├── README.md
├── app.json
├── package-lock.json
└── package.json

```

got structure App.js
```jsx
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

export default class App extends React.Component {
  render() {
    return (
      <View style={styles.container}>
        <Text>Open up App.js to start working on your app!</Text>
        <Text>Changes you make will automatically reload.</Text>
        <Text>Shake your phone to open the developer menu.</Text>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

keys:
* App
  * render()
* styles
  * flexbox
   * flex
   * flexDirection
   * justifyContent
   * alignItems
   * more about {% post_link flexbox %}
