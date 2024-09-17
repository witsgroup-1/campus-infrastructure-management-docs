# Component Details :wrench:

---

## Details of Features

## Onboarding Process

The onboarding process is designed to gather essential information from users before they can fully access the site's features. It involves a step-by-step form that users must complete. The onboarding process is intended for new users accessing the site for the first time. If this is not the first time using the site, they are led to their dashboard. After completing the onboarding process, the page redirects to the dashboard.

### Login

- **Authentication**: Users must log in using their credentials. The system whitelists certain emails not affiliated with The University of Witwatersrand if they have a valid reason to use the university's services (e.g., guest lecturers).
- **Required Information**: Users will need to provide their name, surname, faculty, role, and optionally check if they are a tutor or lecturer.

### Users

- **Student**: Permissions include accessing study resources, booking venues, and participating in academic activities.
- **Student (Tutor)**: Additional permissions for tutoring activities and resources.
- **Staff (Lecturer)**: Permissions include booking venues, managing academic schedules, and accessing staff resources.
- **Staff**: Permissions include managing staff activities and accessing staff resources.

### User Acceptance Tests

#### As a Student

1. **Onboarding Process**: 
   - As a student, I can go through the onboarding process the first time I access the site. This process will collect my basic information and set up my account, allowing me to use the site's features.

#### As a Lecturer

1. **Onboarding Process**:
   - As a lecturer, I can complete the onboarding process when I first access the site. This will include specifying my faculty and role, and optionally indicating if I am a tutor or lecturer. This setup will allow me to access and use all relevant site features.

#### As a Staff Member

1. **Onboarding Process**:
   - As a staff member, I can complete the onboarding process upon first accessing the site. I will need to provide necessary information and complete any optional sections to fully access the site's features.

## Book Venues

#### User Acceptance Tests

As a **Lecturer**, I can:

1. **Search for a Venue**: 
   - I can use the search bar to find available rooms by name or category, such as chemistry laboratories or lecture halls.
   - The system will display only rooms that match my search query and selected filters.

2. **Filter by Room Type**: 
   - I can filter the search results by room type, for example, selecting only "Chemistry Laboratories" or "Lecture Halls."
   - When I select a filter, only venues that match the room type will appear in the list.

3. **View Available Rooms**:
   - I can view details of available venues such as the room name, type, and a "Book" button for each venue.
   - I can click the "Book" button to view more detailed information and proceed with booking.

4. **Book a Venue**:
   - After selecting a venue, I am redirected to the booking details page where I can pick a time slot and specify the purpose of my booking.
   - I can finalize the booking by clicking the "Book Now" button, which confirms the reservation for my chosen time slot.

#### Example Scenario:

As a **Lecturer**, I need to book a **Chemistry Lab** for an experiment demonstration next week. I can:
- Search for "Chemistry Lab" using the search bar.
- Filter the search results to show only chemistry labs.
- Select a lab, choose an available time slot, and provide the purpose of my booking ("Experiment demo for Chemistry 101").
- Confirm the booking.

#### Additional Functionality:

- The page allows users to dynamically filter venues and receive real-time results.
- Booking requests are sent through an API, and the system responds based on availability.

#### Venue Types

- Lecture Halls
- Tutorial Rooms
- Computer Laboratories
- Chemistry Laboratories
- Conference Rooms
- Study Rooms
- Exam Halls

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
- Save changes is a function that will get the id of the request and POST the changes to the database via the API fetch request. Once succesfull it will reload the page.
- Close Popupu is a function that will hide the popup from view so that we return to the normal maintenance logs screen.

### Notifications




## User Guides

### Maintenance

### Maintenance
#### How to make a maintenance Report
1. Click the plus on your user dashboard and select Report.
2. Fill in your name.
3. Fill in the venue where this took place - so you can fill in the name of the lecture hall, tutorial room, confrence hall, labratory (computers etc.).
4. Select an issue type - Electrical, Ventilation, Pests and Rodents, Roofinf and Ceiling ,Other.
5. Write a short description of what you witnessed.
6. Click Submit. The input should clear.
7. Press the back arrow in the top left corner to return to the user dashboard.
#### How to work with maintenance logs
1. Click maintenance on your user dashboard.
2. arrive at the page to see columns of "Scheduled", "In Progress" and "Completed".
3. Click on a block that says Venue: name, with a date.
4. View the popup.
5. Can edit fields, Assigned to, the date picker and the Status bar dropdown.
6. Save changes to save your changes and reload the page
7. Otherwise Close the popup to go back without saving.
8. Press the maintenance log page back arrow on the top left corner to go back the user dashboard.
