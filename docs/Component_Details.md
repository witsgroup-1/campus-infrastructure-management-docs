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

### Maintenance Reports

- **Make a Report**: Users can submit maintenance reports with fields including Name and Surname, Report Type, Venue, and Description. The system will generate data with a report including createdAt timestamp, status, userId of the user who submitted the issue, and log ticket information.
- **Log Page**: Displays the status of a maintenance request as a log. Clicking on a maintenance log reveals more information, allows setting its status, and shows the staff assigned and the scheduled completion time.

### Notifications
