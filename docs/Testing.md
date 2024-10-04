

# Testing and Quality Assurance :test_tube:

---

## Test Plan

- Jest was used to do testing.
- Tests will be made for functions after they are coded so we can test them before deployment.
- There will be unit tests and integration tests.
- The test coverage reports will be uploaded to CodeCov.

## Tests

### Maintenance Tests
### Unit tests for Maintenance
Two copies of the maintenance frontend where made so we could standerdise the urls to the local url and not work with the production url.
#### Testing Maintenance Reports
We were testing the Maintenance Request Form where we mocked the structure of the html and the fetch request. The test mimics the DOMContentLoaded and the general structure of the form. 
- Unit test 1: Submits the form correctly. -> Mocks the data and checks if the form has been posted via fetch request when the form is submitted.
- Unit test 2: Displays an alert if venue is not selected correctly. -> The test mocks the html data and creates a DOM content loaded event. We simulate an empty input for venues and we spy on an alert to see if it tells us to "Please select a valid venue from the dropdown". We expect the venue input field to be reset.

Overall 50% coverage of this file. It is not full coverage as the authentication is tested with other files and some of the integration tests actiually cover these smaller aspects of the code to do with the venue dropdown.
#### Testing Maintenance Logs
We were testing the different functions of the maintenance logs where we mocked the DOM methods, the fetch request and the input data.
- Unit test 1: Fetches maintenance requests and displays them -> it mocks the DOM and the fetch request then checks if the content is appended to our mocked UI.
- Unit test 2: Displays requests for desktop -> using mock data and one of the mocked UI elements, it check if it has displayed the data in the correct desktop format.
- Unit test 3: Displays initial request for mobile and handles Show More button -> using mock data and one of the mocked UI elements, it check if it has displayed the data in the correct mobile format and then checks if the show more click has worked and more data is displayed.
- Unit test 4: Creates request block -> tests that the function to create the test block with the correct value displayed like "Venue: Room 1" in the resulting html.
- Unit test 5: Opens popup with correct content -> tests that when opening the popup, the resulting html contains the correct input text.
- Unit test 6: Saves changes and updates request -> tests that the mocked fetch request for the post method is successful and that the popup becomes hidded after saving the changes that we posted.
- Unit test 7: Closes popup -> tests that the popup closes when we click close.
We are testing the staff users function works
- Unit test 1: Fetches staff members and populates dropdown when input is provided -> Fetches the staff members (those who arent lecturers, tutors and students) via a search of 'Jo' (our mock data). It poulates the dropdown and we verify this.
- Unit test 2: Clears and hides dropdown when no query is provided. So provide a empty query in the input field, start the event and expect a clear dropdown that is hidden.
- Unit test 3: Check if the code handles an API error gracefully for the staff search. -> Mock the failed API response, then check if the dropdown is hidded and cleared.
- Unit test 4: Handles staff selection from dropdown. -> So we call the setupStaffSearch(apiKey) function to set up the search. Then we populate the dropdown. We simulate the click of an option and then verify the input value is updated.

Overall 89% coverage of this file- the left our lines of coverage were not integral for testing.

### Integration Testing for Maintenance
Using playwright we did ingtegration testing as it would go into the browser and test the code from there.

#### Testing Maintenance Reports
Testing the dropdown integration:
- Get some mock data and test that the dropdown should populate the dropdown when the venue data loads. We expect to see the mock room names ro appear
- Check if a venue is selected, it updates the input field. So we populate the dropdown, mock the click and then we expect the input field to update with our choice.
- Clear the dropdown when  the clearVenueDropdown function is called. We populate the dropdown and see if it clears once we call the function.
Testing maintenance logs dropdown:
- 


### Testing for editBookings.js

## Overview

The test suite for editBookings.js focuses on validating the correctness of utility functions related to date formatting, time slot extraction, and validation of dates and time slots. The tests use the Jest framework to ensure these functions behave as expected under various scenarios.

## Test Descriptions

`formatDateDMY` Function:

