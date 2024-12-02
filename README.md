# Data-Dawgs-MIST-4610-Project-2

# Team Name
## Data Dawgs
## CRN: 15058 

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

### 1- Which flights generate the most revenue for Delta? 

<img width="758" alt="Screenshot 2024-12-02 at 11 27 44 AM" src="https://github.com/user-attachments/assets/5b1187f2-6f00-47b8-a54b-ec96430e6d11">

#### Description-
This query calculates which flights generate the most Revenue for Delta Airlines. Because some flights are taken more than others, this figure is communicated using the average revenue per instance of the flight. Information about the airplane model is also given. 
 
#### Justification-
This information is valuable for Delta to know because they can know which flights to prioritize their best service on and advertise. Additionally, this can give Delta an idea about which planes are preferred and help them guide their capital investments by showing which planes often generate the most revenue. 


### 2- Which Pilots have flown the most flights and how far?

<img width="718" alt="Screenshot 2024-12-02 at 11 26 33 AM" src="https://github.com/user-attachments/assets/9ae60a28-4bd7-4a71-9288-cbdd2afc95db">

#### Description-
This query calculates the amount of miles traveled on each flight for each pilot. This is done by finding their total number of flights and total mileage. Information about their employee number and full name are given. 
 
#### Justification-
This can show Delta which pilots are putting in the most work. If each pilot earns the same amount of salary (fixed) per year, this can allow Delta to see which pilots should be prioritized in the case of giving out bonuses. In the case where pilots earn commission, this can give Delta a foundation to base their salaries off of. Additionally, by incorporating their total mileage, this can show Delta which Pilots tend to do more short distance or a few long distance trips which can allow them to categorize them so they know which pilots to assign to certain flights (whether its short or long distance). 


### 3- How do Passenger's baggage weight compare to the Total Baggage Weight?

<img width="718" alt="Screenshot 2024-12-02 at 11 25 05 AM" src="https://github.com/user-attachments/assets/97928293-5f5d-4454-a4c9-b1947270dc46">

#### Description- 
This query calculates the weight of baggage that passengers have brought for different trips in relation to the total amount of baggage weight. Information about who the customer is is also provided by generating their full name, passenger ID, and state of residence.

#### Justification- 
This can allow Delta to predict which customers tend to carry a large proportion of luggage on a flight. Knowing who these customers are can allow Delta to identify potential solutions in the case of having excess weight. Further, it lists the full name of the customer so Delta can know which customers they can potentially offer rewards or discounts for them to bring less bags. As a result, Delta can also make predictions based on the customers on the flight how heavy they will be traveling if they are a returning customer and anticipate more luggage for certain states. 

### 4- Which airplanes have the most maintenance performed on them?

<img width="718" alt="Screenshot 2024-12-02 at 11 22 44 AM" src="https://github.com/user-attachments/assets/bdcbb99c-1153-4440-a2b3-d0791bd62cfc">

#### Description- 
This query lists which airplanes have the most maintenance performed on them. Additionally, it also provides which specific airplane and its model. The type of maintenance is also listed to convey whether the maintenance is performed due to use (such as safety checks/inspections) or if it is due to wear-and-tear (such as repairs). 

#### Justification- 
Delta can get an idea of which planes tend to cause more issues. They can potentially identify a pattern about which model usually has more issues than others. As a result, Delta can take this into consideration when choosing which airplanes to use and which ones they want to invest in.

### 5- Which seasons have the most travel activity?

<img width="718" alt="Screenshot 2024-12-02 at 11 24 11 AM" src="https://github.com/user-attachments/assets/98a005d1-ef4f-4c97-97d5-f17d6cb5583b">

#### Description-
This query starts by calculating which months correspond to which seasons. It then returns the total number of trips for that season and ranks them by trips to show which season contains the most trips and therefore travel activity.
 
#### Justification-
It is important for Delta to know which season will contain the most travel activity so they can prepare and plan accordingly prior to when they are actually busy. This can allow them to avoid delays, shortages, and other issues that can result from a lack of preparation. We chose to evaluate the trips based on the season, as opposed to months,  to view this on a broader scale and convey overall trends.  



# Data Visualizations

## Dashboard

