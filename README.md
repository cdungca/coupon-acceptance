# coupon-acceptance
A study on the acceptance of coupons in different driving situations. This is part of the course work for [UC Berkeley Professional Certificate in Machine Learning and Artificial Intelligence](https://exec-ed.berkeley.edu/professional-certificate-in-machine-learning-and-artificial-intelligence/). 

You can follow the detailed analysis done in the [Jupyter notebook](https://github.com/cdungca/coupon-acceptance/blob/main/prompt.ipynb).

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

Before looking at the bar and coffee house coupon types, we've looked at the acceptance rate of all coupons and also per type.

As you can see from the figure below, 56.86% of the total obsevations chose to accept the coupon.

Figure 1 - Acceptance Rate of All Coupons
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_all.png "Acceptance Rate of All Coupons")

Carry out and take away coupons have the highest acceptance rate, 73.55%, but for this study, we will focus on bar and coffee house coupons.

Figure 2 - Acceptance Rate of Coupons per Type
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_coupons.png "Acceptance Rate of Coupons per Type")

### Bar Coupons Analysis

The overall acceptance rate for bar coupons on the data set is 40.91%. To make the campaign effective, we need to find the different scenarios which will have the highest acceptance rate.

Figure 1 - Acceptance Rate of Bar Coupons
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barcoupons.png "Acceptance Rate of Bar Coupons")

To start off, are those drivers who are already visiting bars more likely to accept the coupons? If we look at the figure below, the acceptance rate increases as the number of visits to bars increases. The highest acceptance rate of 78% is achieved when drivers visits bars 4 times per month.

Figure 2 - Acceptance Rate Based On Bar Visits
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barvisits.png "Acceptance Rate Based On Bar Visits")

To further explore the different scenarios that contribute to the acceptance rate, we will compare:

- drivers who go to a bar more than once a month and are over the age of 25 to the all others
- drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry
- go to bars more than once a month, had passengers that were not a kid, and were not widowed
- go to bars more than once a month and are under the age of 30
- go to cheap restaurants more than 4 times a month and income is less than 50K

Figure 3 - Compare Acceptance Rate Between 2 Scenarios
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barscene1.png "Compare Acceptance Rate Between 2 Scenarios")

Figure 4 - Compare Acceptance Rate Between 2 Scenarios
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barscene2.png "Compare Acceptance Rate Between 2 Scenarios")

Figure 5 - Compare Acceptance Rate Between 3 Scenarios
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_barscene3.png "Compare Acceptance Rate Between 3 Scenarios")

Based on the different analysis, the acceptance rate increases when the driver goes to bars for more than 1 per month. 

To increase the chances of bar coupons being accepted by drivers, they should be given when the following conditions are present:
- goes to bar for more than 1 per month
- does not have a kid as a passenger
- income is more than 50k
- age is older than 25
- occupation is not farming, fishing, or forrestry

### Coffee Coupons Analysis

We've applied the same analysis on the coffee coupons to come up with conditions that will increase acceptance rate.

There is no significant difference on the acceptance rate between male and female as you can see below. The acceptance rate for male is 50.37% and for female is 49.27%.

Figure 1 - Acceptance Rate Based On Gender
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_coffeegender.png "Acceptance Rate Based On Gender")

The highest acceptance rate in terms of age is 69.54% and this is achieved when the drivers are 20 years old. There is also a slight increase in acceptance rate if there is at least 1 day left before the coupon expire (58.32%) compared to 2 hours left (43.02%).

Figure 2 - Acceptance Rate Based On Age
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_couponexpire.png "Acceptance Rate Based On Coupon Expiration")

Figure 3 - Acceptance Rate Based On Coupon Expiration
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_age.png "Acceptance Rate Based On Age")

Does income plays a significant role in affecting the acceptance rate? If we look at the figure below, it is interesting to see that the acceptance rate for those earning less than $12,500 per year (55.19%) is almost the same as those earning between $85,000 - $100,000 (57.20%). 

Figure 4 - Acceptance Rate Based On Income
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_income.png "Acceptance Rate Based On Income")

Since we know from the previous analysis that drivers who are 20 years old will most likely accept the coupons, we will try to combine this with other conditions/scenarios to further increase the rate. We will compare and look at the drivers who:

- goes to cheap restaraunts more than once per month
- goes to regular restaurants more than once per month
- goes to bars more than once per month

Figure 5 - Compare Acceptance Rate Between 3 Scenarios
![alt text](https://github.com/cdungca/coupon-acceptance/blob/main/images/acceptance_rate_coffeescene1.png "Compare Acceptance Rate Between 3 Scenarios")

In all cases, if the driver is 20 years old and they go to restaurants or bars more than once per month, the chances of accepting the coffee coupons is more than 50%. 

The highest percentage though is if they go to regular restaurants more than once per month, 86.67%

In conclusion, to achieve the highest acceptance rate for bar and coffee house coupons, we should offer bar coupons if the following conditions are met:

- goes to bar for more than 1 per month
- does not have a kid as a passenger
- income is more than 50k
- age is older than 25
- occupation is not farming, fishing, or forrestry

And for coffee house coupons, the following conditons should be present:

- age is 20
- goes to a regular restaurants more than once per month
- time left for coupon to expire is at least 1 day


