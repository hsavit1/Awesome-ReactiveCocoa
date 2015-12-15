
## ReactiveCocoa, Functional Reactive Programming, and MVVM aren't easy to understand (especially for an Object Oriented developer), so here's a few good things to look at (from my experience). Note that most of these are in Objective C (my language of choice when I first started to learn RAC) and are centered around RAC 2.5. Some are in other languages (Haskell, Scala, Erlang) but none are in Swift. By design, I've decided to make a separate list for Swift and RAC 3.0

##### RAC 2.5 Reads

- **[Zweitag FRP Breakdown](https://www.zweitag.de/en/blog/technology/functional-reactive-programming-frp)**: Before you jump into RAC, it's probably a good idea to learn a thing or 2 about what functional programming really is
- **[RXMarbles](https://github.com/staltz/rxmarbles)**: Really cool demonstrations of reactive programming operators in RX
- [**RX Website**](http://reactivex.io/documentation/operators.html): This pretty much gives a visual representation of ALL the reactive operators. Remember, RX came before RAC, and a lot of major RACStream and RACSignal methods have an RX equivalent. For example, flattenMap corresponds to SelectMany (in LINQ talk) or FlatMap in RX talk. Dont forget that an Observable is pretty much a Signal and an Enumerable is pretty much a Sequence
- **[Atomic Object](http://spin.atomicobject.com/?s=reactivecocoa)** Bunch of articles from a really respected iOS development consultant group
- **[Yalantis Reactive Programming Objective-C](https://yalantis.com/blog/reactive-programming-on-objective-c/)**: Some great examples and visuals are abundant 
- [**How I Learned to Write Custom Signals in Reactive Cocoa**](https://yalantis.com/blog/how-i-learned-to-write-custom-signals-in-reactive-cocoa/): RACSignal Tutorial
- **[ifNotApps](http://ifnotapps.com/2013/08/10/reactivecocoa-from-the-ground-floor-part2/)**: Great overall breakdown. Comes with this practice project which has tons of various exmaples **_[RACExample](https://github.com/tLewisII/RACExample)_**
- **[ExpressiveReactiveCocoa](https://github.com/kastiglione/ExpressiveReactiveCocoa)**: Before you do anything RAC related, make sure to give this presentation a peak!
- **[RACDesignPatterns](http://rcdp.io)**: Definitely not the best site in the world, but I thought it was worth a read through. Definitely a conecpt that needs to be expanded on
- **[RAC Performance](https://github.com/ReactiveCocoa/ReactiveCocoa/issues/1503)**: Investigation of RAC performance
- **[RAC + MVVM introduction](http://www.sprynthesis.com/2014/12/06/reactivecocoa-mvvm-introduction/)**: One of the clearest write-ups I've ever seen. Great visuals 
- **[Modern Concurrency: Erlang, Scala, Go, Clojure](http://kachayev.github.io/talks/kharkivpy%230/#/)**: Really good presentation about what makes functional programming awesome in other languages. Let me just try to summarize quickly with some talking points
- - Remember, concurrency is not parallelism! 
- - Also, locks are awful. 
- - "Actor" is a state (Scala) VS. passing state as an argument (Erlang).
- - > "Rough analogy: writing to a file by name (process, Erlang) vs. writing to a file descriptor (channel, Go)." (c) Rob Pike 
- - Why functional programming matters in Clojure: Side-effect free functions and Deterministic functions/calculations
- - There is no silver bullet
 -- Use most natural approach for your technology / OP (there are many STM implementations, but in Clojure it's idiomatic and part of the core)
-- Look deeply into your domain (presenters usually use most convenient case(s) to tell about functionality)
-- Use "unusual" approach but remember that on this way only conventions rule
If you need distributed concurrency - look at actors
- - For Scala developers from 
Jonas Boner
:
Start with deterministic, declarative, immutable core
-- Add indeterminism selectively (actors)
-- Add mutability selectively (STM)
-- Finally: add locks and explicit threads
-- check out these [slides](https://github.com/kachayev/talks/tree/master/kharkivpy%230)
- **[twocentstudios](http://twocentstudios.com/blog/2014/06/08/on-mvvm-and-architecture-questions/)**: a friendly, project based introduction to RAC
- **[RAC TableView Binding](http://blog.scottlogic.com/2014/05/11/reactivecocoa-tableview-binding.html)**: An exploration of using RAC to update the contents of a UITableView
- **[Ray Wenderlich](http://www.raywenderlich.com/62699/reactivecocoa-tutorial-pt1)**: Some people like these
- **[Ash Furrow Video](https://www.youtube.com/watch?v=TlgUWYrQ0sc)**: Great presentation by one of RAC's leading voices
- **[Cocoa Samuri](http://cocoasamurai.blogspot.ca/2013/03/basic-mvvm-with-reactivecocoa.html)**: Introduction that everyone is referring to
- **[Reactive Cookbook](http://reactivecookbook.com/)**: Cookbook for a few reactive cococa things. Comes with this [example](https://github.com/jeroenvloothuis/Reactive-Cookbook)
- **[Bi-directional data bindings with RACChannel](http://spin.atomicobject.com/2015/05/04/bi-directional-data-bindings-reactivecocoa/)**: If you want to really push your knowledge of RAC, this is an interesting read
- [**RAC Changelog**](https://github.com/ReactiveCocoa/ReactiveCocoa/blob/fd533d07b64d40cf79d069584d8cd95158998095/CHANGELOG.md#simpler-two-way-bindings): You've probably already read the RAC documentation (highly recommended). However, you probably haven't read [this](https://github.com/ReactiveCocoa/ReactiveCocoa/blob/fd533d07b64d40cf79d069584d8cd95158998095/CHANGELOG.md#simpler-two-way-bindings)
- [**Reactive Cocoa and Ruby Motion**](http://spin.atomicobject.com/2013/06/18/reactivecocoa-rubymotion/): If you HAVE to use Ruby Motion, you might want to check out this set up guide for getting your RAC code up and running
 

##### RAC 3.0+ Reads







### ReactiveCocoa should transform EVERYTHING when it comes to writing iOS code so here's a bunch of projects that should make your RAC transtion a little bit smoother

##### RAC 2.5 Projects

- **[Functional Reactive Pixels (FRP)](https://github.com/ashfurrow/FunctionalReactivePixels)**: A great project from the zen master Ash Furrow. Featured in his book
- **[ExpressiveReactiveCocoa](https://github.com/kastiglione/ExpressiveReactiveCocoa)**: Before you do anything RAC related, make sure to give this presentation a peak!
- **[RACAction](https://github.com/Automatic/RACAction)**: Make your RACCommands look like Swith and RAC 3.0 's RACAction!
- **[101 RAC Samples](https://github.com/dogwith1eye/101RACSamples)**: 101 different examples of using RAC :) I;m pretty sure that this is inspired by [101 RX Samples](http://rxwiki.wikidot.com/101samples) 
- **[Bizhi](https://github.com/lzyy/bizhi)**: the holy grail of example projects. uses objection + reactivecocoa (my favs) + AFNetworking + UICollectionView
- **[Typhoon + Core Data + RAC](https://github.com/appsquickly/Typhoon-CoreData-RAC-Example)**: The holy grail for those who prefer Typhoon over aObjection
- **[RateStuff](https://github.com/danbennett/RateStuff)**: Another RAC + Typhoon example
- **[Firebase + RACExtensions](https://github.com/joenoon/Firebase-RACExtensions)**: a lib that adds extension abilities to Firebase. I find this ultra awesome for dynamic user interfaces in need of live updates
- **[UIGestureRecognizer-RACExtension](https://github.com/kaiinui/UIGestureRecognizer-RACExtension)**: Adds UIGestureRecognizer extensions to RAC
- **[ReactiveCocoaLayout](https://github.com/ReactiveCocoa/ReactiveCocoaLayout)**: an awesome lib for creating animations with ReactiveCocoa
- **[ReactiveViewModel](https://github.com/ReactiveCocoa/ReactiveViewModel)**: a library that shows, by example, how to use the MVVM design pattern
- **[ReactiveCoreData](https://github.com/apparentsoft/ReactiveCoreData)**: Below is an example of how this lib can be used. ReactiveCocoaLayout brings RAC code to the most obnoxious parts of iOS ibrary (I'm looking at you, autolayout!)
 
            RAC(self.filteredParents) = [[[[Parent findAll]
              where:@"name" contains:filterText options:@"cd"]
              sortBy:@"name"]
              fetchWithTrigger:objectsChanged];
 
- **[CETableViewBinding](https://github.com/ColinEberhardt/CETableViewBinding)**: A library that makes the somewhat overwhleming task of using RAC with UITableViews less obnoxious
- **[Bikes](https://github.com/edc1591/Bikes)**: A great example project for proper use of the MVVM pattern built by some guy over at TimeHop
- **[Reactive+iBeacon](https://github.com/eliperkins/ReactiveBeacon)**: Very Very cool lib that makes your iPhone discoverable in an NFC environment
- **[MMPReactiveCoreLocation](MMPReactiveCoreLocation)**: CoreLocation annoyances made less annoying with RAC
- **[LibExtobj](https://github.com/jspahrsummers/libextobjc)**: This is a library that gives you some cool little additions, most notably @weakify(self) and @strongify(self)
- **[OctoKit](https://github.com/octokit/octokit.objc)**: A massive project undertaking from the makers of RAC. A good project to look at if you need ideas on RAC
- **[Artsy/Eigen](https://github.com/artsy/eigen)**: From one of RAC's biggest supporters, Ash Furrow
- **[*RACCommandExample](https://github.com/olegam/RACCommandExample)**: An incredibly insightful example project that accompanies this blog [post](http://codeblog.shape.dk/blog/2013/12/05/reactivecocoa-essentials-understanding-and-using-raccommand/) 
- **[AFNetworking-RACExtensions](https://github.com/CodaFi/AFNetworking-RACExtensions)**: Incredibly helpful RACifying AFNetworking code! Would be pretty difficult to build by yourself (check out this blog [post](http://codeblog.shape.dk/blog/2013/11/16/wrapping-afnetworking-with-reactivecocoa/) too)
 
        AFHTTPRequestOperationManager *manager = [[AFHTTPRequestOperationManager alloc] initWithBaseURL:url];
        manager.requestSerializer = [AFJSONRequestSerializer serializer];
        manager.responseSerializer = [AFJSONResponseSerializer serializer];
        [[manager rac_GET:path parameters:params] subscribeNext:^(RACTuple *JSONAndHeaders) {
                //Voila, a tuple with (JSON, HTTPResponse)
        }];
        
- **[SKPKeyboardAwareness](https://github.com/shapehq/SHPKeyboardAwareness)**: Aha! Now we really can see some power of RAC. This lib uses it to understand the presence of a keyboard (which is really annoying ususally)
        // shpka_rac_notifyUntilDealloc is our own convenience method that returns
        // a signal with a notification that completes when the receiver deallocates.
        RACSignal *keyboardSignal = [self shpka_rac_notifyUntilDealloc:UIKeyboardWillShowNotification];
 
        // viewSignal is a signal that fires whenever a UITextField or UITextView becomes first responder.
        RACSignal *viewSignal = [RACSignal merge:@[
        [self shpka_rac_notifyUntilDealloc:UITextFieldTextDidBeginEditingNotification],
          [self shpka_rac_notifyUntilDealloc:UITextViewTextDidBeginEditingNotification]]
        ];
        // The two signals above, combined in a ‘zip’, meaning that one of the zipped signals
        // will wait for the other before combinedShowSignal is fired.
        RACSignal *combinedShowSignal = [RACSignal zip:@[viewSignal,keyboardSignal]];
 
- **[MVVM iOS Example](https://github.com/Machx/MVVM-IOS-Example)**: Solid introduction to the MVVM design pattern
- **[ReactiveCocoa-IO](https://github.com/ReactiveCocoa/ReactiveCocoaIO)**: Use RAC for file IO!!
- **[RAC-Parse](https://github.com/kastiglione/Parse-RACExtensions)**: If you're dumb enough to use Parse, then you better use RAC - you're gonna need it!
- **[RAC-Example](https://github.com/tLewisII/RACExample)**: Another example. Nt bad
- **[RAC-Playground](https://github.com/Machx/Reactive-Cocoa-Playground)**: Someone's playground project
- **[Expecta+RAC](https://github.com/kylef/Expecta-ReactiveCocoa)**: LOVE THIS. Expecta is the testing framework that's great for MVVM. It only makes sense to add RAC support!
- **[LLRreactiveMatchers](https://github.com/lawrencelomax/LLReactiveMatchers)**: Just like the one above. LLReactiveMatchers should be able to cover most of the reasons you want to test Signals. One matcher = One Subscription, n Matchers = n Subscriptions. Tests that compose on top of Subjects should use LLSignalTestRecorder and expectations should be made on the recorder.
 
            NSMutableArray *sentValues = [NSMutableArray array];
            NSArray *expected = @[@0, @1, @2];
            BOOL hasCompleted = NO;
                [signal subscribeNext:^(id value) {
            [sentValues addObject:value];
            } completed:^{
            hasCompleted = YES;
            }];
            expect(hasCompleted && [sentValues isEqualToArray:expected]).will.beTruthy();
            
- **[RAC+BLE](https://github.com/indragiek/ReactiveBLE)**: RAC support for Buletooth low energy communication with core bluetooth
- **[Simple Weather](https://github.com/TCLee/ReactiveWeather)**: Awesome test project that uses RAC and Mantle
- **[RAC+RestKit](https://github.com/stefanomondino/SMReactiveRestKit)**: RAC support for RestKit- awesomeness. RestKit is a framework for consuming and modeling RESTful web resources on iOS and OS X
- **[Ash Furrow Func Reactive Demo](https://github.com/ashfurrow/FunctionalReactiveDemo)**: Because ash furrow. A small demonstration of how to use ReactiveCocoa in iOS applications
- **[RAC+Healthkit](https://github.com/kerryknight/ReactiveHealthKit)**: Because it's awesome to get live health updates
- **[RAC+Pull-To-Refresh](https://github.com/iandundas/SimpleReactiveTableViewExample)**: Demonstrates networking, JSON parsing, displaying in a tableView and implementing pull-to-refresh using ReactiveCocoa, also laid out using MVVM pattern
- **[RAC+Accounts Framework](https://github.com/ikesyo/ReactiveAccountStore)**: RACSupport for Accounts
- **[RAC+AlertAction](https://github.com/ashfurrow/RACAlertAction)**: Ash Furrow made it. Pretty useful for this scenario
- **[RAC+Notification](https://github.com/mpurbo/MMPReactiveNotification)**: RAC for push notis
- **[RAC+Reachability](https://github.com/kaiinui/Reachability-RACExtensions)**: Needs work but you get the idea
- **[Loverly](https://github.com/moyunmo/Loverly)**: AFNetworking, ReactiveCocoa+MVVM, Pop
- **[RAC+Evernote](https://github.com/rizumita/Reactive-Evernote-SDK-iOS)**: For the Evernote SDK
- **[RACSnippets](https://github.com/lzyy/RAC-Snippets)**: Various RAC Snippets. This project is really really good. Possibly my favorite RACExample project. It has a whole bunch of different cases in which you might use RAC. These cases are listed below
    - Use 'then' and 'take' 
    - Simple MVVM
    - Notification with RAC
    - UITableView and reloadData
    - Waterfall (with SDWebImage)
    - RAC and RACObserve and map
    - use 'tryMap'
    - Repeat after TimeInterval
    - RACCommand
    - Auto Fetch access token
    - Use TakeUntil with Cell
    - Deal Multiple Errors
 
- **[RAC+PullToRefresh](https://github.com/WilliamZang/ZCWRACPullRefresh)**: Refresh control written in RAC
- **[C-41](https://github.com/ashfurrow/C-41)**: Yet another fantastic Ash Furrow project. This guy seriously knows his stuff. This project is great not only in it's completeness, but also because it is fully tested with Expecta, Specta, and OCMock
- **[Reactive Cocoa Playground](https://github.com/Machx/Reactive-Cocoa-Playground)**: Made by the guy who made that highly quoted MVVM article. Lots of really good examples
- [**RAC Ruby Motion**](https://github.com/kastiglione/RACSignupDemo-RubyMotion): An example project for these "special" developers
- ReactiveCocoaExample: Good prohect that shows how to use RAC with a UISearchBar over a UITableView
 
 
 ##### RAC 3.0+ Projects
 
 
 
 
 
 
 
##### Wow - you might be saying to yourself... "THERE'S SO MANY PROJECTS!" OKAAY. I'LL LIST MY FAVORITE ONES IN ORDER
 
##### RAC 2.5 Example Projects
1. RACSnippets
2. Functional Reactive Pixels (Ash Furrow)
3. C-41 (Ash Furrow)
4. RACExample 
5. 101 RAC Examples
6. Artsy/Eigen (Ash Furrow)
7. Func Reactive Demo (Ash Furrow)
8. RACCommand Example
9. Bizhi
10. Reactive Cocoa Playground 
11. Bikes

##### RAC 3.0+ Example Projects

##### RAC 2.5 +Extensions
1. AFNetworking + RACExtensions
2. Expecta + RAC
3. CETableViewBinding

##### RAC 3.0+ Extensions

