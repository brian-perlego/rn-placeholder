Display some placeholder stuff before rendering your text or media content in React Native.

------
<p align="center">
<img src="https://img15.hostingpics.net/pics/581590skeletonloader.gif"/>
</p>

------

# Usage

```
rnpm install rn-placeholder
```

In your code :
```javascript
import Placeholder from 'rn-placeholder';

/*...*/
render() {
    return (
      <View>
        <Placeholder.ImageContent
          size={60}
          animate="fade"
          lineNumber={4}
          lineSpacing={5}
          lastLineWidth="30%"
          onReady={this.state.isReady}
        >
          <Text>Placeholder has finished :D</Text>
        </Placeholder.ImageContent>
      </View>
    );
  }
/*...*/
```

When the value of `this.state.isReady` changes to something *existing*, the `<Text>` component will be rendered

# Components

The project currently supports 4 different placeholder components.

## Line

Display a simple line on the screen.

#### Props available

- `textSize: String`: Text size of the Line
- `color: String`: Color of the line
- `width: String`: Width of the line, percentage available

## Media

Display a shape that represent a media placeholder

#### Props available

- `size: Number`: The size of the media shape (default: `40`)
- `hasRadius: Boolean`: Is the shape rounded or not ? (default: `false`)
- `color: String`: Color of the media shape (default: `#efefef`)

## Paragraph

Display a set of lines called a Paragraph

#### Props available

- `lineNumber: Number`: Number of line to display (mandatory)
- `textSize: Number`: Text size of a single Line (default: `12`)
- `lineSpacing: Number`: Space between the lines (default: `12`)
- `color: String`: Color of the lines (default: `#efefef`)
- `width: String`: Width of the lines (default: `100%`)
- `lastLineWidth: String`: Custom width of the last line (default: `100%`)
- `firstLineWidth: String`: Custom width of the first line (default: `100%`)

## ImageContent

Display a Media on the left / right part of a Paragraph

#### Props available

- `animate: String`: Animation to start when placeholder is displayed (default: `null`)
- `position: String`: The position of the Media (left / right) (default: `left`)
- `hasRadius: Boolean`: Is the shape of the media rounded or not ? (default: `false`)
- `lineNumber: Number`: Number of line to display (mandatory)
- `textSize: Number`: Text size of a single Line (default: `12`)
- `lineSpacing: Number`: Space between the lines (default: `12`)
- `color: String`: Color of the lines (default: `#efefef`)
- `width: String`: Width of the lines (default: `100%`)
- `lastLineWidth: String`: Custom width of the last line (default: `100%`)
- `firstLineWidth: String`: Custom width of the first line (default: `100%`)

# Custom components

You can create your own placeholder component based on your own ones. Based on that, we're exposing a `Placeholder.connect` function that returns a new `ComponentContainer`.

This container allows you to use the `onReady` props that will automatically display the placeholder children when its value is true. It also gives you access to the `animate` props that works just as described before, and so, you can take advent from the prebuilt animations of this project.

```javascript

import { CustomPlaceholder } from '../somewhere';
import Placeholder from 'rn-placeholder';

const CustomPlaceholderContainer = Placeholder.connect(CustomPlaceholder);

/* ... */
return (
  <CustomPlaceholderContainer onReady={this.state.isReady} animate="fade">
    <Text>Hey guys !</Text>
  </CustomPlaceholderContainer>
)
/* ... */
```
