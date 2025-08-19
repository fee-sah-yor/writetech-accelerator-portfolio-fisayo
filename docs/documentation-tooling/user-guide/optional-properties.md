---
sidebar_position: 3
---

# Optional Properties

React Native Onboarding Swiper provides several optional props to help you customize the look, feel, and behavior of your onboarding flow.  

---

## 🎛️ Button Controls

| Prop         | Type                      | Default   | Description |
|--------------|---------------------------|-----------|-------------|
| `nextLabel`  | `string` \| `ReactNode`   | `"Next"`  | Custom label or component for the **Next** button. |
| `showNext`   | `boolean`                 | `true`    | Controls the visibility of the **Next** button. |
| `skipLabel`  | `string` \| `ReactNode`   | `"Skip"`  | Custom label or component for the **Skip** button. |
| `showSkip`   | `boolean`                 | `true`    | Controls the visibility of the **Skip** button. |
| `onSkip`     | `function`                | —         | Callback fired when the user presses **Skip**. |
| `skipToPage` | `number`                  | —         | Navigate directly to a specific page on **Skip**. If provided, `onSkip` is ignored. Example: `skipToPage={2}` |
| `onDone`     | `function`                | —         | Callback fired after the onboarding is completed. |
| `showDone`   | `boolean`                 | `true`    | Controls the visibility of the **Done** button. |

---

## ⚙️ General Configuration

| Prop                       | Type      | Default       | Description |
|----------------------------|-----------|---------------|-------------|
| `bottomBarHeight`          | `number`  | `60`          | Height of the bottom bar. |
| `bottomBarColor`           | `string`  | `"transparent"` | Background color of the bottom bar. |
| `bottomBarHighlight`       | `boolean` | `true`        | Whether the bottom bar should be highlighted. |
| `controlStatusBar`         | `boolean` | `true`        | Syncs the status bar color with the background color of each page. |
| `showPagination`           | `boolean` | `true`        | Controls the visibility of the bottom pagination dots. |
| `flatlistProps`            | `object`  | —             | Additional props passed to the underlying `FlatList`. |
| `transitionAnimationDuration` | `number` | `500`        | Duration (in ms) of the background color transition between pages. |
| `allowFontScalingText`     | `boolean` | `true`        | Enables/disables font scaling for text elements. |
| `allowFontScalingButtons`  | `boolean` | `true`        | Enables/disables font scaling for button labels. |
| `pageIndexCallback`        | `function`| —             | Receives the current page index on change. Example: `pageIndexCallback={(i) => console.log(i)}` |

---

## 🎨 Default Page Styles

| Prop                  | Type     | Description |
|-----------------------|----------|-------------|
| `containerStyles`     | `object` | Override the default container styles. |
| `imageContainerStyles`| `object` | Override the image container styles (default `paddingBottom: 60`). |
| `titleStyles`         | `object` | Override the default title styles. |
| `subTitleStyles`      | `object` | Override the default subtitle styles. |

---

## 🖌️ Per-Page Style Overrides

For **per-page customization**, you can pass style props inside the `pages` array and override the default page styles.  

| Prop            | Type     | Description                                      |
| --------------- | -------- | ------------------------------------------------ |
| `titleStyles`   | `object` | Modify the style of a specific page’s title.     |
| `subTitleStyles`| `object` | Modify the style of a specific page’s subtitle.  |

Example:

```tsx
const pages = [
  {
    backgroundColor: '#fff',
    image: <Image source={require('./assets/page1.png')} />,
    title: 'Welcome',
    subtitle: 'This is your first step!',
    titleStyles: { color: 'blue' },      // Page-specific title style
    subTitleStyles: { fontSize: 14 },    // Page-specific subtitle style
  },
];
```