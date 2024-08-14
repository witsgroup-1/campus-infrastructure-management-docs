# Welcome to Campus Infrastructure Management Docs! :paperclips:

---

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

---

# Development Process :gear:

---

# Component Details :wrench:

---

# API Specifications :memo:

## User Management API :bust_in_silhouette:

## Booking API :calendar:


## Overview

The Room Booking and Venue Management API allows users to manage venues and bookings for various purposes such as classes, meetings, and events. The API provides endpoints to create, update, retrieve, and delete venue records, as well as manage bookings associated with these venues.

## API Version

- **Version:** 1.0.0


## Endpoints

### 1. Venue Endpoints

#### 1.1. Retrieve a List of Venues

- **Endpoint:** `GET /venues`
- **Description:** Retrieves a list of available venues.
- **Responses:**
  - **200 OK**: Returns a list of venue objects.
    - **Response Body Example:**
    ```json
    [
      {
        "id": "0001",
        "name": "FNB 37",
        "location": "FNB Building, Floor 1",
        "capacity": 50,
        "features": ["Projector", "Wi-Fi", "Whiteboard"]
      }
    ]
    ```

#### 1.2. Create a New Venue

- **Endpoint:** `POST /venues`
- **Description:** Creates a new venue.
- **Request Body:**
  - **Body Parameters:**
    - `name` (String, Required) - The name of the venue.
    - `location` (String, Required) - The physical location of the venue.
    - `capacity` (Integer, Required) - The maximum number of people the venue can accommodate.
    - `features` (Array of Strings, Optional) - A list of features available at the venue.
  - **Request Body Example:**
    ```json
    {
      "name": "FNB 37",
      "location": "FNB Building, Floor 1",
      "capacity": 50,
      "features": ["Projector", "Wi-Fi", "Whiteboard"]
    }
    ```
- **Responses:**
  - **201 Created**: The venue is successfully created.
    - **Response Body Example:**
    ```json
    {
      "id": "0001",
      "name": "FNB 37",
      "location": "FNB Building, Floor 1",
      "capacity": 50,
      "features": ["Projector", "Wi-Fi", "Whiteboard"]
    }
    ```

#### 1.3. Update an Existing Venue

- **Endpoint:** `PUT /venues/{venue_id}`
- **Description:** Updates the details of an existing venue.
- **Path Parameters:**
  - `venue_id` (String, Required) - The unique identifier of the venue to update.
 - **Request Body Example:**
    ```json
    {
      "name": "FNB 102",
      "location": "FNB Building, Floor 1",
      "capacity": 50,
      "features": ["Projector", "Wi-Fi", "Whiteboard"]
    }
    ```
- **Responses:**
  - **200 OK**: The venue is successfully updated.
    - **Response Body Example:** 
        ```json
    {
      "id": "0001",
      "name": "FNB 102",
      "location": "FNB Building, Floor 1",
      "capacity": 50,
      "features": ["Projector", "Wi-Fi", "Whiteboard"]
    }
    ```

#### 1.4. Delete a Venue

- **Endpoint:** `DELETE /venues/{venue_id}`
- **Description:** Deletes a venue.
- **Path Parameters:**
  - `venue_id` (String, Required) - The unique identifier of the venue to delete.
- **Responses:**
  - **200 OK**: The venue is successfully deleted.

### 2. Booking Endpoints

#### 2.1. Retrieve a List of Bookings

- **Endpoint:** `GET /bookings`
- **Description:** Retrieves a list of bookings.
- **Query Parameters:**
  - `venue_id` (String, Optional) - Filter bookings by the venue ID.
  - `user_id` (String, Optional) - Filter bookings by the user ID.
  - `date` (String, Optional) - Filter bookings by date (format: YYYY-MM-DD).
