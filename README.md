# Appium Overview

*For automation of mobile apps, we are learning Appium in this course. What is Appium exactly? What features does it provide? And how do we use it, at a high level?*

Let's talk about Appium in depth! What is Appium? What is the story of Appium and how it came to be what it is? How, generally speaking, does it work, and how do you use it?

### What is Appium?

What is Appium? |
---- |
Mobile app/device automation tool (and more). |
Fully open-source project (development on GitHub, run by OpenJS Foundation). |
Wraps automation up in a WebDriver interface. Doesn't perform automation *directly*, for much greater flexibility. |
Allows authoring of automation scripts and tests in any language. |
Cross-platform API, by and large. |
Huge community of users and practitioners - lots of places to go for help. |

First of all, what is Appium? Well, Appium is a number of things. Let's go through each of them:

1. First, Appium is a mobile automation tool. You can think of it as being very analogous to Selenium. Selenium's purpose is to allow you to automate web browsers, and Appium's purpose is to allow you to automate mobile devices. Actually, Appium's purpose is bigger than that! It certainly started out as a tool to automate mobile apps, but it has broadened into a generalized tool that aims to give you automation ability for all kinds of apps. But for now, Appium is mostly known as a mobile device and mobile app automation tool, and that is what this course is all about.
2. Second, Appium is an open source project. Like Selenium, Appium has an open source license for its use, and a very permissive license, which means that anybody can use Appium for just about any purpose. You can go to GitHub and read Appium's source code yourself, and extend it, or contribute back to it. This is really important. Appium is different than tools like XCUITest, which is developed behind closed doors at Apple, or even Espresso, which is technically open source but practically run as a closed source project by Google. Appium isn't owned by any mobile device platform, or any testing company. It's owned by a non-profit foundation called the OpenJS foundation, which exists precisely to provide a neutral home for code. You don't have to worry about the whims of one company affecting a tool that you have integrated deeply into your development process.
3. Third, Appium is a tool that wraps fundamental automation tools in a WebDriver API. Here's what I mean by this: Appium does not have any code in it that tells iOS devices how to tap an element. It does not have any code in it which tells an Android device how to perform a swipe movement in an automated fashion. Now this is a bit surprising, since isn't this the whole point of Appium? Isn't Appium supposed to do these things? Well, yes and no. The fact is that there are already other tools which do this, and which do it in a better way than the Appium team could do. For example, Apple develops the XCUITest framework to be tightly integrated with iOS. Apple's engineers write both iOS platform code and XCUITest code. Who better than Apple to teach an iOS device how to tap on an element in an automated fashion? Likewise, who better than Google, with their UiAutomator 2 or Espresso frameworks, to provide automation support for Android devices? The problem that Appium sees out there in the world isn't that automation tools don't exist. They do, and they're fine. Unfortunately, they put too many burdens on their users, in Appium's opinion. Appium would like to see the power and flexibility of the WebDriver API for mobile automation. And that's exactly what Appium's main role is: to take the existing automation technologies and make them available in a WebDriver interface, so you can write mobile test code that looks just like web test code, and is based on industry standard APIs!
4. Fourth, this choice of Appium to provide automation technology from within a WebDriver model means that you can write Appium tests in any programming language. This is a great benefit for many teams, who might want to write tests in a language other than Objective-C or Swift for iOS, or Java or Kotlin for Android.
5. Fifth, Appium provides the same API for multiple platforms, which means that you can write test code that looks and feels more or less the same for both the Android and iOS versions of your app. In fact, if you design your test suite well, and if your apps work relatively similarly across both platforms, you can have test code that is exactly the same for both Android and iOS, with no duplication. This is something which would be an impossibility if you used the native frameworks like XCUITest and Espresso.
6. Sixth, because Appium is open source, it has generated a huge community of practitioners, people who use Appium every day in their work. The result of this is that there is a lot of knowledge out there about how to get stuff done with Appium. There are Appium user forums, Appium chat groups, and lots of online guides to Appium out there, including my own set of articles and tutorials at appiumpro.com.

### Appium's History

How did Appium get to be this way? Let's look at a bit of Appium's history to learn more. Before there was anything called "Appium," a QA manager at a dating company in San Francisco had an idea. The manager was called Dan Cuellar, and his job was to ensure quality for the iOS app. He thought that surely there must be a way to automate the iOS app, the same way we could already do with web browsers. He learned about a little tool from Apple called Instruments, which was a standalone app you ran on a Mac. He discovered that within Instruments, there was the capability type a snippet of JavaScript, and that this would be executed on an iOS device with a sort of automation API called UIAutomation.

