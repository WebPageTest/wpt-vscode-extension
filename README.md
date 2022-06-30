<p align="center"><img src="https://docs.webpagetest.org/img/wpt-navy-logo.png" alt="WebPageTest Logo" /></p>
<p align="center"><a href="https://docs.webpagetest.org/api/integrations/#officially-supported-integrations">Learn about more WebPageTest API Integrations in our docs</a></p>

# Visual Studio Code Extension For WebPageTest
The Visual Studio Code(Vscode) Extension for WebPageTest lets you run tests against WebPageTest from within Vscode. Once the tests are complete, some of the performance metrics, a copy of the waterfall, screenshot, and a link to the full results will be displayed in Vscode, right where you are developing, helping you to easily troubleshoot and diagnose performance issues directly from Vscode and possibly refactor the code if needed.

**Features:**
- Run WebPageTest from within Vscode, and get the results back in Vscode

### Updating Vscode Settings

To update the settings for Vscode, we need to open settings.json file on Vscode. Open your command palette on Vscode (command/ctrl + shift + P) and start typing "Settings", click on 'Preferences: Open Settings (JSON)' from the command palette. 

![image](https://user-images.githubusercontent.com/31168643/123271784-cd000d80-d51e-11eb-889c-c8be782b60fd.png)

You'll need an API key to run the extension. [Get yours here](https://app.webpagetest.org/ui/entry/wpt/signup?enableSub=true&utm_source=docs&utm_medium=vscode&utm_campaign=vscode&utm_content=account)

The following properties are configurable in your settings.json file:

```json
// Your WebPageTest API key. REQUIRED
"WebPageTest.apiKey": "YOUR_API_KEY",

// The URL to test. If left out of settings.json, the extension will prompt you for a URL when run.
"WebPageTest.urlToTest": null,

// The location to test from. The location is comprised of the location of the testing agent, the browser to test on, and the connectivity in the following format: location:browser.connectivity.
"WebPageTest.location": "Dulles:Chrome.Cable",

// The number of tests to run
"WebPageTest.runs": 1,

// The interval (in seconds) to poll the API for test results
"WebPageTest.pollResults": 5,

// emulate mobile browser: Chrome mobile user agent, 640x960 screen, 2x scaling and fixed viewport (Chrome only)
"WebPageTest.emulateMobile": true,

// device name from mobile_devices.ini (Link: https://github.com/WPO-Foundation/webpagetest/blob/master/www/settings/mobile_devices.ini) to use for mobile emulation (only when emulateMobile=true is specified to enable emulation and only for Chrome)
"WebPageTest.device": "MotoG4",
```
[Find all the supported locations here.](https://webpagetest.org/getLocations.php?k=API_KEY&f=html)
### Running The Test

In the new window of Vscode, open the command palette(command/ctrl + shift + P) and start typing WebPageTest, you should see a WebPageTest command in it. Run the command.

![image](https://user-images.githubusercontent.com/31168643/123274196-eefa8f80-d520-11eb-85a4-11fe5479b990.png)

If you had not entered the URL before you get an option to enter it, the test requires an URL to run. Below option is only asked if you had not entered an URL in settings.json

![image](https://user-images.githubusercontent.com/31168643/123274476-2d904a00-d521-11eb-982d-c22749bb5b9b.png)

A dropdown will appear for you to choose from multiple locations if you had not mentioned it in settings.json

![image](/assets/images/locations.png)

You will be asked to choose if you want to run the test on a mobile device.

![image](/assets/images/emulatemobile.png)

A list of mobile devices provided by WebPageTest appears if selected yes.

![image](/assets/images/device.png)

Once the test is submitted, you get the below response on Vscode.

![image](https://user-images.githubusercontent.com/31168643/123274877-806a0180-d521-11eb-9f14-020e83af7284.png)

And, when the test has successfully run, you get the metrics, waterfall and screenshot from the test.

![image](https://user-images.githubusercontent.com/31168643/123275440-f3737800-d521-11eb-9798-7e9474fe6d0f.png)
