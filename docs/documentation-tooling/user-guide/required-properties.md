---
sidebar_position: 2
---

# Required Properties

The **Onboarding** component will throw an error if any of these props are missing.  

---

## 📋 Required Props

| Prop              | Type                        | Required | Description |
|-------------------|-----------------------------|----------|-------------|
| `pages`           | `Array<Page>`               | ✅        | An array of onboarding pages. Each page object must include the properties below. |
| `backgroundColor` | `string`                    | ✅        | Background color of the page. The text and pagination dots adapt automatically to ensure readability. |
| `image`           | `ReactNode` (e.g. `<Image/>`) | ✅        | A React Native component (usually an image) displayed at the top of the page. |
| `title`           | `string` \| `ReactNode`     | ✅        | Page title. Can be plain text or a custom React component. |
| `subtitle`        | `string` \| `ReactNode`     | ✅        | Page subtitle. Can be plain text or a custom React component. |

---

## 📝 Example Usage

```tsx
import Onboarding from 'react-native-onboarding-swiper';
import { Image } from 'react-native';

export default function App() {
  return (
    <Onboarding
      pages={[
        {
          backgroundColor: '#fff',
          image: <Image source={require('./assets/page1.png')} />,
          title: 'Welcome',
          subtitle: 'Discover amazing features in our app.',
        },
        {
          backgroundColor: '#fdeb93',
          image: <Image source={require('./assets/page2.png')} />,
          title: 'Stay Connected',
          subtitle: 'Keep in touch with your friends and family.',
        },
        {
          backgroundColor: '#e9bcbe',
          image: <Image source={require('./assets/page3.png')} />,
          title: 'Get Started',
          subtitle: 'Sign up now and enjoy the experience!',
        },
      ]}
    />
  );
}
