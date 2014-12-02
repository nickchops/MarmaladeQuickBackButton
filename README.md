Marmalade Quick Back Button Helper
==================================

Helper function that adds a back button to a scene of a Marmalade Quick app

The button can be a visual touch button and/or simply

Functions:

**backButtonHelper:add(values)**

- Add the helper. Pass a table of the following values (defaults in brackets):
  - listener - Function to call after button is pressed
  - xCentre - x middle pos
  - yCentre - y middle pos
  - btnWidth (width of btnTexture) - O-screen button width in pixels
  - btnTexture - Texture to use if there is an on screen button
  - pulse (false) - Give the button a shrink/grow pulsing animation when enabled
  - activateOnRelease (true) - Listener is called when user releases finger
  - animatePress (true) - Animate push/release
  - respondToKey (true) - Pressing s3eKeyAbsBSK also causes the button to be pushed
  - deviceKeyOnly (false) - whether to show an on-screen touch button or not:
    - If true, respond to key s3eKeyAbsBask only and show no button on screen
	- If false, always show touch button
	- If a table of platforms don't show the touch button for platforms listed. e.g. deviceKeyOnly={"ANDROID","WINDOWS"} Values should match those for device:getInfo("platform")
	- If "guess", hide keys for Android and Windows Phone (platforms know to always have back keys)
  - drawArrowOnBtn - draw a left-pointing arrow image on the button
  - arrowColor (color.black) - colour of that arrow
  - arrowThickness (2) - thickness of arrow outline
  - enabled - whether button is enabled at start


**backButtonHelper:enable()**

- Enable button

**backButtonHelper:disable()**

- Disable button. Still shown but cannot be touched and wont respond to key press

**backButtonHelper:remove()**

- Destroy the button, remove all listeners and clean up resources

Supporting the device's back key
--------------------------------

If respondToKey is true (default) the helper checks for Marmalade's s3eKeyAbsBSK

You need to set this to point to a real key via your ICF. e.g. to use "Esc"
on Win/Mac and "Back" (e.g. the Android on screen back button) on anything else:

```
[s3e]
KeyAbsBSK = Back
{OS=WINDOWS}
KeyAbsBSK = Esc
{OS=OSX}
KeyAbsBSK = Esc
```

------------------------------------------------------------------------------------------
(C) 2014 Nick Smith.

All code is provided under the MIT license unless stated otherwise:

 Permission is hereby granted, free of charge, to any person obtaining a copy
 of this software and associated documentation files (the "Software"), to deal
 in the Software without restriction, including without limitation the rights
 to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
 copies of the Software, and to permit persons to whom the Software is
 furnished to do so, subject to the following conditions:

 The above copyright notice and this permission notice shall be included in
 all copies or substantial portions of the Software.

 THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
 IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
 FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
 AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
 LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
 OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
 THE SOFTWARE.
