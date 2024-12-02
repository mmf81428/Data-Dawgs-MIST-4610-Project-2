# Data-Dawgs-MIST-4610-Project-2

# Team Name
15058 Data Dawgs

# Team Members:
1. Anabelle Dolhun - [@Anabelledolhun](https://www.github.com/Anabelledolhun)
2. Hailey Franz - [@Haileyfranz](https://www.github.com/Haileyfranz)
3. Madeleine Fordham - [@mmf81428](https://www.github.com/mmf81428)
4. Alex Craig - [@ACC69908](https://www.github.com/ACC69908)
5. Dakota Corry - [@dakotamarie](https://www.github.com/dakotamarie)

# Scenario Description
The goal of this project is to model and implement a relational database system to help manage essential operational data for Delta airlines. The system mostly branches off from the main entity, trip, that connects information about airports, flights, tickets, baggage, passengers, and more through their relationships. This model is used to help centralize and organize key operational data improving efficiency in areas such as flight management, customer service, baggage handling, and employee assignments. The project includes queries to help produce and analyze data that can be used to enhance the overall experience for both the staff and passengers at Delta Airlines.

# Data Model
Our model works to connect entities within Delta in order to allow managers to filter information regarding customers, employees, flights, specific trips, airports, baggage, Delta accounts, and much more. 

The main center of the data model is the trip entity. The model has the following relationships: 

 The trip entity has a one-to-many identifying relationship with the ticket entity. A ticket can consist of many trips while a specific trip belongs to one specific ticket. This relationship allows managers to filter the tickets that are being bought most or least often. The relationship is identifying because a trip requires the ticket number to be uniquely defined.
 
The trip entity also has a one-to-many non-identifying relationship to the baggage entity. A specific trip can be associated with multiple bags while a specific bag can only be associated with one specific trip. This allows managers to filter data regarding baggage weight, type, etc for each individual trip. The relationship is non-identifying because baggage and trip can exist independently.

The trip entity also has two one-to-many relationships with the airport entity. One for departing airports, and one for arriving airports. An arriving airport can have many different trips, but a trip can only have one arriving airport. The same is true for a departing airport. These relationships help analyze popular flight routes without needing the airport keys for trip identification.

The trip entity has a one-to-many relationship with the passenger entity. A passenger can book multiple trips, but one specific trip is associated with one specific passenger. This relationship is non-identifying because a trip doesn’t need the passenger’s key for identification.

The passenger entity has a one-to-one relationship with the Delta Account entity. A passenger only has one Delta Account and a specific Delta Account can only be related to one customer. This is non-identifying because some customers may not have a Delta Account and it is therefore not necessary to define a specific passenger. 
The ticket entity has a one-to-many relationship with the flight entity. A flight can have many tickets associated with it, however, a specific ticket only links to a specific flight. This relationship is non-identifying because a flight is not necessary to define a ticket. 

The flight entity has a one-to-many relationship to the airplane entity. An airplane can have many different flights that it is used for, while a flight only uses one specific airplane. This relationship is non-identifying, because an airplane is not identified by its flight. 

The flight entity also has a one-to-many relationship with the flight crew entity. A flight crew can go on multiple flights but a flight only has one specific flight crew. This relationship is non-identifying because a flight is not identified by the flight crew that is on it. 

The flight crew entity has a many-to-many relationship with the employee entity. A flight crew can have multiple employees and an employee can work on many different flight crews. This relationship is identifying because you need to know both the employee and the flight crew they were working on to identify an employee on a flight crew. The weak entity of this many-to-many relationship, flight_crew_employee, is used to help connect the relationships. This entity helps identify the flight crew for a specific flight and what each of the employee’s specific roles were.

Finally, one of our improvements was to add a mantinenance entity. An airplane can have many mainenance visits, but one specific mainenance visit belongs to a specific airplane. The addition of this entity is useful because it can be used to track the maintenance dates, types, and statuses of each of the aircraft.


<img width="776" alt="Screenshot 2024-11-29 at 8 47 36 PM" src="https://github.com/user-attachments/assets/e855f3b3-2e5b-4972-89a3-0709a7a8d38c">


# Improvements

We started by making adjustments based off the feedback from the first project. For example, we changed one of the relationships to non-identifying because it did not need to be identifying. The previous model included an identifying relationship between ticket and trip which is unnecessary because ticket and trip entities each have their own unique identifying primary keys. The new data model reflects the changes in altering this relationship to non-identifying.

The next improvement was adding the modality to the model. This provides more specific information about the relationships in the model. For instance, using the relationship between employee and flight_crew_employee, we see that employees do not have to be on the flight crews but flight crews have to be made up of employees. 

Additionally, a new attribute was added to the trip entity. The "date" attribute was added to capture the specific date of each trip so that data related to days, months, and years can be analyzed. 

One of the biggest changes we made to the model was the addition of the maintenance entity for a more thorough and complex model. Please see the description above for further information about this entity (last paragraph of the Data Model explanation).

We then added a substantial amount of data to the model to make it more robust. For instance, the ticket entity returns 800 rows of data.

Finally, the last modification made was that the total miles attribute was removed from the DeltaAccount entity. This attribute was removed because the total miles earned from a Delta account can already be determined using a query that joins DeltaAccount, passenger, and trip with the miles_earned attribute. 

# Data Dictionary


<img width="709" alt="Screenshot 2024-11-29 at 8 58 08 PM" src="https://github.com/user-attachments/assets/38ac5df8-c253-48f2-84df-993f7ce322b5">


<img width="704" alt="Screenshot 2024-11-29 at 8 58 42 PM" src="https://github.com/user-attachments/assets/8d5cea3d-b094-40c6-8d83-47b3386255e2">


<img width="714" alt="Screenshot 2024-11-29 at 8 58 59 PM" src="https://github.com/user-attachments/assets/0f6bb8c3-6d99-48a8-91ec-8b688e79d56f">


<img width="763" alt="Screenshot 2024-11-29 at 8 59 44 PM" src="https://github.com/user-attachments/assets/59076b63-9235-459e-8b96-aff2fe687218">


<img width="761" alt="Screenshot 2024-11-29 at 9 21 20 PM" src="https://github.com/user-attachments/assets/31218575-0dfd-476e-be8e-82d4f52a4741">


<img width="708" alt="Screenshot 2024-11-29 at 9 21 39 PM" src="https://github.com/user-attachments/assets/842fabe5-3f06-42c3-8bc4-c2f57d7eb085">


<img width="694" alt="Screenshot 2024-11-29 at 9 22 01 PM" src="https://github.com/user-attachments/assets/b9887544-996b-4b2a-93ae-790e2f8c669a">


<img width="690" alt="Screenshot 2024-11-29 at 9 22 17 PM" src="https://github.com/user-attachments/assets/84c50336-c41e-40d8-8f00-6a4066838b91">


<img width="695" alt="Screenshot 2024-11-29 at 9 22 31 PM" src="https://github.com/user-attachments/assets/e7e3fd95-2a4f-4b4d-8f58-542529113cac">


<img width="698" alt="Screenshot 2024-11-29 at 9 23 10 PM" src="https://github.com/user-attachments/assets/2f6a8f0c-4027-4bbf-9c58-5704f3bd3eac">


<img width="694" alt="Screenshot 2024-11-29 at 9 23 19 PM" src="https://github.com/user-attachments/assets/e4a99d16-f565-4d7f-b4a9-5dffdccc22fe">


<img width="695" alt="Screenshot 2024-11-29 at 9 23 34 PM" src="https://github.com/user-attachments/assets/e58f0ebb-b490-46f2-8167-9b16e2677b88">


# Queries

1. Which flights generate the most revenue for Delta, and which airplane model are these flights using? 


<img width="588" alt="Screenshot 2024-11-29 at 9 24 29 PM" src="https://github.com/user-attachments/assets/8106f872-c619-4909-a4e2-4b3f49fce201">

This can give Delta an idea of what flights are the most important to prioritize and potentially add more of that flight to their schedule. Additionally, this can also give them a sense of which plans to invest more in as as comparing the the peformances of the different airplane models. This can help managers review wich models are the most used that Delta may want to continue to invest in or to help manage with expected maintenance.


2. Which pilots have flown the most flights (been apart of the most flight crews) and how many miles have they flown overall? 


<img width="701" alt="Screenshot 2024-11-29 at 9 28 10 PM" src="https://github.com/user-attachments/assets/1fdca3d1-2917-42ab-9792-2f569e747b8d">

This can give Delta insight into how far their pilots are flying and how do their miles compare to the number of flights which will tell them if that pilot typically does short or long distance flights. This can also help with data regarding seniority and planning for retirements. Additionally, revealing these experienced pilots can help reveal wich pilots may be the most useful for training and mentoring other less experienced pilots.

3. 


# Data Visualizations

# Dashboard

![viz_project_third](https://github.com/user-attachments/assets/28d33281-9d05-417d-9d2e-cdc52d9261b9)


1. 
<img width="604" alt="Screenshot 2024-11-29 at 9 39 43 PM" src="https://github.com/user-attachments/assets/54ddb9e9-5f99-4bca-9ee3-617bcc18e5e8">


The visualization above models the number of maintenance visits (blue) and trips (orange) that occur throughout each month of the year. This could be helpful for management because it can help show the relationship between maintenance visits and trips (which typically stays relativly close together) and what to expect for the amount of maintenance and trips during the different times of the year. 





# Implementation of the Database


<img width="388" alt="Screenshot 2024-11-29 at 9 52 03 PM" src="https://github.com/user-attachments/assets/f4850605-358e-441a-aae1-5d852c80ebe4">


<img width="536" alt="Screenshot 2024-11-29 at 9 52 17 PM" src="https://github.com/user-attachments/assets/a453a672-b6c9-4156-ba4d-dc7f69025aa6">






