Purpose: To verify that the formatDateDMY function correctly formats a given date string into the "Day Month Year" format.
Test Case: For the input date string '2024-09-17', the function should return '17 September 2024'.

`extractStartEndTime` Function:

Purpose: To ensure that the extractStartEndTime function accurately extracts and returns the start and end times from a time slot string.
Test Case: For the input time slot '9:00 AM - 11:00 AM', the function should return an object { startTime: '9:00 AM', endTime: '11:00 AM' }.

`isValidDate` Function:

Purpose: To check if the isValidDate function correctly identifies valid and invalid date strings.
Test Cases: The function should return true for the valid date string '2024-09-17' and false for an invalid date string 'Invalid Date'.

`isValidTimeSlot` Function:

Purpose: To verify that the isValidTimeSlot function correctly validates time slot strings based on the expected format.
Test Cases: The function should return true for the valid time slot string '9:00 AM - 11:00 AM' and false for an invalid time slot string 'Invalid Time Slot'.

## Setup and Teardown
Global Mock: fetch is mocked globally to prevent actual network requests during tests.
Reset State: Before each test, the mock for fetch is cleared, and any necessary global or DOM state is reset.
These tests ensure that the utility functions in editBookings.js perform their intended tasks accurately, contributing to the overall robustness of the application.

### Book Venue Testing

#### Unit Tests for `book-venue.js`

In this section, I created unit tests to verify the functionality of key functions in the `book-venue.js` file. The main goal is to ensure that the user data is fetched correctly, venues are rendered as expected, and the allowed categories for bookings are properly determined based on user roles. I used Jest for testing and mocked several dependencies, including Firebase and the global `fetch` function.

**Mocking Firebase and Global Dependencies**

Before diving into the individual tests, Firebase services and global functions like `fetch` and `alert` are mocked to isolate the code being tested:

- **Firebase Mocks:** Firebase is mocked to avoid actual API calls to Firebase's authentication and Firestore services during testing. This ensures that the tests focus on how the application handles Firebase-related data and functions.
  
- **Global Fetch Mock:** The `fetch` function is mocked to simulate API responses. This allows us to control whether the fetch request succeeds or fails, which is particularly useful for testing error handling.

- **Global Alert Mock:** `window.alert` is mocked to prevent actual alerts from popping up during tests, while still allowing us to verify that it was called.

**Test 1: `fetchUserData` Function**

The `fetchUserData` function is responsible for fetching user data from the API. The function should return user information if the API call is successful, or `null` if the user is not found (404 error).

- **First Test:** Verifies that `fetchUserData` correctly fetches and returns user data. The test mocks a successful API response with a sample user object and checks that `fetch` is called with the expected URL.
  
- **Second Test:** Simulates a 404 response from the API and verifies that `fetchUserData` returns `null` in this case.

**Test 2: `fetchAndRenderBookings` Function**

This function fetches available venues based on the user’s role and renders them in the DOM. The test mocks the DOM elements necessary for rendering the venues and verifies that the function correctly fetches the appropriate venues based on the user's role.

- **Test:** The test checks that the function fetches venues with the correct category filter and renders them in the DOM. It ensures that the `fetch` function is called with the correct API URL.

**Test 3: `getAllowedCategories` Function**

The `getAllowedCategories` function determines which categories of venues the user is allowed to book, based on their role (e.g., Student, Tutor, Lecturer).

- **First Test:** Verifies that students who are not tutors or lecturers can only book study rooms. The test provides user data with the role of "Student" and checks that the function returns the correct allowed categories.

- **Second Test:** Verifies that staff members who are lecturers can book multiple categories of venues, including tutorial rooms, exam venues, boardrooms, and lecture halls.

**Test 4: `renderVenues` Function**

This function renders venue data into the DOM. The test ensures that venues are displayed correctly in the bookings container based on the user's role and privileges.

- **Test:** The test checks that the function correctly renders the venue names and details into the DOM. It mocks two venue objects (Lecture Hall and Tutorial Room) and verifies that both venues are displayed in the `bookingsContainer` element.

