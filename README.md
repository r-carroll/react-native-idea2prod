## React Native: From idea to production
This is the companion guide for the talk "Building and publishing native, cross-platform mobile app from the ground up"

### Idea
Remember, it all starts with an idea. React Native and Expo are great technologies, but they are just tools in the engineer's toolbox to bring outstanding ideas to life. 
You probably don't want to develop another to-do list app; what are your interests? What are you passionate about? What is something small that is missing from your daily life?
As you find inspiration throughout your day, write those ideas down and keep track of them. You are much more likely to carry a project to its completion, and thus learn new tech along the way,
if you are passionate about the idea you are bringing to life. 

### The state of mobile app dev
Here are some fun statistics. Remeber, thousands of new apps are launched every week, what will make yours stand out?
* [Total devices](https://www.statista.com/statistics/245501/multiple-mobile-device-ownership-worldwide/)
* [App store downloads](https://www.statista.com/statistics/271644/worldwide-free-and-paid-mobile-app-store-downloads/)
* [Revenue](https://www.statista.com/outlook/amo/app/worldwide)

![image](https://github.com/user-attachments/assets/959f1c02-d007-4b44-9b44-53fc59a571a2)

### Approaches
In the talk I propose considering cross-platform as your way to develop, but if you are interested in diving deeper into the topic, [check out this article](https://dzone.com/articles/native-vs-hybrid-vs-cross-platform-how-and-what-to).
If you are interested in learning more about React Native vs Flutter, you can [learn more here](https://www.justinkek.com/blog/flutter-vs-react-native/flutter-vs-react-native).

## Developing
### Getting started with Expo
When you're ready to get to the keyboard and start developing, I highly recommend the Expo documentation. So, rather than repeat the great work they have already done, [you should go check them out](https://docs.expo.dev/get-started/create-a-project/)

### Resources
Developing an app from scratch takes a long time, fortunately there are a plethora of libraries and frameworks to speed up the process so you don't have build everything yourself. When choosing frontend and styling frameworks there is rarely a right or wrong answer, and each developer will have their favorites. Below are some libraries that I have found useful. 
> **Note:** React web and React Native libraries are not necessarily compatible with each other. For example, you probably won't be able to grab an icon library for React web and use it in your React Native project. This is because the HTML markup etc is different between the two and will cause strange errors when your app tries to render the view. 

I have included an example `package.json` file in this repo with several of these libraries for further reference.

#### Graphics
* [React Native Skia](https://shopify.github.io/react-native-skia/docs/getting-started/installation)
* [Lottie](https://docs.expo.dev/versions/latest/sdk/lottie/)
* [Lottie Animations](https://creattie.com/blog/best-free-lottie-animation-websites)

#### UI/UX
* [React Native Elements](https://reactnativeelements.com/docs)


### Ads and monetization
If your monetization involves serving ads on your app, you will need to implement this yourself and use a library like [React Native Google Mobile Ads](https://docs.page/invertase/react-native-google-mobile-ads). Ads are not something you can simply "turn on" using the app store. If you do serve ads, carefully read the privacy section later in this guide as it will impact what you will need to disclose to the app stores. 

## Publishing
Unfortunately, publishing to the app stores is a long and arduous process. I am going to lay out some steps and gotchas that I ran into along the way, but the videos linked below from notJust.dev are excellent resources and the most concise resources I have found covering the process. 
* [Google Play Publishing](https://www.youtube.com/watch?v=oBWBDaqNuws)
* [Apple App Store Publishing](https://youtu.be/LE4Mgkrf7Sk?si=ufya29zUOAde-JOo)

### Screenshots
Grabbing all of the necessary screenshots can take a long time. To make this process easier, there are some [amazing figma templates](https://www.figma.com/community/file/1152456658984601101/ultimate-app-icon-screenshot-generator) where you can paste your own images.

### Accounts
* [Apple Developer](https://developer.apple.com/)
* [Google Play Console](https://play.google.com/console/signup)
* [Google Play Service Account](https://github.com/expo/fyi/blob/main/creating-google-service-account.md)
* [Expo.dev](https://expo.dev/)

### Privacy Declarations
#### Apple
When publishing to the Apple App Store you will be required to declare all of the system components your app utilizes along with the reasons those components are accessed. In this repo you can see the `infoPlist` section of [`app.json`](app.json) for an example set of declarations. You can also find a complete list of [reasons](https://developer.apple.com/documentation/bundleresources/app-privacy-configuration/nsprivacyaccessedapitypes/nsprivacyaccessedapitypereasons) and [types](https://developer.apple.com/documentation/bundleresources/app-privacy-configuration/nsprivacyaccessedapitypes/nsprivacyaccessedapitype) in the Apple Developer documentation. Here is [additional expo documentation](https://docs.expo.dev/guides/permissions/) on documenting permissions in your `app.json`.

If you are incorporating ads into your project, you will need to make sure to install and configure the [Expo TrackingTransparency plugin](https://docs.expo.dev/versions/latest/sdk/tracking-transparency/). If you fail to incorporate these steps properly into your application it is highly likely you will not be able to advance past the review stage. 

#### Android
In addition to the TrackingTransparency plugin from above, Google will have you fill out a data disclosure quiz. If you are using admob, [see this article](https://developers.google.com/admob/android/privacy/play-data-disclosure) for how to fill that out.

#### Review Process
Google's new developer requirements require new developer accounts to undergo a lengthy closed beta before they are able to release apps to production. [See this writeup](https://support.google.com/googleplay/android-developer/answer/14151465?hl=en) for a detailed look into this process. Some developers may be able to bypass this process by registering themselves as a company instead of creating a personal account, but that may come with implications such as making your address public on the app listing. For more information on personal vs organizational accounts, [see Google's writeup here](https://support.google.com/googleplay/android-developer/answer/13628312?sjid=3916598752768348261-NC).


### Privacy Policy
* https://www.privacypolicies.com/ 

### Expo guides
* [Google Play Submission](https://docs.expo.dev/submit/android/)
* [Apple App Store](https://docs.expo.dev/submit/ios/)