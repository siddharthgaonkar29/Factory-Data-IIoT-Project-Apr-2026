# Data Thinking
## Learn Fact vs Dimension tables + map factory example :

### Facts 
- Event Based
- Measure Heavy
- Answers Questions like : How much / When / Who etc.
- Very large Dataset : Can go upto million of rows.
- Continuously growing every moment.
eg : machine downtime / production count / temperature readings etc.

### Dimensions 
- Conveys Description - The Context
- Usually Textual Information
- Qualitative 
- Smaller sized data
- Used extensively for filtering and grouping joining tables etc. 
- eg. : Machine Details, manufacturers details, operator information, plant location, product data

### Factory Example
  
#### Fact Table : fact_prod_data : 
  
  | machine_id | product_id | time_id | production_qty | downtime_minutes | temperature |
| ---------- | ---------- | ------- | -------------- | ---------------- | ----------- |
| M01        | P100       | T001    | 120            | 5                | 75          |
| M02        | P200       | T002    | 90             | 12               | 80          |

Questions Answered :
How much produced? 
What were the temperature recorded?
How much was downtime?
Who produced maximum?
 
    
#### Dimension : dim_machines 
  | machine_id | machine_name | plant | type  |
| ---------- | ------------ | ----- | ----- |
| M01        | CNC-1        | Pune  | CNC   |
| M02        | Press-2      | Pune  | Press |
 
Questions Answered :
- What is the Machine Name
- Who was the vendor
- What is the manufacturing year
- What is the expected life expectancy
- Servicing durations 

#### Dimension : dim_products
  | product_id | product_name | category |
| ---------- | ------------ | -------- |
| P100       | Gear         | Auto     |
| P200       | Bolt         | Hardware |

  Question Answered :
- Product Name
- Product type
- product Category
- mfg Criticality

#### Dimension : dim_time
  | time_id | date       | shift | hour |
| ------- | ---------- | ----- | ---- |
| T001    | 2026-04-01 | A     | 10   |

Questions Answered :
- Specific ID given to a particula date/ particular time/ particular/ shift

### Important : How do they connect with each Other : 
- Defined by the Data Model Architecture
- Here we will be using the Star Schema to create a user friendly Data Model for connecting the various tables and facilitating a common source for Business Stakeholders and Analysis teams.

## Star Schema + Design Factory Schema :

#### Star Schema
Star Schema is a type of data model. where the facts table in the centre and connected to the dimensions table through a foreign key and the primary key of the dimension table / surrogate key in case of reliable joins and slowly changing dimensions

#### Factory Schema :

<img width="600" height="467" alt="image" src="https://github.com/user-attachments/assets/07d13013-70a7-4809-96b6-01dd13d1318b" />


## Data WareHouse and Data Lake

<img width="892" height="687" alt="image" src="https://github.com/user-attachments/assets/5edaeee4-ae9f-4b96-9081-27b897bb1d7b" />


## ETL vs. ELT and Mapping to Factory Data Flow.

### ETL vs. ELT

<img width="877" height="380" alt="image" src="https://github.com/user-attachments/assets/135bba63-09a6-4e5e-b778-82d326ccc261" />

### Mapping Factory Data :-

####  ETL in your factory

Extract >> Transform >> Load 

<img width="700" height="450" alt="image" src="https://github.com/user-attachments/assets/52e30627-1f36-4e2d-8e35-a7cb3f7399a9" />

#### When to Use :
- Small / medium Data
- Structured Data
- Final Goal is Data for Reporting / Analytics

####  ELT in your factory modern approach.

Extract >> Load  >> Transform

<img width="600" height="300" alt="image" src="https://github.com/user-attachments/assets/c78f8d69-9fd6-45fd-a854-547e3ba0ce1e" />

#### When to Use :
- IOT Sensor Heavy Data
- High Data Volume
- Need Predictive Maintenance (ML Model)
- Future Flexibility

### Modern Day FActory data Architecture
<img width="800" height="350" alt="image" src="https://github.com/user-attachments/assets/7d16812b-cafb-47ae-888b-eb113cf5ee08" />

















 
