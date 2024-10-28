

# Challenges and Solutions :thinking:
1. Limited Jest Experience 

Challenge: 
A significant challenge was that the team had limited experience with Jest, which initially slowed down the testing process. Without a solid understanding of Jest’s syntax and testing functions, creating effective and accurate tests for the project required additional time and effort. 

Solution: 
The team addressed this challenge by taking the initiative to self-study Jest, focusing on documentation and tutorials to improve familiarity. Additionally, open communication played a key role in overcoming obstacles; team members actively shared insights, examples, and tips, enabling everyone to progress more efficiently. This collaborative learning approach not only accelerated the learning curve but also fostered a more cohesive team dynamic, ultimately strengthening our testing skills as a whole. 

 
2. Integration with other systems 

Challenge: 
Integration with other groups was challenging, primarily due to communication gaps and delays in receiving essential APIs. With dependencies on their API functionality for certain parts of our system, these delays impacted our timeline, making it difficult to test end-to-end workflows effectively. Misalignment on requirements and delivery dates also added to the challenge, as changes on their side occasionally required rework on our end. 

Solution: 
To maintain momentum and robustness in our system, we created mocks for the missing APIs. This approach allowed us to simulate expected responses and continue development and testing without waiting for the final APIs. By mocking the necessary data, we could validate our system’s functionality independently and ensure smooth integration once the actual APIs became available. Additionally, regular check-ins with the other teams helped keep us updated on their progress, aligning our work whenever possible. 

 
3. Data Formatting (Handling Timestamps for Dates)
   
One of the challenges encountered was related to formatting the data retrieved from the database, specifically when working with timestamps. The booking data in the database was stored using Unix timestamps, which represent dates and times as the number of seconds since January 1, 1970. While this format is efficient for storage and computation, it’s not user-friendly when displaying the date on a web page. 

Challenge: 
The raw timestamp data was not suitable for direct display, and converting it into a readable format (e.g., “10 October 2024") for users posed a challenge, especially when different parts of the application required different formatting styles, such as long-form dates (including day and time) versus short-form (just the date or just the time). 

Solution: 
We had to implement the formatting of dates to make them correctly visible in the booking information. This solution made it possible to display the date on various pages in a format that users could easily understand. 

 
4. API Key Security and Usage Logging 

Securing our API with API keys presented a significant technical challenge. The goal was not only to restrict access to the API but also to log the number of times each API key was used.  

Challange: 
The problem with API keys was that we needed a simple and effective solution so as to not overcomplicate our security system. 

Solution:   
We created five API keys. Four of these keys would be given to the other subsystems to use to access our API. 

Challange: 
The problem with API key logging was that If one of the five API keys was used to update the APILogs database it would cause an infinite loop. 

Solution:  
A special API key for logging other API keys was created. This keys use would not be tracked. 


---