<img width="800" src="https://user-images.githubusercontent.com/70295997/226076481-f5da59e4-9e1d-4990-9b42-d0a6ce3128fd.png">

Dan took this idea with him to the Selenium user conference in 2012, in London, and talked about this idea during a lightning talk. In it, he shared how he'd come up with a way to actually run this UIAutomation JavaScript code from outside the Instruments app, which was something Apple had never intended. This was the crucial insight that would open up the path to Appium, because when you no longer needed to manually open up a desktop app to run the automation code, you could have a fully scriptable automation environment.

Some months later, Jason Huggins was working for a testing company called Sauce Labs, and wanted to find some solution for automating iOS. He recalled Dan's demo at SeleniumConf, because Jason was actually the one who had been chairing the lightning talks! So they got together and hatched a plan to take Dan's idea, and make it something that worked more like WebDriver. It was an obvious thought for Jason, because of his work on Selenium and WebDriver, and it was clear that what the world needed wasn't just mobile automation, but mobile automation that had the same advantages as Selenium. And what could be better than trying to use the same API, to keep life easy for users? That's how the name "Appium" was born--automation like Selenium, but for apps and not just websites!

Jon Lipps happened to be a developer working at Sauce Labs at the time, and got tapped to develop this Appium idea and turn it into reality. And that's what he did. He put together a small team and together they implemented Appium's original iOS support, based on Dan's methods. Jon then added Android support, bringing Appium into the cross-platform world underneath the standard WebDriver API. The rest, as they say, is history. There have been many changes in Appium since that time, most notably the expansion of the Appium model to other platforms beyond iOS and Android, for example Mac and Windows desktop platforms. But the basic idea has been the same: Appium lets you automate your app in any programming language, without requiring modifications to it, and using standard APIs that thousands of developers already use for web automation. And on top of all this, it's open source, so you don't have to pay for it, and you don't have to be afraid that some company will go and do something nefarious with it for their own purposes.

### Appium's Features

Appium's Features |
---- |
Basic UI automation behaviors (find and interact with elements) |
Functionality beyond UI automation |
Send files, take screenshots, start/stop apps, etc. |


What features does Appium have, exactly? What can you do with it? Many, many things. You have access to all the basic automation behaviors you'd expect from Selenium or any of the other mobile automation tools. You can find UI elements and interact with them. You can tap, enter text, swipe, and so on. Beyond that, Appium has implemented a whole host of helpful methods that go beyond the UI automation tools Appium wraps, like XCUITest or UiAutomator 2. Appium lets you send files to devices, take screenshots and videos from device screens, start and stop apps, and so on. We'll see a lot of these features throughout the course of our time together here, but you can always explore the Appium documentation to get a broader idea.

Conceptual Requirements for Appium |
---- |
Virtual or test devices. to test on (or cliud service provider) |
Mobile app development setup (Xcode for iOS, Android Studio for Android) |
The Appium software (installed via NPM or GUI app) |
Appium driver(s) for the platform(s) you want to automate (e.g., the XCUITest driver for iOS) |
Programming language and Appium client library |

How do you use Appium? Well, more or less exactly the same way you use Selenium, with some additional steps because there are requirements for the mobile development and test environments that go well beyond what is required for web development. Here are the things you'll need:

1. First, you'll need a set of virtual or real devices that you want to test on. Appium supports both virtual and real devices, though there are some limitations for both categories, which we'll go into more later. Just like with Selenium, if there are devices or platforms you don't have available locally, there are cloud services like HeadSpin that can give you remote access to them.
2. Second, you'll need a mobile app development setup for each platform you want to automate. For iOS, this means Xcode and related tools. For Android, it means Android Studio, the Android SDKs, Java, and related tools.
3. hird, you'll need Appium itself, which you can get in a variety of ways.
4. Fourth, you'll need the appropriate Appium driver for the platform you want to automate. Once you have Appium, you can use it to download drivers without needing to go anywhere else.
5. Fifth, you'll need a programming language and a Selenium or Appium client library, just like for Selenium.

With all these pieces, you will be able to write automation scripts in your programming language of choice, starting up whichever apps you like, and automating them as if a little software robot were obeying your commands.





