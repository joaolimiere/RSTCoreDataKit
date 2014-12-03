![RSTCoreDataKit banner][bannerLink]

[![license BSD](http://img.shields.io/badge/license-BSD-orange.png)][bsdLink]

## About

CoreData sucks.

## Requirements

* iOS 8.0+
* ARC
* Xcode 6+

## Installation

````ruby
# For latest release in cocoapods
pod 'RSTCoreDataKit'

# Feeling adventurous? Get the latest on develop
pod 'RSTCoreDataKit', :git => 'https://github.com/rosettastone/RSTCoreDataKit.git', :branch => 'develop'
````

## Getting Started

````objective-c
// New school
@import RSTCoreDataKit;

// Old school
#import <RSTCoreDataKit/RSTCoreDataKit.h>
````

### Standing up your stack

````objective-c
// Initialize the Core Data model, this class encapsulates the notion of a .xcdatamodeld file
// The name passed here should be the name of an .xcdatamodeld file
RSTCoreDataModel *model = [[RSTCoreDataModel alloc] initWithName:@"MyModelName"];

// Initialize the stack
RSTCoreDataStack *stack = [[RSTCoreDataStack alloc] initWithStoreURL:model.storeURL
                                                            modelURL:model.modelURL
                                                             options:nil
                                                     concurrencyType:NSMainQueueConcurrencyType];

// Alternatively, use the convenience initializers for common use cases

// Same as above, with some default options
RSTCoreDataStack *defaultStack = [RSTCoreDataStack defaultStackWithStoreURL:model.storeURL modelURL:model.modelURL];

// Create a private queue stack
RSTCoreDataStack *privateStack = [RSTCoreDataStack privateStackWithStoreURL:model.storeURL modelURL:model.modelURL];

// Create an in-memory stack
RSTCoreDataStack *inMemoryStack = [RSTCoreDataStack stackWithInMemoryStoreWithModelURL:model.modelURL];
````

### Unit Testing

`RSTCoreDataKit` has a suite of unit tests included. 


## Documentation

Sweet documentation is [available here][docsLink] via [@CocoaDocs](https://twitter.com/CocoaDocs).

* Apple's [Core Data Programming Guide](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/CoreData/cdProgrammingGuide.html)
* objc.io's [Issue #4: Core Data](http://www.objc.io/issue-4/)

## License

`RSTCoreDataKit` is released under the [BSD 3.0 License][bsdLink]. See `LICENSE` for details.

>**Copyright &copy; 2014 Rosetta Stone.**

[docsLink]:http://cocoadocs.org/docsets/RSTCoreDataKit
[bsdLink]:http://opensource.org/licenses/BSD-3-Clause
[bannerLink]:https://bytebucket.org/livemocha/rstcoredatakit/raw/8b9fa998ebae1972ae3f890525ed033367e1c46f/banner.jpg?token=bf14bd9749c56f42586bd0e41ac9f4a93ce99a0a
