# Limbic iOS SDK
Limbic's Stress detection AI for iOS

(insert intro about the SDK over here - what it does etc)

## Installation

### CocoaPods

To integrate Limbic into your Xcode project using [CocoaPods](https://cocoapods.org), add it to your `Podfile`:

```ruby
pod 'Limbic'
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
  
## Notes
Instabug needs access to the microphone and photo library to be able to let users add audio and video attachments. Starting from iOS 10, apps that don’t provide a usage description for those 2 permissions would be rejected when submitted to the App Store.

For your app not to be rejected, you’ll need to add the following key to your app’s info.plist file with text explaining to the user why those permissions are needed:

* `NSHealthShareUsageDescription`

If your app doesn’t already access healthKit, we recommend a line that is similar to:

* "`<app name>` needs access to your health data to present accurate stress level predictions."

**The permission alert for accessing HealthKit will NOT appear unless one of the stress methods is invoked and permissions haven't been given yet.**

```xml
<mxfile userAgent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36" version="8.0.2" editor="www.draw.io" type="device"><diagram id="b7379b5f-7600-eb8e-8f9a-d4733ee47cac" name="Page-1">5VpLc9s2EP41uuSQIQmSko+x6jaZNDOe+ND2iJAwiRokGBCypP76LkTwAYCqaVuUPaoOGmLxWnzf7nIX0gKti91vAlf5N54Stgi8dLdAvyyC4Cry4FsJ9o0g8uJGkAmaNiK/F9zRf4gW6nnZhqakNgZKzpmklSlMeFmSRBoyLATfmsPuOTN3rXBGHMFdgpkr/YOmMm+kq/ZYSv6Z0Cxvd/Y93fMDJw+Z4JtS77cI0P3h03QXuF1Lj69znPLtQIRuFmgtOJfNU7FbE6agbWFr5v16pLfTW5BSTpmANC+PmG1Iq/JBMblvwTgch6gJ/gJdb3MqyV2FE9W7BfZBlsuC6W69HBGS7I7q5HcnBQMivCBS7GGInhCuNDjaeMIr3d72VPgtgPmAhljLsGY/65buEYAHDcI4IFdP40HK9JOyMWglDNc1TUwIyI7KPwfPf8Gz9zFSrRK0UV1e2+j7mm1I6himBRuowjci0aM0fRKLjHTGOI7uAL1oBLxWJgjDkj6aWowhqne45RT068mzuLM5aZTXk4aGaa9jGQEKrIWaIzsLHfjtTj2J8ugduoB1eDTiAcuZPAA5cHwpH/kDOSAiSF2rgLopE0l56QAFR5YmGjAHJq854wIkJS9h5PU9ZcwSYUazUrkUQERAfq0ApBCSP+mOgqap2mYU/p4g7zQMLC0GohEG/BEGbDN9CQPhnDFoapx5qwDS5QAt8i+NIJ1CxxY6XQR51kvUO0sEcU5/zhCydPBY5yR5UCMgEfI+E8xk/pUqsioiCgr2y8v6wyF5O8QZIi83skwKLWim0NI616tiS5fFfPT8pZnJeCv0dAZ0SwQFzRUXA1BPkfoEbxm5wjgwiA3DE+U+oTdb5PJXLv3Aw51uciFznvESs5tearnEuGVEhl1A428i5V5XengjOYj61X/nvDJi33ONwfenW8Nkmqc6VVs0nBpEt0g4P4jIeyWI4ya+DEwT9ye+nCEw4f1gWKUG1Mf3iS1XClZWPfy88fDQaPBif/PfX6pgh5tg7IU0V73tB+8fkC7+ngUQtxz9Tn5uSG1lSw5KF5MgRVZs6BKmAfzhXPmRm8p/o6XKSVMssVq8TOEbsEk2EACNopiRR8IumRfPcovA5WU1Ey8jtxK3Q1/wSq78I1VZZQGEpZdLQ+hFpnvE53OPkasJkwZ8GD6kAXaNcaGQaL4vvbwL/ae9ZDZ63HeHSU8mMIB0wc4RxSb6Y9ces6HvvjvGYtTFcxC3Pyr9Rz45Fwct3e/pMn/pLZ/EY7Z0ErkFx3ciN6JU9WFRSaVnShMwzJgp86srDF1xpp6hqFSbNR2w0bDvcs13GVp0nTH9RG6a4wA99epf38Ho67dX3AocuUZ5k98TI2ShPPVOLbJ/mLyyFjrdnRoaq+C0y/1vi4XIn61YgGb/h4mGr/5PKejmXw==</diagram></mxfile>
```
