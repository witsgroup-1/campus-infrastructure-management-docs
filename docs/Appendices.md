

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


### Sprint 1 Retrospective

Date: 20/08/2024

- Attendees:
- Claire Newman
- Busisiwe Vemba
- Mayuri Balakistan
- Dineo Chiloane
- Menzi Shazi
- Chloe Dube

- documentation is good, but needs to be more descriptive and specific.
- overall documentation structure was liked by the client
- client hopes that we can make document information more accessable (different pages for different headings).
- marks were lost on lack of communication between subsystems.
- the team worked well together and finished their work well in advance.
- next sprint, focus on communicating with other groups.

### Sprint 2 Meeting 4 (Sprint Planning)

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
- client asked for no signup page (just login with GoogleAuth)

### Meeting 6

Date: 3 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

Minutes
- Progression in the creatoin of APIs
- Currently, most members are testing their API's and making it more robust (specific GET conditions, PUT etc.)
- mockups are completed for all UI.
- next we must contact other groups for their API information.
- new work was delegated: 
  - google Auth, map API. login front-end and back-end: Menzi
  - making a booking functionality, onboarding functionality: Dineo
  - functionality for maintenance reports and logs, onboarding front-end: Claire
  - manage bookings functionality, dining reservation API: Busi
  - Schedule front-end and functionality, security API: Mayuri
  - My bookings functionality, user dashboard front- and back-end: Chloe
- onboarding pages requested by client.

### Meeting 7 (Sprint Review)

Date: 10 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)
- client

Minutes of meeting with client
- Client likes our newest version of the UI.
- Members are worried about API integration.
- APIs are unavailable, so we must stub them.
- Stubbing security API by hardcoding contact information, dining API by hardcoding reservations and transportation by hardcoding major locations for some venues.
- We must focus on getting our backend to work and integrate well.
- We must also remember to test our code (unit, integration tests etc.)