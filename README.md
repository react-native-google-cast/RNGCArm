# RNGC Arm Example

> This is an example of configuring https://github.com/react-native-google-cast/react-native-google-cast to build on an Arm (M1/M2) Mac.

This example was created using the following steps:

1. `npx react-native init RNGCArm`
2. `cd RNGCArm`
3. `yarn add react-native-google-cast`
4. Create `react-native.config.js`:
   ```js
   module.exports = {
     dependencies: {
       'react-native-google-cast': {
         platforms: {
           // disable autolinking because we specify a variant in Podfile
           ios: null,
         },
       },
     },
   };
   ```
5. Add to `ios/Podfile`:
   ```rb
   pod 'react-native-google-cast/NoBluetoothArm', path: '../node_modules/react-native-google-cast/'
   ```
6. `cd ios && pod install`
7. [Setup](https://react-native-google-cast.github.io/docs/getting-started/setup)
