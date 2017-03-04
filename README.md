# hyper-pane
Extension for Hyper.app to enhance pane navigation. Navigate through panes with arrows, jump directly to a specific pane with digit or change focus on mouse hover.

![hyper-pane](https://cloud.githubusercontent.com/assets/4137761/22717106/844a9c5c-ed99-11e6-8e88-8c71a8cbbd5a.gif)

Inspired by https://github.com/iamstarkov/hyper-panes-iterm2-hotkeys

## Install

To install, edit `~/.hyper.js` and add `"hyper-pane"` to `plugins`:

```
plugins: [
  "hyper-pane",
],
```

## Configuration

### Default configuration:
``` js
module.exports = {
  config: {
    // other configs...
    paneNavigation: {
      debug: false,
      hotkeys: {
        navigation: {
          up: 'ctrl+alt+up',
          down: 'ctrl+alt+down',
          left: 'ctrl+alt+left',
          right: 'ctrl+alt+right'
        },
        jump_prefix: 'ctrl+alt', // completed with 1-9 digits
        permutation_modifier: 'shift', // Added to jump and navigation hotkeys for pane permutation
      },
      showIndicators: true, // Show pane number
      indicatorPrefix: '^⌥', // Will be completed with pane number
      indicatorStyle: { // Added to indicator <div>
        position: 'absolute',
        top: 0,
        left: 0,
        fontSize: '10px'
      },
      focusOnMouseHover: false
    }
  }
  //...
};
```
### Supported keys
Supported keys are the same than for [Mousetrap](https://craig.is/killing/mice).

For modifier keys you can use `shift`, `ctrl`, `alt`, or `meta`. You can substitute `option` for `alt` and `command` for `meta`.

Other special keys are `backspace`, `tab`, `enter`, `return`, `capslock`, `esc`, `escape`, `space`, `pageup`, `pagedown`, `end`, `home`, `left`, `up`, `right`, `down`, `ins`, `del`, and `plus`.

Any other key you should be able to reference by name like `a`, `/`, `$`, `*`, or `=`.  

## Usage
### Navigation with arrows

Use `ctrl+alt+<Up,Down,Left,Right>` (or your configured hotkeys) to navigate to a neighbor pane.

### Jump with digit

Use `ctrl+alt+<1-9>` (or your configured hotkeys) to jump directly to a numbered pane.
Panes are ordered "first child descendent" and `9` is reserved to the last pane.

Hotkey indicators are displayed on top left corner of each pane from 2 panes opened.
You can change its content, its style or hide them completly.

### Pane permutation

Adding `shift` key (or your configured key) to previous hotkeys cause a pane switching.

### Focus on mouse hover

Set `config.paneNavigation.focusOnMouseHover` to `true` and focus will change when mouse cursor enters into an another pane.

