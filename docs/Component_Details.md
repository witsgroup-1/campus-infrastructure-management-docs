# Component Details :wrench:

---

## Details of Features

### Schedule Integration

- **Create a Schedule**: 
  - Fields: Name and Surname, Course, Venue, Day of the Week, Times, Date, and Recurrence.
  - **Time** type is used to input times, and **Date** type is used to input a date.
  - If Recurrence is "Yes", an option to add an end date is provided.
  - **Submit** button adds the information to the database.

- **Schedule Timetable**: 
  - Displays all timetables made by the user, including the day, date, course, venue, and times.
  - Includes a delete button to remove a schedule.
  - A button at the bottom takes the user to the form to add a schedule.

### Maintenance

- **Make a Report**: 
  - Fields: Name and Surname, Report Type, Venue, Description.
  - Generated Data: `createdAt` timestamp, status, `userId` of the user who submitted the issue.

- **Log Page**: 
  - Shows the status of a maintenance request as a log.
  - Clicking on the maintenance log reveals a popup with more information where you can set the status, assigned staff, and scheduled completion time.

#### How It Was Implemented

- **Maintenance Report**:
  - The frontend sends a POST request to the API with the input values from the HTML form.
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

## Onboarding Process

The onboarding process is designed to gather essential information from users before they can fully access the site's features. It involves a step-by-step form that users must complete. The onboarding process is intended for new users accessing the site for the first time. If this is not the first time using the site, users are led to their dashboard. After completing the onboarding process, the page redirects to the dashboard.

### Login

- **Authentication**: Users must log in using their credentials. The system whitelists certain emails not affiliated with The University of Witwatersrand if they have a valid reason to use the university's services (e.g., guest lecturers).
- **Required Information**: Users need to provide their name, surname, faculty, role, and optionally check if they are a tutor or lecturer.

### Users

- **Student**: Permissions include accessing study resources, booking venues, and participating in academic activities.
- **Student (Tutor)**: Additional permissions for tutoring activities and resources.
- **Staff (Lecturer)**: Permissions include booking venues, managing academic schedules, and accessing staff resources.
- **Staff**: Permissions include managing staff activities and accessing staff resources.

## Book Venues

### User Acceptance Tests

As a **Lecturer**, I can:

1. **Search for a Venue**: 
   - Use the search bar to find available rooms by name or category, such as chemistry laboratories or lecture halls.
   - The system will display only rooms that match my search query and selected filters.

2. **Filter by Room Type**: 
   - Filter search results by room type, e.g., selecting "Chemistry Laboratories" or "Lecture Halls."
   - Only venues that match the room type will appear in the list.

3. **View Available Rooms**:
   - View details of available venues, including the room name, type, and a "Book" button for each venue.
   - Click the "Book" button to view more detailed information and proceed with booking.

4. **Book a Venue**:
   - After selecting a venue, be redirected to the booking details page to pick a time slot and specify the purpose of the booking.
   - Finalize the booking by clicking the "Book Now" button, which confirms the reservation for the chosen time slot.

#### Example Scenario

As a **Lecturer**, I need to book a **Chemistry Lab** for an experiment demonstration next week. I can:
- Search for "Chemistry Lab" using the search bar.
- Filter the search results to show only chemistry labs.
- Select a lab, choose an available time slot, and provide the purpose of my booking ("Experiment demo for Chemistry 101").
- Confirm the booking.

#### Additional Functionality

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

### Maintenance

#### How to Make a Maintenance Report

1. Click the plus on your user dashboard and select "Report."
2. Fill in your name.
3. Fill in the venue where the issue took place (e.g., lecture hall, tutorial room, conference hall, laboratory).
4. Select an issue type (e.g., Electrical, Ventilation, Pests and Rodents, Roofing and Ceiling, Other).
5. Write a short description of the issue.
6. Click "Submit." The input should clear.
7. Press the back arrow in the top left corner to return to the user dashboard.

#### How to Work with Maintenance Logs

1. Click "Maintenance" on your user dashboard.
2. Arrive at the page with columns for "Scheduled," "In Progress," and "Completed."
3. Click on a block that displays Venue: name, with a date.
4. View the popup with detailed information.
5. Edit fields such as Assigned to, date picker, and Status bar dropdown if necessary.
6. Click "Save Changes" to save changes and reload the page or "Close" the popup to return without saving.
7. Press the maintenance log page back arrow on the top left corner to return to the user dashboard.
