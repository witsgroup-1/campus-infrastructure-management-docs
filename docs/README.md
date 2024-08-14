# Welcome to Campus Infrastructure Management Docs! :paperclips:

---

<p style="text-align: center;">
    <img src="media/docscover.svg" alt="Users Table" width="500" height="auto"/>
</p>

---

> **Made By Group -1:**<br>
> Claire Newman (2549861) :woman_technologist:<br>
> Dineo Chiloane (2563191) :woman_technologist:<br>
> Chloe Dube(2602515) :woman_technologist:<br>
> Mayuri Balakistan (2543986) :woman_technologist: <br>
> Busisiwe Vemba (2561620) :woman_technologist:<br>
> Menzi Shazi (2453308) :man_technologist:<br>

# Introduction

The Classroom/Venue Management App is designed to enhance the efficiency of managing classroom and venue assignments, bookings, and maintenance on campus. This application integrates seamlessly with academic schedules, providing a centralized platform for room bookings, maintenance issue reporting, and schedule management.

Key features include a room booking system that allows users to reserve classrooms and venues for various purposes, a visual availability calendar for easy schedule viewing, and a notification system to keep users informed of upcoming bookings and updates. The app also supports an admin interface for managing schedules and maintenance tasks, ensuring that all aspects of campus venue management are handled efficiently.

While push notifications are a stretch goal, the app’s secure and scalable infrastructure is built to ensure data integrity and availability. The user-friendly dashboard and robust APIs for booking, scheduling, maintenance, notifications, and user management together provide a comprehensive solution for optimizing space utilization on campus.

---

# Development Process

---

# Component Details

---

# API Specifications

## User Management API

## Booking API

## Schedule API

## Maintenance API

## Notification API

---

# Database Schema

For our project, we use a **Hierarchical Model**, which organizes data in a “tree-like” structure with parent-child relationships. Our chosen database, Firebase Firestore, uses this hierarchical model to effectively manage and scale our data.

## User Database

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
**Example Document:**

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

## Booking Database

## Schedule Database

## Maintenance Database

# Testing and Quality Assurance

---

# Deployment and Integration

---

# Challenges and Solutions

---

# Conclusion and Future Work

---

# Appendices

```

```
