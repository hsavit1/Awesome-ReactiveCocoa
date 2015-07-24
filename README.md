### ReactiveCocoa should transform EVERYTHING when it comes to writing iOS code so here's a bunch of projects that should make your RAC transtion a little bit smoother

- **[ExpressiveReactiveCocoa](https://github.com/kastiglione/ExpressiveReactiveCocoa)**: Before you do anything RAC related, make sure to give this presentation a peak!
- **[RACAction](https://github.com/Automatic/RACAction)**: Make your RACCommands look like Swith and RAC 3.0 's RACAction!
- **[101 RAC Samples](https://github.com/dogwith1eye/101RACSamples)**: 101 different examples of using RAC :)
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
- **[RACSnippets](https://github.com/lzyy/RAC-Snippets)**: Various RAC Snippets
- **[RAC+PullToRefresh](https://github.com/WilliamZang/ZCWRACPullRefresh)**: Refresh control written in RAC
