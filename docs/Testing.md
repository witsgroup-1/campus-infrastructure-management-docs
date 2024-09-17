

# Testing and Quality Assurance :test_tube:

---

## Test Plan

- Jest was used to do testing.
- Tests will be made for functions after they are coded so we can test them before deployment.
- There will be unit tests and integration tests.
- The test coverage reports will be uploaded to CodeCov.

## Tests

### Maintenance Tests
Two copies of the maintenance frontend where made so we could standerdise the urls to the local url and not work with the production url.
#### Testing Maintenance Reports
We were testing the Maintenance Request Form where we mocked the structure of the html and the fetch request. The test mimics the DOMContentLoaded and the general structure of the form. 
- Unit test 1: checks if the form submits the form and resets it -> So spies on the console logs and errors afer submitting the required mock values using a fireEvent. It expects a successful log.
- Unit test 2: checks if the form logs an error on failed request -> So it spies on the console logs and errors after submitting required mock values using a fireEven. It expects an error to be logged.
- Integration test: Testing both of these on similar inputs to check if both work as intended on similar inputs.

#### Testing Maintenance Logs
We were testing the different functions of the maintenance logs where we mocked the DOM methods, the fetch request and the input data.
- Unit test 1: Fetches maintenance requests and displays them -> it mocks the DOM and the fetch request then checks if the content is appended to our mocked UI.
- Unit test 2: Displays requests for desktop -> using mock data and one of the mocked UI elements, it check if it has displayed the data in the correct desktop format.
- Unit test 3: Displays initial request for mobile and handles Show More button -> using mock data and one of the mocked UI elements, it check if it has displayed the data in the correct mobile format and then checks if the show more click has worked and more data is displayed.
- Unit test 4: Creates request block -> tests that the function to create the test block with the correct value displayed like "Venue: Room 1" in the resulting html.
- Unit test 5: Opens popup with correct content -> tests that when opening the popup, the resulting html contains the correct input text.
- Unit test 6: Saves changes and updates request -> tests that the mocked fetch request for the post method is successful and that the popup becomes hidded after saving the changes that we posted.
- Unit test 7: Closes popup -> tests that the popup closes when we click close.
- Integration test: Testing that all these functions work on the same mock input.

### User Acceptance Tests
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


### Manage Bookings Testing

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