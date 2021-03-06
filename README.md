CRNavigationController
======================

A `UINavigationController` subclass that brings about a more vivid, brighter `UINavigationBar`.

With the release of iOS 7, Apple has brought translucency all throughout the operating system. As developers, we are (in a sense) responsible for utilizing these new libraries to present unity between our apps and the OS. With the introduction of gaussian, translucent navigation bars, we are able to allow for more dynamic context with the views that we are presenting.

However, there's a subtle flaw; much of the color options are rather desaturated. Suppose you wanted a translucent navigation bar that was a slightly light, rich blue. With native classes, you would get this (under a white background):

![Blue UINavigationBar without Layer](http://www.coreyjustinroberts.com/projects/CRNavigationController/blue_no_layer.png)

Not exactly what you'd expect. You could come up with a combination of values for red, green, and blue and still never get the color you wanted. This is because Apple has decided to lower the saturation of the color *by about 40%*. Additionally, it inherits some color from whatever is behind it. As a result, we get this very pale blue color that isn't necessarily what we want.

*Enter this library.*

This library does a simple little addition to the `UINavigationBar`. By adding a layer directly above the navigation bar's background layer, we can enhance the navigation bar's vibrance. This layer takes on the same color that we specify in the navigation bar's `barTintColor`, at 50% opacity. This can be changed, but I've found that this percentage is the best blend of vibrance and translucency. With this library, we get:

![Blue UINavigationBar with Layer](http://www.coreyjustinroberts.com/projects/CRNavigationController/blue_layer.png)

This still doesn't allow us to achieve an absolute color; however, it brings us **many** steps closer in the right direction. 

`UINavigationController` vs. `CRNavigationController`:
==============================================================

Achieving a red `barTintColor`:
----------------------------------

![Red UINavigationBar without Layer](http://www.coreyjustinroberts.com/projects/CRNavigationController/red_no_layer.png)

vs.

![Red UINavigationBar with Layer](http://www.coreyjustinroberts.com/projects/CRNavigationController/red_layer.png)

Achieving a black `barTintColor`:
----------------------------------

![Black UINavigationBar without Layer](http://www.coreyjustinroberts.com/projects/CRNavigationController/black_no_layer.png)

vs.

![Black UINavigationBar with Layer](http://www.coreyjustinroberts.com/projects/CRNavigationController/black_layer.png)

Requirements
------------------------------------------------------------------

- Xcode 5
- iOS 7
- A desire to experiment with colors!

Demonstration
------------------------------------------------------------------

A demo app is available in the repo. Mess with the toggles to change the color of either the `CRNavigationBar` or the `backgroundColor` of the view to understand how much impact a specific color may have on a certain `barTintColor`. RGB values in decimal format are also displayed for your convenience if you decide to use this as a tool to find the perfect color.

Credits, Licensing, and Other What Have You
------------------------------------------------------------------

I can't take all of the credit for this solution. This was a collaborated effort on [Stack Overflow](http://stackoverflow.com/questions/18897485/achieving-bright-vivid-colors-for-an-ios-7-translucent-uinavigationbar), created by me and many others. Feel free to use this library in your projects. Mess with the settings and find what blends work best with your apps! I only ask that you leave boilerplates unchanged and that you mention the use of this library in any apps you decide to ship into the store.

I guess this goes here, too. The infamous MIT License:

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.