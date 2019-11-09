This application is a Day Planner that stores user data by the hour, and color codes each hour relative to the actual time. 

It uses moment.js to compare the time to the relevant ID and localStorage to save the user input even after a refresh.

Line 71
The below function is just for creating a shadow under each div as the user hovers over each block.

Line 77
This section adds a click function to the saveBtn and takes the value of userInput, and the ID of it's parent, and saves a key pair into localStorage.

Line 83
The following lines are not very DRY but I like the simplicity and readability that it provides.
I'm using jQuery to select elements with a class of userInput and also the ID that corresponds to the hour that is being saved.
Then we get the value from local storage for each.

Line 94
This function is what compares the hour ID to the current hour via moment.js
Here we declare variable 'blockHour' and 'currentHour' 
blockHour takes the ID and parses it into a number so that we can compare it to the currentHour, which is determined by moment.js, all we have to do is format it with the format method to get an output that should be easy to compare.

Next is a conditional statement that says if the blockHour is less than the currentHour we should add the class "past" as well as the bootstrap class of "bg-light"

We then go through all the possibilities assigning new classes so we can color code the past present and future hours.

Technically the classes of past present and future are useless, they were originally there so that I could easily test if the classes were being applied.

Line 111
This simple function updates the page every 100 milliseconds. I guess that makes it a little bit resource hungry, but for testing purposes I wanted it to basically update immediately. I was originally testin with a refresh rate of a minute, but it made testing the program more difficult.