# react-native-bottomsheet

RNBottomSheet is a cross-platform ActionSheet for both Android and iOS. It uses original ActionSheet on iOS and [soarcn BottomSheet](https://github.com/soarcn/BottomSheet) on Android with some minor fixes, such as title and list item margins.

Note: On Android, `message` property is not available. Instead, there's an `dark` option to turn on Dark Mode like so:

```
RNBottomSheet.showBottomSheetWithOptions({
  options: ['Option 1', 'Option 2', 'Option 3'],
  title: 'Demo Bottom Sheet',
  dark: true,
  cancelButtonIndex: 3,
}, (value) => {
  alert(value);
});
```

## Installation

First, install the npm package:
```
npm install --save react-native-bottomsheet
```
Then link the native module, since we are using native bottom sheet on Android:
```
react-native link react-native-bottomsheet
```

## Demo

![Android](https://s17.postimg.org/pjlqnhgz3/android.png "Android")

![iOS](https://s17.postimg.org/cthiae90v/ios.png "iOS")

## Usage

### Import the package
```
import BottomSheet from 'react-native-bottomsheet';
```

### Use it like how you do with ActionSheet.
````
BottomSheet.showBottomSheetWithOptions(options: Object, callback: Function)
BottomSheet.showShareBottomSheetWithOptions(options: Object, failureCallback: Function, successCallback: Function)
````

Example:

```
import BottomSheet from 'react-native-bottom-sheet';
...
BottomSheet.showBottomSheetWithOptions({
  options: ['Option 1', 'Option 2', 'Option 3'],
  title: 'Demo Bottom Sheet',
  dark: true,
  cancelButtonIndex: 3,
}, (value) => {
  alert(value);
});
```

```
BottomSheet.showShareBottomSheetWithOptions({
  url: 'https://google.com',
  subject: 'Share',
  message: 'Simple share',
}, (value) => {
  alert(value);
}, (resultcode, path) => {
  alert(resultcode);
  alert(path);
})
```
