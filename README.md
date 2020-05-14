# Boiled Page tooltip component

Tooltip SCSS component for Boiled Page frontend framework. It is intended to create tooltips which appear on hover.

## Install

Place `_tooltip.scss` file to `/assets/css/components` directory, and add its path to components block in `assets/css/app.scss` file.

## Usage

### Classes

Class name | Description | Example
---------- | ----------- | -------
`tooltip` | Applies a bottom aligned tooltip. | `<span class="tooltip"></span>`

### Attributes
Attribute name | Description | Example
---------- | ----------- | -------
`data-tooltip` | Sets tooltip content. | `<span class="tooltip" data-tooltip="Tooltip content"></span>`

### Examples

#### Example 1

The following example shows a link with a tooltip.

```html
<span class="tooltip tooltip--top-right" data-tooltip="Earth's highest mountain">
  <a href="#">Moun Everest</a>
</span>
```

### Extension ideas

#### Top aligned tooltip

```scss
/* Tooltip component extensions */
span.tooltip {

  // Top aligned tooltip
  &.tooltip--top {

    &:before, &:after {
      bottom: calc(100% + #{$box-arrow});
      top: auto;
      transform: translate3d(-50%, -0.5rem, 0);
    }

    &:before {
      border-width:($box-padding * 0.5) ($box-padding * 0.5) 0;
      margin-bottom: ($box-padding * -0.5);
      margin-top: 0;
    }

    body.no-touch &:hover {

      &:after, &:before {
        transform: translate3d(-50%, 0, 0);
      }
    }
  }
}
```

#### Top-left aligned tooltip

```scss
/* Tooltip component extensions */
span.tooltip {

  // Top-left aligned tooltip
  &.tooltip--top-left {

    &:before, &:after {
      bottom: calc(100% + #{$box-arrow});
      top: auto;
    }

    &:before {
      border-width:($box-padding * 0.5) ($box-padding * 0.5) 0;
      margin-bottom: ($box-padding * -0.5);
      margin-top: 0;
      transform: translate3d(-50%, -0.5rem, 0);
    }

    &:after {
      transform: translate3d(($box-padding * -1), -0.5rem, 0);
    }

    body.no-touch &:hover {

      &:before {
        transform: translate3d(-50%, 0, 0);
      }

      &:after {
        transform: translate3d(($box-padding * -1), 0, 0);
      }
    }
  }
}
```

#### Top-right aligned tooltip

```scss
/* Tooltip component extensions */
span.tooltip {

  // Top-right aligned tooltip
  &.tooltip--top-right {

    &:before, &:after {
      bottom: calc(100% + #{$box-arrow});
      left: auto;
      right: 50%;
      top: auto;
    }

    &:before {
      border-width:($box-padding * 0.5) ($box-padding * 0.5) 0;
      margin-bottom: ($box-padding * -0.5);
      margin-top: 0;
      transform: translate3d(50%, -0.5rem, 0);
    }

    &:after {
      transform: translate3d($box-padding, -0.5rem, 0);
    }

    body.no-touch &:hover {

      &:before {
        transform: translate3d(50%, 0, 0);
      }

      &:after {
        transform: translate3d($box-padding, 0, 0);
      }
    }
  }
}
```

#### Left aligned tooltip

```scss
/* Tooltip component extensions */
span.tooltip {

  // Left aligned tooltip
  &.tooltip--left {

    &:before {
      transform: translate3d(-50%, 0.5rem, 0);
    }

    &:after {
      transform: translate3d(($box-padding * -1), 0.5rem, 0);
    }

    body.no-touch &:hover {

      &:before {
        transform: translate3d(-50%, 0, 0);
      }

      &:after {
        transform: translate3d(($box-padding * -1), 0, 0);
      }
    }
  }
}
```

#### Right aligned tooltip

```scss
/* Tooltip component extensions */
span.tooltip {

  // Right aligned tooltip
  &.tooltip--right {

    &:before, &:after {
      left: auto;
      right: 50%;
    }

    &:before {
      transform: translate3d(50%, 0.5rem, 0);
    }

    &:after {
      transform: translate3d($box-padding, 0.5rem, 0);
    }

    body.no-touch &:hover {

      &:before {
        transform: translate3d(50%, 0, 0);
      }

      &:after {
        transform: translate3d($box-padding, 0, 0);
      }
    }
  }
}
```
