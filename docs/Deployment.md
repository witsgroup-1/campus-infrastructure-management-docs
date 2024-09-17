

# Deployment and Integration :rocket:

---

## Deployment

The website deploys via Azure Web app services using Github actions CI/CD pipeline.

### Version Control

When it comes to version control we need to define some things first:

- Product: A product is what we can offer to the user to fufill their requirments.
- Product feature: A products specific characteristics or functions that are important to the customer - so desin and functionality are included.

Ref: https://www.aha.io/roadmapping/guide/requirements-management/what-are-product-features

Version Control is mostly managed by github actions using the CI/CD pipeline - so it will record the date, time etc.
Branch management guidlines were given to help ensure a lack of mix ups:

- Each collaborator must commit to their own respective branch (labled by their username) or the "Bugs-and-Problems" branch for any problematic code.
- Always pull new updates before you push your new updates to you respective branches.
- Make sure your tests pass before commits.
- Give your commits to your branch meaningful names including: What you did and who you are - Github actions will reflect the date and time so you do not need to worry about that.
- Do not merge to main without the agreement of all devs.

The branch names are set as:

- main
- Bugs-and-Problems
- Chloe
- Busi
- Dineo
- Lunar
- May
- Menzi

## Integration

- Transport: Why integrate. The Map API can give us the most up to date locations of venues within our Application.
- Events Management: Why integrate. To keep our booking system up to date so that we do not face clashes.
- Saftey: Why integrate. For security details we can get the most up to date security information.
- Dining: Why integrate. We can allow our users to book a reservation for a meeting etc.

### Details on Integration Implementation:
### How will we stub their data

- Transport: Hardcode some locations for major venues.
- Events Management: hardcode some events to make sure our system is aware of them and up to date.
- Saftey: Hardcode some known security information (contact details for security of every campus).
- Dining: We will have some hardcoded resturants to make reservations too in our venue data collection. The reservations will be noted down in a list and acted upon in a timely manner.
  
#### Transport
We plan to show users the venue location of venues in our application by displaying the map location.
- We will fetch their MAP API and display the locations of venues

#### Events Managment (requires there API):

#### Safety
On the footer of the user dashboard we will call the Security applications API of most relevent security contact information incase someone needs an emergency number. 
- so preform a fetch request on the externel API and disply the information on the user dashboard footer.
What if the externel API is not working
- We will hardcode emergency contact information to display in the footer.

#### Dining
When a user books a venue they must get a popup asking if they want to book a reservation along with their venue booking. 
- So fetch request of different dining options
- Click on your desired eatery.
- State how many will attend
- close popup.
What if the externel API is not workingl:
- We will hardcode some places to eat with their contact information.
- It will be up to the user discretion to call the establishments.
