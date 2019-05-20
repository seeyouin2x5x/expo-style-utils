# @expo/style-utils

Components for reacting to pseudo-classes and observable styles in React Native.

## Installation

```bash
yarn add @expo/style-utils
```

### Usage

Import the library into your JavaScript file:

```js
import { Hoverable, Resizable } from '@expo/style-utils';
```

You can wrap a function or a component.

```tsx
import React, { Component } from 'react';
import { Text, TouchableOpacity, View } from 'react-native';
import { Hoverable } from '@expo/style-utils';

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

Observe window resize events.

```tsx
return (
  <Resizable>
    {layout => <View style={{ width: layout.width / 2, height: layout.width / 2 }} />}
  </Resizable>
);
```
