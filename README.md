# Welcome to Pyroclastic Nerds' itigen
![Poster](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/itigen.png)

## Team Members
### Leah Roselyn James and Vishruti Ranjan
## Proposed Level of Acheivement
### Apollo 11
## Tech Stack
This project is fuelled by [ReactJS](https://reactjs.org/), [ExpressJS (NodeJS)](https://expressjs.com/) and [MySQL](https://www.mysql.com/).
- **Why React?** ReactJS has extensive documentation and a large community of users to aid in online learning as compared to others such as Angular etc. Features such as being able to change data without reloading the page are in-line with features we want to implement in our application.
- **Why Express?** We had initially decided to use PHP, but on further research, after liftoff we decided to go with Express JS as our backend framework. This would help us maintain a sense of consistency as both React and Express are based on JavaScript.
- **MySQL?** It is one of the most widely used databases in the world as well as relatively simple to use.
In addtion to this, our application uses the following API:
- [Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript/overview): To provide accurate details of distances between places, place details and to autocomplete places searched by the user.
- [Material UI](https://material-ui.com/): To create a clean and user-friendly environment in the application. Provides react components fro easier and effective web development.
## What has changed since Milestone #2?
Based off the constructive feedback, the purpose of our application seemed to be fitting for the intended audience. So, we decided to continue in the same trajectory as planned. However, we did not realise that some things we planned to do were a bit of a stretch as they had a completely new tech stack to learn. In retrospect, we should have put a little thought into the complexity of implementation rather than the idea itself. Alas! We had to forgo the feature of the Telegram Bot for reminders.
Sadness aside, we did focus a lot more on the user interface and experience as well as the optimisation algorithm for the itinerary. This made our application visually pleasing and easy to use!
### Our Updated Poster with Modified Features
![Poster](https://github.com/sevenseasofbri/Orbital-README/blob/master/poster.png)

## Motivation
As two international students in Singapore, we realised the difficulty of planning schedules with limited knowledge of places of interest in Singapore. To ease this process of travelling, we were highly motivated to create an _Itinerary Planning Web Application_ that would help travellers plan their journey **anywhere in the world** in a personalised and effective manner.

## Aim
Our aim is three fold:
- To create an optimised itinerary using [Google Maps API](https://developers.google.com/maps/documentation) based on time of transit and opening/closing hours of the places.
- In addition to this, we aim to enable portability of the generated itinerary by importing it to the user's Google Calendar OR enabling PDF download.
- To develop a personal user experience with suggested places and points of interest.

## Target Audience
All people who want to be able to manage their travel efficiently with the use of a web application. Here, efficiency translates to be able to get suggested places for travel, generate itinerary as well as provide the itinerary to the user in an appropriate manner.

## User Stories
1. As busy businessperson, whilst on trips, I really want to be able to plan my travel itinerary _easily on the go and accessible on a platform like Google Calendars_ rather than having to write it down and fear missing something out.
2. As a resident in a new city, I want to be able commute to run my errands in a timely fashion with a _optimised schedule_.
3. I love to travel but I often forget when I'm supposed to be where. I wish I had a _reminder on my phone that woud alert me according to the itinerary_ I have planned.
4. As an intrepid traveller, I want to be able to access my planned itineraries _by downloading it to a local device_, even when I do not have quick access to WiFi/Cellular data, instead of hunting for hotspots or free WiFi areas.
5. I am interested in exploring the city I wish I could have a app that allows me to _search for places of interest and add them to my list within the same website_ without migrating back and forth between different sites.

## Why our Itinerary Generator?(Unique Selling Points)
1. Unlike popular websites like [Itineree](http://itineree.com/) and [Tripomatic](https://maps.sygic.com/?utm_source=content-pages&utm_medium=cta&utm_campaign=homepage#/?map=12,1.32568,103.846519) which require the user to install their mobile apps to sync their own implemented calendars; our application allows the user to sync their itinerary to their Google Calendar (more widely present on people's mobile phones, and user friendly).
2. Our application provides 2-way customisation- one through the user deciding the timings of their trip and the other generating timings for the trip based on opening and closing hours.
## Link to frontend repo
We ran into some issues during deployment, while we have our full repository with backend and frontend available (linked in Programming Practices section) we thought it would be easier for people to try out the application without having to create a table in MySQL and running Apache to set up login/logout. So we decided to provide a version of the application that can simply be updated with **npm insatll** and then run with **npm start** to try out the frontend features.[Click here] (https://github.com/rosejtec/itigen_frontend).
## Brief Introduction To Features 
- 2 Way optimisation by creating a personalised and optimal itinerary based on _travel time_ OR generating a schedule based on _travel time_ AND _opening/closing hours_.
- Suggests places to travel to based on user inputs.
- Integration with Google Calendar: The itinerary can be accessed on any device that uses Google and provides a familiar UI/UX experience for the user (Reduces storing in files like PDFs and gives a more on-the-go experience).

### What if I don't have a Google Account?
- Downloadable: The app also provides the option of downloading the itinerary as a PDF.

## Overall Timeline With Features
### Features Completed in Milestone#2 + Modifications for Milestone#3
**1. _Basic Algorithm for Itinerary Generation_**
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
This algorithm takes only distance into consideration. Since this is a less constrained method of generating an itinerary,it gives room for users to customise. So we give users a choise as to whether they want to optimise by distance only or both distance and opening hours. 
-**Concerns:**
1. There is an excessive use of submit buttons for each place. Won't this hamper the UI/UX experience for the user?
Ans: Yes, we do agree. In Milestone#3 we revamped this entire system. While we still wanted to have a single confirm button for all the values of time, we opted for a confirm button for each row. This was done keeping in mind Current Object State Bug (Discussed in Bugs and Difficulties Encountered). The end result is still a cleaner interface, rather than the excessive submit buttons.
**[IMAGE HERE]**
2. If the user inputs overlapping/non chronological times, then what will happen?
Ans: First off, thank you for this feedback, we had completely missed this out in the last Milestone. Now we do check if the timeslots overlap when 'Add Itinerary' or 'Download PDF' is pressed and supply an error message telling users that the timings overlap. Then requires the users to re-enter values of time.
**[IMAGE HERE]**
3. Will the user be able to manually reorder the places?
Ans: Unfortunately no, this is because of the presence of the Current Object State Bug (Discussed in Bugs and Difficulties Encountered). While this may limit the app's pontential to customise the schedule, we tried to enable flexibility by providing 2 different methods of customisation.
**[IMAGE HERE]**

**2. _Implementation of Google Maps API Key and its Functions_**
We implemented Google Places Autocomplete API for the user to be able to enter places they want to visit. The results from this are stored in an array of places, from which information of latitudes/longitudes are used for geocoding with NPM package - [geolib](https://www.npmjs.com/package/geolib). 
Furthermore, we implemented [Google Maps Places API](https://developers.google.com/places/web-service/details) to obtain place details and thereby optimise the itinerary based on opening and closing hours. A more detailed look into this is in the section "Features completed in time for Milestone#3."
 - **Additional feature:** Delete location is the user has a change of mind after adding the location to the itinerary in th eplanning stages.
 - **Need for these features:** Provides an interactive platform for users to enter names of places with suggestions. Moreover, all the APIs are important on the backend side of things as information procured from them aids in itinerary generation.
 - **Links to User Story 1**
 
![Delete Feature](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(168).png)
**[IMAGE HERE]**

**3. _Implementing Google Calendar_**
This allows the user to import the generated itinerary to the Google Calendar which is accessible both as an app and as a website. We use the [Google Calendar API](https://developers.google.com/calendar) which implements safe login to the users account using [OAuth2](https://developers.google.com/identity/protocols/oauth2) and allows the Itinerary Generator to create an event in your Google calendar.
 - **Need for this feature:** From our previous milestone, a common suggestion was to make the application more portable such that it may be used on a smartphone. We decided that syncing our application with a widely used app like Google Calendar would allow users to access their itinerary from the comfort of any device.
 - **Other Calender examples in detail can be seen in the video**
 - **Picture below links to User Story 3:** A week ago, on the 22nd of June while we were **performing unit testing** for Google Calender we put a notification called "Egg" with a random address for the 26th. We forgot about it later but on **the 26th of June we received a reminder and realised how useful the feature was** and decided to take a screen shot to **link this to the user story mentioned to demostrate how it can be a useful tool to keep track of a schedule**.

 
![Reminder](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/photo6328029699976047138.jpg)

- **Concerns:** For adding the itinerary to the Google Calendar, the user has to sign in repeatedly. Won't this be cumbersome?
Ans: In the video for Milestone#2, we did everything in a Guest Browser. This required us to sign in to our Google Account. However, the in a regular browser, OAuth does not require the user to sign in again. An example of this will be in the video.

**4. _Downloadable PDF_**
There will be an option to allow the user to download the created itinerary locally onto their devices in PDF format. 
 - **Need for this feature:** In the event a user does not have Telegram OR a Google Account, they can choose to store their generated itinerary locally on their device. Moreover, it will be useful if the user does not have access to internet and cannot open the Web-App to find their saved itinerary.
 - **Links to User Story 4**
  
![Download pdf](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(306).png)

**5. _Login/Logout_** (**Security feature**)
This feature had already been implemented in the phase 1 of the project. This feature is required to store user information and places preference data to help give good suggestions on the home-page (read: Point 5, Features to be Completed).
All passwords are encrypted and the database server uses TCP/IP abstraction layers for routing and switching. 
- **Testing:** Incorrect inputs during login prompts an incorrect input alert and redirects back to the Registration page. 

![Invalid User alert and redirection](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(167).png)

### Features Completed in Time for Milestone#3

**1. _Addition of Constraints to Itinerary Generation_**
Accuracy plays an important factor in optimising an itinerary. While the basic generation algorithm provided a distance-based solution, the need for taking opening/closing hours of places is necessary to provide a better schedule. Another thought was that an increase in constraints largely constricts the users from customisation. Therefore, we provide users an option: either customising the itinerary ordered based on distance OR generating an itinerary optimised based on opening and closing hours and distance. 
The same algorithm was used to rank places according to distance. We decided to sort the places according to closing hours, giving each a priority. So a place that closes early would be given a higher rank than places that close later or are open 24 hours. A simple insertion sort was employed to sort closing hours because we are working with smaller values of N and we aim to avoid overhead recursive function calls with sorts like quicksort. 
Now that both priority ranked lists have been obtained based on distance and opening_hours, we perform rank multiplication. That is, a multiplicative score function is used to determine the rank of the place in the final list. This is chosen over a additive score function because we can obtain a more accurate relative rank for each place rather than a more absolute one. 
Once the places have been ranked, the user enters the time they want to spend at each place and start time of their trip. Following this, the timings are calculated without the user having to enter each timing.
  - **Need for this feature:** To improve quality of itinerary created and make it more accurate and usable as possible.
  - **Links to User Story 2**
  **[IMAGE]**
- **Concerns:** The previous Milestone's feedback voiced an apt concern: Some places do not have opening/ closing hours? How are we going to account for that? Keeping that in mind we did a little bit of research and here's what we found:
We obtain the details of the places using Google Places API. A place request is initiated with the place id. This Place Details request returns more comprehensive information about the indicated place such as its complete address, opening_hours, phone number, user rating and reviews. Based on this, we found that there are 2 instances where one can say that a place does not have opening/closing hours:
1. When the request returns a NULL/ undefined value under opening_hours then this means the result was not received quick enough OR theres a Google 403 forbidden error, which occurs when the server is receiving too many request and refuses to connect. Alternatively, Google PlacesAutoComplete occasionally lags and returns a null place_id, without which we many not be able to send a request. Taking these issues into consideration, it was decided that in the event any of this occurs, the application  ignores the place altogether/ removes it from the list. (More about Google Request Lag in Problems Faced)
2. When a place is open 24/7 like parks, hospitals, cinema halls etc. A place_id request for place_details returns a result. This result has an object called opening_hours. Under opening hours we have an array periods[] describing HHMM values called day, open and close. In the case that the place is open 24/7, the values for day=0, open=0000 and close = undefined. So we have a check for this and all 24 hour places are "lower priority" under the visiting schedule.

**2. _Complete UI/UX of the Website_**
Not a feature, but an important part of our project that was completely revamped since last time. We tried to make everything as user friendly as possible to privde an all-round user experience. 
  - **Need for this to be Implemented:** It is imperative for a good website to provide its users an enjoyable experience while using it. We redesigned some parts of the and made it user friendly especially the customise and generate section.
  
**3. _HomePage with Suggested Places_**
The main aim for this feature is it allows users to explore places they want to vist and even get visual data like pictures of these places. This feature has been implemented using Cards in Material UI. A card contains information and actions related to a single topic. We display cards based on places 
  - **Need for this feature:** This will make the homepage rather visually pleasing and will create a personalised experience for them.
  - **Links to User Story 5**
  
**4. _TESTING_**


## Bugs and Difficulties Encountered
1.**Asynchronous functions**: All of our google Places functions were asynchronous. Because it was our first time encoutnering this in a practical set up, it took us a few days to learn about the use of **"Promises"**. When we implemented it, most of our lags and bugs relating to our google functions disappeared.

2.**Google ERROR 403**: To our surprise we found out in the midddle of Milestone 1 that Google may not always return a value if they get too many requests from many local hosts. Inspite of keeping within our daily request limit, there were times when ERROR 403 was returned and we had to test our product for those unlikely situations also. These errors are beyond us and we just have to accept them as trail users for Google Places API. Only paid users are guareenteed surety of response.



## Software Engineering Practices and Principles Applied 

### Program Flow and Design 

1. This is a detailed Program Flow of our app currently. Looking at this should five any first time user a good idea of what our web application does.
![trello](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/OrbitalMilestone2.png)

### Project Management and Programming Practices
We have used GitHub to handle our project with efficiency, by the next milestone we will be able to make our repository public. **Right now, we have sensitive information like API keys whose usage directly translates to our billing amount on Google Cloud (^_^").**
We took the feedback from Milestone 1 and decided to ensure documentation and keep track of our features through trello and a more detailed README.

- **Github**
![github](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(154).png)

![github](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(155).png)

- **Trello**
![trello](https://github.com/sevenseasofbri/Orbital-README/blob/master/Images/Screenshot%20(164).png)


### Agile Design Principles Used Primarily

1. Dependency Injection: We have decoupled most dependencies. We have ensured that there is **no cyclic dependency** to ensure **smooth bottom-up testing** of our unit tests. Although there was a single dependency in the cases where the calendar and pdf generation depend on the itinerary stored in the class.

2. Single Responsibility Principle: All our class components have a single responsibility allocated to them with all the code split between Profile.js, Register.js, Login.js, Intinerary.js, and UserFunctions.js. Each class Component is responsible for a **single responsibility** as evident by their names.

**As we progress and add more features we will follow  Liskov's Substitution Principle while implementing class single dependence.**

### Current Testing and Security Features 
**1. Unit/Integration/System/Acceptance testing**

- Like many programs, ours had bugs like delayed responses in autocomplete and the coordinate searching. We were able to fix those bugs through tracking via **console.log()** and performed at least **30 different unit location testing** to ensure that our algorithm was working as it was supposed to. This was followed by **integration testing**  with other features like calendar and download PDF and a additional **15 rounds of manual acceptance tesing** before we recorded our video. **Typically system testing was performed everyday atleast 10 times in the last week owing to most of the features we implemented this week.**

- Our Calendar features also had unknown bugs to begin with like the **feature of reccurrence** that we had to disable. We tested the ability of it to **set reminders and we were able to receive those notifications** on our mobile Phones. This was resolved again with **integration and system testing** as it depended on the itinereary stored.

- For the Intinerary, the overapping of times and invalid times was also tested in the case that the user accidentaly inputs the wrong time an alert message pops and informs the user. Then the user enters the times again.

**2. Security feature**  

- For our Login page, if the backend detects that the **user is not registered an incorrect input alert and redirects back to the Registration page**. This feature can be seen in the video. We also used **jwt auth to ensure that user information is kept private through encoding and decoding during Login/Registration**.

###

