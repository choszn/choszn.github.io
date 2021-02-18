---
layout: post
category: code
title: "React Native UI Kitten Guide"
date:   2020-02-09 16:58:41 -0800
tags: [💧, react]
---


## Brand

#### **6 Semantic Colors**

1. Basic
2. Primary
3. Success
4. Info 
5. Warning
6. Danger

Primary and Basic -- main colors shown on default state for components.

#### **11 Shades of Basic Color**

Take lightest shade of background, and move down by picking darker shades.

```json
{
  "color-basic-100": "#FFFFFF",
  "color-basic-200": "#F5F5F5",
  "color-basic-300": "#F5F5F5",
  "color-basic-400": "#D4D4D4",
  "color-basic-500": "#B3B3B3",
  "color-basic-600": "#808080",
  "color-basic-700": "#4A4A4A",
  "color-basic-800": "#383838",
  "color-basic-900": "#292929",
  "color-basic-1000": "#1F1F1F",
  "color-basic-1100": "#141414"
}
```

#### 9 Shades for Semantic Color

Each semantic color has 9 shades, and 6 shades for the same same color iwth transaparency.

```json
{
  "color-primary-100": "#FFECD2",
  "color-primary-200": "#FFD3A6",
  //...
  "color-primary-900": "#7A0C06",

  "color-primary-transparent-100": "rgba(255, 103, 33, 0.08)",
  "color-primary-transparent-200": "rgba(255, 103, 33, 0.16)",
  // ...
  "color-primary-transparent-600": "rgba(255, 103, 33, 0.48)"
}
```

#### 5 Stateful Color Variables for each Semantic Color

```json
{
  "color-primary-default": "$color-primary-500",
  "color-primary-hover": "$color-primary-400",
  "color-primary-focus": "$color-primary-600",
  "color-primary-active": "$color-primary-600",
  "color-primary-disabled": "$color-basic-transparent-300"
}
```



Each semantic color has borders:

``` json
{
  "color-primary-default-border": "$color-primary-default",
  "color-primary-hover-border": "$color-primary-hover",
  "color-primary-focus-border": "$color-primary-700",
  "color-primary-active-border": "$color-primary-active",
  "color-primary-disabled-border": "$color-primary-disabled"
}

```



#### **6 Shades of Transparency**

Take color-basic-600 and transform it to rgba format with adding an alpha channel. Start with 8% transparency and move up with same value. 

Note: Transparent palette is always a `-500` color with an alpha channel. Used for disabled, outlined, and ghost controls. 

```json
{
   "color-basic-transparent-100": "rgba(128, 128, 128, 0.08)",
   "color-basic-transparent-200": "rgba(128, 128, 128, 0.16)",
   "color-basic-transparent-300": "rgba(128, 128, 128, 0.24)",
   "color-basic-transparent-400": "rgba(128, 128, 128, 0.32)",
   "color-basic-transparent-500": "rgba(128, 128, 128, 0.4)",
   "color-basic-transparent-600": "rgba(128, 128, 128, 0.48)"
}
```



#### Text and Icons

Configure extra-test variables to make text visible.

`text-basic-color`:used as default text color

`text-hint-color`: used for placeholders, labels, captions, subtitles, icons in default

`text-disabled-color`: used for controls in disabled state.

```json
{
  "text-basic-color": "$color-basic-400"
  "text-hint-color": "$color-basic-400"
  "text-disabled-color": "$color-basic-400"
}

```

#### Typography

1. Copy `.ttf` into assets directory.
2. Create `react-native.config.js` with the following code:

```js
module.exports = {
  project: {
    ios: {},
    android: {},
  },
  assets: ['./assets'],
};
```

3. Run `npx react-native link` from project root to link fonts. 
4. Create `mapping.json` with the following code

```json
{
  "strict": {
    "text-font-family": "OpenSans-Regular"
  }
}
```

5. Go to `App.js` 

```js
import React from 'react';
import * as eva from '@eva-design/eva';
import { ApplicationProvider, Layout,,Button } from '@ui-kitten/components';
import { default as theme } from './theme.json';
import { default as mapping } from './mapping.json';

export default () => (
  <ApplicationProvider 
    {...eva}
    theme={{ ...eva.dark, ...theme }}
    customMapping={mapping}>
    <Layout style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Button>HOME</Button>
    </Layout>
  </ApplicationProvider>
);
```

6. Reload app and see custom fonts.

#### 13 Text Categories

Each category has `fontSize` `fontWeight` and `fontFamily`

- Headings: h1 -- h6
- Subtitles: s1, s2
- Paragraphs: p1, p2
- Captions: c1, c2
- Label



In `mapping.json` to change text categories across whole app:

```json
{
  "strict": {
    "text-font-family": "OpenSans-Regular",

    "text-heading-1-font-size": 36,
    "text-heading-1-font-weight": "800",
    "text-heading-1-font-family": "OpenSans-Bold",

    // Same for `h2...h6`

    "text-subtitle-1-font-size": 15,
    "text-subtitle-1-font-weight": "600",
    "text-subtitle-1-font-family": "OpenSans-SemiBold",
    // Same for `s2`

    "text-paragraph-1-font-size": 15,
    "text-paragraph-1-font-weight": "400",
    "text-paragraph-1-font-family": "OpenSans-Regular",
    // Same for `p2`

    "text-caption-1-font-size": 12,
    "text-caption-1-font-weight": "400",
    "text-caption-1-font-family": "OpenSans-Regular",
    // Same for `c2`

    "text-label-font-size": 12,
    "text-label-font-weight": "800",
    "text-label-font-family": "OpenSans-Bold"
  }
}
```

#### 4 Levels of Background

```
{
  "background-basic-color-1": "$color-basic-800",
  "background-basic-color-2": "$color-basic-900",
  "background-basic-color-3": "$color-basic-1000",
  "background-basic-color-4": "$color-basic-1100"
}
```

