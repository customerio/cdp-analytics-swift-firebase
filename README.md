# Analytics-Swift Firebase

Add Firebase device mode support to your applications via this plugin for [cdp-analytics-swift](https://github.com/customerio/cdp-analytics-swift)

## Adding the dependency

***Note:** the Firebase library itself will be installed as an additional dependency.*

### via Xcode
In the Xcode `File` menu, click `Add Packages`.  You'll see a dialog where you can search for Swift packages.  In the search field, enter the URL to this repo.

https://github.com/customerio/cdp-analytics-swift-firebase

You'll then have the option to pin to a version, or specific branch, as well as which project in your workspace to add it to.  Once you've made your selections, click the `Add Package` button.  

### via Package.swift

Open your Package.swift file and add the following to your the `dependencies` section:

```
        .package(
            url: "https://github.com/customerio/cdp-analytics-swift-firebase",
            .exact("1.3.6+cio.1")
        )
```


*Note the Firebase library itself will be installed as an additional dependency.*


## Using the Plugin in your App

Open the file where you setup and configure the Analytics-Swift library.  Add this plugin to the list of imports.

```
import CioDataPipelines
import SegmentFirebase // <-- Add this line
```

Just under your Analytics-Swift library setup, call `analytics.add(plugin: ...)` to add an instance of the plugin to the Analytics timeline.

```
        // Configure and initialize the Customer.io SDK
        let config = SDKConfigBuilder(cdpApiKey: "cdpApiKey")
        CustomerIO.initialize(withConfig: config.build())
        
        CustomerIO.shared.add(plugin: FirebaseDestination())
```

Your events will now begin to flow to Firebase in device mode.

## License
```
MIT License

Copyright (c) 2021 Segment

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
