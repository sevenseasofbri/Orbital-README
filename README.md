# Welcome to Pyroclastic Nerds' Itinerary Generator
## Team Members
### Leah Roselyn James and Vishruti Ranjan
## Proposed Level of Acheivement
### Gemini
## Tech Stack
This project is fuelled by [ReactJS](https://reactjs.org/), [NodeJS](https://nodejs.org/en/) and [MySQL](https://www.mysql.com/).
## Motivation
As two international students in Singapore, we realised the difficulty of plannig schedules with limited knowledge of Singapore. To ease this process of travelling, we were highly motivated to create an _Itinerary Planning Web Application_ that would help travellers plan their journey in a personalised and effective manner.
## Aim
Our aim is two fold:
- To create a highly optimised itinerary using [Google Maps API](https://developers.google.com/maps/documentation) based on time of transit and opening/closing hours of the places.
- In addition to this, we aim to enable portability of the generated itinerary by importing it to the user's Google Calendar OR enabling PDF download.
## User Stories
1. As busy businessperson, whilst on trips, I really want to be able to plan my travel itinerary _easily on the go and accessible on a platform like Google Calendars_ rather than having to write it down and fear missing something out.
2. As a resident in a new city, I want to be able commute to run my errands in a timely fashion with a _highly optimised schedule_.
3. As an intrepid traveller, I want to be able to access my planned itineraries _by downloading it to a local device_, even when I do not have quick access to WiFi/Cellular data, instead of hunting for hotspots or free WiFi areas.
## Why our Itinerary Generator?
1. Unlike popular websites like [Itineree](http://itineree.com/) and [Tripomatic](https://maps.sygic.com/?utm_source=content-pages&utm_medium=cta&utm_campaign=homepage#/?map=12,1.32568,103.846519) which require the user to install their mobile apps to sync their own implemented calendars; our application allows the user to sync their itinerary to their Google Calendar (more widely present on people's mobile phones, and user friendly).
2. We are also planning to create a Telegram Bot to remind the user as and when they have to go to the next location. This offsets our application from the others, as it integrates a more interactive and personal idea, via messsaging.
## Features
- Creates a personalised and optimal itinerary based on: _travel time_ and _opening/closing hours_.
- Integration with Google Calendar: The itinerary can be accessed on any device that uses Google and provides a familiar UI/UX experience for theh user (Reduces storing in flies like PDFs and gives a more on-the-go experience).
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
 ### Current Implemented Features
 
 1. _Basic Algorithm for Itinerary Generation_
 Due to time constraint (aka Special Term for both of us) we decided to implement  Dijkstra's algorithm for optimising the itinerary. 
 
Therefore, currently it takes only travel time into consideration. We plan to add the opening/closing hours constraint in the next phase for the final milestone.
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

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/sevenseasofbri/Orbital-README/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