![viz_project_third](https://github.com/user-attachments/assets/28d33281-9d05-417d-9d2e-cdc52d9261b9)


### 1- Number of Maintenances and Trips per month

![maintenance](https://github.com/user-attachments/assets/d61740be-3112-4275-bebf-160957bb5585)


#### Description-
The visualization above models the number of maintenance visits (blue) and trips (orange) that occur throughout each month of the year. It indicates how the number of maintenance and number of trips can relate to one another. This visualization also provides information about which months have more travel activity, and therefore maintenance activity as a result. 

#### Justification-
It is important for Delta to know which months demand more plane usage. Knowing that there is a relationship between the number of maintenance and the number of trips in a given month can show Delta when to prepare for more busy travel months and when they will need to make sure they have an extra supply of maintenance workers. 

### 2- Years at Delta by Job Title

![years_at_delta](https://github.com/user-attachments/assets/844dacd0-0506-470b-b9b9-41be66c6ac0f)


#### Description-
The number of years at Delta according to each job title shows the maximum, minimum, and average amount of years that the employees have worked at Delta, categorized by different job titles.

#### Justification-
This gives delta an idea about the amount of time that each worker works there. This allows them to compare which positions have a higher retention rate. As a result, Delta can have a better idea of their employee turnover rate and gain an understanding of when they need to look for new applicants. It is important for Delta to anticipate this so they can avoid a shortage of labor during those turnover periods. 

### 3- Baggage by State Residence and Membership

![status](https://github.com/user-attachments/assets/c748817a-ba80-4a61-915b-1a81bb9f526c)


#### Description-
The baggage count by Delta Account status shows a total of the amount of bags that passengers bring according to their state of residence. It is further categorized into whether they are a member or not. The orange color is different Delta Account statuses while the blue are the null values (or members who do not have accounts). The data is sorted by the top seven states with the most baggage.

#### Justification- 
This can allow Delta to be able to predict which states tend to have more bags brought on their flights. They can make additional predictions based on the general proportions of members versus nonmembers on the flight. It is important for Delta to have an understanding of how many bags to anticipate on certain flights and choose a plane with proper storage. 


# Implementation of the Database

### Employees (1) Table
<img width="988" alt="Screenshot 2024-12-02 at 11 52 16 AM" src="https://github.com/user-attachments/assets/8ae12f91-b1f2-4f25-86fd-36c46759291e">

### Flight_Crew_Employees (2) and Flight_crew (3) Tables 
<img width="914" alt="Screenshot 2024-12-02 at 11 55 17 AM" src="https://github.com/user-attachments/assets/2507ac1e-8e02-4682-83ce-49ee7d02328d">

### Airplane (4) Table
<img width="1027" alt="Screenshot 2024-12-02 at 11 56 03 AM" src="https://github.com/user-attachments/assets/4cb19c2c-3c1e-4762-9134-608efb97def4">

### Maintenance (5) Table
<img width="997" alt="Screenshot 2024-12-02 at 11 57 10 AM" src="https://github.com/user-attachments/assets/ce30dcc9-4c85-491e-9994-ca2c46de3f8a">

### Flight (6) Table
<img width="928" alt="Screenshot 2024-12-02 at 11 58 47 AM" src="https://github.com/user-attachments/assets/3d54e9fc-613f-4184-966e-35731ca60dd8">

### Airport (7) Table
<img width="1025" alt="Screenshot 2024-12-02 at 11 59 59 AM" src="https://github.com/user-attachments/assets/b612e61d-81f2-49e8-904d-a736e3779670">

### Ticket (8) Table
<img width="932" alt="Screenshot 2024-12-02 at 12 01 01 PM" src="https://github.com/user-attachments/assets/679bfc9c-d0f6-41b1-9d42-ae92090d1917">

### Trip (9) Table
<img width="1004" alt="Screenshot 2024-12-02 at 12 01 45 PM" src="https://github.com/user-attachments/assets/d326b29a-0267-4b95-81f9-0bd13c01e94a">

### Baggage (10) Table
<img width="1035" alt="Screenshot 2024-12-02 at 12 02 43 PM" src="https://github.com/user-attachments/assets/1883c421-08bf-4e04-b1ed-5689c5184e2b">

### Passenger (11) Table
<img width="1014" alt="Screenshot 2024-12-02 at 12 03 13 PM" src="https://github.com/user-attachments/assets/b712a1f4-72a9-42df-a993-3ff8986110d9">

### DeltaAccount (12) Table
<img width="986" alt="Screenshot 2024-12-02 at 12 03 49 PM" src="https://github.com/user-attachments/assets/59a42ab9-ed48-4985-80e1-0d1e282ab3e3">

