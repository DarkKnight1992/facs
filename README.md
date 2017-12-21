# facs - free angular component solution

I'm not looking for contributors on this repository at the moment. (I make the thorough design first)
The first commits can be expected from end of January.

##### Purpose
The aim of this repository not to recreate angular material or ionic, just to create some flexible angular components, which are just working on ios, safari, android, firefox and chrome. (IE won't be supported)

##### Reason
Most of the framework has tons of components, thus the component system is quite complex.

Angular material might have some basic and "high quality" ones, but i had to use ionic because some component does not exist. Ionic has been created, when angular just started to come up, and whatever plugin i used, was very buggy.
I saw that Ionic team is just messing around with the styles, and customize them for every browser.
I need to note also the fact that box-shadow with animation is killing the safari, and making black squares on the screen,
what ionic team used so frequently.

1) To make components which resizes themself automatically, when orientation or window size has been changed.
2) Just use styles which has been handled in the same ways in every browser, instead of customizing for different browser.
3) Create flexible components, instead of creating hundreds.
4) create components which can be very easily modified. (for example ionic components have got 9-10 public method parameters usually, which is very bad, and blocks me to use it - it should be private orpublic with less parameters)
5) components can be configured based on data coming from server. (you just need to implement the interface)
6) create a component library instead of checking hundreds of node repositories. (my experience is, that many has got lots of bugs - many times i have recreated the functionality)
7) post components, which anyway works in a live system also.
8) reduce the number of scss parameters
9) components will be based on angular 5.
10) Eliminate the need of chaining event emitters. (sub components inside a container might need to talk outside)

##### What flexible components mean?
For example header/footer/card etc. is not the components which are really usefull, i would rather focus to create a flexible table. The only component which was working in ionic without hacking was the ion-grid.

Many times you have customized components:

I would focus on the ease of the positioning. If it's easy and works as expected, you can create the "item/header/footer". (with a div table you can create many of them)

As ionic toggle was the only one which i was not able to fix for mac os, will be the first one.

##### Toggle features (I have recreated the ionic one, i might not finish this list at the moment)
1) You can add one title, two titles (range for example) and more titles.
2) Instead of saving boolean value, it will save number.
3) You can add more knobs, but there wouldn't be fancy ballons.
(my experience is the most efficient way, if you place the current value above)
4) Knobs will be svg, instead of some fancy "content", which are not supported by different browsers. (my experience is that the svg performs very well on mobile devices also) - you won't place hundreds of svg to the screen.
5) I was not able to figure out in the case of ionic toggle, why the box shadowing sometimes works sometimes not.
With buttons it definitely works, with fancy "content" tag, it won't.
6) Automatically resizes itself if it's necessary.

##### Expected components
1) Tab - it will be a container only (in addition very likely can parse url later on similar to deep linking). Buttons will be outside as a menu items. (there can be button rows vertically and horisontally, but the items can be  grabbed as a structural directive - no hard coded images inside the component) - popupover is a special tab with positioning capability.
2) Virtual scroll - it will handle image lazy loading automatically, and can work with different heights of item.
I'm pretty sure that i can produce a more faster (lag free on mobile devices) Virtual scroll than the ionic one.
You can pass default image while the items are rendering, as an argument.
3) frame - you can position items around something, or just create a "fab" icon. ( for example Ionic hasn't any style to position fab buttons vertically - you need to manipulate to add a new button at the top of the other one)
Why the frame is not a table? There can be holes in it, and it should be transparent also. Layers below should remain clickable. I have also experienced, that i was able to place more items into the screen using frame, than create a vertical "item" list. I had 20-30% more room. Don't be confused with the HTML frames, as it's a totally different thing! (my frame is div based)
4) image uploader (it will be an editor also - rotate, scale etc. - the code is not production ready, but it's created already)
5) calendar - (i have created a calendar component which i have rewritten 3 times, but i found out the most efficient one on mobile - i haven't seen similar one. It's partially based on ionic components, which is not working under Mac OS - the aim is to recreate the ionic part in more simpler way)

I have experienced that in the case of ionic to open 3-4 popup at the top of each other, mobile won't render correctly.
Ionic Virtual scroll is too complex on code level

I'm very confident that i'm able to achieve these goals. When jquery was the popular framework, i have recreated plugins which were 10 times faster, than the original one. I'm not confident that to use ionic component i can make that kind of improvements. (in the last year, i would have rewritten all the ionic components instead of using it - i came to a position that i just had to fix and make workarounds on all the styles related to ionic components - my intention was not to customize, just make it working, without erroneous extra paddings, margins etc., and it's swallowed my development time to let me focus on my real tasks)
