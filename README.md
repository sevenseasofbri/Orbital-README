![Poster](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/itigen.png)


# Welcome to Pyroclastic Nerds' itigen

## Team Members
### Leah Roselyn James and Vishruti Ranjan
## Proposed Level of Acheivement
### Apollo 11
## Tech Stack
This project is fuelled by [ReactJS](https://reactjs.org/), [ExpressJS (NodeJS)](https://expressjs.com/) and [MySQL](https://www.mysql.com/).
- **Why React?** ReactJS has extensive documentation and a large community of users to aid in online learning as compared to others such as Angular etc. Features such as being able to change data without reloading the page are in-line with features we want to implement in our application.
- **Why Express?** We had initially decided to use PHP, but on further research, after liftoff we decided to go with Express JS as our backend framework. This would help us maintain a sense of consistency as both React and Express are based on JavaScript.
- **MySQL?** It is one of the most widely used databases in the world as well as relatively simple to use.
## What has changed since Milestone #1?
After careful consideration, reading feedbacks and constant deliberation, we have reimagined the purpose this application was meant to solve. A common critique was that the application did not provide adequate portability through smartphones. Thus, slightly changing our course of direction- but keeping the basic aspects of our initial features. The core feature of our app no longer focuses only our generated itinerary but shares equal weightage with our newer features like importing to google calendar, setting reminders via Telegram, suggested places and downloadable PDF. This would mean we would steer away from the many constraints that our algorithm would have otherwise taken into consideration and rather focus our time and energy by distributing equal efforts to implement all these features for an all round user experience.
### Our Updated Poster with New Features
![Poster](https://github.com/sevenseasofbri/Orbital-README/blob/master/poster.png)

## Motivation
As two international students in Singapore, we realised the difficulty of planning schedules with limited knowledge of places of interest in Singapore. To ease this process of travelling, we were highly motivated to create an _Itinerary Planning Web Application_ that would help travellers plan their journey **anywhere in the world** in a personalised and effective manner.

## Aim
Our aim is three fold:
- To create an optimised itinerary using [Google Maps API](https://developers.google.com/maps/documentation) based on time of transit and opening/closing hours of the places.
- In addition to this, we aim to enable portability of the generated itinerary by importing it to the user's Google Calendar OR enabling PDF download OR sending reminders via Telegram bot.
- To develop a personal user experience with suggested places and points of interest.

## Target Audience
All people who want to be able to manage their travel with efficiency with the use of a web application. Here, efficiency translates to be able to get suggested places for travel, generate itinerary as well as provide the itinerary to the user in an appropriate manner.

## User Stories
1. As busy businessperson, whilst on trips, I really want to be able to plan my travel itinerary _easily on the go and accessible on a platform like Google Calendars_ rather than having to write it down and fear missing something out.
2. As a resident in a new city, I want to be able commute to run my errands in a timely fashion with a _optimised schedule_.
3. I love to travel but I often forget when I'm supposed to be where. I wish I had a _reminder on my phone that woud alert me according to the itinerary_ I have planned.
4. As an intrepid traveller, I want to be able to access my planned itineraries _by downloading it to a local device_, even when I do not have quick access to WiFi/Cellular data, instead of hunting for hotspots or free WiFi areas.
5. I am interested in exploring the city I wish I could have a app that allows me to _search for places of interest and add them to my list within the same website_ without migrating back and forth between different sites.

## Why our Itinerary Generator?(Unique Selling Points)
1. Unlike popular websites like [Itineree](http://itineree.com/) and [Tripomatic](https://maps.sygic.com/?utm_source=content-pages&utm_medium=cta&utm_campaign=homepage#/?map=12,1.32568,103.846519) which require the user to install their mobile apps to sync their own implemented calendars; our application allows the user to sync their itinerary to their Google Calendar (more widely present on people's mobile phones, and user friendly).
2. We are also planning to create a Telegram Bot to remind the user as and when they have to go to the next location. This offsets our application from the others, as it integrates a more interactive and personal idea, via messaging.

## Features
- Creates a personalised and optimal itinerary based on: _travel time_ and _opening/closing hours_.
- Suggests places to travel to based on user inputs.
- Integration with Google Calendar: The itinerary can be accessed on any device that uses Google and provides a familiar UI/UX experience for the user (Reduces storing in flies like PDFs and gives a more on-the-go experience).

### What if I don't have a Google Account?
- Downloadable: The app also provides the option of downloading the itinerary as a PDF.
- Telegram Bot: An additional feature to remind the user of the events they have to attend.

## Previous Timeline
Features to be completed by the end of June.
- Login and logout + database configuration.
- Basic algorithm for itinerary generation and testing. 
- Implementation of Google Maps API key and its functions into the Web page.
- Implementing Calendar to display Itinerary.

Features to be completed by the mid of July:
- Complete Design(UI/UX)  of Webpage.
- Add suggested places and blog like format.
- Telegram notifications.
- Download PDF option.
- More testing of cases.

## New Timeline
### Features that have been Completed

1. **_Basic Algorithm for Itinerary Generation_**
 Due to time constraint (aka Special Term for both of us) we decided to implement Dijkstra's algorithm for optimising the itinerary. 
  - **Need for this Feature:** An important part of this web application is to be able to produce an ideal itinerary for a user. Therefore, it is imperative to have a basic algorithm for itinerary generation.
  - **Links to User Story 2**
```
# Note: All nodes on a map are assumed to be connected, therefore creating a complete connected graph.
# n is the number of places input by the user
# nodes[] is an array of nodes (places) entered by the user
# final[] stores final itinerary
initial: index=0
LOOP( i from 1 to n times){
  Using Dijkstra(node[index]) find closest Node in array of Nodes store the _value_
  splice(node[index])
  final.push(node[index])
  index <= indexOf(_value_)
}
```
Therefore, currently it takes only travel time into consideration. We plan to add the opening/closing hours constraint in the next phase for the final milestone.

2. **_Implementation of Google Maps API Key and its Functions_**
Our current implementation uses Google Places Autocomplete API for the user to be able to enter places they want to visit. The results from this are stored in an array of places, from which information of latitudes/longitudes are used for geocoding with NPM package - [geolib](https://www.npmjs.com/package/geolib). Apart from this, we will be able to retrieve information like opening/closing hours as a constraint to implement in the next phase.
 - **Additional feature:** Delete location is the user has a change of mind after adding the location to the itinerary in th eplanning stages.
 - **Need for these features:** Provides an interactive platform for users to enter names of places with suggestions. Moreover, all the APIs are important on the backend side of things as information procured from them aids in itinerary generation.
 - **Links to User Story 1**
![Delete Feature](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(305).png)

3. **_Implementing Google Calendar_**
This allows the user to import the generated itinerary to the Google Calendar which is accessible both as an app and as a website. We use the [Google Calendar API](https://developers.google.com/calendar) which implements safe login to the users account using [OAuth2](https://developers.google.com/identity/protocols/oauth2) and allows the Itinerary Generator to create an event in your Google calendar.
 - **Need for this feature:** From our previous milestone, a common suggestion was to make the application more portable such that it may be used on a smartphone. We decided that syncing our application with a widely used app like Google Calendar would allow users to access their itinerary from the comfort of any device.
 - **Other Calender exmaples in detail can be seen in the video**
 
 - **Picture below links to User Story 3:** A week ago, on the 22nd of June while we were **performing unit testing** for Google Calendera we put a notification called "Egg" with a random address for the 26th. We forgot about it later but on **the 26th of June we received a reminder and realised how useful the feature was** and decided to take a screen shot to **link this to the user story mentioned to demostrate how it can be a useful tool to keep track of a schedule**.

 
![Reminder](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/photo6328029699976047138.jpg)


4. **_Downloadable PDF_**
There will be an option to allow the user to download the created itinerary locally onto their devices in PDF format. 
 - **Need for this feature:** In the event a user does not have Telegram OR a Google Account, they can choose to store their generated itinerary locally on their device. Moreover, it will be useful if the user does not have access to internet and cannot open the Web-App to find their saved itinerary.
 - **Links to User Story 4**
  
![Download pdf](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(306).png)

5. **_Login/Logout_** (**Security feature**)
This feature had already been implemented in the last phase of the project. This feature is required to store user information and places preference data to help give good suggestions on the home-page (read: Point 5, Features to be Completed).
- **Testing:** Incorrect inputs during login prompts an incorrect input alert and redirects back to the Registration page. 

![Invalid User alert and redirection](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(309).png)

### Features to be Completed (Ideally by Milestone #3)

1. **_Addition of Constraints to Itinerary Generation_**
As mentioned before, we plan to take into consideration opening/closing hours of places the users want to visit to help generate the desired itinerary. This will require us to revamp our algorithm to withstand more testing in terms of accuracy (eg. Restaurant timings). We will alert the user if the timings do not fit the constraints so thatt the user can make the relevant changes in timings.
  - **Need for this feature:** To improve quality of itinerary created and make it more accurate and usable as possible.
  - **Links to User Story 2**
2. **_Complete UI/UX of the Website_**
Our current method of input is quite cumbersome for the user to enter values. We plan to fix this by the next milestone and provide a pleasant UI/UX experience for our users!
  - **Need for this to be Implemented:** It is imperative for a good website to provide its users an enjoyable experience while using it. We intend to redesign some parts of the website to make it user friendly especially the itinerary section.

3. **_Telegram Notifications_**
We plan to create a telegram bot linked to this application which will remind the user of the events they have scheduled using the application, notification will be sent they are supposed to start spending time in that places and a notification will be send when they are supposed to leave. These timings will be inputted by the user itself according to his preferences. Can be seen in the video 
  - **Need for this feature:** The integration of our Web App with Google Calendar came with its own set of drawbacks. This would mean people who do not have Google Accounts will not be able to view/store thier itinerary in an effective manner (like, on their phones). As creators, we cannot favour a certain population of users and must aim to take everyone into account. Telegram is a widely used application for messaging and bots alike, therefore we decided that it was necessary we include this feature.
  - **Links to User Story 3**
  
4. **_HomePage with Suggested Places_**
We plan to add suggested places on the home page for the user either based on previous searches, repeated locations or current location of the user. These places of interests will show up as tiny boxes to choose or click on to find more information. This will act as the homepage when the user first does a login. The user can either input a location around which he/she wants to visit places or interest or if nothing is inputted then the places of interest are based on the users current location and previous itinerary.
  - **Need for this feature:** This will make the homepage rather visually pleasing and will create a personalised experience for them.
  - **Links to User Story 5**
  
5. **_TESTING_**
While this is may not be a feature, it is important that before the application goes into deployment, although we have done quite a bit of testing, more extensive (automated) testing of cases has to be done for Milestonee 3 which will see more integration of our features. This will help us clear out any bugs, hiccups and loose ends in our codes and remove them in time for the future.


## Software Engineering Practices and Principles applied :

### Project Management and Programming Practices
We have used GitHub to handle our project with efficiency, by the next milestone we will be able to make our repository public. **Right now, we have sensitive information like API keys whose usage directly translates to our billing amount on Google Cloud (^_^").**
We took the feedback from Milestone 1 and decided to ensure documentation and keep track of our features through trello and a more detailed README.

- **Github**
![github](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(154).png)

![github](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(155).png)

- **Trello**
![trello](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(153).png)


### Agile Design Principles Used Primarily

1. Dependency Injection: We have decoupled most dependencies. We have ensured that there is **no cyclic dependency** to ensure **smooth bottom-up testing** of our unit tests. Although there was a single dependency in the cases where the calendar and pdf generation depend on the itinerary stored in the class.

2. Single Responsibility Principle: All our class components have a single responsibility allocated to them with all the code split between Profile.js, Register.js, Login.js, Intinerary.js, and UserFunctions.js. Each class Component is responsible for a **single responsibility** as evident by their names.

**As we progress and add more features we will follow  Liskov's Substitution Principle while implementing class single dependence.**

### Current Testing and Security Features 

1. Like many programs, ours had bugs like delayed responses in autocomplete and the coordinate searching. We were able to fix those bugs through tracking via **console.log()** and performed at least **30 different unit location testing** to ensure that our algorithm was working as it was supposed to. This was followed by **integration testing**  with other features like calendar and download PDF and a additional **15 rounds of manual acceptance tesing** before we recorded our video. **Typically system testing was performed everyday atleast 10 times in the last week owing to most of the features we implemented this week.**

2. Our Calendar features also had unknown bugs to begin with like the **feature of reccurrence** that we had to disable. We tested the ability of it to **set reminders and we were able to receive those notifications** on our mobile Phones. This was resolved again with **intergartion and system testing** as it depended on the itinereary stored.

**Security feature** 

3. For our Login page, if the backend detects that the **user is not registered an incorrect input alert and redirects back to the Registration page**. This feature can be seen in the video. We also used **jwt auth to ensure that user information is kept private through encoding and decoding during Login/Registration**.
