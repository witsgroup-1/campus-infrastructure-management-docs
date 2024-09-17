

# Component Details :wrench:

---

## Details of Features

### Login

- authentication:
- whitelist: certain emails that are not The University of Witwatersrand affiliated will be whitelisted if they have valid reason to use the university's services e.g. guest lecturers
- required information:

### Users

- Student: Permissions ->
- Student (tutor): Permissions ->
- Staff (Lecturer): Permissions ->
- Staff: Permissions ->

### Book Venues


#### Venue Types

- Lecture Halls
- Tutorial Rooms
- Computer Laboratories
- Chemistry Laboratories
- Conference rooms
- Study rooms
- Exam Halls
- ...

### Schedule Integration
- create a schedule: (Name and Surname, course, venue, day of the week, times, date and recurrence). 'Time' type is used to input the times and 'date' type is used to input a date. If recurrence is "yes", then option to add an end date is added. Lastly, there is a submit button to add the information to the database.
schedule timetable: a table is present showcasing all the timetables that a user has made. This includes the dy, date, course, venue and times, as well as a delete button to remove a schedule. At the bottom, there is a button that takes the user to the form to add a schedule.


### Maintenence
- make a report: (report fields: Name and Surname, Report Type, Venue, Description), (generated data with report: createdAt timestamp, timestamp set to today, status, userId of user who submitted the issue).
- log page: shows the status of a maintenance request as a log. If you click on the maintenace log you can see a popup with more information and set its status, the staff assigned, and when it is scheduled to be done (you can edit these respective fields) and then save changes and close the popup.

#### How it wad implemented
Maintenance Report:
- The frontend makes a fetch request of type POST to the API, with the inputed values from the html form once the submit button has been clicked. The form input will clear with the submission.
Maintenance Logs:
- The form does a fetch request of type GET for all maintenance requests. They will display in different colummns depending on their status ("Scheduled", "In Progress")
- All the data will appear as grey blocks depicting the venue the request is for and the timestamp of when the request was created in the Scheduled Column or the timestamp for when it will be completed or when it wad completed in "In progress" and "Completed" respectively. This is done using the .filter method to check the json data for these headings.
- If the content is desktop they will be all outputted but if it is mobile then only one in each column will appear until you click "show more". So we baisically have two functions to handle the general display of the data in the columns.
- These desktop and mobile display functions call a function to create a Request Block which will baisically dynaimally create the html and CSS tailwind style for the request blocks that appear in the columns. The method also calls the Open Popup function.
- The Open Popup function allows each maintenance request to be clicked so that more information can be displayed such as the venue, the issue type, the problem description, who it was assigned to, the status ("Scheduled" etc.), the created at timestamp if in the scheduled status column or the timestamp otherwise. In this popup you can edit the time (unless it is in "Scheduled"), who it is assigned to and the status. Once edited Click save changes to reload the page - else if not editing click close.
- 

### Notifications




## User Guides

### Maintenance
