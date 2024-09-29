# Component Details :wrench:

## Details of Features

### Login

#### Authentication
- **Purpose**: Allows users to log in using their credentials.
- **Required Information**: Name, surname, faculty, role. Optionally, check if they are a tutor or lecturer.
- **Whitelisting**: Certain emails not affiliated with The University of Witwatersrand may be whitelisted if they have valid reasons (e.g., guest lecturers).

#### Users
- **Student**: Access to study resources, booking venues, and academic activities.
- **Student (Tutor)**: Additional permissions for tutoring activities and resources.
- **Staff (Lecturer)**: Permissions include booking venues, managing academic schedules, and accessing staff resources.
- **Staff**: Permissions include managing staff activities and accessing staff resources.

### Schedule Integration

- **Create a Schedule**:
  - **Fields**: Name and Surname, Course, Venue, Day of the Week, Times, Date, and Recurrence.
  - **Time** type is used to input times, and **Date** type is used to input a date.
  - If Recurrence is "Yes", an option to add an end date is provided.
  - **Submit** button adds the information to the database.

- **Schedule Timetable**:
  - Displays all timetables made by the user, including the day, date, course, venue, and times.
  - Includes a delete button to remove a schedule.
  - A button at the bottom takes the user to the form to add a schedule.

### Maintenance

- **Make a Report**:
  - **Fields**: Name and Surname, Report Type, Venue, Description.
  - **Generated Data**: `createdAt` timestamp, status, `userId` of the user who submitted the issue.

- **Log Page**:
  - Shows the status of a maintenance request as a log.
  - Clicking on the maintenance log reveals a popup with more information where you can set the status, assigned staff, and scheduled completion time.

#### How It Was Implemented

- **Maintenance Report**:
  - The frontend sends a POST request to the maintenance API with the input values from the HTML form.
  - You can only enter in a valid venue name which is aided by a search dropdown that does a get request via the venue API based on the name of the venue.
  - The form input clears upon submission.

- **Maintenance Logs**:
  - A GET request fetches all maintenance requests.
  - Data is displayed in columns ("Scheduled", "In Progress") depending on status.
  - Desktop and mobile display functions handle dynamic display and creation of request blocks.
  - The "Open Popup" function shows detailed information and allows editing of time, assignment, and status.
  - **Save Changes**: Updates the database via a POST request and reloads the page.
  - **Close Popup**: Hides the popup and returns to the maintenance logs screen.

### Notifications

## User Guides

### Landing page User Guide

##### Step 1: Welcome
1. **Access the Landing Page**:
   - The landing page is the main point of arrival.
2. **Introduction**:
   - You will see an information card with rules on how to login or request email approval.


### Onboarding User Guide

#### Overview
The onboarding process is designed to collect essential information about you before you can fully access our platform. The process is divided into four steps:
1. **Welcome**
2. **Name and Surname**
3. **Faculty and Role**
4. **Checkboxes and Finish**

#### Step-by-Step Instructions

##### Step 1: Onboarding
1. **Access the Onboarding Page**:
   - Open the onboarding page from the provided link.
2. **Introduction**:
   - You will see a welcome message inviting you to tell us more about yourself.
3. **Start the Onboarding Process**:
   - Click the **"Get Started"** button to proceed to the next step.

##### Step 2: Name and Surname
1. **Enter Your Information**:
   - **Name**: Enter your first name.
   - **Surname**: Enter your last name.
2. **Validation**:
   - Ensure that both fields are filled out before proceeding.
3. **Proceed to Next Step**:
   - Click the **"Next"** button to move on.

##### Step 3: Faculty and Role
1. **Select Your Faculty**:
   - Choose your faculty from the dropdown menu:
     - Commerce, Law and Management
     - Engineering and the Built environment
     - Health Sciences
     - Humanities
     - Science
     - Other
2. **Select Your Role**:
   - Choose your role from the dropdown menu:
     - Student
     - Staff
3. **Validation**:
   - Ensure that both the faculty and role fields are selected before proceeding.
4. **Proceed to Next Step**:
   - Click the **"Next"** button to continue.

##### Step 4: Checkboxes and Finish
1. **Select Your Roles (if applicable)**:
   - **Tutor**: Check the box if you are a tutor.
   - **Lecturer**: Check the box if you are a lecturer.
2. **Validation**:
   - You must select at least one checkbox (either tutor or lecturer) to complete the onboarding process.
