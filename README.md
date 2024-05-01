# Case Study: Analysing the Sydney Used Motorbike Market

## Introduction
This project, part of the Google Data Analytics Professional Certificate, aims to analyse the Sydney used motorbike market data to determine key factors influencing prices. 

Employing the six step process for data analysis, we derive insights to empower prospective buyers.

## Step 1 - Ask
### 1.1 Problem Statement
Prospective buyers face challenges navigating the Sydney used motorbike market. This project seeks to provide insights for informed purchasing decisions.

### 1.2 Case-Study Objectives
1. Identify trends and insights.
2. Empower buyers with informed purchasing decisions.

### 1.3 Key Stakeholders
- Prospective buyers and sellers
- Insurance companies
- Motorbike dealerships

### 1.4 Deliverables
1. Clear problem statement
2. Data sources description
3. Data cleaning documentation 
4. Analysis
5. Visualisations and findings
6. High-level recommendations

### 1.5 Tools
- Google Sheets: Data cleaning, manipulation, transformation, and analysis 
- Tableau Public: Data visualisations

## Step 2 - Prepare
### 2.1 Data Sources
Facebook Marketplace, Gumtree, and Bikesales. 

### 2.2 Data Collected
Focused on Yamaha MT-03 model sales listings data for depth and popularity.

A preview of the first 25 rows:
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/62e9be26-de7c-4745-847b-64dfa9a71729)

### 2.3 Challenges and Limitations
1. Limited generalisability of findings to other motorbike models 
2. Small sample size (<50) and short collection period (four weeks).

### 2.4 Data Quality Assessment (ROCCC)
A high quality data source is ROCCC, which stands for:
1. Reliable - High
2. Original - High
3. Comprehensive - Low
4. Current - High
5. Cited - High

## Step 3 - Process
### 3.1 Data Cleaning
Removed or fixed data that did not belong in the dataset.
- No null or missing values
- No duplicates
- Removed a irrelevant row referring to a new motorbike data
  ![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/41a57c02-d601-44c8-9258-b7aba87deb33)
- Fixed a typo within _Price_ incorrectly entered as $550 instead of $5500
  ![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/a9beddf1-0cb5-4d3c-b25b-38bab266ae12)

### 3.2 Data Transformation
Converted data types to different types to prepare for subsequent analysis:
- Converted _Price_ column from string to numeric data type
- Converted _Odometer Reading (km)_ to integer data type
- Standardised _Registration Expiry Date_ and _Listing Date_ columns to DD-MM-YYYY date formats 

### 3.3 Data Manipulation
- Created a new _Price/km_ column to normalise the price based on mileage for further analysis
  ![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/46f8b56a-6dfb-4372-b834-ead0331333d0)

## Steps 4 - Analyse
### 4.1 Linear Regression Analysis
#### 4.1.1 Manufacture Year
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/6dde4d45-683a-46ae-8cba-96d5a2b61c49)

Regression Equation:

  $Price = 290.023 × Manufacture Year - 579744$

- R of 0.7 (R^2 = 0.49) suggests a moderate positive correlation
- For every additional year, the price increases by approximately $290.023, all else being equal
- Insight: Newer models tends to command higher prices, indicating depreciation

#### 4.1.2 Odometer Reading
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/45557e16-7dee-4935-8d9b-bfd866332026)
- R of -0.39 (R^2 = 0.15) suggests a weak negative correlation
- Thus, other factors may also play a significant role in influencing price
- Insight: Lower odometer readings generally lead to higher prices, suggesting buyers were willing to pay more for motorbikes that have been ridden less

#### 4.1.3 Price/km
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/cfd9eb48-def8-4529-89f0-ffc3bdc9c9aa)
Removed outlier as it may skew the subsequent analysis by applying filter
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/661b589b-e1eb-4a2d-b3ff-ae09b0e3f356)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/e004ae55-b98b-424c-871b-bdcfef158673)
- R of 0.43 (R^2 = 0.18) suggests a weak positive correlation.
- Again, the weak correlation suggests that other factors also play a significant role in impacting price
- Insight: Used motorbikes with a lower Price/km generally tend to be priced lower in the market 
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/5046d7cf-f3e6-4da1-991c-12074dbfff6c)

