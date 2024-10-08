
# BOLD ROUTE AND TOURS

## Project Description

The BOLD ROUTE AND TOURS can better understand their clients thanks to this dashboard. It enables BOLD ROUTE AND TOURS to ascertain whether or not their clients are happy with their offerings. They learn about their areas for improvement through various ratings, and by recognising these areas, they may enhance their services. Additionally, it provides them with the average delay and departure time. Having discovered the issue through the use of this dashboard, they can now focus on the causes of these unwelcome delays.

Since, number of neutral/dissatisfied customers (almost 57 %) are more than satisfied customers (around 43 %), thus in all they must work on improving their services. 




### Steps followed 

- Step 1: Load data into Power BI Desktop, the dataset is a CSV file.
- Step 2: Open the power query editor & in the view tab under the Data Preview section, and check the "column distribution", "column quality" & "column profile" options.
- Step 3: Also since by default, the profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4: It was observed that in none of the columns errors & empty values were present except column named "Arrival Delay".
- Step 5: For calculating average delay time, null values were not taken into account as only less than 1% of values are null in this column(i.e column named "Arrival Delay") 
- Step 6: In the report view, under the view tab, the theme was selected.
- Step 7: Since the data contains various ratings, thus to represent ratings, a new visual was added using the three ellipses in the visualizations pane in the report view. 
- Step 8: Visual filters (Slicers) were added for four fields named "Class", "Customer Type", "Gate Location" & "Type of travel".
- Step 9: Two card visuals were added to the canvas, one representing the average departure delay in minutes & other representing the average arrival delay in minutes.
           Using a visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration in the average calculation.

           However, by default, while calculating the average, blank values are ignored.
- Step 10: A bar chart was also added to the report design area representing the number of satisfied & neutral/unsatisfied customers. While creating this visual, a field named "Gender" was also added to the Legends bucket, and the number of customers is also segregated according the gender. 
- Step 11: Ratings Visual was used to represent different ratings mentioned below,

  (a) Baggage Handling

  (b) Check-in Services

  (c) Cleanliness

  (d) Ease of online booking

  (e) Food & Drink

  (f) In-freight Entertainment

  (g) In-freight Service

  (h) In-freight wifi service

  (i) Leg Room service

  (j) On-board service

  (k) Online boarding

  (l) Seat comfort

  (m) Departure & arrival time convenience

In our dataset, some parameters were assigned a value of 0, representing those parameters that do not apply to some customers.

All these values have been ignored while calculating the average rating for each of the abovementioned parameters.

- Step 12: In the report view, under the insert tab, two text boxes were added to the canvas, in one of them name of the airline was mentioned & in the other one company's tagline was written.
- Step 13: In the report view, under the insert tab, using the shapes option from the elements group a rectangle was inserted & similarly using the image option company's logo was added to the report design area. 
- Step 14: Calculated column was created in which, customers were grouped into various age groups.

for creating a new column following the DAX expression was written;

        Age Group = 

        if(airline_passenger_satisfaction[Age]<=25, "0-25 (25 included)",

        if(airline_passenger_satisfaction[Age]<=50, "25-50 (50 included)",

        if(airline_passenger_satisfaction[Age]<=75, "50-75 (75 included)",

        "75-100 (100 included)")))

CUSTOMERS GENDER DISTRIBUTION TABLE

![Page 2]![Screenshot (113)](https://github.com/user-attachments/assets/ac36d0cd-53d4-41f5-bb77-f6da311fad18)


        
- Step 15: A new measure was created to find the total count of customers.

The following DAX expression was written for the same,

        Count of Customers = COUNT(airline_passenger_satisfaction[ID])

VISUAL SAMPLE CARD OF CUSTOMER COUNT.

![Snap_Count](https://user-images.githubusercontent.com/102996550/174090154-424dc1a4-3ff7-41f8-9617-17a2fb205825.jpg)

        
 - Step 16 : New measure was created to find  % of customers,

 Following DAX expression was written to find % of customers,

         % Customers = (DIVIDE(airline_passenger_satisfaction[Count of Customers], 129880)*100)

 A card visual was used to represent this perecntage.

 Snap of % of customers who preferred business class

 ![Snap_Percentage](https://user-images.githubusercontent.com/102996550/174090653-da02feb4-4775-4a95-affb-a211ca985d07.jpg)


 - Step 17 : New measure was created to calculate total distance travelled by flights & a card visual was used to represent total distance.

 Following DAX expression was written to find total distance,

         Total Distance Travelled = SUM(airline_passenger_satisfaction[Flight Distance])

 A card visual was used to represent this total distance.


 ![Snap_3](https://user-images.githubusercontent.com/102996550/174091618-bf770d6c-34c6-44d4-9f5e-49583a6d5f68.jpg)

 - Step 18 : The report was then published to Power BI Service.


![Publish_Message](https://user-images.githubusercontent.com/102996550/174094520-3a845196-97e6-4d44-8760-34a64abc3e77.jpg)

# Snapshot of Dashboard (Power BI Service)

![dashboard_snapo](https://user-images.githubusercontent.com/102996550/174096257-11f1aae5-203d-44fc-bfca-25d37faf3237.jpg)


 # Report Snapshot (Power BI DESKTOP)


![Dashboard_upload](https://user-images.githubusercontent.com/102996550/174074051-4f08287a-0568-4fdf-8ac9-6762e0d8fa94.jpg)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Customers = 129880

   Number of satisfied Customers (Male) = 28159 (21.68 %)

   Number of satisfied Customers (Female) = 28269 (21.76 %)

   Number of neutral/unsatisfied customers (Male) = 35822 (27.58 %)

   Number of neutral/unsatisfied customers (Female) = 37630 (28.97 %)


           thus, higher number of customers are neutral/unsatisfied.
           
### [2] Average Ratings

    a) Baggage Handling - 3.63/5
    b) Check-in Service - 3.31/5
    c) Cleanliness - 3.29/5
    d) Ease of online booking - 2.88/5
    e) Food & Drink - 3.21/5
    f) In-flight Entertainment - 3.36/5
    g) In-flight service - 3.64/5
    h) In-flight Wifi service - 2.81/5
    i) Leg room service - 3.37/5
    j) On-board service - 3.38/5
    k) Online boarding - 3.33/5
    l) Seat comfort - 3.44/5
    m) Departure & arrival convenience - 3.22/5

  while calculating average rating, null values have been ignored as they were not relevant for some customers. 

  These ratings will change if different visual filters will be applied.  

  ### [3] Average Delay 

      a) Average delay in arrival(minutes) - 15.09
      b) Average delay in departure(minutes) - 14.71
Average delay will change if different visual filters will be applied.

 ### [4] Some other insights

 ### Class

 1.1) 47.87 % customers travelled by Business class.

 1.2) 44.89 % customers travelled by Economy class.

 1.3) 7.25 % customers travelled by Economy plus class.

         thus, maximum customers travelled by Business class.

 ### Age Group

 2.1)  21.69 % customers belong to '0-25' age group.

 2.2)  52.44 % customers belong to '25-50' age group.

 2.3)  25.57 % customers belong to '50-75' age group.

 2.4)  0.31 % customers belong to '75-100' age group.

         thus, maximum customers belong to '25-50' age group.
         
### Customer Type

3.1) 18.31 % customers have customer type 'First time'.

3.2) 81.69 % customers have customer type 'returning'.

       thus, more customers have customer type 'returning'.

### Type of travel

4.1) 69.06 % customers have travel type 'Business'.

4.2) 30.94 % customers have travel type 'Personal'.

# BOLD ROUTE & TOURS
