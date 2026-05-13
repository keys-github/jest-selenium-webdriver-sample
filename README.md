# Run Selenium Tests With Jest — TestMu AI (Formerly LambdaTest)
![JavaScript](https://user-images.githubusercontent.com/95698164/172134732-2e9c780e-10ac-4956-b366-86ffc25bf070.png)

<p align="center">
  <a href="https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/@TestMuAI" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

*Learn how to use Jest framework to configure and run your JavaScript automation testing scripts on the TestMu AI platform*

[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register)

## Table Of Contents

* [Pre-requisites](#pre-requisites)
* [Run Your First Test](#run-your-first-test)
* [Executing The Test](#executing-the-test)
* [Local Testing With TestNG](#testing-locally-hosted-or-privately-hosted-projects)

## Pre-requisites

Before getting started with Selenium automation testing on TestMu AI, you need to:

* Download and install **NodeJS**. You should be having **NodeJS v6** or newer. Click [here](https://nodejs.org/en/) to download.
* Make sure you are using the latest version of **JavaScript**.
* Install **npm** from the official website by clicking [here](https://www.npmjs.com/).
* Download [Selenium JavaScript bindings](https://www.selenium.dev/downloads/) from the official website. Latest versions of **Selenium Client** and **WebDriver** are ideal for running your JavaScript automation testing script on TestMu AI’s Selenium Grid.

### Installing Selenium Dependencies and tutorial repo

Clone the TestMu AI’s [jest-selenium-webdriver-sample repository](https://github.com/LambdaTest/jest-selenium-webdriver-sample) and navigate to the code directory as shown below:
```bash
git clone https://github.com/LambdaTest/jest-selenium-webdriver-sample
cd jest-selenium-webdriver-sample
```
Next, you need to install **Jest**. Run the below command to install Jest:
```bash
npm install --save-dev jest --force
```

### Setting up Your Authentication
Make sure you have your TestMu AI credentials with you to run test automation scripts on TestMu AI Selenium Grid. You can obtain these credentials from the [TestMu AI Automation Dashboard](https://automation.lambdatest.com/build/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample) or through [TestMu AI Profile](https://accounts.lambdatest.com/login/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample).

Set TestMu AI `Username` and `Access Key` in environment variables.
  * For **Linux/macOS**:
  ```bash
  export LT_USERNAME="YOUR_USERNAME" export LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```
  * For **Windows**:
  ```bash
$env:LT_USERNAME='YOUR USERNAME'
$env:LT_ACCESS_KEY='YOUR ACCESS KEY'
  ```

## Run Your First Test

### Sample Test with Jest
**Test Scenario:** Let’s check a sample **Jest** Selenium code running on TestMu AI Selenium Grid. This is a simple Jest test automation script that tests a sample to-do list app. Check out this [single.test.js](https://github.com/LambdaTest/jest-selenium-webdriver-sample/blob/master/test/single.test.js) file to run your first sample test.

### Configuration of Your Test Capabilities
In this code, we are passing browser, browser version, and operating system information, along with TestMu AI Selenium grid capabilities via capabilities object. The capabilities object in the above code are defined as:
```js
 const capabilities = {
  build: 'jest-LambdaTest-Single',
  browserName: 'chrome',
  version: 'latest',
  platform: 'Windows 10',
};
```
> You can generate capabilities for your test requirements with the help of our inbuilt **[Capabilities Generator tool](https://www.testmuai.com/capabilities-generator/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample)**.

## Executing the Test

The tests can be executed in the terminal using the following command
```bash
npm test single.test.js
```
Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on [TestMu AI automation dashboard](https://automation.lambdatest.com/build/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample). TestMu AI Automation Dashboard will help you view all your text logs, screenshots and video recording for your entire automation tests.

## Testing Locally Hosted or Privately Hosted Projects

You can test your locally hosted or privately hosted projects with [TestMu AI Selenium grid cloud](https://www.testmuai.com/selenium-automation/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample) using TestMu AI Tunnel app. All you would have to do is set up an SSH tunnel using TestMu AI Tunnel app and pass toggle `tunnel = True` via desired capabilities. TestMu AI Tunnel establishes a secure SSH protocol based tunnel that allows you in testing your locally hosted or privately hosted pages, even before they are made live.

>Refer our [TestMu AI Tunnel documentation](https://www.testmuai.com/support/docs/testing-locally-hosted-pages/) for more information.

Here’s how you can establish TestMu AI Tunnel.

>Download the binary file of:
* [TestMu AI Tunnel for Windows](https://downloads.lambdatest.com/tunnel/v3/windows/64bit/LT_Windows.zip)
* [TestMu AI Tunnel for Mac](https://downloads.lambdatest.com/tunnel/v3/mac/64bit/LT_Mac.zip)
* [TestMu AI Tunnel for Linux](https://downloads.lambdatest.com/tunnel/v3/linux/64bit/LT_Linux.zip)

Open command prompt and navigate to the binary folder.

Run the following command:
```bash
LT -user {user’s login email} -key {user’s access key}
```
So if your user name is lambdatest@example.com and key is 123456, the command would be:
```bash
LT -user lambdatest@example.com -key 123456
```
Once you are able to connect **TestMu AI Tunnel** successfully, you would just have to pass on tunnel capabilities in the code shown below :

**Tunnel Capability**
```js
const capabilities = {
        tunnel: true,
}
```
### Executing Local Tests with Jest

To run parallel tests using **Jest**, we would have to execute the below command in the terminal:
```bash
npm test local.test.js
```
Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on [TestMu AI automation dashboard](https://automation.lambdatest.com/build/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample).

## Additional Links

* [Advanced Configuration for Capabilities](https://www.testmuai.com/support/docs/selenium-automation-capabilities/)
* [How to test locally hosted apps](https://www.testmuai.com/support/docs/testing-locally-hosted-pages/)
* [How to integrate TestMu AI with CI/CD](https://www.testmuai.com/support/docs/integrations-with-ci-cd-tools/)

## Tutorials 📙

Check out our latest tutorials on TestNG automation testing 👇

* [Jest Tutorial For Selenium JavaScript Testing With Examples](https://www.testmuai.com/blog/jest-tutorial-for-selenium-javascript-testing-with-examples/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample)
* [Jest vs Mocha vs Jasmine: Comparing The Top 3 JavaScript Testing Frameworks](https://www.testmuai.com/blog/jest-vs-mocha-vs-jasmine/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample)

## Documentation & Resources :books:
 
Visit the following links to learn more about TestMu AI's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [TestMu AI Documentation](https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample)
* [TestMu AI Blog](https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample)
* [TestMu AI Learning Hub](https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample)    

## TestMu AI Community :busts_in_silhouette:

The [TestMu AI Community](https://community.testmuai.com/?utm_source=github&utm_medium=repo&utm_campaign=jest-selenium-webdriver-sample) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At TestMu AI ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/)

## 🚀 LambdaTest is Now TestMu AI

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/) - we have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

**🔄 Our Rebrand Journey**

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).

**🔭 Explore TestMu AI**

The same infrastructure LambdaTest customers relied on, now delivered through autonomous AI agents.

- [KaneAI](https://www.testmuai.com/kane-ai/)
- [Agent-to-Agent Testing](https://www.testmuai.com/agent-to-agent-testing/)
- [HyperExecute](https://www.testmuai.com/hyperexecute/)
- [Real Device Cloud](https://www.testmuai.com/real-device-cloud/)
- [Pricing](https://www.testmuai.com/pricing/)
- [Documentation](https://www.testmuai.com/support/docs/)