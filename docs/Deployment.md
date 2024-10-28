

# Deployment and Integration :rocket:

---

## Deployment

The website deploys via Azure Web app services using Github actions CI/CD pipeline.

### Version Control 

The CI/CD pipeline is an integral part of the project's workflow. It manages the testing, building and deploying of our application through GitHub actions. It allows for smooth integration between our local development environment and the Azure platform. 

GitHub actions was important to use as it automates the workflow, allowing for tests to be automatically run to keep the website building and deploying in a faulty state. This allowed our code to be reliable and it reduced the manual effort that we would have to do to deploy our website otherwise. 

Another benefit was the continuous integration (CI) and continuous delivery (CD). CI made sure that code was integrated well with the main branch and tested whilst CD automated the deployment so that code reached production with efficiency. 

Furthermore, the CI/CD pipeline along with GitHub actions records the date, time etcetera of the deployment and by who it was done. This made sure we could always keep an audit trail of who made changes and when. 

Overall, the use of GitHub Actions with the CI/CD pipeline allowed for a streamlined approach to testing, building and deployment of our program. 

Branch management guidlines were given to help ensure a lack of mix ups:

- Each collaborator must commit to their own respective branch (labled by their username) or the "Bugs-and-Problems" branch for any problematic code.
- Always pull new updates before you push your new updates to you respective branches.
- Make sure your tests pass before commits.
- Give your commits to your branch meaningful names including: What you did and who you are - Github actions will reflect the date and time so you do not need to worry about that.
- Do not merge to main without the agreement of all devs.

The branch names were initially set as:

- main
- Bugs-and-Problems
- Chloe
- Busi
- Dineo
- Lunar
- May
- Menzi

## Integration
### Details on Integration Implementation: 

#### Safety 
We call the contacts API from the Campus Safety app, and display the essential information in the footers of the user and admin dashboard. The external contacts API is quite extensive and covers many contact details, however we only display the main security details for each campus (west campus, east campus, health campus and education campus). Thus, it is easily accessible and visible for any of those who might be in need for it.  

#### Dining 
Our platform is integrated with Campus Dining services, allowing users to easily make meal reservations. This involved collaborating closely with the Campus Dining team to ensure smooth system integration. By using RESTful APIs, we were able to connect our systems efficiently without requiring either team to dive too deeply into the inner workings of the other’s system. This ensured a seamless user experience and effective collaboration between the teams. 

- So, fetch request of different meal options, 
- choose an establishment 
- State how many will attend,
- close popup. 

What if the external API is not working: 
- We will hardcode some places to eat and their menus with their contact information. 
- It will be up to the user discretion to call the establishments. 


#### Transport 

Our platform is integrated with Campus Transportation, we made us of a map which is powered by an API from the campus transport system, which plays a central role in supplying the essential data needed to inform users of where venues are located. This API provides precise coordinates for each venue, along with venue-specific images, which are both integral to the map’s functionality. With this information, the map can dynamically place markers at the correct locations, allowing users to visualize each venue's placement within the campus environment. 

 - When a user clicks on a marker, they can view these details, enriched by the API’s data, which enables a user-friendly and visually engaging experience.
 - This seamless integration with the campus transport API ensures that the map is always up-to-date, reflecting any changes in venue locations or details.
 - Allows for real-time, accurate navigation support tailored specifically to the campus layout. 


Why we chose to integrate with each feature: 

 
- Safety: Even though we could hardcode it, integrating this information means that it will always be up-to-date. Any changes made in the Campus Security database will automatically reflect on our web application. 
- Dining: Why integrate. We can allow our users to book a reservation for a meeting etc. 
- Transport: To allow for people unfamiliar with some parts of campus to view where they are booking, they can access the map to see in which general part of campus the venue is located. 

In order to make our application more robust, and less reliant on the other subsystems, we have set measures in place to make sure that the components that we intend to integrate into our web app have fallbacks should they fail. Thus, even if the external APIs or data is down or inaccessible, our users are not short on the features that they require. 

How we stub the other groups’ data: 
- Safety: We have a database with basic security contact details (one for each campus), and we use it in tandem with a mock API. If the security contact details from the Campus Safety App are inaccessible, then our app will use our security API to display the data from our security Info database. 
- Dining: We will create a fake API for reservations to restaurants to make reservations. 
- Map: Stubbed using a general Google Maps API which shows the Wits Campus.


---

 
