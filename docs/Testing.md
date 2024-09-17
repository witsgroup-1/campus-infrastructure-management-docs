

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
#### Testing Maintenance Repors
We were testing the Maintenance Request Form where we mocked the structure of the html and the fetch request. The test mimics the DOMContentLoaded and the general structure of the form. 
- unit test 1: checks if the form submits the form and resets it -> So spies on the console logs and errors afer submitting the required mock values using a fireEvent. It expects a successful log.
- unit test 2: checks if the form logs an error on failed request -> So it spies on the console logs and errors after submitting required mock values using a fireEven. It expects an error to be logged.
- Integration test: Testing both of these on similar inputs to check if both work as intended on similar inputs.


