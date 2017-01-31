# Microsoft Windows Elements in HTML  

Attach an element to the document:  
```js
document.body.appendChild(yourElement.element);
```

### Classes  
* [`Window`](#window)  
* [`ComboBox`](#combobox)  
* [`Button`](#button)  
* [`CheckBox`](#checkbox)  
* [`ProgressBar`](#progressbar)  
* [`Label`](#label)  

#### Additional files  
* [`Utility`](#utility)  

--

#### Window  
**Constructor:**  
* `Window(options)`:  
  * `options` *(object)*: The options for the creation of the window.  
    Properties: `width`, `height` and `title` (See below), `icon` (The path to a .ico file).  

**Properties:**  
* `moveToFront` *(boolean)*: Moves the window to the front if it's clicked.  
* `x` *(float)*: The x position of the window.  
* `y` *(float)*: The y position of the window.  
* `width` *(float)*: The window's width.  
* `height` *(float)*: The window's height.  
* `title` *(string)*: The window's title.  
* `alwaysInFront` *(boolean)*: The window is always in front of other windows.  

**Functions:**  
* `append(element)`: Appends an element to the window.
  * `element` *(HTMLElement)*: The element to append.

**Example:**  
```js
const app = new Window({
  width: 640,
  height: 360,
  title: 'App Window',
  icon: './app.ico'
});
```

--

#### ComboBox  
**Constructor:**  
* `ComboBox(options)`:
  * `options` *(object)*: The options for the creation of the combo box.  
    Properties: `options`, `x`, `y` and `z` (See below)  
    * `width` *(float)*: The width of the combo box.  
    * `optionHeight` *(float)*: The height of each option.  

**Properties:**  
* `element` *(HTMLElement)*: The HTML element of the instance.  
* `onselect` *(function)*: Event handler that fires when an option is selected. Parameters:  
    * `item` *(string)*: The item that was selected.  
* `options`: *(array)*: The options for the combo box.  
* `x` *(float)*: The x position of the window.  
* `y` *(float)*: The y position of the window.  
* `z` *(float)*: The z-index of the window.  
* `selectedIndex` *(float)*: The index of the selected item in the options array.  

**Functions:**  
* `enable(index)`: Enables the combo box or a specific option.  
  * `index` *(integer, optional)*: If given, enables a single option.  
* `disable(index)`: Disables the combo box or a specific option.  
  * `index` *(integer, optional)*: If given, disables a single option.  
* `toggle(index)`: Toggles the state of the combo box or of a specific option.  
  * `index` *(integer, optional)*: If given, toggles the state of a single option.    
* `push()`: Pushes the current state of the combo box and its options (enabled or disabled).  
* `push()`: Restores the pushed state of the combo box and its options.  

**Example:**  
```js
const dropdownMenu = new ComboBox({
  x: 20,
  y: 20,
  z: 1,
  options: ['Option1', 'Option2']
})
```

--

#### Button  
**Constructor:**  
* `Button(options)`:
  * `options` *(object)*: The options for the creation of the button.  
    Properties: `x` and `y` (See below)  
    * `width` *(float)*: The width of the buttom.  
    * `height` *(float)*: The height of the buttom.  
    * `class` *(string)*: A css class.  

**Properties:**  
* `element` *(HTMLElement)*: The HTML element of the instance.  
* `x` *(float)*: The x position of the button.  
* `y` *(float)*: The y position of the button.  
* `text` *(string)*: The text inside the button.  
* `onclick` *(function)*: Event handler that fires when the button is clicked (no parameters).  

**Functions:**  
* `enable()`: Enables the button.  
* `disable()`: Disables the button.  
* `toggle()`: Toggles the state of the button.    

**Example:**  
```js
const downloadButton = new Button({
  x: 210,
  y: 10,
  width: 180,
  height: 28,
  text: 'Download',
  class: 'download-button'
});
```

--

#### CheckBox  
**Constructor:**  
* `CheckBox(options)`:
  * `options` *(object)*: The options for the creation of the check box.  
    Properties: `text`, `x` and `y` (See below)  
    * `class` *(string)*: A css class.  

**Properties:**  
* `element` *(HTMLElement)*: The HTML element of the instance.  
* `x` *(float)*: The x position of the check box.  
* `y` *(float)*: The y position of the check box.  
* `text` *(string)*: The text inside the check box.  
* `checked` *(string)*: Gets or sets the status of the check box.
* `onchange` *(function)*: Event handler that fires when the state of the check box was changed (no parameters).  

**Functions:**  
* `enable()`: Enables the check box.  
* `disable()`: Disables the check box.  

**Example:**  
```js
const freeCandyCheckBox = new CheckBox({
  x: 10,
  y: 90,
  text: 'Include free Candy',
  class: 'free-candy-check-box'
});
```

--

#### ProgressBar  
**Constructor:**  
* `ProgressBar(options)`:
  * `options` *(object)*: The options for the creation of the check box.  
    Properties: `text`, `max`, `value`, `x`, `y`, `width` and `height` (See below)  

**Properties:**  
* `element` *(HTMLElement)*: The HTML element of the instance.  
* `x` *(float)*: The x position of the progress bar.  
* `y` *(float)*: The y position of the progress bar.  
* `text` *(string)*: The text inside the progress bar.  
* `width` *(float)*: The width of the progress bar.  
* `height` *(float)*: The height of the progress bar.  
* `value` *(float)*: The current value of the progress bar.  
* `max` *(float)*: The maximum value of the progress bar.

**Example:**  
```js
const progress = new ProgressBar({
  x: 210,
  y: 80,
  width: 180,
  height: 30,
  value: (0).toFixed(1),
  max: 100
});
```

--

#### Label  
**Constructor:**  
* `Label(options)`:
  * `options` *(object)*: The options for the creation of the check box.  
    Properties: `text` (See below)  
    * `class` *(string)*: A css class.  
    * `x` *(float)*: The x position of the progress bar.  
    * `y` *(float)*: The y position of the progress bar.  
    * `width` *(float)*: The width of the progress bar.  
    * `height` *(float)*: The height of the progress bar.  

**Properties:**  
* `element` *(HTMLElement)*: The HTML element of the instance.  
* `text` *(string)*: The text inside the progress bar.  

**Example:**  
```js
const textLabel = new Label({
  text: 'Random',
  x: 10,
  y: 100,
  width: 100,
  height: 20,
  class: 'text-label'
})
```

--

#### Utility  
**Classes:**  
* `Vector(x, y)`: A simple vector class. Used for moving a [Window](#window).  

**Functions:**  
* `Object.prototype.define(property, descriptor)`: Same effect as [`Object.defineProperty(obj, prop, descriptor)`](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)

--
Licensed under MIT License. ©Jonas Vanen 2017.  
Design: ©Microsoft Windows  
