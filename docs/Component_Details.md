

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
schedule timetable: a table is present showcasing all the timetables that a user has made. This includes the day, date, course, venue and times, as well as a delete button to remove a schedule. At the bottom, there is a button that takes the user to the form to add a schedule.


### Maintenence
- make a report: (report fields: Name and Surname, Report Type, Venue, Description), (generated data with report: createdAt timestamp, status, userId of user who submitted the issue, log ticket information).
- log page: shows the status of a maintenance request as a log. If you click on the maintenace log you can see a popup with more information and set its status, the staff assigned, and when it is scheduled to be done (you can edit these respective fields) and then save changes and close the popup.

#### How it wad implemented
Maintenance Report:
- The frontend makes a fetch request of type POST to the API, with the inputed values from the html form once the submit button has been clicked. The form input will clear with the submission.
Maintenance Logs:
- The form does a fetch request of type GET for all maintenance requests. They will display in different colummns depending on their status ("Scheduled", "In Progress")


### Notifications




## User Guides

### Schedule
- Open the sidebar on the main dashboard and click on "Schedules".
- Here, you will be able to view all created schedules.
- On each row, there is a button with a bin. Click on this button in order to delete a schedule. You will be asked to confirm your deletion: click yes (or cancel if you do not want to).
- Beneath the table is a button which says "Add a Schedule". Clicking this button will take you to a new page with a form.
- Type in your name, the course of the schedule and the venue where it will be held. Select a day from the drop-down. You can use the clocks under "Time" to choose a time or input your own time directly. You can click the calendar to choose a date or input your own date.
- Then if your schedule is one that recurs weekly, click "yes" on the Recurring dropdown. This will casue another Date picker to appear. Here you must choose the date that your last schedule will be held on. Otherwise, if your schedule is only for one day, choose "no".
- Once the form is fully filled out, you can click the "Submit" button to add your new schedule.


### Maintenance
