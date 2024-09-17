

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
- we had difficulty working in a large sub-system and integrating with other groups.
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

### Sprint 2 Meeting 5

Date: 25 August 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

Minutes:
- Basic mockups and wireframes completed.
- Progress on creating databases. 
- Databases must be completed by the end of the sprint and begin creating APIs next sprint.
- We were finally able to get in touch with other groups.
- Security said we can have their contact information API.
- Dining asked for our list of venues API:
  - An extra API and database must be created to deal with this.
- Documentation must be continually updated so information is recent and correct.

### Sprint 2 Meeting 6 (Sprint Review)

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

### Sprint 2 Retrospective

Date: 28 August 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

- Not all databases were created on time. 
- All mockups were completed and appeoved by fellow teammates and the client as well.
- This showed that we were integrating feedback, but fell behind on work.

Challenges we faced during Sprint 2:
- As we were writing tests and focussed on other projects, we fell behind schedule on our website. 
- Communicating with other groups was difficult.

How to improve:
- Focus on the website in the upcoming sprints.
- have fallbacks when the other groups dont pull through.

### Sprint 3 Meeting 7 (Sprint Planning)

Date: 30 August 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

Minutes
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

### Sprint 3 Meeting 8

Date: 1 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

Minutes:
- all databases have now been completed according to the documentation.
- Progression in the creating of APIs.
- API creation may take time because it is a new skill for many members.
- API creation may fall into the next sprint as well.
- members must use the break to make up time.
- work has begun on creating the ui.

- new work will be delegated in the next sprint.
- focus will be on creating core functionaily.


### Sprint 3 Retrospective

Date: 3 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

- we were not able to complete all our APIs.
- this was expected, but we hope to finish them in the next sprint.

Challenges we were faced with:
- API creation because it was not something we were used to.

Moving forward:
- help each other out as much as you can.
- those will more knowledge in one section should help those who are recently learning it.

(Note that Sprint 3 had no Sprint Review as it took place over a semester break. Both the team and the client agreed that the next review will be held in the next sprint.)

### Sprint 4 Meeting 9 (Sprint Planning)

Date: 4 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

Minutes
- Currently, most members are testing their API's and making it more robust (specific GET conditions, PUT etc.)
- next we must contact other groups for their API information.
- new work was delegated: 
  - google Auth, login front-end and back-end: Menzi
  - making a booking ui and functionality: Dineo
  - maintenance reports and logs ui and functionality: Claire
  - manage bookings ui and functionality: Busi
  - Your bookings ui and Schedule front- and back-end: Mayuri
  - My bookings functionality, user dashboard front- and back-end: Chloe
- onboarding pages requested by client.

### Sprint 4 Meeting 10

Date: 8 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

Minutes: 
- most of the ui is completed and work has begun on the functionality.
- it was decided that similar pages will follow the same ui design (such as all forms having the same layout).
- some ui differs from the mockups:
  - must update the changed designs in the documentation.
- settled on design choices such as only the dashboard having a sidebar, what links the sidebar will have and how the onboarding will work. 
- focus must be on functionality in order to get the work done on time.

### Sprint 4 Meeting 11 (Sprint Review)

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

### Sprint 4 Retrospection

Date: 10 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

- all APIs are now completed and all ui is created.
- we were unable to complete the functionality.
- this is a problem since we also have to complete basic testing.

Challenges we faced:
- time management
- the break broke our flow of teamwork

How to deal with it in the next sprint:
- try to complete the work as fast and early as possible to make integration quicker and less stressful.
- communicate better with each other.

### Sprint 5 Meeting 12 (Sprint Planning)

Date: 10 September 2024 (whatsapp)

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

Minutes
- other groups have stated that we will only get their apis later in the week.
- this may be too late to integrate it with our work, therefore we must plan of mocking the API information.

- new work was delegated: 
  - Menzi: mocking map API
  - Dineo: onboarding page functionality
  - Claire: onboarding page ui
  - Busi: dining reservation mocking
  - Mayuri: security api mocking
  - Chloe: whitelist implementation (requested by client)
- new focus is on testing.
- this may also be difficult because the members are not used to it.

### Sprint 5 Meeting 13

Date: 13 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)
 
Meeting:
- most core functionality is completed.
- members are struggling with testing.
- the focus is on functionality, even if testing is not completed.
- we have decided that core functionality will be completed by Sunday evening
- api stubs will be completed by monday evening.
- documenatation must be ready to go by tuesday morning.

### Sprint 5 Meeting 14 (Sprint Review)

Date: 17 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)
- client

Observations made by the client plus improvements that could be made:
- client likes our front-end/ui.
- clearing maintenance logs after a specific time.
- admin must be able to edit, delete venues
- admins must be able to manage whitelist.
- record access to API keys: increment count every time x===API_KEY to use as proof if nobody uses our keys.
- use a Google form with graphs and charts to record user feedback.
- mock APIs instead of hardcoding it.
- clean up and rectify testing.
- remove apple and facebook logos from login.
- only allow wits accounts to log in.
- hopefully implement dark mode.


### Sprint 5 Retrospective
Date: 17 September 2024

Attendees:
- Mayuri Balakistan(2543986)
- Chloe Dube (2602515)
- Claire Newman (2549861)
- Dineo Chiloane (2563191)
- Busisiwe Vemba(2561620)
- Menzi Shazi(2453308)

- we were unable to complete all testing.
- most functionality was working, although there were bugs.

Challenges:
- our time management and working well alongside other projects.
- API integration
- testing

How to proceed:
- we plan on having more meetings, so we can better deal with our progress and time management.
- properly mock APIs
- spend time on getting testing to work accurately.
- study the rubric so we can have everything we need and more.