- **Responses:**
  - **200 OK**: Returns a list of booking objects.
    - **Response Body Example:**
    ```json
    [
      {
        "id": "1234",
        "venue_id": "0001",
        "user_id": "1000",
        "start_time": "2024-08-14T09:00:00Z",
        "end_time": "2024-08-14T10:00:00Z",
        "purpose": "SDP Lecture",
        "status": "Confirmed"
      }
    ]
    ```

#### 2.2. Create a New Booking

- **Endpoint:** `POST /bookings`
- **Description:** Creates a new booking.
- **Request Body:**
  - **Body Parameters:**
    - `venue_id` (String, Required) - The ID of the venue being booked.
    - `user_id` (String, Required) - The ID of the user making the booking.
    - `start_time` (String, Required) - The start time of the booking (format: ISO 8601).
    - `end_time` (String, Required) - The end time of the booking (format: ISO 8601).
    - `purpose` (String, Optional) - The purpose of the booking.
  - **Request Body Example:**
    ```json
    {
      "venue_id": "0001",
      "user_id": "1000",
      "start_time": "2024-08-14T09:00:00Z",
      "end_time": "2024-08-14T10:00:00Z",
      "purpose": "SDP Lecture"
    }
    ```
- **Responses:**
  - **201 Created**: The booking is successfully created.
    - **Response Body Example:**
    ```json
    {
      "id": "7894",
      "venue_id": "0001",
      "user_id": "1000",
      "start_time": "2024-08-14T09:00:00Z",
      "end_time": "2024-08-14T10:00:00Z",
      "purpose": "SDP Lecture",
      "status": "Confirmed"
    }
    ```

#### 2.3. Update an Existing Booking

- **Endpoint:** `PUT /bookings/{booking_id}`
- **Description:** Updates the details of an existing booking.
- **Path Parameters:**
  - `booking_id` (String, Required) - The unique identifier of the booking to update.

- **Request Body:**
  - **Body Parameters:**
    - `venue_id` (String, Required) - The ID of the venue being booked.
    - `user_id` (String, Required) - The ID of the user making the booking.
    - `start_time` (String, Required) - The start time of the booking in ISO 8601 format.
    - `end_time` (String, Required) - The end time of the booking in ISO 8601 format.
    - `purpose` (String, Optional) - The purpose of the booking.
  - **Request Body Example:**
    ```json
    {
      "venue_id": "0001",
      "user_id": "1000",
      "start_time": "2024-08-14T09:00:00Z",
      "end_time": "2024-08-14T10:00:00Z",
      "purpose": "SDP Lecture"
    }
    ```

- **Responses:**
  - **200 OK**: The booking has been successfully updated.
    - **Response Body Example:**
      ```json
      {
        "booking_id": "12345",
        "venue_id": "0001",
        "user_id": "1000",
        "start_time": "2024-08-14T09:00:00Z",
        "end_time": "2024-08-14T10:00:00Z",
        "purpose": "SDP Lecture",
        "status": "updated"
      }
      ```

#### 2.4. Cancel a Booking

- **Endpoint:** `DELETE /bookings/{booking_id}`
- **Description:** Cancels a booking.
- **Path Parameters:**
  - `booking_id` (String, Required) - The unique identifier of the booking to cancel.
- **Responses:**
  - **200 OK**: The booking is successfully canceled.



## Schedule API :watch:

## Maintenance API :hammer_and_wrench:

## Notification API :bell:

---

# Database Schema :floppy_disk:

For our project, we use a **Hierarchical Model**, which organizes data in a “tree-like” structure with parent-child relationships. Our chosen database, Firebase Firestore, uses this hierarchical model to effectively manage and scale our data.

## User Database :file_folder:

**Users Collection**

**1. Collection**: `users`

**Document**: `{userId}` (Document ID is a unique identifier for each user, such as `firebase_uid`)

**Document Fields:**

- `name`: User’s first name (string)
- `surname`: User’s last name (string)
- `email`: User’s email address (string)
- `role`: User’s role (string) – e.g., student, or staff
- `faculty`: User’s faculty or department (string)
- `is_tutor`: Indicates if the user is a tutor (boolean)
- `is_lecturer`: Indicates if the user is a lecturer (boolean)