**Conclusion**

These unit tests ensure that key functions in `book-venue.js` are working correctly by simulating various scenarios, such as successful and failed API calls, different user roles, and venue rendering in the DOM. Mocking Firebase and global functions allows us to isolate the functionality of the code and focus on testing its logic without interacting with external services.



## User Acceptance Tests

The application and the designs of this application was given to family members and friends to try and view. Here are some of their responses:
- The colour scheme is much better then the original initial desing.
- The structure is good - feels progessional.
- Clean and logical.


### Onboarding UATs

#### As a Student

1. **Onboarding Process**: 
   - As a student, I can go through the onboarding process the first time I access the site. This process will collect my basic information and set up my account, allowing me to use the site's features.

#### As a Lecturer

1. **Onboarding Process**:
   - As a lecturer, I can complete the onboarding process when I first access the site. This will include specifying my faculty and role, and optionally indicating if I am a tutor or lecturer. This setup will allow me to access and use all relevant site features.

#### As a Staff Member

1. **Onboarding Process**:
   - As a staff member, I can complete the onboarding process upon first accessing the site. I will need to provide necessary information and complete any optional sections to fully access the site's features.

### Maintenance UATs
- Given that I am a user, when I submit a filled in maintenance report then it must be submitted successfully: Expected  console log "Maintenance request created successfully!" and a cleared input form. Test outcome: Pass - recieved the log and a cleared  input form.
- Given that I am a user, when I submit an unfilled in maintenance report then it must tell me to enter data into the required fields: Expected  a field to appear under one of the inputs saying to fill in the required fields. Test outcome: Pass - recieved the message.
- Given that I am a user, when I view the maintenance logs then I should see maintenance request blocks appearing in all three columns: Expected maintenance request blocks appearing under columns "Scheduled","In progress","Completed". Test outcome: Pass - Saw the popups.
- Given that I am a user, when I click a maintenance log request then I should see a popup containing its details: Expected   Popup appeared. Test outcome: Pass - Saw the popup.
- Given that I am a user, when I edit a maintenance log popup field and click save changes it should then update the information on the screen: Expected   Input entered and once changes saved see the popup in a new column. Input (status: Completed, assignedTo: staff123, timestamp: 17th September 2024 09:00 ). Test outcome: Pass - The maintenance request was updated and in the new column.
-  Given that I am a user, when I click close on a maintenance log popup then I should see the popup closing and go back to the main screen: Expected   Popup closed. Test outcome: Pass - Saw the popup close.

### Manage Bookings UATs

- Given the page is loaded, when `fetchVenues` is called, then the venue dropdown should be populated with data from the API and the correct venue should be selected based on the booking ID.
- Given the page is loaded, when `fetchBookings` is called, then bookings should be fetched from the API and stored in the `bookings` array.
- Given `populateVenues` is called with venue data, when the dropdown with ID `venueSelector` is updated, then it should contain options for each venue with the venue ID as the value and the venue name as the text.
- Given a venue ID is provided, when `isValidVenue` is called, then it should return `true` for a valid venue ID and `false` for an invalid one.
- Given a date string is provided, when `isValidDate` is called, then it should return `true` for a valid date and `false` for an invalid date.
- Given a time slot string is provided, when `isValidTimeSlot` is called, then it should return `true` for a correctly formatted time slot and `false` otherwise.
- Given valid venue, date, and time slot data are provided, when `saveChanges` is called, then the booking should be successfully updated via the API and an alert should notify "Booking edited successfully."
- Given an invalid venue is selected, when `saveChanges` is called, then an alert should notify "Please select a valid venue."
- Given an invalid date is entered, when `saveChanges` is called, then an alert should notify "Please enter a valid date."
- Given an invalid time slot is entered, when `saveChanges` is called, then an alert should notify "Please select a valid time slot."
- Given a date string is provided, when `formatDateDMY` is called, then it should return the date formatted as "Day Month Year."
- Given a time slot string is provided, when `extractStartEndTime` is called, then it should return an object with the start and end times extracted from the string.

