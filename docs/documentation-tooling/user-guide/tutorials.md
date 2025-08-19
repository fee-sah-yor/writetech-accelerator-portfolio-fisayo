---
sidebar_position: 1
---

# Tutorial

#### 🚀 Building a Custom Onboarding Slider in React Native

Onboarding screens are often the first interaction a user has with your app — so let’s make them smooth, engaging, and **customized**.  

In this tutorial, we’ll build an **Onboarding Slider** using `react-native-onboarding-swiper`.  
We’ll customize:  
- ✅ Dots (to show active and inactive slides)  
- ✅ A `Skip` button **above the screen** that jumps to the last slide  
- ✅ A `Done` button that replaces `Skip` on the last slide  
- ✅ Navigation to any page you want  

By the end, you’ll have a **working onboarding flow** in a single file.  

---

## 1️⃣ Installation

Please refer to our installation guide to install the library in [two easy steps](http://localhost:3000/docs/documentation-tooling/getting-started#installation)

## 🏗 Step 2 — Basic Setup

Let’s create a new component called OnboardingScreen.js (or .tsx if using TypeScript). For the purpose of this tutorial however, we will be  using TypeScript.
```bash
import React from "react";
import { StyleSheet, Image } from "react-native";
import Onboarding from "react-native-onboarding-swiper";

const OnboardingScreen = ({  }) => {
  return (
    <Onboarding
      pages={[
        {
          backgroundColor: "#fff",
          image: <Image source={require('../assets/images/2.gif')} />,
          title: "Welcome",
          subtitle: "Swipe to discover more!",
        },
        {
          backgroundColor: "#fdeb93",
           image: <Image source={require('../assets/images/1.gif')} />,
          title: "Learn",
          subtitle: "Find out how to use this app.",
        },
        {
          backgroundColor: "#e9bcbe",
           image: <Image source={require('../assets/images/3.gif')} />,
          title: "Get Started",
          subtitle: "Click Done to begin!",
        },
      ]}
    />
  );
};

export default OnboardingScreen;

```

<div style={{ display: "flex", justifyContent: "center" }}>
  <img src="/img/image1.png" alt="tutorial with default dots and buttons" width="300" />
</div>

## 3️⃣ Customizing the Dots

You can also customize the dots to follow your apps theme or style.
Add this custom component:

```bash
const Dots = ({ selected }) => {
  let backgroundColor = selected ? "#000" : "rgba(0, 0, 0, 0.3)";
  return (
    <View
      style={{
        width: 8,
        height: 8,
        marginHorizontal: 3,
        backgroundColor,
        borderRadius: 4,
      }}
    />
  );
};
```

Then pass it to Onboarding:

```bash
<Onboarding
  DotComponent={Dots}
  pages={[ ... ]}
/>
```

<div style={{ display: "flex", justifyContent: "center" }}>
  <img src="/img/image2.png" alt="tutorial with customized dots" width="300" />
</div>

## 4️⃣ Custom Skip & Done Buttons

We’ll make a Skip button above the screen and a Done button on the last slide.

```bash
const Skip = ({ ...props }) => (
  <TouchableOpacity style={styles.skipButton} {...props}>
    <Text style={styles.skipText}>Skip</Text>
  </TouchableOpacity>
);

const Done = ({ ...props }) => (
  <TouchableOpacity style={styles.skipButton} {...props}>
    <Text style={styles.skipText}>Done</Text>
  </TouchableOpacity>
);
```


Update Onboarding to use them:

```bash
<Onboarding
  DotComponent={Dots}
  SkipButtonComponent={Skip}
  DoneButtonComponent={Done}
  onSkip={() => navigation.replace("HomeScreen")}   // 👈 Replace with your screen
  onDone={() => navigation.replace("HomeScreen")}   // 👈 Navigate after done
  pages={[ ... ]}
/>
```

<div style={{ display: "flex", justifyContent: "center" }}>
  <img src="/img/image3.png" alt="tutorial with customized dots" width="300" />
</div>

## Final Full Code

```bash
import React from "react";
import { StyleSheet, Text, View, TouchableOpacity } from "react-native";
import Onboarding from "react-native-onboarding-swiper";

const Dots = ({ selected }) => {
  let backgroundColor = selected ? "#000" : "rgba(0, 0, 0, 0.3)";
  return (
    <View
      style={{
        width: 8,
        height: 8,
        marginHorizontal: 3,
        backgroundColor,
        borderRadius: 4,
      }}
    />
  );
};

const Skip = ({ ...props }) => (
  <TouchableOpacity style={styles.skipButton} {...props}>
    <Text style={styles.skipText}>Skip</Text>
  </TouchableOpacity>
);

const Done = ({ ...props }) => (
  <TouchableOpacity style={styles.skipButton} {...props}>
    <Text style={styles.skipText}>Done</Text>
  </TouchableOpacity>
);

const OnboardingScreen = ({ navigation }) => {
  return (
    <Onboarding
      DotComponent={Dots}
      SkipButtonComponent={Skip}
      DoneButtonComponent={Done}
      onSkip={() => navigation.replace("HomeScreen")}
      onDone={() => navigation.replace("HomeScreen")}
      pages={[
        {
          backgroundColor: "#fff",
          image: <View style={styles.imageBox} />,
          title: "Welcome",
          subtitle: "Swipe to discover more!",
        },
        {
          backgroundColor: "#fdeb93",
          image: <View style={styles.imageBox} />,
          title: "Learn",
          subtitle: "Find out how to use this app.",
        },
        {
          backgroundColor: "#e9bcbe",
          image: <View style={styles.imageBox} />,
          title: "Get Started",
          subtitle: "Click Done to begin!",
        },
      ]}
    />
  );
};

export default OnboardingScreen;

const styles = StyleSheet.create({
  imageBox: {
    width: 200,
    height: 200,
    backgroundColor: "#333",
    borderRadius: 20,
  },
  skipButton: {
    position: "absolute",
    top: 40,
    right: 20,
    padding: 10,
  },
  skipText: {
    fontSize: 16,
    color: "#000",
    fontWeight: "bold",
  },
});
```
🎉 Congratulations, You Did It!

Now you have a custom onboarding flow with:
- Styled dots

- A floating Skip button that becomes Done

- Navigation to your next screen
