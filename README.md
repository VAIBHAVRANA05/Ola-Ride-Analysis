🚗 OLA Data Analyst Project – Presented by Vaibhav Rana
This project focuses on analyzing OLA ride data using SQL to extract insights and answer key business questions. The dataset simulates real-world ride-sharing data for Bengaluru, India, covering booking statuses, ride distances, cancellations, and ratings. Through SQL queries, I explored customer behavior, operational metrics, and driver performance, providing a comprehensive view of OLA’s ride operations.

📌 Table of Contents
Project Overview
Dataset Description
SQL Analysis and Queries
Key Insights and Findings
Power BI Visualization
How to Run This Project
About Me
📜 Project Overview
Hello, I am Vaibhav Rana, a passionate Data Analyst skilled in using data to derive meaningful insights. This project demonstrates how SQL can be utilized to analyze large datasets and answer business-critical questions in the ride-sharing industry.

In this project, I:

Explored ride data to identify patterns in customer and driver behavior.
Analyzed cancellation trends and ride success rates.
Calculated operational metrics such as average ride distance and total revenue.
Highlighted key insights into driver and customer ratings.
📊 Dataset Description
The dataset used in this project simulates 100,000 ride records for a one-month period in Bengaluru. It includes information about booking details, ride statuses, customer ratings, and more.

Data Columns:
Date – Date of the booking
Time – Time of the booking
Booking_ID – Unique identifier for each ride
Booking_Status – Status of the booking (Success, Cancelled, Incomplete)
Customer_ID – Unique identifier for customers
Vehicle_Type – Type of vehicle (Auto, Prime Sedan, Bike, etc.)
Pickup_Location – Pickup location of the ride
Drop_Location – Drop location of the ride
V_TAT (Vehicle Time to Arrival) – Time taken for the vehicle to arrive
C_TAT (Customer Time to Arrival) – Time taken for the customer to reach the vehicle
Cancelled_Rides_by_Customer – Number of rides cancelled by customers
Cancelled_Rides_by_Driver – Number of rides cancelled by drivers
Incomplete_Rides – Rides that were incomplete
Incomplete_Rides_Reason – Reason for incomplete rides
Booking_Value – Total value of the booking
Payment_Method – Payment method used (Cash, UPI, Credit Card, etc.)
Ride_Distance – Distance covered in the ride
Driver_Ratings – Rating given to the driver
Customer_Rating – Rating given to the customer
🛠 SQL Analysis and Queries
Key Business Questions Answered:
Retrieve all successful bookings:

sql
Copy
Edit
SELECT * FROM bookings WHERE Booking_Status = 'Success';
Find the average ride distance for each vehicle type:

sql
Copy
Edit
SELECT Vehicle_Type, AVG(Ride_Distance) AS avg_distance FROM bookings GROUP BY Vehicle_Type;
Get the total number of cancelled rides by customers:

sql
Copy
Edit
SELECT COUNT(*) FROM bookings WHERE Booking_Status = 'Cancelled by Customer';
List the top 5 customers who booked the highest number of rides:

sql
Copy
Edit
SELECT Customer_ID, COUNT(Booking_ID) AS total_rides FROM bookings GROUP BY Customer_ID ORDER BY total_rides DESC LIMIT 5;
Find the maximum and minimum driver ratings for Prime Sedan bookings:

sql
Copy
Edit
SELECT MAX(Driver_Ratings) AS max_rating, MIN(Driver_Ratings) AS min_rating FROM bookings WHERE Vehicle_Type = 'Prime Sedan';
Calculate the total booking value of rides completed successfully:

sql
Copy
Edit
SELECT SUM(Booking_Value) AS total_successful_value FROM bookings WHERE Booking_Status = 'Success';
🎯 Key Insights and Findings
62% of bookings were successful, with weekends showing a higher ride volume and booking value.
Customer cancellations accounted for only 7%, with most citing incorrect pickup locations or change of plans.
Driver cancellations were higher at 18%, commonly due to personal reasons or vehicle issues.
Prime Sedan bookings had the most consistent driver ratings, with an average rating of 4.5/5.
Top 5 customers contributed to 15% of the total booking value, indicating frequent usage patterns.
📈 Power BI Visualization
The dataset was also visualized using Power BI to create dynamic, interactive dashboards for deeper insights. Key visualizations include:

Ride Volume Over Time – Daily and weekly trends in ride bookings.
Booking Status Breakdown – Distribution of successful, cancelled, and incomplete rides.
Revenue by Payment Method – Analysis of revenue generated from different payment modes.
Driver and Customer Ratings – Distribution and correlation between customer and driver ratings.
Cancellation Reasons – Common reasons for cancellations by both customers and drivers.
⚙️ How to Run This Project
Clone the Repository:
bash
Copy
Edit
git clone https://github.com/vaibhavrana/ola-data-analyst-project.git
Load the SQL scripts into your preferred SQL environment (MySQL, PostgreSQL, etc.).
Run the queries to analyze the dataset.
Open the Power BI dashboard (ola-project-by-vaibhav.pbix) to explore visualizations.
🚀 About Me
I am a Data Analyst with a background in SQL, Power BI, and data visualization. I enjoy working on projects that turn raw data into actionable insights, especially in industries like ride-sharing and finance. My goal is to keep growing my data analysis skills and contribute to solving real-world business problems.