### User acceptance tests for Schedules

- Given that I am a user, when I log into the app, then I am able to make a booking.
- Given that I am a user, when i log in using GoogleAuth, then the process is simpler.
- Given that I am a user, when I specify my role, then i am able to access the right functionality.
- Given that I am a user, when I view all venues, then i can choose one to book.
- Given that I am a user, when I view all my upcoming bookings, then I will not forget them.
- Given that I am a user, when I view all past bookings, then i can keep a record of them.
- Given that I am a user, when I view all my schedules, then i can prepare for them.
- Given that I am a user, when I add a new schedule, then i can keep my life organized.
- Given that I am a user, when I view all scheduled maintenance requests, then i can delegate them.
- Given that I am a user, when I view all in progress maintenance requests, then i can make sure they finish.
- Given that I am a user, when I view all completed maintenance requests, then i can keep a reord of them.
- Given that I am a user, when I report a maintenance issue, then i can prevent sny accidents.
- Given that I am a user, when I log out, then i am able to keep my information safe.
- Given that I am a user, when I receive notification, then i can stay up to date.
- Given that I am a user, when I see security contact information, then i am able to contact security.
- Given that I am a user, when i make a dining reservation, then i am sure that my place in the dining hall is booked.

## User Acceptance Tests for Venue Booking

**1. Book Study Room as a Student**
- **Given** that I am a student user who is neither a lecturer nor a tutor,
- **When** I attempt to book a study room,
- **Then** I can book the study room for the specified time.

**2. Book Study Room and Tutorial Room as a Student Tutor**
- **Given** that I am a student user who is a tutor but not a lecturer,
- **When** I attempt to book a study room or tutorial room,
- **Then** I can successfully book either a study room or tutorial room for the specified time.

**3. Book Study Room, Tutorial Room, Exam Venue, Boardroom, and Lecture Hall as a Student Lecturer**
- **Given** that I am a student user who is a lecturer but not a tutor,
- **When** I attempt to book a study room, tutorial room, exam venue, boardroom, or lecture hall,
- **Then** I can successfully book any of these venues for the specified time.

**4. Book Tutorial Room, Exam Venue, Boardroom, and Lecture Hall as a Staff Lecturer**
- **Given** that I am a staff member who is a lecturer,
- **When** I attempt to book a tutorial room, exam venue, boardroom, or lecture hall,
- **Then** I can successfully book any of these venues for the specified time.

**5. Book Study Room, Tutorial Room, Exam Venue, Boardroom, and Lecture Hall as a Staff Member**
- **Given** that I am a staff member who is neither a tutor nor a lecturer,
- **When** I attempt to book a study room, tutorial room, exam venue, boardroom, or lecture hall,
- **Then** I can successfully book any of these venues for the specified time.

**6. Book All Allowed Venues as a Staff Member who is Both a Lecturer and a Tutor**
- **Given** that I am a staff member who is both a tutor and a lecturer,
- **When** I attempt to book any venue,
- **Then** I can successfully book a study room, tutorial room, exam venue, boardroom, or lecture hall for the specified time.

**7. Book All Allowed Venues as a Student who is Both a Lecturer and a Tutor**
- **Given** that I am a student user who is both a lecturer and a tutor,
- **When** I attempt to book any venue,
- **Then** I can successfully book a study room, tutorial room, exam venue, boardroom, or lecture hall for the specified time.

**8. Book No Venues if User Role is Unspecified**
- **Given** that my user role is unspecified or missing,
- **When** I attempt to book any venue,
- **Then** I will be unable to book any venues.

## User Acceptance Tests for General Dashboard

**1. View Venues Section**
- **Given** the user is on the dashboard page,
- **When** the user views the "Venues" section,
- **Then** the section should display a list of venues with relevant details.

**2. View Upcoming Bookings Section**
- **Given** the user is on the dashboard page,
- **When** the user views the "Upcoming Bookings" section,
- **Then** the section should display a list of their upcoming bookings with correct dates and times.

