# Expo ImagePicker: Handling undefined 'uri' after cancelled selection

This repository demonstrates a common issue and its solution when using Expo's ImagePicker.  The problem occurs when a user cancels the image selection; the returned result has an undefined `uri` property, leading to errors if not handled correctly.

## Problem

The `ImagePicker.launchImageLibraryAsync` function returns a result object. If the user cancels the selection, the `uri` property within this object is undefined.  Attempting to access `uri` directly will result in a `TypeError`. 

## Solution

The solution involves adding a check to verify if the `uri` property exists before attempting to use it. This prevents the error by handling the case where the user cancels the image selection.

## How to reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `expo start`. 
4. Try selecting an image, and then try cancelling the image selection. 

## Additional notes

Always check for null or undefined values when dealing with asynchronous operations and user input to prevent unexpected errors.