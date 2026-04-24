## **Data Dictionary for Student Success Risk Pipeline** ##

-------------------------------------------------------


## **Target Variable**

| Column | Description              | Values                       |
| ------ | ------------------------ | ---------------------------- |
| target | Student academic outcome | 1 = Dropout, 0 = Not Dropout |

## **Demographics**

| Column            | Description                  | Values                     |
| ----------------- | ---------------------------- | -------------------------- |
| marital_status    | Student marital status       | Encoded numeric categories |
| gender            | Student gender               | 0 = Female, 1 = Male       |
| age_at_enrollment | Age at enrollment            | Numeric                    |
| nationality       | Student nationality          | Encoded numeric categories |
| international     | International student status | 0 = No, 1 = Yes            |

## **Academic Background**

| Column                       | Description                  | Values                            |
| ---------------------------- | ---------------------------- | --------------------------------- |
| application_order            | Program preference ranking   | Numeric (lower = higher priority) |
| daytime_evening_attendance   | Attendance type              | 0 = Evening, 1 = Daytime          |
| previous_qualification       | Prior education level        | Encoded numeric categories        |
| previous_qualification_grade | Previous qualification grade | Numeric (0–200)                   |
| admission_grade              | Admission score              | Numeric (0–200)                   |

## **Financial & Status Indicators**

| Column                    | Description            | Values          |
| ------------------------- | ---------------------- | --------------- |
| debtor                    | Has outstanding debt   | 0 = No, 1 = Yes |
| tuition_fees_up_to_date   | Tuition payment status | 0 = No, 1 = Yes |
| scholarship_holder        | Scholarship status     | 0 = No, 1 = Yes |
| displaced                 | Displacement status    | 0 = No, 1 = Yes |
| educational_special_needs | Special needs status   | 0 = No, 1 = Yes |

## **Academic Performance — 1st Semester**

| Column                                       | Description              |
| -------------------------------------------- | ------------------------ |
| curricular_units_1st_sem_credited            | Units credited           |
| curricular_units_1st_sem_enrolled            | Units enrolled           |
| curricular_units_1st_sem_evaluations         | Evaluations taken        |
| curricular_units_1st_sem_approved            | Units passed             |
| curricular_units_1st_sem_grade               | Average grade (0–20)     |
| curricular_units_1st_sem_without_evaluations | Units without evaluation |

## **Academic Performance — 2nd Semester**

| Column                                       | Description              |
| -------------------------------------------- | ------------------------ |
| curricular_units_2nd_sem_credited            | Units credited           |
| curricular_units_2nd_sem_enrolled            | Units enrolled           |
| curricular_units_2nd_sem_evaluations         | Evaluations taken        |
| curricular_units_2nd_sem_approved            | Units passed             |
| curricular_units_2nd_sem_grade               | Average grade (0–20)     |
| curricular_units_2nd_sem_without_evaluations | Units without evaluation |

## **Economic Indicators**

| Column            | Description                |
| ----------------- | -------------------------- |
| unemployment_rate | National unemployment rate |
| inflation_rate    | Inflation rate             |
| gdp               | Gross Domestic Product     |

## **Course (One-Hot Encoded)**

Each column = 1 if student is in that category, else 0

| Column                        |
| ----------------------------- |
| course_Business/Management    |
| course_Business/Services      |
| course_Computer Science/IT    |
| course_Design/Creative        |
| course_Education              |
| course_Engineering/Technology |
| course_Health                 |
| course_Media/Communication    |
| course_Social Services        |

## **Application Mode (One-Hot Encoded)**

| Column                             |
| ---------------------------------- |
| application_mode_Regular Admission |
| application_mode_Special Entry     |
| application_mode_Transfer/Change   |
| application_mode_Other             |


## **Parent Occupation (One-Hot Encoded)**

### Mother

| Column                            |
| --------------------------------- |
| mothers_occupation_Highly Skilled |
| mothers_occupation_Skilled        |
| mothers_occupation_Unskilled      |
| mothers_occupation_Military       |
| mothers_occupation_Other          |

### Father

| Column                            |
| --------------------------------- |
| fathers_occupation_Highly Skilled |
| fathers_occupation_Skilled        |
| fathers_occupation_Unskilled      |
| fathers_occupation_Military       |
| fathers_occupation_Other          |


## **Parent Qualification (One-Hot Encoded)**

### Mother

| Column                             |
| ---------------------------------- |
| mothers_qualification_Higher       |
| mothers_qualification_Secondary    |
| mothers_qualification_No Education |
| mothers_qualification_Other        |

### Father

| Column                             |
| ---------------------------------- |
| fathers_qualification_Higher       |
| fathers_qualification_Secondary    |
| fathers_qualification_No Education |
| fathers_qualification_Other        |

## **Preprocessing Notes**

* Categorical variables were **simplified into broader groups** before encoding
* One-hot encoding was applied, resulting in binary columns (0/1)
* Each encoded group has an **implicit reference category** (not shown due to `drop_first=True`)
* Target variable was converted to binary:

  * Dropout = 1
  * Enrolled/Graduate = 0