**3. Floating Action Button: Navigate to Report Page**
- **Given** the user is on the dashboard page,
- **When** the user clicks on the floating action button,
- **Then** a menu should appear with quick access options, including "Report",
- **And** clicking on "Report" should navigate the user to the report page.

**4. Floating Action Button: Navigate to Book Page**
- **Given** the user is on the dashboard page,
- **When** the user clicks on the floating action button,
- **Then** a menu should appear with quick access options, including "Book",
- **And** clicking on "Book" should navigate the user to the booking page.

**5. Notification Bell: View Notifications**
- **Given** the user is on the dashboard page,
- **When** the user clicks on the notification bell icon,
- **Then** a dropdown should appear showing a list of notifications,
- **And** each notification should be clickable to view details.

**6. Menu Button: Open Navigation Bar**
- **Given** the user is on the dashboard page,
- **When** the user clicks on the menu button,
- **Then** a navigation bar should open from the side of the screen,
- **And** the navigation bar should display links to various pages, such as "My Bookings", "Make a Report", "Make a Reservation", etc.

**7. Navigation Bar: Navigate to a Page**
- **Given** the user is on the dashboard page with the navigation bar open,
- **When** the user clicks a link in the navigation bar,
- **Then** the user should be navigated to the corresponding page,
- **And** the navigation bar should close automatically after navigation.


## User Acceptance Tests for Admin Dashboard

**1. Manage Bookings**
- **Given** the user is on the admin dashboard page,
- **When** the user selects the "Manage Bookings" option,
- **Then** the user should be navigated to the bookings management page,
- **And** the user should be able to view, edit, or delete bookings.

**2. Manage Venues**
- **Given** the user is on the admin dashboard page,
- **When** the user selects the "Manage Venues" option,
- **Then** the user should be navigated to the venues management page,
- **And** the user should be able to view, edit, or delete venue details.

**3. Add Venue Button**
- **Given** the user is on the "Manage Venues" page,
- **When** the user clicks the "Add Venue" button,
- **Then** a form should appear allowing the user to input details for a new venue,
- **And** the venue should be added to the list upon successful submission.

**4. Manage Reports**
- **Given** the user is on the admin dashboard page,
- **When** the user selects the "Manage Reports" option,
- **Then** the user should be navigated to the maintenance reports logs page,

**5. Manage Schedules**
- **Given** the user is on the admin dashboard page,
- **When** the user selects the "Manage Schedules" option,
- **Then** the user should be navigated to the schedules management page,
- **And** the user should be able to view, add, or update schedules.

**6. Notification Bell: View Maintenance Reports**
- **Given** the user is on the admin dashboard page,
- **When** the user clicks the notification bell icon,
- **Then** a dropdown should appear showing the latest maintenance reports submitted,

**7. Inbox: View Whitelist Requests**
- **Given** the user is on the admin dashboard page,
- **When** the user clicks on the inbox icon,
- **Then** a dropdown should appear showing people requesting to be added to the whitelist

**8. Menu Button: Open Navigation Page**
- **Given** the user is on the admin dashboard page,
- **When** the user clicks on the menu button,
- **Then** a navigation page should open from the side of the screen,
- **And** the navigation page should display links such as "Manage Whitelist", "Manage Requests", "Admin Dashboard" and "Log out".

**9. Navigate to View All Whitelist Members**
- **Given** the user is on the navigation page,
- **When** the user clicks the "Manage Whitelist" link,
- **Then** the user should be navigated to the page displaying all whitelist members.

**10. Navigate to Whitelist Requests**
- **Given** the user is on the navigation page,
- **When** the user clicks the "Manage Requests" link,
- **Then** the user should be navigated to the page displaying all pending whitelist requests.

**11. Navigate to Admin Dashboard in General User Dashboard**
- **Given** the user is on the navigation page,
- **When** the user clicks the "Admin Dashboard" link,
- **Then** the user should be navigated back to the admin dashboard.