3. **Complete Onboarding**:
   - Click the **"Finish"** button to submit your information.
4. **Completion**:
   - You will see a confirmation message. You will be redirected to the user dashboard upon successful completion.

#### Troubleshooting
- **Form Validation Errors**:
  - Ensure all required fields are filled out.
  - Verify that at least one checkbox in the final step is selected.
- **Submission Issues**:
  - If you encounter any issues, check your network connection and try again. If the problem persists, contact support.

### User Guide: Dashboard

#### Overview
Welcome to the Dashboard of your web application! This guide provides an overview of how to navigate and use the various features of the dashboard, including viewing upcoming bookings, viewing available venues and making maintenance reports.

#### Dashboard Layout

##### Header
- **Logo**: Located at the top left of the header.
- **Title**: Displays the name of the application 'Infrustructure Management'.
- **Accesses**: Located at the top right of the header, there is a notification bell and navigation menu icon.

##### Main Content

###### Desktop View

- **Available venues**:
  - **Description**: This shows the venues available to book in the next available slot, through generic category images. The last image has a click ability which upon clicking will navigate the user to a whole page showing all available venues, the 'Available venues' page.
  -**Available venues page**:
  - This page can be accessed via the last image in the 'Available venues' section, or via the 'Venues' tab in the nav bar, it shows the venues available to be booked in the next slot of the day and also contains an extra information button about those venues.

- **Upcoming Bookings**:
  - **Description**: Shows the first 3 bookings scheduled for the future, when there are more than 3 bookings, users navigate to the 'Your bookings' page via the 'see more' link what will appear beneath the bookings. 
  -**Your bookings page**:
  - This page can be accessed via 'see more' under the bookings on the main page or via the navigation bar under the 'Bookings' tab,
  -This page allows you to see upcoming bookings which you can choose to cancel and past bookings which you can choose to book again.

- **Footer**: Contains campus security information, a map to find your way around campus and naturally, Group -1's copy right.

###### Mobile View
- **Available venues**:
  - **Description**: This shows the venues available to book in the next available slot, through generic category images. The last image has a click ability which upon clicking will navigate the user to a whole page showing all available venues, the 'Available venues' page.
  -**Available venues page**:
  - This page can be accessed via the last image in the 'Available venues' section, or via the 'Venues' tab in the nav bar, it shows the venues available to be booked in the next slot of the day and also contains an extra information button about those venues.

- **Upcoming Bookings**:
  - **Description**: Shows the first 3 bookings scheduled for the future, when there are more than 1 booking, users navigate to the 'Your bookings' page via the 'see more' link what will appear beneath the bookings. 
  -**Your bookings page**:
  - This page can be accessed via 'see more' under the bookings on the main page or via the navigation bar under the 'Bookings' tab,
  -This page allows you to see upcoming bookings which you can choose to cancel and past bookings which you can choose to book again.

- **Footer**: Contains campus security information, a map to find your way around campus and naturally, Group -1's copy right.

#### Features

##### Viewing Bookings
- **Desktop**: The desktop view displays both upcoming and past bookings in separate sections with pagination controls.
- **Mobile**: The mobile view provides a compact summary of bookings, with one item displayed from upcoming and past bookings respectively.

##### Booking Management
- **Cancel Booking**: Cancels the selected booking.
- **Rebook**: Rebooks the selected past booking.

##### Pagination Controls
- **Previous Button**: Allows navigation to the previous page of bookings.
- **Next Button**: Allows navigation to the next page of bookings.
- **Visibility**: Pagination controls are visible only when there are multiple pages of bookings.

#### Functionality
- **Loading State**: Displays a loading message while fetching booking data.
- **Date and Time Formatting**:
  - **Date**: `DD/MM/YY`
  - **Time Slot**: `HH:MM-HH:MM`

### Venue Booking System

#### Overview
This guide provides instructions on how to use the venue booking system. It covers two main pages:
1. **Book a Venue** - For searching and filtering available venues.
2. **Booking Details** - For viewing detailed information about a selected venue and making a booking.

#### 1. Book a Venue

##### Page Overview
The "Book a Venue" page allows you to search and filter available venues. You can select a venue to view its details and make a booking.

##### Features
- **Search Bar**:
  - Located at the top of the page.
  - Type the name of the room or venue you are looking for.
  - Results will dynamically update based on your input.
