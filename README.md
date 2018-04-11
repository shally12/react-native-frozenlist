# React Native FrozenList

A List that just be composited by more ScrollView supports freezing columns, horizontal or vertical scrolling together.


## Example running in iOS (captured by GIPHY CAPTURE)

![enter image description here](https://github.com/danceyoung/react-native-frozenlist/blob/master/screenCapture/screencapture.gif?raw=true)

## View Hierarchy
![enter image description here](https://github.com/danceyoung/react-native-frozenlist/blob/master/screenCapture/viewhierarchy.png?raw=true)

## Running demo env

 - "react": "16.0.0",
 - "react-native": "0.51.0"

## Why using ScrollView
The `FlatList` or `SectionList` does not support the method `scrollTo`, so it does not work well for two List horizotal or vertical scrolling together through pure React-Native code. But `ScrollView` simply renders all child components at a once, so the `FrozenList` does not support render items lazily and has a performance downside.

## Why iOS only
Because `ScrollView` on Andorid supports vertical scrolling only.

## Features

 - ListHeader
 - SectionHeader
 - RenderItem
 - vertical scrolling together
 - horizontal scrolling together

## Installation

cd your project root direction

    $ npm install react-native-frozenlist --save

## Usage

code example
[App.js](https://github.com/danceyoung/react-native-frozenlist/blob/master/App.js)
     

## Props
### leftList
The prop `leftList` will rendering a frozen columns.

    leftList:{
	    listHeader,
	    sectionHeader,
	    renderItem,
	    sections
    }

 - **listHeader**
A element rendered at the top of all items, default is no any style `<View/>`.
	 **Type**:	function
	 **Required**:	No
 - **sectionHeader**
A  element rendered and sticked at the top of each section, default is no any style `<View/>`.  
	 **Type**:	function
	 **Required**:	No
The function will be passed args with the following keys:
	 `section` - the full section object as specified in `sections`
	 `sectionIndex` - section's index within the `sections`
 - **renderItem**
 A element rendered  for every item in every section. You can over-ride on a per-section basis.
	 **Type**:	function
	 **Required**:	Yes
 The function will be passed args with the following keys:
 `section` - the full section object as specified in `sections`
 `sectionIndex` - section's index within the `sections`
 `item` - the item object as specified in this section's `data` key
 `itemIndex` - item's index within this section's `data`
