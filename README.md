# @expo/pseudo-classes

Component for reacting to pseudo-classes in the browser. Based on the [hoverable element](https://codesandbox.io/s/o9q8vy70l5) by @necolas.

## Installation

```bash
yarn add @expo/pseudo-classes
```

### Usage

Import the library into your JavaScript file:

```js
import { Hoverable, Resizable } from '@expo/pseudo-classes';
```

You can wrap a function or a component.

```tsx
import React, { Component } from 'react';
import { Text, TouchableOpacity, View } from 'react-native';
import { Hoverable } from '@expo/pseudo-classes';

const createLogger = (...msg) => () => {
  console.log(...msg);
};

class App extends Component {
  render() {
    return (
      <View>
        <Hoverable onHoverIn={createLogger('start hover')} onHoverOut={createLogger('end hover')}>
          {isHovered => (
            <TouchableOpacity accessible style={{ backgroundColor: isHovered ? '#333' : '#fff' }}>
              <Text>Welcome to React</Text>}
            </TouchableOpacity>
          )}
        </Hoverable>
      </View>
    );
  }
}
```
