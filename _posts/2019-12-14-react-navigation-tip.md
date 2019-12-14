---
layout: post
title: React Navigation tip!
---

When I started developing multi screen react native applications, I had to deal with a strange interaction: when the user clicked on a navigation button,
the button would **freeze** on 'clicking' state for some time and then the next screen would be transitioned.
After some testing and research, I could get to the following recommendations from the docs.

As this is a simple rule, I will go straight forward: **Render a simpler version of your screen first, then load the most complex one later**

React navigation renders the screen on the background before animating.
If we load our whole beautiful screen with all the data, components, and animations in one shot when the user clicks on a TouchableOpacity,
for example, the navigation will be delayed and the user will see your component freezed.

Rendering first the header and a loading indicator is a simple but effective solution for this problem!
Even if we already have all the data available, we can take advantage of the loading indicator running smoothly while React Native takes care of loading all the components for the second rendering. We can even add an stylish animation for the additional components revealing to justify even more this approach!

Check the following links with a React JS example that illustrate this concept:

[CodePen](https://codesandbox.io/s/react-navigation-tips-8pdjw)

[Repository](https://github.com/renanliberato/react-navigation-tips)