## Why is our code coverage ___%
### For Milestone 2 
We focused our attention on unit tests for the core features. 

Some lines of code are not covered as thouroughly: This is not a bad thing as some lines are not nessacary to cover or do not need to be as strongly covered as they are functions not prone to error/pointless in the grand scheme of the project.

Some functions have not been unit tested yet and some tests have not been integrated with the main repository.

Patch Coverage is sometimes higher then code coverage: This can often be better then high code coverage as it focuses on the changes to code introduced per pull, patch etc. So it checks how much of the new code is covered by tests and thus shows a good quality in the changes made and helps prevent the introduction of new issues such as regressions.
(ref: https://about.codecov.io/blog/why-patch-coverage-is-more-important-than-project-coverage/)

# Add Venues Page Unit Testing 

## Overview

The test suite for the addVenues page uses Jest to perform unit tests on the main functions in `addVenueCopy.js`. The tests cover the core functionality of fetching venues, displaying venues, creating venue blocks, adding new venues, and handling form submissions.

## Test Coverage

The current test coverage for this suite is 82.6%.

## Key Areas Tested

1. **API Interactions**: 
   - `fetchVenues()`: Tests successful API calls and error handling.
   - `addVenue()`: Verifies correct API calls for adding new venues.

2. **DOM Manipulations**:
   - `displayVenues()`: Ensures correct rendering of venue information.
   - `createVenueBlock()`: Checks the structure of individual venue blocks.

3. **Form Handling**:
   - `handleFormSubmit()`: Tests the form submission process, including successful submissions and error scenarios.

## Testing Approach

- **Mocking**: The global `fetch` function is mocked to simulate API calls without actually making network requests.
- **DOM Simulation**: A minimal HTML structure is set up before each test to simulate the necessary DOM elements.
- **Event Simulation**: Form submission events are simulated to test the `handleFormSubmit` function.

## Why Not 100% Coverage?

While 82.6% coverage is good, it's not 100% for several reasons:

1. **Error Scenarios**: Some error paths might not be fully covered, especially for network or unexpected errors.

2. **DOM Event Listeners**: The `initVenueManagement` function, which sets up event listeners, is likely not fully tested due to the complexity of simulating DOM content loading.

3. **Browser-Specific Functions**: Functions like `alert()` are mocked but their full behavior in a browser environment isn't tested.

4. **Asynchronous Operations**: Some edge cases in asynchronous operations might be missed.

5. **Environment Variables**: The `apiKey` constant isn't tested, as it's typically an environment variable.

# Integration Testing for addVenue Page

## Overview

This document outlines the integration tests for the addVenues Page using Playwright. These tests verify the end-to-end functionality of adding new venues and fetching existing venues.

## Test Suite

### 1. Add Venue and Verify List

This test case verifies the process of adding a new venue and confirms its presence in the venues list.

#### Steps:

1. Navigate to the Add Venue page.
2. Fill out the venue form with test data.
3. Submit the form.
4. Verify the success alert.
5. Check if the new venue appears in the updated venues list.

#### Assertions:

- Confirm the success alert message.
- Verify the presence of the newly added venue in the list.
- Check if all venue details (name, capacity, category, features, building) match the input data.

### 2. Fetch and Display Existing Venues

This test case ensures that existing venues are properly fetched and displayed on the page load.

#### Steps:

1. Navigate to the Add Venue page.
2. Wait for the venues list to load.
3. Extract the list of displayed venues.

#### Assertions:

- Verify that the venues list is not empty.
- Check the structure of each venue block, ensuring all required information is present.

## Test Environment

- **Framework**: Playwright
- **Browser**: Default browser provided by Playwright
- **Base URL**: `http://localhost:3000/adminDashboard/addVenue.html`

## Running the Tests

To run these tests:

1. Ensure the application is running on `localhost:3000`.
2. Execute the Playwright test command (e.g., `npx playwright test`).

## Notes
- The tests include a 1-second wait time after adding a venue to allow for list updates. This might need adjustment based on actual application performance.
