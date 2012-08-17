#Roman Efimov's Objective-C Style and Usage Guide

This is an evolving document for my personal style and usage guidelines when writing Objective-C code.

Where possible, these guidelines are derived from the notion that code must be read many times, but written only once, and so places an emphasis on clarity and explicitness over terseness.

##Background

Apple has already written a very good, and widely accepted, coding guide for Objective-C.  This Objective-C guide aims to be a very natural combination of Apple's and my recommendations. So, before reading this guide, please make sure you've read [Apple's Cocoa Coding Guidelines](http://developer.apple.com/documentation/Cocoa/Conceptual/CodingGuidelines/index.html).

##Indent style
K&R C indent style is preferred. When adhering to K&R, each function has its opening brace at the next line on the same indentation level as its header, the statements within the braces are indented, and the closing brace at the end is on the same indentation level as the header of the function at a line of its own. The blocks inside a function, however, have their opening braces at the same line as their respective control statements; closing braces remain in a line of their own, unless followed by an else or while keyword.

###Summary:

__C functions and Objective-C messages__: Opening brace goes on a new line. <br />
__If statement__: Opening brace stays on the same line.<br />
__C-Blocks__: Opening brace goes on a new line, except when the block is a parameter for a C function or ObjC message send... Xcode will auto-format improperly otherwise.

```objective-c
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
    ...
    while (x == y) {
        [Object something];
        [Object somethingelse];

        if (someError) {
            /* the curly braces around this code block could be omitted */
            [Object doCorrectSomething];
        } else
            [Object continueAsUsual];
    }

    [Object finalthing];
    ...
    // Override point for customization after application launch.
    self.window.backgroundColor = [UIColor whiteColor];
    [self.window makeKeyAndVisible];
    return YES;
}
````

##White space
Xcode defaults to 4 spaces, so to increase the likelihood of consistency, use 4 spaces.

##Identifier Naming
Stack variables are named using camel-case-first-lower, and should form a noun. Example: `int someVariable = 0;`

The asterisk used for pointer declarations should be prefixed to the variable identifier. Example: `NSString *someHtmlString;`

C functions are named using camel-cased-first-lower, and should form a verb or action.

```objective-c
void doSomething(void)
{
}
```

##Commenting
While comments are highly encouraged for documenting details and reasonings that are not obvious from the code itself, comments should never be considered a replacement for clear code. Before adding a comment, ask yourself if the code itself could be clarified, removing the need for the comment altogether.

Wrong:

```objective-c
int nEntsW; // Number of entities in the world
```

Correct:

```objective-c
int numberOfEntitiesInTheWorld;
```