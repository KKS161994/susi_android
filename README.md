# SUSI.AI Android App

Dev [![CircleCI](https://circleci.com/gh/fossasia/susi_android.svg?style=svg&branch=development)](https://circleci.com/gh/fossasia/susi_android)
Master [![CircleCI](https://circleci.com/gh/fossasia/susi_android/tree/master.svg?style=svg)](https://circleci.com/gh/fossasia/susi_android/tree/master)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/6ec0032213274fa0a07574919928c6a6)](https://www.codacy.com/app/harshithdwivedi/susi_android?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=fossasia/susi_android&amp;utm_campaign=Badge_Grade)
[![Preview the app](https://img.shields.io/badge/Preview-Appetize.io-orange.svg)](https://appetize.io/app/mbpprq4xj92c119j7nxdhttjm0)
[![Gitter](https://badges.gitter.im/fossasia/susi_android.svg)](https://gitter.im/fossasia/susi_android?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
[![Mailing List](https://img.shields.io/badge/Mailing%20List-FOSSASIA-blue.svg)](mailto:susiai@googlegroups.com)
[![Twitter Follow](https://img.shields.io/twitter/follow/susiai_.svg?style=social&label=Follow&maxAge=2592000?style=flat-square)](https://twitter.com/susiai_)


The main feature of the app is to provide a conversational interface to provide intelligent answers using the loklak/AskSusi infrastructure. The app also offers login functionalities to connect to other services and store personal data. Additionally, the application uses data provided by the user's phone to improve Susi answers. Geolocation information, for example, helps to offer better answers related to questions about "things nearby".

## Roadmap

Planned features & enhancements are:
- Hotword Detection training
- Full-Screen Voice interaction
- Feedback for skills.
- Displaying SUSI skills
- Susi Smart Speaker Configuration and Control


## Communication

Please join our mailing list to discuss questions regarding the project: https://groups.google.com/forum/#!forum/susiai

Our chat channel is on gitter here: https://gitter.im/fossasia/susi_android

## Screenshots

<table>
  <tr>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/login.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/signup.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/voice_input.png" height = "480" width="270"></td>
  </tr>
  <tr>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/chat.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/skills_menu.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/skills.png" height = "480" width="270"></td>
  </tr>
  <tr>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/groupwise_skills.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/rating_and_feedback.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/devices.png" height = "480" width="270"></td>
  </tr>
  <tr>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/connect_to_device.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/set_up_wifi.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/room.png" height = "480" width="270"></td>
  </tr>
  <tr>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/settings.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/help.png" height = "480" width="270"></td>
    <td><img src="./fastlane/metadata/android/en-US/images/phoneScreenshots/privacy.png" height = "480" width="270"></td>
  </tr>
</table>

## Development

A native Android app using both Java and Kotlin for writing code. The answers for user queries comes from [SUSI Server](https://github.com/fossasia/susi_server) which further uses skills defined in [SUSI Skill Data](https://github.com/fossasia/susi_skill_data).

### Android App Development Set up

Please find info about the set up of the Android app in your development environment [here](docs/Android_App_Setup.md).

### Libraries used and their documentation

- Realm [Docs](https://realm.io/docs/java/latest/)
- Retrofit [Docs](http://square.github.io/retrofit/2.x/retrofit/)
- ButterKnife [Docs](http://jakewharton.github.io/butterknife/javadoc/)
- Espresso [Docs](https://developer.android.com/training/testing/espresso)
- Tajchert Waiting Dots [Docs](https://github.com/tajchert/WaitingDots)
- Picasso [Docs](http://square.github.io/picasso/)
- LeakCanary [Docs](https://github.com/square/leakcanary)
- LeonardoCardoso/Android-Link-Preview [Docs](https://github.com/LeonardoCardoso/Android-Link-Preview)
- Gericop/Android-Support-Preference-V7-Fix [Docs](https://github.com/Gericop/Android-Support-Preference-V7-Fix)
- Snowboy Hotword Detection [Docs](http://docs.kitt.ai/snowboy/)
- zagum/SpeechRecognitionView [Docs](https://github.com/zagum/SpeechRecognitionView)
- MPAndroidChart [Docs](https://github.com/PhilJay/MPAndroidChart)
- Timber [Docs](https://github.com/JakeWharton/timber)
- Play services authentication [Docs](https://developers.google.com/identity/smartlock-passwords/android/store-credentials)

### Project Conventions

There are certain conventions we follow in the project, we recommend that you become familiar with these so that the development process is uniform for everyone:

#### MVP

The project follows Model-View-Presenter design pattern and requires schematic interfaces for each component to be written first as contracts and then implemented.   
All the interactions are done using interfaces only. This means any model, view or presenter will only be referenced by its interface. We do so it is easy to mock and test them and there is no discrepancy in the callable methods of the concrete class and the interface.  
We realize that MVP is opinionated and there is no strict boundary between the responsibility of each component, but we recommend following this style:
- `View` is passive and dumb, there is no logic to be exercised in View, only the ability to show data provided by the presenter through contract is present in the View. This makes it easy to unit test and remove the dependence on Android APIs, thus making the need for instrumentation tests scarce.
- `Presenter` is responsible for most of the business logic, manipulation of data and organising it for the view to present. All logic for the app is present here and it is devoid of ANY Android related code, making it 100% unit testable. We have created wrapper around common Android APIs in form of models so that they can be mocked and presenter stays clean. The responsibility of presenter includes the fetching of data from external source, observing changes and providing the view with the latest data. It also needs to handle all View interactions that require any logic, such as UI triggers causing complex interactions. Notable exception for this is launching of an Activity on click of a button. There is no logic required in the action and is completely dependent on Android APIs. Lastly, presenter should always clean up after the view is detached to prevent memory leaks.
- `Model` has the responsibility to hold the data, load it intelligently from appropriate source, be it disk or network, monitor the changes and notify presenter about those, be self sufficient; meaning to update data accordingly as needed without any external trigger (saving the data in disk after updating from network and providing the saved data from next time on), but be configurable (presenter may be able to ask for fresh data from network). The presenter should not worry about the data loading and syncing conditions (like network connectivity, failed update, scheduling jobs, etc) as it is the job of model itself.

#### Use of Kotlin

Around 50% of the App is written in [Kotlin](https://kotlinlang.org/). Kotlin is a very similar language to Java but with much more advantages than Java. It is easy to adapt and learn. So, you need not worry if you don't have prior experience with it. Follow [these](https://kotlinlang.org/docs/reference/) docs for syntax reference. The latest Android Canary Version has in built support for Kotlin but if you don't have the Canary version, you can add Kotlin Plugin in your Android Studio. Follow [this](https://android.jlelse.eu/setup-kotlin-for-android-studio-1bffdf1362e8) link to see how to do that.

#### Project Structure

Generally, projects are created using package by layer approach where packages are names by layers like `ui`, `activity`, `fragment`, etc but it quickly becomes unscalable in large projects where a large number of unrelated classes are crammed in one layer and it becomes difficult to navigate through them.  
Instead, we follow package by feature, which at the cost of flatness of our project, provides us packages of isolated functioning related classes which are likely to be a complete self-sufficient component of the application. Each package contains all related classes of view, presenter, their implementations like Activities and Fragments.  
A notable exception to this is the `helper` module and data classes like Models and Repositories as they are used in a cross component way.  
***Note:** The interface contract for Presenter and View is present in `contract` package in each module*

#### Separation of concerns

Lastly, each class should only perform one task, do it well, and be unit tested for it. For example, if a presenter is doing more than it should, i.e., parsing dates or implementing search logic, better move it in its own class. There can be exceptions to this practice, but if the functionality can be generalised and reused, it should most definitely be transferred in its own class and unit tested.

## Contributions Best Practices

### For first time Contributor

First time contributors can read [ContributionHelp.md](docs/ContributionHelp.md) file for help regarding creating issues and sending pull requests.

### Branch Policy

We have the following branches

 * **development** All development goes on in this branch. If you're making a contribution, you are supposed to make a pull request to _development_. PRs to development branch must pass a build check and a unit-test check on Circle CI.
 * **master** This contains shipped code. After significant features/bugfixes are accumulated on development, we make a version update and make a release.
 	- Please Note that :-
		> Each push to master branch automatically publishes the application to Play Store as an Alpha Release. Thus, on each merge into master, the versionCode and versionName MUST be changed accordingly in app/build.gradle

	 - _versionCode_ : **Integer** : To be monotonically incremented with each merge. Failure to do so will lead to 				publishing error, and thus is a crucial step before any merge
	 - _versionName_ : **String** : User visible version of the app. To be changed following [semantic versioning](http://semver.org/)
 * **apk** This branch contains many apk files, that are automatically generated on the merged pull request a) debug apk for Fdroid and Playstore b) release apk for Fdroid and Playstore
    - There are multiple files in the apk branch of the project, this branch consists of all the APK files and other files that are relevant when an APK is generated.
    - Once a pull request is merged, the previous APK branch is deleted and a new APK branch is created.
    - If a PR is merged in development branch then the new APKs for the development branch are generated whereas the APKs corresponding to the master branch are not regenerated and simply the previously generated files are added.

### Code practices

Please help us follow the best practice to make it easy for the reviewer as well as the contributor. We want to focus on the code quality more than on managing pull request ethics.

 * Single commit per pull request
 * For writing commit messages please read the [COMMITSTYLE](docs/commitStyle.md) carefully. Kindly adhere to the guidelines.
 * Follow uniform design practices. The design language must be consistent throughout the app.
 * The pull request will not get merged until and unless the commits are squashed. In case there are multiple commits on the PR, the commit author needs to squash them and not the maintainers cherrypicking and merging squashes.
 * If the PR is related to any front end change, please attach relevant screenshots in the pull request description.

* Before you join development, please set up the project on your local machine, run it and go through the application completely. Press on any button you can find and see where it leads to. Explore. (Don't worry ... Nothing will happen to the app or to you due to the exploring :wink: Only thing that will happen is, you'll be more familiar with what is where and might even get some cool ideas on how to improve various aspects of the app.)
* If you would like to work on an issue, drop in a comment at the issue. If it is already assigned to someone, but there is no sign of any work being done, please free to drop in a comment so that the issue can be assigned to you if the previous assignee has dropped it entirely.

## For Developers: Adding Fabric API KEY
1. Go to AndroidManifest.xml
	Replace the fabric_api_key with the Real Fabric API Key by adding :
	```
	<meta-data android:name="io.fabric.ApiKey" android:value="fabric_api_key" />
	```

2. Open the app/fabric.properties:
	Replace the fabric_api_key with your actual Fabric API Secret.

3. Open MainApplication.java,
	a) After adding the API KEYS and API Secret uncomment the line :
		```
		Fabric.with(this, new Crashlytics())
		```

	b) Add imports :
		```
		import com.crashlytics.android.Crashlytics;
		import io.fabric.sdk.android.Fabric;
		```

4. Uncomment the line in the ```app/gradle```: 
	```
	apply plugin: 'io.fabric'
	```
## For Developers: Updating the URL of the smart speaker
1. Go to build.gradle file and the URL of the smart speaker local server under the name of SPEAKER_BASE_URL as a buildConfigField can be updated there under the buildtypes section in both the release and debug blocks : 
    ```
    buildConfigField "String", "SPEAKER_BASE_URL", '"http://10.0.0.1:5000"'	
    
 	```
 	
## For Developers: Adding the YouTube API key
Go to AndroidManifest.xml and replace the ${YOUTUBE_API_KEY} with the real youtube API Key by adding :
  	
    <meta-data
    android:name="com.google.android.youtube.API_KEY"
    android:value="${YOUTUBE_API_KEY}" />
   
## For Testers: Testing the App
If you are a tester and want to test the app, you have two ways to do that:
1. **Installing APK on your device:** You can get debug [APK](https://github.com/fossasia/susi_android/blob/apk/app-fdroid-debug.apk) as well as Release [APK](https://github.com/fossasia/susi_android/blob/apk/app-fdroid-release-unsigned.apk) in apk branch of the repository. After each PR merge, both the APKs are automatically updated. So, just download the APK you want and install it on your device. The APKs will always be the latest one.
2. **Testing on [appetize.io](https://appetize.io/app/mbpprq4xj92c119j7nxdhttjm0):** If you don't want to download the APKs, you can simply go on [this](https://appetize.io/app/mbpprq4xj92c119j7nxdhttjm0) link and use the App on an online simulator. You will always find the latest version of App on that link because it is updated after each PR merge.

## License

This project is currently licensed under the Apache License Version 2.0. A copy of [LICENSE.md](https://github.com/fossasia/susi_android/blob/master/LICENSE) should be present along with the source code. To obtain the software under a different license, please contact FOSSASIA.
