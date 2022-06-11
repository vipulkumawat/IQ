**ReactNative**

complete-react-native-mobile-development-zero-to-mastery-with-hooks
===================================================================

Objective-C
Swift
Java
Kotlin


ReactNative Foundations
React Fundamentals
Native Navigation
Firebase
Payments Stripe
Google Maps API
Animations
Deploy to AppStore and Google Play (ios,Android)
Device Permissions
Styling and layout
ReactHooks
Debugging


Softwares:
Install latest version of Node LTS
Install visual studio code
Visual Studio code settings(Optional)
Install Expo's Command line interface
Create a React Native App(focusTime)
Android Simulator
iPhone Simulator



Exercise: Meet Your Classmates and Instructor
1. Before we get started, let's do a quick exercise that will take less than 3 minutes:


Step 1 - Click on this link to join our Private Online Classroom: CLICK HERE TO JOIN NOW.


Step 2 -  Once inside, go to #introductions channel and share who you are, where you are from, and why you chose to do this course.

Step 3 -  Go to the #accountability-buddies and find a buddy who is starting a ZTM course today just like you (doesn't have to be the same course)! You will be keeping each other accountable throughout the course and motivating each other to finish. Who knows, maybe you will find life long friends/coworkers this way. 

Step 4 - check out #general or your course specific channel to meet others in your class. We will be announcing class hangouts and instructor meetups/livestreams in there. Some of the channels available for you to join are:


#react-native - For all questions Mobile Development and React Native
#alumni - Ask graduates of this course questions
#womenintech - For the female coders out there
#job-hunting - Anything related to finding a job as a developer

....and many many more!!



OPTIONAL Step - A fellow ZTM student, Matt, has made a video walkthrough for you of the community here if you want to watch and take a deep dive as to all the things that happen in the community every month.



2. Course updates and cheatsheets?
We are constantly adding new videos and updating this course, announcing new community events, and creating course cheatsheets/resources. To stay up to date with all the latest changes to the course and new videos, keep an eye out on the #announcements channel in our Discord community. Anything important will be announced in there (you can scroll to see past announcements).


You can also follow me on twitter where I keep you updated about industry news, upcoming courses, and random thoughts on life: @andreineagoie and @zerotomasteryio



3. One more thing...


As you start the course, Udemy will have a popup that  will ask you to leave a review ⭐️⭐️⭐️⭐️⭐️ of the course. Yes, it can get a little annoying (it's a Udemy system and not something we have control over) but please leave an honest review (even if you just started the course) as it really helps us out and allows more people to discover this course in this massively competitive marketplace. It would truly mean a lot 😊.




Thank you and welcome to ZTM,

- Andrei



Monthly Coding Challenges, Free Resources and Guides
Every month in the community, we will have coding challenges for you to participate in, monthly industry blogs and other top free resources emailed to you. We also have annual events like Advent of Code🎄, Hacktoberfest 👾, and Frosty February Hackathon☃️, plus some giveaways 🎁 as well.

Make sure you have your email settings on Udemy to allow this, as every month we will be emailing you a community update email where we list all of the new challenges, free resources, videos and giveaways.

Some students have mentioned they do not receive these emails and it's mainly because of this (Go to Your profile Icon and click: Account > Notification Settings). Make sure you have these 2 boxes checked if you want to receive the monthly email like in the image below.


Native:
IOS
Android


Web based:
Cordovo
Ionic
Progressive Webapp

Native Like:
React native: have direct access to native side of the view
Flutter: given by google
Xamarin given by microsoft converts the c# code to native code


why react native?
big community and enough document
enough solutions for common issues
big companies
cross platform, write once and run on both android/ios
infinatively extensive

https://reactnative.dev/docs/getting-started#interactive-examples


expo app

core components
APIs
react library


8:00
the building blocks of react native:
Core components and Native components

<View>
<Text>
<Image>
<ScrollView>
<TextInput>


React native gives two things:
Components:
Basic
UserInterface
Listviews
IOS and Android specific views
Alerts

APIs:

ReactNative components compiled into native components of IOS and Android depending on OS. So that it is super Performant and fast. It also gives us APIs to interact with phone like phone dimensions etc.

It also have access to React Library. without react library react native doesn't know react specific things like state, props in react components. these are react specific.

React component
react native components
Core components, Community native components, community components

community components can be found in native directory
https://reactnative.directory/

you can have your own native components
we are going to follow four step process as we build our UI.
javascript code with react library
1. import required components
2. create our own components
3. creating styles
4. export the components


video11:
React Native internals
what happens when you run react native code?
native react views are converted to native views

step1: react native compiles our views into native views
which is very performant
this makes react app more performance 	

our react native compiles our views into native views which is very very performant
it also needs to understand javascript knowledge on phone.
javascript core that powers to browser
it also helps to read the logic, the js core engine is used to read this logic and then js vm communicates with the phone to tell it what actions to be performaned.

ournativeviews are converted into native platform apis.


react native internals2:
https://github.com/facebook/react-native

Hermis: opensource javascript engine optimized for running react native apps on android.
why apps are faster for IOS than android?
because IOS naturally comes with javascript core. javascript core is used by safari given by apple. javascript core is by default available on all IOS apps. Android doesnot have that. So with android apps we need to ship jscore with our js logic. Shipping js core with app makes it heavy. instead use hermis which is optimized js engine for android.



Exercise: is there CSS?
is there CSS in React Native?
technically No, there is no css with React Native.
html and css are for the web.
react native instead uses native mobile tools.
so the css that we use in react native is built through javascript. it is based on CSS syntax but little different.
https://reactnative.dev/docs/getting-started


section3:
The 2 paths


