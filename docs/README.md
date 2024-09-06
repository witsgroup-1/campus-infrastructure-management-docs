# Welcome to Campus Infrastructure Management Docs! :paperclips:

## <!-- https://witsgroup-1.github.io/campus-infrastructure-management-docs/ -->

<p style="text-align: center;">
    <img src="media/docscover.svg" alt="Users Table" width="500" height="auto"/>
</p>

---

> **Made By Group -1:**<br>
> Dineo Chiloane (2563191) :woman_technologist:<br>
> Claire Newman (2549861) :woman_technologist:<br>
> Chloe Dube(2602515) :woman_technologist:<br>
> Mayuri Balakistan (2543986) :woman_technologist: <br>
> Busisiwe Vemba (2561620) :woman_technologist:<br>
> Menzi Shazi (2453308) :man_technologist:<br>

# Introduction :book:

The Classroom/Venue Management App is designed to enhance the efficiency of managing classroom and venue assignments, bookings, and maintenance on campus. This application integrates seamlessly with academic schedules, providing a centralized platform for room bookings, maintenance issue reporting, and schedule management.

Key features include a room booking system that allows users to reserve classrooms and venues for various purposes, a visual availability calendar for easy schedule viewing, and a notification system to keep users informed of upcoming bookings and updates. The app also supports an admin interface for managing schedules and maintenance tasks, ensuring that all aspects of campus venue management are handled efficiently.

While push notifications are a stretch goal, the app’s secure and scalable infrastructure is built to ensure data integrity and availability. The user-friendly dashboard and robust APIs for booking, scheduling, maintenance, notifications, and user management together provide a comprehensive solution for optimizing space utilization on campus.

## Important Links

- Code Repository: https://github.com/witsgroup-1/campus-infrastructure-management
- Documentation Repository: https://github.com/witsgroup-1/campus-infrastructure-management-docs
- Documentation Website: https://witsgroup-1.github.io/campus-infrastructure-management-docs/#/?id=welcome-to-campus-infrastructure-management-docs-paperclips

---

# Development Process :gear:

## Planning of Architecture

At the begining of the process we focused on the technology choices, the high-level view of the system and the database and API specifications. Then we added more detail to the planning of the key features.

The project architecture is: Multi-tier architecture

We chose this architecture as we have a front-end, a web hosting server, api and backend NO-SQL database.

The technology stack is:

- Frontend: HTML, CSS , Tailwind - (This is good for mobile-first development)
- Authentication: 
- Backend: Node Js, Express Js
- Databases: Firebase Firestore

