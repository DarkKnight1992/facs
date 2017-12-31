# facs - free angular component solution

I'm not looking for contributors on this repository at the moment. (I make the thorough design first)
The first commits can be expected from end of January.

##### Purpose
As i have wasted trendemous time digging into the angular and react code base trying to figure out bugs, i'm questining basic things:
1) Is it feasible to introduce java like dependency injection in javascript? To make a code testable in java most of the time it's very hard work to inject everything. Most of the development time has been consumed. In very large system many times it was not economical to mock everything. I think group dependency injection would be better. (create a global variable which is some sort of manager - and with the same name either you populate the real object or the virtual object)
So instead of injecting everything in the constructor, send messages to the global manager at the beggingin of the test.
2) Do we need template system in javascript. (so some parsers, which anyway the responsibility of the browser)
The fact is it's hiding the javascript and adds more complexity of the page, like in the case of angular, but i think react or vue is not different. Can we do a Virtual Dom without introducing a new template language, which is not just hiding javascript, it takes time to create. I don't think so it's necessarily.

The abovementioned problem can be easily solved within a day, instead of team work which last for month, and needs so many performance improvements. In Angular the end result was to profile javascript so frequently that i was not able to focus on my real task.

Are these frameworks really useful? I'm not sure, as many times the size just growing, too many bloatware in it, and does not answer to some basic needs. The configuration cost can be trendemous, and if something is buggy you need to wait, as it's hard to fix.

The only principle i think which does matter, don't manipulate dom directly! I'm using typescript, and define some decorators which is similar how spring is working, but it won't be superflouos, i also attach the UI library, which are available separately in many frameworks. I'm not going to recreate html 5, i just want to achieve some UI, which is hard to create and that's all. I might use deep linking and define some sort of backend to be able to open the page in the previous state, when the user is going there, with all the modification what the page has. (the service worker caching is good, when you are offline, but when you have dynamic data to be updated, it's not the right answer for the problem)

Unfortunatelly you cannot cherry pick from the different javacript framework, so i have decided to cherry pick some advantages, and principles, which does not harm the productiveness in practice. (my components laso appears on my personal life system)

The big advantage of cherry picking that at the end of the day, you have the ui library, but your site is not growing too much. At the moment my unzipped codebase is about 120KB in typescript. (it contains already many things, and has got far better features than the ionic itself, and the css itself is very lightweigtht - at the moment there is no scss templating, as i have no time for it) It does not use hammerjs also, as i found it buggy after the pointer changes- (new feature in modern browsers, which is responsoible tohandle mouse / pen and touch event only with one code)

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

##### Toggle features (I have recreated the ionic one)
1) Instead of saving boolean value, it will save number.
2) You can add at least 2 knobs, but there wouldn't be fancy ballons.
(my experience is the most efficient way, if you place the current value above)
3) Knobs will be div with border-radius: 50%
4) Automatically resizes itself if it's necessary.

##### Expected components
1) Tab - it will be a container only (in addition very likely can parse url later on similar to deep linking). Buttons will be outside as a menu items. (there can be button rows vertically and horizontally, but the items can be  grabbed as a structural directive - no hard coded images inside the component) - popover is a special tab with positioning capability, there is also dockable features. (it does make sense only to split up the screen horizontally by two vertically by three to dock some sort of tabs)
2) Virtual scroll - it will handle image lazy loading automatically, and can work with different heights of item.
I'm pretty sure that i can produce a more faster (lag free on mobile devices) Virtual scroll than the ionic one.
You can pass default image while the items are rendering, as an argument.
3) frame - you can position items around something, or just create a "fab" icon. ( for example Ionic hasn't any style to position fab buttons vertically - you need to manipulate to add a new button at the top of the other one)
Why the frame is not a table? There can be holes in it, and it should be transparent also. Layers below should remain clickable. I have also experienced, that i was able to place more items into the screen using frame, than create a vertical "item" list. I had 20-30% more room. Don't be confused with the HTML frames, as it's a totally different thing! (my frame is div based)
4) image uploader (it will be an editor also - rotate, scale etc. - the code is not production ready, but it has been created already)
5) calendar - (i have created a calendar component which i have rewritten 3 times, but i found out the most efficient one on mobile - i haven't seen similar one. It's partially based on ionic components, which is not working under Mac OS - the aim is to recreate the ionic part in more simpler way)

I have experienced that in the case of ionic to open 3-4 popup at the top of each other, mobile won't render correctly.
Ionic Virtual scroll is too complex on code level

I'm very confident that i'm able to achieve these goals. When jquery was the popular framework, i have recreated plugins which were 10 times faster, than the original one. I'm not confident that to use ionic component i can make that kind of improvements. (in the last year, i would have rewritten all the ionic components instead of using it - i came to a position that i just had to fix and make workarounds on all the styles related to ionic components - my intention was not to customize, just make it working, without erroneous extra paddings, margins etc., and it's swallowed my development time to let me focus on my real tasks)

I already recreated some parts of the RXJS, to be able to send messages directly to UI interface or interfaces. (broadcast)

Whatever i share here will be inspirational, but won't be production ready as i have no time to document and make more flexible than what i needed in my own project.