**Example Document:** <br>
In the example below, the user should be able to make venue bookings since the `is_lecturer` field is set to `true`. If it was set to `false`, they would not have the priviledge to book venues.

> ```json
> {
>   "name": "John",
>   "surname": "Doe",
>   "email": "john.doe@wits.ac.za",
>   "role": "staff",
>   "faculty": "science",
>   "is_tutor": false,
>   "is_lecturer": true
> }
> ```

**Example Document:** <br>
In the following example, the user should be able to make bookings since the `is_tutor` field is set to `true`. If it was set to `false`, they would not have the priviledge to book venues.


> ```json
> {
>   "name": "Mitsy",
>   "surname": "Nkuna",
>   "email": "2538929632@students.wits.ac.za",
>   "role": "student",
>   "faculty": "science",
>   "is_tutor": true,
>   "is_lecturer": true
> }
> ```

**2. Bookings Subcollection**

**Subcollection**: `bookings` (inside each user document)

**Document**: `{bookingId}` (Document ID for each booking)

**Document Fields:**

- `venue`: The unique identifier for the venue (string) – e.g., `wss1`
- `start_time`: The start time of the booking (timestamp)
- `end_time`: The end time of the booking (timestamp)
- `booker_id`: The email of the user who made the booking (string)

**Example Document**

> ```json
> {
>   "venue": "wss1",
>   "start_time": "2024-10-19T10:15:00Z",
>   "end_time": "2024-10-19T11:00:00Z",
>   "booker_id": "john.doe@wits.ac.za"
> }
> ```

**3. Courses Subcollection**

**Subcollection**: `courses` (inside each user document)

**Document**: `{courseId}` (Document ID for each course)

**Document Fields:**

- `course_code`: The code of the course (string) – e.g., `COMS1018A`
- `lecturer_email`: The email of the course instructor, since they are responsible for making the booking. (string) – e.g., `john.doe@wits.ac.za`

**Example Document:**

> ```json
> {
>   "course_code": "COMS1018A",
>   "lecturer_email": "john.doe@wits.ac.za"
> }
> ```

**Summary of Schema Structure**

![Users Table](media/userstable.svg)

---

---

## Booking Database :clipboard:

## Schedule Database :calendar:

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

>```json
>{
>  "roomId": "Room101",
>  "userId": "User123",
>  "issueType": "Electrical",
>  "description": "Light not working",
>  "status": "Open",
>  "createdAt": "2024-08-12T09:00:00Z",
>  "assignedTo": "Staff456"
>}
>```

**2. Subcollection: `maintenanceLogs`**

This subcollection is found inside each `maintenanceRequests` document. It tracks the history of actions taken on the request.
**Document**: `{logId}`

**Document Fields:**
- `logId` (String): Unique identifier for the log entry.
- `actionTaken` (String): Description of the action – e.g., "Request created," "Status changed to In Progress."
- `actionBy` (String): Identifier for the user who performed the action.
- `timestamp` (Timestamp): Date and time when the action was taken.

**Example Document:** <br>

>```json
>{
>  "logId": "Log001",
>  "actionTaken": "Request created",
>  "actionBy": "User123",
>  "timestamp": "2024-08-12T09:01:00Z"
>}
>```

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

>```json
>{
>  "roomId": "Room101",
>  "building": "Science Building",
>  "floor": "1st",
>  "roomType": "Classroom",
>  "capacity": 30,
>}
>```

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

This structure simplifies the maintenance tracking process by focusing on essential details, making it easier to manage and query.


**Summary of schema structure:**


# Testing and Quality Assurance :test_tube:

---

# Deployment and Integration :rocket:

---

# Challenges and Solutions :thinking:

---

# Conclusion and Future Work :trophy:

---

# Appendices :file_cabinet:

```

```
