# React Art: CSS Styling in React

## Overview

In React development, styling can be approached in several ways. This document explores various methods, including Vanilla CSS, Inline Styles, and CSS Modules, and provides a comparative analysis of their pros and cons.

## Vanilla CSS

### Advantages

1. **Decoupled from JSX**: CSS code is separated from JSX code, making it easier to manage styles independently.
2. **Familiar Syntax**: You can write CSS code in the way you are accustomed to.
3. **Separate Development**: CSS can be written by a different developer who needs minimal access to JSX code.

### Disadvantages

1. **CSS Knowledge Required**: A good understanding of CSS is necessary.
2. **Lack of Scoping**: CSS rules are not scoped to components, which can lead to conflicts. For example, the same CSS class name might be used in different components for different purposes.

### Solutions for Scoping

#### Solution 1: Inline Styles

**Advantages**

1. **Quick and Easy**: Simple to add directly to JSX.
2. **Scoped Styling**: Styles only affect the element to which they are applied.
3. **Dynamic Styling**: Conditional styling is straightforward to implement.

**Disadvantages**

1. **CSS Knowledge Required**: Understanding of CSS is still needed.
2. **Individual Styling**: Each element must be styled individually, which can be cumbersome.
3. **Messy Code**: No separation between CSS and JSX code, leading to cluttered components.

#### Solution 2: CSS Modules

CSS Modules offer a way to scope CSS by transforming class names to ensure uniqueness per file. This requires configuration of your build tool.

**Usage**

Rename `header.css` to `header.module.css`, and import it as follows:

```jsx
import classes from './header.module.css';

<p className={classes.paragraph}></p>
```

**Example CSS (header.module.css)**

```css
.paragraph {
    color: red;
}
```

The class name will be transformed into a unique name, e.g., `paragraph -> _paragraph_ajsi123`, to avoid conflicts.

**Disadvantages**

1. **Multiple CSS Files**: May result in many small CSS files throughout the project.

## Styled Components

To use Styles Components in your project, you have to install some packages. To Install these packages, you can do the following:

```jsx
npm install styled-components
```

when its installed locally, you need to restart the dev server.
after doing so, you can import {styled} from 'styled-components' like:

```jsx
import { styled } from 'styled-components'
```

this styled is a javascript object through which we can access different properties with the dot notation. 

now, lets say i choose styled.div
this will create a div as a separate component but a component that will have any styles you want applied to it.

syntax:

```jsx
const ControlContainer = styled.div`
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
`
```
before:
```html
    <div class"control">...</div> 
    <!-- this div has classname control to give it styling -->
```

after:
```html
    <controlContainer></controlContainer>
    <!-- this div will have styling as mentioned above -->
```

this is called tagged template


For more details or to contribute, please contact [20namastesneha@gmail.com](mailto:20namastesneha@gmail.com).
```