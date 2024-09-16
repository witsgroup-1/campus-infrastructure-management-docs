

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


### Maintenence Reports
- make a report: (report fields: Name and Surname, Report Type, Venue, Description), (generated data with report: createdAt timestamp, status, userId of user who submitted the issue, log ticket information).
- log page: shows the status of a maintenance request as a log. If you click on the maintenace log you can see more information and set its status, the staff assigned, and when it is scheduled to be done.

### Notifications