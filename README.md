# PostCSS Bem [![Build Status][ci-img]][ci]

[PostCSS] plugin implementing BEM as at-rules.Forked from [saladcss-bem](https://github.com/saladcss/saladcss-bem.git).

[PostCSS]: https://github.com/postcss/postcss
[ci-img]:  https://travis-ci.org/ileri/postcss-bem.svg
[ci]:      https://travis-ci.org/ileri/postcss-bem

```css
@utility utilityName {
    color: green;
}

@utility utilityName small {
    color: blue;
}

@component ComponentName {
    color: cyan;

    @modifier modifierName {
        color: yellow;
    }

    @descendent descendentName {
        color: navy;
    }

    @when stateName {
        color: crimson;
    }
}

@component-namespace nmsp {
    @component ComponentName {
        color: red;
    }
}
```

```css
.u-utilityName {
    color: green;
}

.u-sm-utilityName {
    color: blue;
}

.ComponentName {
    color: cyan;
}

.ComponentName--modifierName {
    color: yellow;
}

.ComponentName-descendentName {
    color: navy;
}

.ComponentName.is-stateName {
    color: crimson;
}

.nmsp-ComponentName {
    color: red;
}
```

**With shortcuts**
```css
@b nav { /* b is for block */
    @e item { /* e is for element */
        display: inline-block;
    }
    @m placement_header {
        background-color: red;
    }
}
```

```css
.nav {}
.nav__item {
    display: inline-block
}
.nav_placement_header {
    background-color: red
}
```

## Install

```bash
yarn add postcss-plugin-bem-atrule -D
```
or

```bash
npm i postcss-plugin-bem-atrule -D
```

## Usage

```js
postcss([ require('postcss-bem')({
    defaultNamespace: undefined, // default namespace to use, none by default
    style: 'suit', // suit or bem, suit by default,
    separators: {
        descendent: '__' // overwrite any default separator for chosen style
    },
    shortcuts: {
        utility: 'util' //override at-rule name
    }
}) ])
```

See [PostCSS] docs for examples for your environment.
