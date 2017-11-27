# facs
free angular component solution

I'm not looking for contributors on this repository at the moment. (I make the thorough design first)

##### Purpose
The aim of this repository not to recreate angular material or ionic, just to create some flexible angular components, which are just working on ios, safari, android, firefox and chrome. (IE won't be supported)

##### Reason
Most of the framework has tons of components, thus it makes the component system quite complex.

Angular material has some basic, and they might be "high quality", but i had to use ionic because some components does not exist. Ionic has been created, when angular just started to come up, and whatever plugin i used, was very buggy.
I saw that Ionic team is just messing around with the styles, and cusmoze them with every browser.

1, To make components which resizes themself automatically, when orientation or window size has been changed.
2, Just use styles which has been handled in the same ways in every browser, instead of customizing for different browser.
3, Create flexible components, instead of creating hundreds.
4, create components which can be very easily modify. (Ionic tab has 9-10 constructor parameter for example, which is very bad)
5, components can be configured based on data coming from server. (you just need to implement the interface)
6, create a component library instead of checking hundreds of node repositories. (my experience is, that many has got lots of bugs - many times i have recreated the functionality)
7, post components, which anyway works in a life system also.

##### What flexible components mean?
For example header/footer/card etc. is not the components which are really usefull, i would rather focus to create a flexible table. The only component which was working in ionic without hacking was the ion-grid.

Many times you have customized components:

I would focus on the ease of the positioning. If it's easy and works as expected, than you can create the "item/header/footer". (with a div table you can create many of them)

As ionic toggle was the only one which i was not able to fix for mac os, will be the first one.

##### Toggle features:
1, You can add one title, two title (range for example) and more title.
2, Instead of saving boolean value, it will save number.
3, You can add more knobs, but there wouldn't be fancy ballons.
(my experience is the most efficient way, if you place the current value above)
4, Knobs will be svg, instead of some fancy "content", which not supported by different browsers. (my experience is that thesvg performs very well on mobile devices also) - you won't place hundreds of svg to the screen.
5, I was not able to figure out in the case of ionic toggle, why the box shadowing sometimes works sometimes not.
With buttons it definitely works, with fancy "content" tag, it won't.
6, Automatically resizes itself if it's necessary.

I will create the Tab (wich will be a menu also, you can add/remove tabs dinamically by drag and drop)/Virtual scroll/button frame/popup (which will be a popover also, will be movable on the screen)/image uploader (it will be an editor also - rotate, scale etc.)

I have experienced in the case of ionic to open 3-4 popup at each other, mobile won't render correctly.
Virtual scroll is too complex in ionic side