- **Filter Dropdown**:
  - Allows you to filter venues by type (e.g., Lecture Hall, Tutorial Room, Boardroom, Exam Venue).
  - Options are displayed as a dropdown menu.
- **Venue List**:
  - Displays available venues based on search and filter criteria.
  - Each venue card includes an image, brief description, and a "View Details" button.
- **View Details Button**:
  - Takes you to the Booking Details page where you can view more information and make a booking.

#### 2. Booking Details

##### Page Overview
The "Booking Details" page provides detailed information about a selected venue and allows you to book the venue.

##### Features
- **Venue Information**:
  - Displays detailed information about the selected venue, including its name, type, and available features.
  - **Image**: Shows a large image of the venue.
- **Booking Form**:
  - **Date**: Select the date you want to book the venue.
  - **Start Time**: Choose the start time for your booking.
  - **End Time**: Choose the end time for your booking.
  - **Purpose**: Enter the purpose of the booking.
  - **Submit Button**: Completes the booking process and adds the venue booking to the system.
- **Booking Confirmation**:
  - After submission, you will receive a confirmation message and be redirected to your bookings page.

### Schedules

### Schedule
- Open the sidebar on the main dashboard and click on "Schedules".
- Here, you will be able to view all created schedules.
- On each row, there is a button with a bin. Click on this button in order to delete a schedule. You will be asked to confirm your deletion: click yes (or cancel if you do not want to).
- Beneath the table is a button which says "Add a Schedule". Clicking this button will take you to a new page with a form.
- Type in your name, the course of the schedule and the venue where it will be held. Select a day from the drop-down. You can use the clocks under "Time" to choose a time or input your own time directly. You can click the calendar to choose a date or input your own date.
- Then if your schedule is one that recurs weekly, click "yes" on the Recurring dropdown. This will casue another Date picker to appear. Here you must choose the date that your last schedule will be held on. Otherwise, if your schedule is only for one day, choose "no".
- Once the form is fully filled out, you can click the "Submit" button to add your new schedule.

### Maintenance

#### How to Make a Maintenance Report

1. Click the plus on your user dashboard and select "Report."
2. Fill in your name.
3. Fill in the venue where the issue took place (e.g., a lecture hall, a tutorial room, a conference hall or a laboratory). A dropdown will appear to assist you with inputting a valid venue.
4. Select an issue type (e.g., Electrical, Ventilation, Pests and Rodents, Roofing and Ceiling, Other).
5. Write a short description of the issue.
6. Click "Submit." The input should clear.
7. Press the back arrow in the top left corner to return to the user dashboard.
8. If you do not fill in every field then you can not submit the form.

#### How to Work with Maintenance Logs

1. Click "Maintenance" on your user dashboard.
2. Arrive at the page with columns for "Scheduled," "In Progress," and "Completed."
3. Click on a block that displays Venue: name, with a date.
4. View the popup with detailed information.
5. Edit fields such as Assigned to, date picker, and Status bar dropdown if necessary.
6. You can search for staff users to assign tasks to.
7. You can only assign a timestamp field in the "In Progress," and "Completed" statuses.
9. Click "Save Changes" to save changes and reload the page or "Close" the popup to return without saving.
10. Press the maintenance log page back arrow on the top left corner to return to the user dashboard.






## Maintenance Guides for all features.

API Key:
- The API key (apiKey) is a sensitive piece of information used to authenticate requests to the API.
- Ensure that the API key is rotated on a regular basis for security.

  
Maintenance Reports:



Maintenance Logs:
- Fetching Data from the API:
    - The code fetches maintenance requests from an API endpoint and processes them based on their status (Scheduled, In Progress, Completed).
    - Tasks:
        - Always check the status of the API response to ensure it's successful before processing the data.
        - Ensure robust error handling with try-catch blocks.
        - Log errors meaningfully with console.error();
- Handling and Displaying Maintenance Requests:
    - Maintenance requests are filtered into different categories: "Scheduled", "In Progress", and "Completed".
    - Date Handling: Ensure the timestamps are correctly converted into a human-readable format using: new Date(request.timestamp.seconds * 1000).toLocaleString();
    - Ensure the function 'displayInitialRequestsForMobile' works so as to ensure consistently responsive displays accross devices.
- Updating Maintenance Requests:
    - Maintenance requests can be updated through the saveChanges function, which sends a PUT request to the API.
    - Tasks:
        - Ensure Correct Status is Reflected: Check that the status changes (like Scheduled, In Progress, or Completed) are saved properly.



