# coupon-acceptance
A study on the acceptance of coupons in different driving situations. 

## Data
The data comes from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. 

The attributes of this data set include:
1. User attributes
    -  Gender: male, female
    -  Age: below 21, 21 to 25, 26 to 30, etc.
    -  Marital Status: single, married partner, unmarried partner, or widowed
    -  Number of children: 0, 1, or more than 1
    -  Education: high school, bachelors degree, associates degree, or graduate degree
    -  Occupation: architecture & engineering, business & financial, etc.
    -  Annual income: less than \\$12500, \\$12500 - \\$24999, \\$25000 - \\$37499, etc.
    -  Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    -  Number of times that he/she buys takeaway food: 0, less than 1, 1 to 3, 4 to 8 or greater
    than 8
    -  Number of times that he/she goes to a coffee house: 0, less than 1, 1 to 3, 4 to 8 or
    greater than 8
    -  Number of times that he/she eats at a restaurant with average expense less than \\$20 per
    person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    -  Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    

2. Contextual attributes
    - Driving destination: home, work, or no urgent destination
    - Location of user, coupon and destination: we provide a map to show the geographical
    location of the user, destination, and the venue, and we mark the distance between each
    two places with time of driving. The user can see whether the venue is in the same
    direction as the destination.
    - Weather: sunny, rainy, or snowy
    - Temperature: 30F, 55F, or 80F
    - Time: 10AM, 2PM, or 6PM
    - Passenger: alone, partner, kid(s), or friend(s)


3. Coupon attributes
    - time before it expires: 2 hours or one day

## Question
What's the best way to recommend bar and coffee house and get a high probablility of being accepted by the drivers? 

## Analysis and Recommendations

### Bar Coupons Analysis

Figure 1 - Acceptance Rate of All Coupons
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_all.png "Acceptance Rate of All Coupons")

Figure 2 - Acceptance Rate of Bar Coupons
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barcoupons.png "Acceptance Rate of Bar Coupons")

Figure 3 - Acceptance Rate of Bar Coupons
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barcoupons.png "Acceptance Rate of Bar Coupons")

Figure 4 - Acceptance Rate Based On Bar Visits
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barvisits.png "Acceptance Rate Based On Bar Visits")

Figure 5 - Compare Acceptance Rate Between 2 Scenarios
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barscene1.png "Compare Acceptance Rate Between 2 Scenarios")

Figure 6 - Compare Acceptance Rate Between 2 Scenarios
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barscene2.png "Compare Acceptance Rate Between 2 Scenarios")

Figure 7 - Compare Acceptance Rate Between 3 Scenarios
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barscene3.png "Compare Acceptance Rate Between 3 Scenarios")

### Coffee Coupons Analysis

Figure 1 - Acceptance Rate Based On Gender
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_coffeegender.png "Acceptance Rate Based On Gender")

Figure 2 - Acceptance Rate Based On Age
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_couponexpire.png "Acceptance Rate Based On Coupon Expiration")

Figure 3 - Acceptance Rate Based On Coupon Expiration
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_age.png "Acceptance Rate Based On Age")

Figure 4 - Acceptance Rate Based On Income
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_income.png "Acceptance Rate Based On Income")

Figure 5 - Compare Acceptance Rate Between 3 Scenarios
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_coffeescene1.png "Compare Acceptance Rate Between 3 Scenarios")