### 4.2 Exploratory Data Analysis 
#### 4.2.1 Seller Type
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/a84a41ee-8294-45fb-b63c-c0ecac338e6b)

![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/4bfcd236-cf96-42a6-8c01-f1c41ed815b7)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/b8c6afee-2772-4f64-b538-42bb6285b5be)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/cd90ffae-bce0-43a9-bb21-f14ab6e5d3fb)
	
1. The mean and median for dealer prices were $273 and $1065 higher than private prices, respectively.
    - This could be due to various factors such as dealers offering additional services like warranties or having higher overhead costs.
2. The price range for private sellers is wider ($4000 - $6800) compared to dealers ($5199 - $7099).
		○ A key reason for the difference could be negotiation dynamics as private sellers may have more flexibility and willingness to negotiate prices compared to dealerships

#### 4.2.2 Colour
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/c1071277-74c1-4116-ac3a-950e43c391c7)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/b7f9fa8e-fd77-4df6-a845-392e1a168e85)
- Blue motorbikes have the highest average price ($5771.6) among the analysed colours
- Grey motorbikes follow closely behind with $5706.1
- Silver motorbikes have the lowest average price of $4960
- Significant range ($4960 - $5771) indicates differences in market demand or other influencing factors

#### 4.2.3 Registration Expiry Date
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/48802be5-4383-45f6-9815-a4c851f8454e)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/bc142a51-6905-4cab-937e-0c74675ab944)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/bc7e1183-46c7-40a7-84bf-70956048c601)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/fdd6af47-a64f-4a98-aba0-8524d827d908)

- The mean and median were $141 and $295 higher than those without registration expiry dates, respectively
  - This may be because there is a financial value associated with registered motorbikes
-  Registered bikes have a large price range ($4450 - $7500) than bikes without details ($5199 - $7099))

#### 4.2.4 Description
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/d8fc7c78-8b29-4510-b73e-7a945c08b235)

Assign sentiment labels to the Top 15 words
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/d9c7da87-7564-48d8-9f8d-4662c6985192)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/ee7ea10d-7bf2-4287-a84c-85cc758aed3e)
- Listing descriptions often emphasise positive attributes like "great," "new," and "service". This indicates the sellers' efforts to highlight the quality, condition, and maintenance history of the motorbikes to instill confidence in buyers
2. Mention of "tail" and "tidy" likely refers to the aftermarket accessories which enhance aesthetics, showcasing the sellers' focus on visual appea
3. While positive descriptors are essential for attracting buyers, sellers maintained transparency about potential issues "scratches" which was the 13th most frequently occurring word
This may help sellers build trust with prospective buyers and mitigate any concerns about the condition of motorbikes

#### 4.2.5 Listing Status
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/d8a9354f-4af4-415b-bf68-466e418ec2de)
- 45% of bikes were sold, and 55% remained available
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/86676509-7b46-4936-9782-989c6e2dd115)
![image](https://github.com/RichardShi1/Analysis-of-Used-Motorbike-Prices/assets/168516843/c0faaac8-78de-45b8-bfd6-533f5f5f2bee)

## Step 5 & 6 - Share and Act
Key Insights 
1. Newer motorbike tend to command higher prices, indicating depreciation. Each additional year typically results in a price increase of approximately $290.93
2. Lower odometer readings lead to higher prices, suggesting buyer preference for less ridden vehicles
3. Dealers list motorbikes at higher prices compared to private sellers. Private sellers offer a wider price range, potentially due to negotiation dynamics
4. Blue motorbikes have the highest average price, followed by grey, while silver motorbikes have the lowest average price
5. Sellers emphasise positive attributes and aftermarket accessories in listings, enhancing the perceived value. Additionally, transparency about potential issues may help sellers establish trust among buyers
- Note: It is important to note that external factors such as economic conditions, market trends, and seasonal demand could also influence motorbike prices. Furthermore, correlation does not imply causation, and other factors may be at play

High-level Recommendations 
1. Priortise newer bikes with lower odometer readings for better value and potentially fewer maintenance issues
2. Assess pros and cons buying from dealers versus private sellers. For example, private sellers may offer more negotiation flexibility, whereas dealers may provide warranties
3. Consider colour preferences and associated price differences. Blue and grey motorbikes command higher prices on average, indicating potential resale advantages or market demand
