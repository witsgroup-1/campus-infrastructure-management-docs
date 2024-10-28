

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
- Saftey: Why integrate. For security details we can get the most up to date security information.
- Dining: Why integrate. We can allow our users to book a reservation for a meeting etc.

### Details on Integration Implementation:
### How will we stub their data
- Saftey: Use a mock API for some known security information (contact details for security of every campus).
- Dining: We will create a fake API for reservstions to resturants to make reservations.
  
#### Safety
On the footer of the user dashboard we will call the Security applications API of most relevent security contact information incase someone needs an emergency number. 
- so preform a fetch request on the externel API and disply the information on the user dashboard footer.
What if the externel API is not working
- We will hardcode emergency contact information to display in the footer.

#### Dining
When a user books a venue they must get a popup asking if they want to book a reservation along with their venue booking. 
- So fetch request of different meal options
- Click on your desired meal.
- choose an establishment
- State how many will attend
- close popup.
What if the externel API is not working:
- We will hardcode some places to eat and their menyes with their contact information.
- It will be up to the user discretion to call the establishments.
