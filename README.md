# Limbic iOS SDK
Limbic's Stress detection AI for iOS

## Installation

### CocoaPods

To integrate Limbic into your Xcode project using [CocoaPods](https://cocoapods.org), add it to your `Podfile`:

For non xcode beta builds:
```ruby
pod 'Limbic', '~> 0.0.25’
```

For xcode beta builds:
```ruby
pod 'Limbic', '~> 0.1.0’
```

Then, run the following command:

```bash
$ pod install
```

## Usage

1. Import Limbic framework header in your app delegate

    ```swift
    // Swift
    import Limbic
    ```
    
    ```objective-c
    // Objective-C
    #import <Limbic/Limbic.h>
    ```

2. Add the following to your app delegate's application:didFinishLaunchingWithOptions: method.
	
	```swift
	// Swift
	Limbic.apiKey = "YOUR_API_KEY"
	```
	```objective-c
	// Objective-C
	```
	Make sure to replace `YOUR_API_KEY` with your application token. Apply for our beta [here](https://sebastiaandevries.typeform.com/to/FGrq19).
	
3. When your ready to show your user's stress levels, first create an instance.
    ```swift
    // Swift
    let limbic = Limbic()
    ```
    
    Then, call the stress function like below.
    ```swift
    // Swift
    limbic.getStressforCurrentUser(startDate: Date(), endDate: Date()) { stress in
        // for information on return values, see below
        print(stress)
    }
    ```
#### Helper functions
```swift
// Swift
limbic.getLastDayStressForCurrentUser { stress in
    print(stress)
}
    
limbic.getLastWeekStressForCurrentUser { stress in
    print(stress)
}
    
limbic.getLastMonthStressForCurrentUser { stress in
    print(stress)
}

limbic.getLastYearStressForCurrentUser { stress in
    print(stress)
}
```

## Return values

```json
{
"1515174614" : {
 "stressIndex" : 0.49430439430,
 "confidence" : 0.02003929329
 }
}
```
    
## Notes
For your app not to be rejected, you’ll need to add the following key to your app’s info.plist file with text explaining to the user why those permissions are needed:

* `NSHealthShareUsageDescription`

If your app doesn’t already access healthKit, we recommend a line that is similar to:

* "`<app name>` needs access to your health data to present accurate stress level predictions."

It's also important that you turn the Healthkit entitlement on in the capabilities page in your project.

**The permission alert for accessing HealthKit will NOT appear unless one of the stress methods is invoked and permissions haven't been given yet.**

Please see down below for a description of a flow chart what happens when you call one of the stress functions:
![alt text](https://i.imgur.com/LWva5XS.png)

### How do I control when Limbic asks for permissions?

We're working on a function that puts you in full control as to when you ask for permissions. For now the best way to ask for permissions is to request of all permissions listed in the flowchart and add them to wherever your app is asking for permissions as well. As shown in the flowchart, Limbic will only ask for permissions if they are not set yet. If the user has accepted or rejected the HealthKit data sharing request, then Limbic can't and won't ask for that again.