Some frequently asked questions:
- Why use Firestore NOSQL database: It is good for mobile development due to its flexibility and scalability. It has real time data sychronisation and is very customisable in its security rules.
    (ref: https://cloud.google.com/blog/topics/developers-practitioners/all-you-need-know-about-firestore-cheatsheet)
- Why use an API with a firestore NOSQL database: So that other sub-systems do not have to get involved with our database, they can just call our API and acess our data with the correct authentication.

It was important that we hosted our website in our home country: Since our application was designed for use by our university it is important that everything is hosted as close to our country as possible. So we hosted our database and our web server in our country.

## Diagrans

### Use Case Diagram

The Use case diagram to illustrate basic features.
![Users Table](media/UseCaseDiagram.drawio(1).png)

### Deployment Diagram

The Deployment diagram to illustrate how our website deploys.
![Users Table](media/DeploymentDiagram.drawio(1).png)

### Component Diagram

The system components can be seen below in the component diagram.
![Users Table](media/ComponentDiagramSDP.drawio.png)

## UI/UX Design Process

We foucsed on the mobile design first as our website application is more geared to the mobile first aproach.

### Wireframes <!-- {docsify-ignore} -->

We did a couple of wireframes in order to perfect our design.

Login

![Users Table](media/ClaWireframe2.jpg)

Home

![Users Table](media/MayWireframe1.jpg)
![Users Table](media/ClaWireframe1.jpg)
![Users Table](media/ChlWireframe1.jpg)

### Mockups <!-- {docsify-ignore} -->

The Mockups based off of the wireframes (but also more refinied)

![Chloe Mockup 1](media/chlMockup1.png)
![Chloe Mockup 2](media/chlMock2.png)

![May Mockup](media/mockup.png)

Revised mockup designs based on Brendan Griffiths' criticism

![Busi Mockup](image-1.png)
![Busi Mockup](image-2.png)
### Desktop mockups

#### Use case: User books a venue

> Frame 1:
> ![Frame 1](media/bookvenue/Frame1.png)
> Frame 2:
> ![Frame 2](media/bookvenue/Frame2.png)
> Frame 3:
> ![Frame 3](media/bookvenue/Frame3.png)
> Frame 4:
> ![Frame 4](media/bookvenue/Frame4.png)
> Frame 5:
> ![Frame 5](media/bookvenue/Frame5.png)
> Frame 6:
> ![Frame 6](media/bookvenue/Frame6.png)
> Frame 7:
> ![Frame 7](media/bookvenue/Frame7.png)

#### Use case: General user main dashboard
> Frame 1:
> ![Frame 1](media/userdashboard/5%20Search%20Results.png)
> Frame 2:
> ![Frame 2](media/userdashboard/5%20Search%20Results-1.png)

#### Use case: General maintenance reports and logs
![Cla Mockup 1](media/LunarMockup2.png)


### Prototypes <!-- {docsify-ignore} -->

### Details on Frontend Components

- Fonts:
- Main Colours: Wits colours
  - Blue: #003B5C
  - Gold: #917248
- Colour Tints:
  - Lighter blue when hovering: #01517d
  - Darker gold when hovering: #806541
  
Button Specification:
- Primary Button: Gold
- Secondary Button: Blue

Background Specification:
- Blue for headers
- Otherwise white(#ffffff)

## Key Features Overview

- Book venues: Users can book various venues. Lecturers can book most venues such as classes and lecture halls, whilst tutors and students can book tutorial rooms.
- Schedule Integration: Lecturers can integrate there schedules to make automatic bookings for there classes.
- Maintenence Reports: Users can report whether a room requires maintenence and Staff can view these in order to resolve them.
- Notifications: Users except staff can recieve booking notifications whilst staff can recieve maintenence notifications.

### Implementation of the key features Overview

The specifications for their respective databases and API endpoints are shown further below.

### Basics of implementing the key features

- First we will implement the prototype via html, css and tailwind.
- Then the API's and the Databases will be created and implemented based on their respective specifications.
- We will create the Js functions to make use of the API calls and link with the database.
- Create tests around Js functions.

## Integration with Other Systems Overview

- Transport App: Map API for navigation to venues.
- Events and Activities App: Call their API to find out if any venues are booked for an event or activity - to make sure we are synchronised.
- Campus Safety App: Call their API to provide emergency contact information.
- Dining Services: Book reservations through our app.

## Timelines

- 8th -20th Auguast - Sprint 1 -Plan the software (UI/UX and architecture)
- 20th August - 1st Marking
- 20th -27th August - Sprint 2 - begin programming the key features - DB, API, Frontend.
- 27th August -3rd September - Sprint 3 - finalise APIs, finalise integration plans, Create frontend pages(user dashboard, other pages).
- 4th - 10th September - Sprint 4 - Begin implementing core features, finalise frontend pages, secure API, integrate with other systems.
- 11th - 16th September - Sprint 5 -
- 17th September - 2nd Marking
- 01st October - 3rd Marking
- 07th October - Group Report and Documentation
- 08-17th October - Demo
- 20th October - Individual Reports

---

# Component Details :wrench:

---

## Details of Features

### Login

- authentication:
- whitelist: certain emails that are not The University of Witwatersrand affiliated will be whitelisted if they have valid reason to use the university's services e.g. guest lecturers
- required information:

### Users

- Student: Permisions ->
- Student (tutor): Permisions ->
- Staff (Lecturer): Permisions ->
- Staff: Permisions ->

### Book Venues

#### venue Types

- Lecture Halls
- Tutorial Rooms
- Labratories
- Computer Labratories
- Confrence rooms
- ...

### Schedule Integration

### Maintenence Reports
- make a report: (report fields: Name and Surname, Report Type, Venue, Description), (generated data with report: createdAt timestamp, status, userId of user who submitted the issue, log ticket information).
- log page: shows the status of a maintenance request as a log. If you click on the maintenace log you can see more information and set its status, the staff assigned, and when it is scheduled to be done.

### Notifications

# API Specifications :memo:

## User Management API :bust_in_silhouette:

<iframe src="./swagger/user-api.html" width="100%" height="800px"></iframe>

## Booking API :calendar:

<iframe src="./swagger/booking-api.html" width="100%" height="800px"></iframe>

## Schedule API :watch:

<iframe src="./swagger/schedule-api.html" width="100%" height="800px"></iframe>

## Maintenance API :hammer_and_wrench:

<iframe src="./swagger/maintenance-api.html" width="100%" height="800px"></iframe>

## Notification API :bell:

### Purpose <!-- {docsify-ignore} -->

The Notification API handles the scheduling and delivery of notifications to users, including reminders for upcoming bookings and updates on maintenance requests.

### Endpoints <!-- {docsify-ignore} -->

#### Create Notification <!-- {docsify-ignore} -->

- **Endpoint:** `POST /api/notifications`
- **Description:** Create a new notification to be sent at a specific time.
- **Request Body:**

```json
{
  "userId": "Lecturer1923",
  "type": "booking_reminder",
  "message": "Reminder: Your booking for Room101 starts in 30 minutes.",
  "sendAt": "2024-08-19T09:30:00Z"
}
```

- **Response:**

```json
{
  "notificationId": "notif123",
  "message": "Notification scheduled successfully."
}
```

#### Get Notifications for User <!-- {docsify-ignore} -->

- **Endpoint:** `GET /api/notifications/user/{userId}`
- **Description:** Retrieve all notifications scheduled for a specific user.
- **Response:**

```json
[
  {
    "notificationId": "notif123",
    "type": "booking_reminder",
    "message": "Reminder: Your booking for Room101 starts in 30 minutes.",
    "sendAt": "2024-08-19T09:30:00Z"
  },
  ...
]
```

#### Update Notification <!-- {docsify-ignore} -->

- **Endpoint:** `PUT /api/notifications/{notificationId}`
- **Description:** Update an existing notification (e.g., change the message or send time).
- **Request Body:**

```json
{
  "message": "Reminder: Your booking for Room101 starts in 15 minutes.",
  "sendAt": "2024-08-19T09:45:00Z"
}
```

- **Response:**

```json
{
  "notificationId": "notif123",
  "message": "Notification updated successfully."
}
```

#### Delete Notification <!-- {docsify-ignore} -->

- **Endpoint:** `DELETE /api/notifications/{notificationId}`
- **Description:** Delete a scheduled notification.
- **Response:**

```json
{
  "message": "Notification deleted successfully."
}
```

#### Send Immediate Notification <!-- {docsify-ignore} -->

- **Endpoint:** `POST /api/notifications/send`
- **Description:** Send a notification immediately without scheduling.
- **Request Body:**

```json
{
  "userId": "Lecturer1923",
  "type": "booking_reminder",
  "message": "Immediate notification: Your booking for Room101 is starting now."
}
```

- **Response:**

```json
{
  "notificationId": "notif124",
  "message": "Notification sent successfully."
}
```

# Database Schema :floppy_disk:

For our project, we use a **Hierarchical Model**, which organizes data in a “tree-like” structure with parent-child relationships. Our chosen database, Firebase Firestore, uses this hierarchical model to effectively manage and scale our data.

## User Database :file_folder:

**Users Collection**

**1. Collection**: `users`

**Document**: `{userId}` (Document ID is a unique identifier for each user, such as `firebase_uid`)

**Document Fields:**

- `name`: User’s first name (string)
- `surname`: User’s last name (string)
- `email`: User’s Wits email address (string)
- `role`: User’s role (string) – e.g., student, or staff
- `faculty`: User’s faculty or department (string)
- `is_tutor`: Indicates if the user is a tutor (boolean)
- `is_lecturer`: Indicates if the user is a lecturer (boolean)
- `{bookings}`: Contains all the bookings that the user made in the form of documents(collection). -`{courses}`: Contains all the user's courses in the form of documents(collection).

**Example Document:** <br>
In the example below, the `staff` user should be able to make bookings for lecture halls, meeting rooms, tutorial rooms, and exam venues since the `is_lecturer` field is set to `true`. If it was set to `false`, they would not have the priviledge to do so.

> ```json
> {
>   "name": "John",
>   "surname": "Doe",
>   "email": "john.doe@wits.ac.za",
>   "role": "staff",
>   "faculty": "science",
>   "is_tutor": false,
>   "is_lecturer": true,
>   {bookings},
>   {courses}
> }
> ```

**Example Document:** <br>
In the following example, the student user should be able to make bookings for tutorial rooms since the `is_tutor` field is set to `true`.

> ```json
> {
>   "name": "Mitsy",
>   "surname": "Nkuna",
>   "email": "2538929632@students.wits.ac.za",
>   "role": "student",
>   "faculty": "science",
>   "is_tutor": true,
>   "is_lecturer": true,
>   {bookings},
>   {courses}
> }
> ```

**Example Document:** <br>
In the following example, the student user should be able to make bookings for study rooms only since the `is_tutor` field is set to `false`.

> ```json
> {
>   "name": "Mitsy",
>   "surname": "Nkuna",
>   "email": "2538929632@students.wits.ac.za",
>   "role": "student",
>   "faculty": "science",
>   "is_tutor": false,
>   "is_lecturer": true,
>   {bookings},
>   {courses}
> }
> ```

**2. Bookings Subcollection**

**Subcollection**: `bookings` (inside each user document)

**Document**: `{bookingId}` (Document ID for each booking)

**Document Fields:**

- `venue_id`: The unique identifier for the venue in the collection that consists all venues on campus (string)
- `name`: The name of the venue. e.g., WSS1.
- `start_time`: The start time of the booking (timestamp)
- `end_time`: The end time of the booking (timestamp)

**Example Document**

> ```json
> {
>   "venue_id": "DcGxOJax93od7C4B8VQ8",
>   "name": "wss1",
>   "start_time": "2024-10-19T10:15:00Z",
>   "end_time": "2024-10-19T11:00:00Z"
> }
> ```

**3. Courses Subcollection**

**Subcollection**: `courses` (inside each user document)

**Document**: `{courseId}` (Document ID for each course)

**Document Fields:**

- `course_id`: The unique_id for the document belonging to that course in the collection containing all courses.
- `lecturer_id`: The `userId` for the lecturer user.

**Example Document:**

> ```json
> {
>   "course_id": "Wh89K9693odHom85230K",
>   "lecturer_id": "Hcd9xOJax93o72djh3dHgP"
> }
> ```

**Summary of Schema Structure**

![Users Table](media/userstable.svg)

---

---

## Booking Database :clipboard:

**1. Bookings Collection**

**Collection Name:** `bookings`

**Documents:** Each document represents a booking and is identified by a unique `bookingId`.

**Document Fields:**

- **`bookingId`** (String, **Unique Identifier**): A unique identifier for each booking.
- **`venueId`** (String, **Foreign Key**): The unique identifier of the venue being booked.
- **`roomID`**(String, **Foreign Key**): The unique identifier of the room being booked.
- **`userId`** (String, **Foreign Key**): The unique identifier of the user who made the booking.
- **`start_time`** (Timestamp): The start time of the booking (ISO 8601 format).
- **`end_time`** (Timestamp): The end time of the booking (ISO 8601 format).
- **`date`** (Timestamp): The date of the booking
- **`purpose`** (String, Optional): The purpose of the booking.
- **`status`** (String): The status of the booking (e.g., "Confirmed", "Pending", "Cancelled").

**Example Document:**

```json
{
  "bookingId": "1234",
  "venueId": "0001",
  "roomID": "100",
  "userId": "1000",
  "start_time": "T09:00:00Z",
  "end_time": "T10:00:00Z",
  "date": "2024-09-01",
  "purpose": "SDP Lecture",
  "status": "Confirmed"
}
```

---

**2. Venues Collection**

**Collection Name:** `venues`

**Documents:** Each document represents a venue and is identified by a unique `venueId`.

**Document Fields:**

- **`venueId`** (String, **Unique Identifier**): A unique identifier for each venue.
- **`name`** (String): The name of the venue.
- **`category`** (String): The type of venue that it is (lecture hall, exam venue, dining...)

**Example Document:**

```json
{
  "venueId": "0001",
  "name": "FNB Building",
  "category": "Lecture Venue"
}
```

**Subcollection:** `rooms` (inside each venue document)

**Document:** `{roomId}` (Document ID, unique identifier for each room)

**Document Fields:**

`room_id`: Unique identifier for the venue (string, generated by Firebase)
`name`: Actual name of the room (string)
`location`: Physical location of the room within the venue (string)
`capacity`: Maximum number of people the room can accommodate (integer)
`features`: List of features available in that room (array of strings, optional)

**Document Example**:

```json
{
  "room_id": "001",
  "name": "FNB 37",
  "location": "Floor 1, FNB Building",
  "capacity": 40,
  "features": ["Projector", "Whiteboard", "Wi-Fi"]
}
```

**Summary of Schema Structure**

![Users Table](media/booking.drawio.svg)

---

## Schedule Database :calendar:

**Schedule Collection**

**1. Collection** : `schedules`

**Document** : `{scheduleId}`

**Document Fields** :

- `roomId` (string): the room/venue where the lesson will take place.
- `courseId` (string): the course that will be taught.
- `startTime` (timestamp): the time at which the lesson begins.
- `endTime` (timestamp): the time at which the lesson ends.
- `daysOfWeek` (string): the days on which the lesson takes place.
- `startDate` (timestamp): the date on which the lessons begin.
- `endDate` (timestamp): the date on which the lessons end.
- `recurring` (boolean): indicates whether the lesson recurs on a timely basis.
- `userId` (string): the identifier for the lecturer that created the schedule. (Only lecturers can create schedules.)

**Example Document:** <br>

> ```json
> {
>   "roomId": "Room101",
>   "courseId": "COMS3011A",
>   "startTime": "10:00",
>   "endTime": "12:00",
>   "daysOfWeek": "Monday",
>   "startDate": "2024-01-24",
>   "endDate": "2024-06-14",
>   "recurring": "True",
>   "userId": "Lecturer1923"
> }
> ```

**2. Subcollection** : `rooms`

The `rooms` subcollection is found inside every `schedule` collection. It contains the details of the room that is being booked for a particular course.

**Document** : `{roomsId}`

**Document Fields:**

- `roomId` (String): The identifier for the room or venue.
- `building` (String): The building where the room is located.
- `floor` (String): The floor on which the room is located.
- `roomType` (String): The type of room.
- `capacity` (Number): The capacity of the room.

  **Example Document:**

> ```json
> {
>   "roomId": "Room101",
>   "building": "Science Building",
>   "floor": "2nd",
>   "roomType": "Tutorial Room",
>   "capacity": 20
> }
> ```

**Reference** : `courses`

The `schedules` collection makes reference to the `courses` subcollection. This subcollection specifies which course the lecturer will teach in that time slot.

**Document**: `{courseId}`

**Document Fields:**

- `course_code`: (string) The code of the course.
- `lecturer_email`: (string) The email of the course instructor that created the schedule.

**Example Document:**

> ```json
> {
>   "course_code": "COMS3011A",
>   "lecturer_email": "adamwhite@wits.ac.za"
> }
> ```

**Summary of Schema Structure**

![Users Table](media//Schedule_database.drawio.svg)

## Maintenance Database :hammer_and_wrench:

**Maintenance Collection**

**1. Collection** : `maintenanceRequests`
**Document**: `{requestId}`

**Document fields**:

- `roomId` (String): Identifier for the room or venue where the issue was reported.
- `userId` (String): Unique identifier for the user who reported the issue (e.g., firebase_uid).
- `issueType` (String): The type of issue reported – e.g., "Electrical," "Plumbing."
- `description` (Text): Detailed description of the issue.
- `status` (String): Current status of the request – e.g., "Open," "In Progress," "Resolved."
- `createdAt` (Timestamp): Date and time when the request was created.
- `assignedTo` (String): Identifier for the staff member assigned to the request.

**Example Document:** <br>

> ```json
> {
>   "roomId": "Room101",
>   "userId": "User123",
>   "issueType": "Electrical",
>   "description": "Light not working",
>   "status": "Open",
>   "createdAt": "2024-08-12T09:00:00Z",
>   "assignedTo": "Staff456"
> }
> ```

**2. Subcollection: `maintenanceLogs`**

This subcollection is found inside each `maintenanceRequests` document. It tracks the history of actions taken on the request.
**Document**: `{logId}`

**Document Fields:**

- `logId` (String): Unique identifier for the log entry.
- `actionTaken` (String): Description of the action – e.g., "Request created," "Status changed to In Progress."
- `actionBy` (String): Identifier for the user who performed the action.
- `timestamp` (Timestamp): Date and time when the action was taken.

**Example Document:** <br>

> ```json
> {
>   "logId": "Log001",
>   "actionTaken": "Request created",
>   "actionBy": "User123",
>   "timestamp": "2024-08-12T09:01:00Z"
> }
> ```

**3. Subcollection: `rooms`**

This subcollection is found inside each `maintenanceRequests` document. It contains information about the room or venue related to the maintenance request. This is useful if the room details need to be recorded separately or if multiple rooms are associated with a single maintenance request.

**Document**:`roomId`

**Document Fields:**

- `roomId` (String): Unique identifier for the room or venue – e.g., "Room101."
- `building` (String): The building where the room is located – e.g., "Science Building."
- `floor` (String): The floor on which the room is located.
- `roomType` (String): The type of room – e.g., "Classroom," "Lecture Hall," "Lab."
- `capacity` (Number): The capacity of the room – e.g., 30 students.

  **Example Document:**

> ```json
> {
>   "roomId": "Room101",
>   "building": "Science Building",
>   "floor": "1st",
>   "roomType": "Classroom",
>   "capacity": 30
> }
> ```

**Overall Structure:**

- **`maintenanceRequests` (Main Collection)**
  - **`requestId1` (Document)**
    - `roomId`: "Room101"
    - `userId`: "User123"
    - `issueType`: "Electrical"
    - `description`: "Light not working"
    - `status`: "Open"
    - `createdAt`: "2024-08-12T09:00:00Z"
    - `assignedTo`: "Staff456"
    - **`rooms` (Subcollection)**
      - `roomId1` (Document)
        - `roomId`: "Room101"
        - `building`: "Science Building"
        - `floor`: "1st"
        - `roomType`: "Classroom"
        - `capacity`: 30
    - **`maintenanceLogs` (Subcollection)**
      - `logId1` (Document)
        - `actionTaken`: "Request created"
        - `actionBy`: "User123"
        - `timestamp`: "2024-08-12T09:01:00Z"

**Summary:**

- **Main Collection: `maintenanceRequests`**

  - Stores general information about each maintenance request.

- **Subcollection: `rooms`**

  - Contains details about the specific room(s) involved in the maintenance request.

- **Subcollection: `maintenanceLogs`**
  - Tracks the history of actions taken related to the maintenance request.

**Summary of schema structure:**
![Maintenance Table](media/maintenancetable.png)

# Testing and Quality Assurance :test_tube:

---

## Test Plan

- Jest was used to do testing.
- Tests will be made for functions after they are coded so we can test them before deployment.
- The test coverage reports will be uploaded to Code Cov.

# Deployment and Integration :rocket:

---

## Deployment

The website deploys via Azure Web app services using Github actions CI/CD pipeline.

### Version Control

When it comes to version control we need to define some things first:

- Product: A product is what we can offer to the user to fufill their requirments.
- Product feature: A products specific characteristics or functions that are important to the customer - so desin and functionality are included.

Ref: https://www.aha.io/roadmapping/guide/requirements-management/what-are-product-features

Version Control is mostly managed by github actions using the CI/CD pipeline - so it will record the date, time etc.
Branch management guidlines were given to help ensure a lack of mix ups:

- Each collaborator must commit to their own respective branch (labled by their username) or the "Bugs-and-Problems" branch for any problematic code.
- Always pull new updates before you push your new updates to you respective branches.
- Make sure your tests pass before commits.
- Give your commits to your branch meaningful names including: What you did and who you are - Github actions will reflect the date and time so you do not need to worry about that.
- Do not merge to main without the agreement of all devs.

The branch names are set as:

- main
- Bugs-and-Problems
- Chloe
- Busi
- Dineo
- Lunar
- May
- Menzi

## Integration

- Transport: Why integrate. The Map API can give us the most up to date locations of venues within our Application.
- Events Management: Why integrate. To keep our booking system up to date so that we do not face clashes.
- Saftey: Why integrate. For security details we can get the most up to date security information.
- Dining: Why integrate. We can allow our users to book a reservation for a meeting etc.

### How will we stubb their data

- Transport: Hardcode some locations for major venues.
- Events Management: hardcode some events to make sure our system is aware of them and up to date.
- Saftey: Hardcode some known security information.
- Dining: We will have some hardcoded resturants to make reservations too in our venue data collection. The reservations will be noted down in a list and acted upon in a timely manner.


# Challenges and Solutions :thinking:
- Getting the other groups to talk to us at the begining.

---

# Conclusion and Future Work :trophy:

---

# Appendices :file_cabinet:

---

## Meeting Minutes

### Sprint 1 Meeting 1

- Date: 09/08/2024
- Attendance:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)

- Discussion of rubric/project breakdown
- Web app must be able to resize to fit all screens (mobile first aproach)
- Discussion of how to deal with other groups
- Work on launching “Hello World”, and starting on testing, CI/CD
- Colour Palette discussed (planning on going with Wits related colours)
- Testing: Jest
- Database options: CosmoDB, MongoDB, Firebase, Azure. To be discussed further.
- Codecov for code coverage
- Backend: Azure
- Frontend: Html, css and perhaps bootstrap (to be discussed further).

- Questions:
- Only 3rd party providers?
- One database for entire system or each group own database?

- Plan of action
- Design website
- Configure CI/CD pipeline and testing
- Plan API endpoints, schemas
- Deploy Hello World website

### Meeting 2

- Date: 13/08/2024
- Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman ()
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)
- The Client

- Issues with website deployment
- Must focus on API specifications, designs and database schemas.

- Discussion with client:
- Colour palette: Wits colours, dark mode if possible.
- Integration: design API in a way that is useful to other groups, make sure our app does not fail if another API were to fail.
- UI/UX: discussed the 60,30,10 rule, the use of Tailwind and consistency of text size.
- Users: staff, students, admin. Use of wits email and whitelist.
- Client’s requests: heat map for booking (stretch goal), ticket system, dark mode, and more filters for choosing rooms, separated documents (i.e. API documentation separate from database documentation).

### Meeting 3

- Date: 18 August 2024
- Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

- Resolved issue with app deployment.
- In progress of completing API specifications and database schemas.
- Decided on tech stack:
- Backend: Azure, JavaScript, Node.js
-     Frontend: HTML, CSS, Tailwind
- Database: Firebase
- Decided which other APIs to make use of:
- Events API
- Campus Security API
- Issues to keep an eye on moving forward: working around other subsystems

### Sprint 2 Meeting 4

Date: 20/08/2024

- Attendees:
- Claire Newman
- Busisiwe Vemba
- Mayuri Balakistan
- Dineo Chiloane
- Menzi Shazi
- Chloe Dube

Discussion:

- Deciding on the implementation of databases, who will do it and how.
- Acknowledged that we are working on authentication
- Discussed the possibility of storing users in a realtime database vs firestore database
- Chloe was proposed for implementation of the User database in firebase
- Started creating user stories.
- Discussed the creation structure of the databases.
- Assigned databases to different people
- Discussed contact with other groups in the subsystem that we could get information from
- Discussed potential integration with the Campus security application e.g getting emergency contact information, emergency situation locations and etiquette and incident reporting.
- Brain stormed on how to integrate with the Campus transportation application, e.g their Map API.
- Spoke about the possibility of adding a heat map, or how we can make the identification of a venue e.g a map, more accessible when people are booking a venue
- Discussed the possibility of integrating with Events and activities application, specifically their API that handles event cancellations, we would need to know that an event has been cancelled and hence a venue is vacant.
- Tackled the idea of integrating with Dining services, but essentially decided they may diverge too much from the ideas of our application.
- Expanded on the list of possible integrations.

Ten-minute intermission.

- Started delegating API implementations.
- User API: Dineo and Chloe
- Maintenance API: Claire
- Schedule API: Menzi
- Booking API: Mayuri and Busi
- Notification API: Mayuri, Dineo, Busi, Chloe.
- We started discussing what views people would be able to see on the UI based on their role, e.g difference between staff and students.
- Settled on 3 user dashboards.
- Created a user story for Login and Sign up, we will be creating the mobile and desktop versions of the UI for these elements.
  End of meeting.

### Meeting 5

Date: 28 August 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)
- Client

Minutes with client
- The client likes the new design and is happy with integration progress.
- Discussed API’s:
- What to do when other API’s fail.
- For example, hard code directions/security details. 
- Don’t integrate for integrations sake.
- Why integrate?- for relevant, update information.

- Discussed what to do moving forward:
- Work on making API’s
- Create databases.
- Create more designs.
- Start with frontend.
- Hopefully, progress will speed up over break.
