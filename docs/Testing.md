

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
### Maintenance
- Given that I am a user



