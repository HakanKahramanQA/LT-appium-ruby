# Ruby With Appium ![pw](https://img.shields.io/badge/Ruby-CC342D?style=for-the-badge&logo=ruby&logoColor=white)

<p align="center">
<img height="500" src="https://user-images.githubusercontent.com/95698164/171857146-90e52e22-0070-4798-b2a5-6cc525a4da66.png">
</p>

<p align="center">
  <a href="https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/c/LambdaTest" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

*Appium is a tool for automating native, mobile web, and hybrid applications on iOS, Android, and Windows platforms. It supports iOS native apps written in Objective-C or Swift and Android native apps written in Java or Kotlin. It also supports mobile web apps accessed using a mobile browser (Appium supports Safari on iOS and Chrome or the built-in 'Browser' app on Android). Perform Appium automation tests on [LambdaTest's online cloud](https://www.lambdatest.com/appium-mobile-testing).*

*Learn the basics of [Appium testing on the LambdaTest platform](https://www.lambdatest.com/support/docs/getting-started-with-appium-testing/).*

[<img height="53" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register)

## Table of Contents

* [Pre-requisites](#pre-requisites)
* [Run Your First Test](#run-your-first-test)
* [Executing The Tests](#executing-the-tests)

## Pre-requisites

Before you can start performing Ruby automation testing with Appium, you would need to:

- Install **Ruby** on your local system. Follow these instructions to install on different operating systems.

  - For **Windows**, you can download from the [official website](https://rubyinstaller.org/downloads/).
  - For **Linux** or **Ubuntu**, you can run a simple apt command like below:

    ```bash
    sudo apt-get install ruby-full
    ```

  - For **macOS**, you can run a [Homebrew](https://brew.sh/) command like this:

    ```bash
    brew install ruby
    ```


### Clone The Sample Project

Clone the LambdaTest’s [LT_Ruby_Appium](https://github.com/LambdaTest/LT_Ruby_Appium) and navigate to the code directory as shown below:

```bash
git clone https://github.com/LambdaTest/LT_Ruby_Appium
cd LT_Ruby_Appium
```

### Setting Up Your Authentication

Make sure you have your LambdaTest credentials with you to run test automation scripts on LambdaTest. To obtain your access credentials, [purchase a plan](https://billing.lambdatest.com/billing/plans) or access the [Automation Dashboard](https://appautomation.lambdatest.com/).

Set LambdaTest `Username` and `Access Key` in environment variables.

**For Linux/macOS:**

```js
export LT_USERNAME=YOUR_LAMBDATEST_USERNAME \
export LT_ACCESS_KEY=YOUR_LAMBDATEST_ACCESS_KEY
```
 
**For Windows:**
 
```js
set LT_USERNAME=YOUR_LAMBDATEST_USERNAME `
set LT_ACCESS_KEY=YOUR_LAMBDATEST_ACCESS_KEY
```
  
### Upload Your Application

Upload your **_iOS_** application (.ipa file) or **_android_** application (.apk file) to the LambdaTest servers using our **REST API**. You need to provide your **Username** and **AccessKey** in the format `Username:AccessKey` in the **cURL** command for authentication. Make sure to add the path of the **appFile** in the cURL request. Here is an example cURL request to upload your app using our REST API:

**Using App File:**

**For Linux/macOS:**

```js
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" \
--location --request POST 'https://manual-api.lambdatest.com/app/upload/realDevice' \
--form 'name="Android_App"' \
--form 'appFile=@"/Users/macuser/Downloads/proverbial_android.apk"' 
```

**For Windows:**

```js
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" -X POST "https://manual-api.lambdatest.com/app/upload/realDevice" -F "appFile=@"/Users/macuser/Downloads/proverbial_android.apk""
```

**Using App URL:**

**For Linux/macOS:**

```js
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" \
--location --request POST 'https://manual-api.lambdatest.com/app/upload/realDevice' \
--form 'name="Android_App"' \
--form 'url="https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk"'
```

**For Windows:**

```js
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" -X POST "https://manual-api.lambdatest.com/app/upload/realDevice" -d "{"url":"https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk","name":"sample.apk"}"
```

**Tip:**

- If you do not have any **.apk** or **.ipa** file, you can run your sample tests on LambdaTest by using our sample :link: [Android app](https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk) or sample :link: [iOS app](https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_ios.ipa).
- Response of above cURL will be a **JSON** object containing the `App URL` of the format - <lt://APP123456789123456789> and will be used in the next step.

## Run Your First Test

Once you are done with the above-mentioned steps, you can initiate your first Ruby test on LambdaTest.

**Test Scenario:** Check out [Android.rb](https://github.com/LambdaTest/LT-appium-ruby/blob/master/android/android-sample.rb) file to view the sample test script for android and [iOS.rb](https://github.com/LambdaTest/LT-appium-ruby/blob/master/ios/ios-sample.rb) for iOS.

### Configuring Your Test Capabilities

You can update your custom capabilities in test scripts. In this sample project, we are passing platform name, platform version, device name and app url (generated earlier) along with other capabilities like build name and test name via capabilities object. The capabilities object in the sample code are defined as:

**Info Note:**

- In case you're using the Capabilities using the JSON Wire Protocol, then please use appium_lib version 10.6.0 and below.
- Install it using ```gem install appium_lib -v 10.6.0``` command.

<Tabs className="docs__val">

<TabItem value="ios-config" label="iOS" default>

```ruby title="iOS(.ipa)"
 caps = {
            "LT:Options" => {
                :deviceName => "iPhone 13 Pro",  
                :platformName => "iOS",
                :platformVersion => "15",
                :build => "Ruby Vanilla - iOS",
                :name => "Ruby iOS Test",
                :isRealMobile => true,
                :app => "YOUR_APP_URL", #Enter the App (.ipa) URL here
                :w3c => true,
        } }
```

</TabItem>
<TabItem value="android-config" label="Android" default>

```ruby title="Android(.apk)"
caps = {
            "LT:Options" => {
            :deviceName => "OnePlus 7",  
            :platformName => "Android",
            :platformVersion => "9",
            :build => "Ruby Vanilla - Android",
            :name => "Ruby Android Test",
            :isRealMobile => true,
            :app => "YOUR_APP_URL", #Enter the App (.apk) URL here
            :w3c => true,
        } }
```

</TabItem>

</Tabs>

**Info Note:**

- You must add the generated **APP_URL** to the `"app"` capability in the config file.
- You can generate capabilities for your test requirements with the help of our inbuilt **[Capabilities Generator tool](https://www.lambdatest.com/capabilities-generator/)**. A more Detailed Capability Guide is available [here](https://www.lambdatest.com/support/docs/desired-capabilities-in-appium/).

## Executing The Tests

<Tabs className="docs__val">

<TabItem value="ios" label="iOS" default>

If you are using an **iOS** app, the cURL command will generate an app URL for the corresponding iOS app and install the same for running the tests. You can either use our sample :link: [iOS app](https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_ios.ipa) or upload your own app as discussed earlier.

Navigate to the corresponding directory based on your app.

```bash
cd ios
```

Execute the following command to run your test on LambdaTest platform:

```bash
ruby ios-sample.rb
```

</TabItem>

<TabItem value="android" label="Android" default>

If you are using an **android** app, the cURL command will generate an app URL for the corresponding Android app and install the same for running the tests. You can either use our sample :link: [Android app](https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk) or upload your own app as discussed earlier.

Navigate to the corresponding directory based on your app.

```bash
cd android
```

Execute the following command to run your test on LambdaTest platform:

```bash
ruby android-sample.rb
```

</TabItem>

</Tabs>

**Info Note**
In case of Windows, if you get any error message. Please try this method:

1. Navigate to the corresponding directory based on your app.

```bash
cd android
```
2. Refresh the gem bundles through given command

```bash
gem uninstall -aIx
```
3. Re-install the gems required

```bash
gem install appium_lib -v 10.6.0
gem install ffi
```
4. Now try running the corresponding automation script for your app.

```bash
ruby android-sample.rb
```

**Info:** Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on the :link: [LambdaTest App Automation Dashboard](https://appautomation.lambdatest.com/build).

### Troubleshooting

If you encounter an issue where the gem installation fails with an error like `No such file or directory @ rb_sysopen`, you can resolve it by creating the required directory, setting up a custom gem path, or installing with administrator privileges.

#### Option 1: Create the Missing Directory

**macOS/Linux:**  
Run the following command to create the required directory structure:
```bash
mkdir -p ~/.local/share/gem/ruby/<ruby_version>/cache
```
**Windows:**
```bash
mkdir -p %USERPROFILE%\.gem\ruby\<ruby version>\cache
```
#### Option 2: Set a Custom GEM Path
**macOS/Linux:**
```bash
export GEM_HOME=$HOME/gems
export PATH=$HOME/gems/bin:$PATH
gem install appium_lib -v 10.6.0
```
**Windows:**
```bash
set GEM_HOME=%USERPROFILE%\gems
set PATH=%USERPROFILE%\gems\bin;%PATH%
gem install appium_lib -v 10.6.0
```
#### Option 3: Install with Administrator Privileges
**macOS/Linux:**
```bash
sudo gem install appium_lib -v 10.6.0
```
**Windows:**
Run Command Prompt as Administrator, then:
```bash
gem install appium_lib -v 10.6.0
``` 

## Additional Links

- [Advanced Configuration for Capabilities](https://www.lambdatest.com/support/docs/desired-capabilities-in-appium/)
- [How to test locally hosted apps](https://www.lambdatest.com/support/docs/testing-locally-hosted-pages/)
- [How to integrate LambdaTest with CI/CD](https://www.lambdatest.com/support/docs/integrations-with-ci-cd-tools/)

## Documentation & Resources :books:
      
Visit the following links to learn more about LambdaTest's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [LambdaTest Documentation](https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby)
* [LambdaTest Blog](https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby)
* [LambdaTest Learning Hub](https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby)    

## LambdaTest Community :busts_in_silhouette:

The [LambdaTest Community](https://community.lambdatest.com/) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At LambdaTest ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/) 
      
## About LambdaTest

[LambdaTest](https://www.lambdatest.com) is a leading test execution and orchestration platform that is fast, reliable, scalable, and secure. It allows users to run both manual and automated testing of web and mobile apps across 3000+ different browsers, operating systems, and real device combinations. Using LambdaTest, businesses can ensure quicker developer feedback and hence achieve faster go to market. Over 500 enterprises and 1 Million + users across 130+ countries rely on LambdaTest for their testing needs.    

### Features

* Run Selenium, Cypress, Puppeteer, Playwright, and Appium automation tests across 3000+ real desktop and mobile environments.
* Real-time cross browser testing on 3000+ environments.
* Test on Real device cloud
* Blazing fast test automation with HyperExecute
* Accelerate testing, shorten job times and get faster feedback on code changes with Test At Scale.
* Smart Visual Regression Testing on cloud
* 120+ third-party integrations with your favorite tool for CI/CD, Project Management, Codeless Automation, and more.
* Automated Screenshot testing across multiple browsers in a single click.
* Local testing of web and mobile apps.
* Online Accessibility Testing across 3000+ desktop and mobile browsers, browser versions, and operating systems.
* Geolocation testing of web and mobile apps across 53+ countries.
* LT Browser - for responsive testing across 50+ pre-installed mobile, tablets, desktop, and laptop viewports
    
[<img height="53" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register)

      
## We are here to help you :headphones:

* Got a query? we are available 24x7 to help. [Contact Us](support@lambdatest.com)
* For more info, visit - [LambdaTest](https://www.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-ruby)
