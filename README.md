# RNTFLiteExample

This is a plug-and-play example using [react-native-tflite](https://github.com/kaka-lin/react-native-tflite)


# Getting stared

## 1. Clone this repository

```bash
git clone https://github.com/kainolophobia/RNTFLiteExample.git
```

## 2. Install and link dependencies

```bash
npm install
react-native link
```

## 3. Install TensorFlow-experimental

```bash
cd ios
pod install
```

## 4. Build TensorFlow Lite v1.5.1 for iOS

- Clone [Tensorflow](https://github.com/tensorflow/tensorflow)

```bash
git clone https://github.com/tensorflow/tensorflow.git
```

- Checkout v1.5.1

```bash
git fetch --all --tags --prune
git checkout tags/v1.5.1
```

- Follow the documentation to build [here](https://github.com/tensorflow/tensorflow/blob/v1.5.1/tensorflow/contrib/lite/g3doc/ios.md), skipping the last section titled "Using in your own application"

## 5. Link TensorFlow Lite

- Open RNTFLiteExample.xcworkspace instead of RNTFLiteExample.xcodeproj

- In the Xcode project's "Libraries" folder find `RNTFLite.xcodeproj`, then in "Build Settings" modify `TF_ROOT` to fit your `Tensorflow v1.5.1` path

- Add the library at `$(TF_ROOT)/tensorflow/contrib/lite/gen/lib/libtensorflow-lite.a` to your linking build stage

## 7. Run App

```bash
react-native run-ios
```

# Notes

The `.tflite` model and associated labels are hackiliy stored at the project's root and hardcoded in `RNTFLiteView.mm` within the `RNTFLite.xcodeproj` Library.

To add your own model/labels, right-click the `RNTFLiteExample` project and select "Add files to project..."

Make sure to update the associated model/label filepaths in the `RNTFLiteView.mm` file.

# Support

Many thanks to Github user `kaka-lin` for creating this proof-of-concept. This repository summarizes the steps needed to build and add Tensorflow Lite to a React Native project using the `react-native-tflite` package; the main changes involve highlighting a working version of Tensorflow and simplifying the linking steps.


