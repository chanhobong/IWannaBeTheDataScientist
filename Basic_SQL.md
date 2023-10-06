# SQL
## Basic Select
### Weather Observation Station 5
Query the two cities in STATION with the **shortest and longest CITY names**, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when **ordered alphabetically**.
The STATION table is described as follows:  

<img width="328" alt="Screenshot 2023-10-06 at 11 07 01" src="https://github.com/chanhobong/SQL/assets/118742537/ae764c53-c396-4152-9358-f81b2941c1fa">

<img width="517" alt="Screenshot 2023-10-06 at 11 07 39" src="https://github.com/chanhobong/SQL/assets/118742537/583adb92-d55a-45f6-b8dc-e491d839c807">

- **char_length()**: show the lenght of chart,
- **as**: for using **order by**
- **ASC,DESC**: order by ascending, descending
- **LIMIT**: choose the first one

### Weather Observation Station 7
Query the list of CITY **names ending with vowels** (a, e, i, o, u) from STATION. Your result **cannot contain duplicates**.  

<img width="517" alt="Screenshot 2023-10-06 at 11 14 12" src="https://github.com/chanhobong/SQL/assets/118742537/350f3722-752d-4fb3-86d7-ca6e3b957cdf">

- **distinct**: avoid duplicates
- **regexp**:
-  **'^sa'**: Gives all the names starting with ‘sa’
-  **'on$'**: Gives all the names ending with ‘on’
-  **'be|ae'**: Gives all the names containing ‘be’ or ‘ae’
-  **'[jz]'**: Gives all the names containing ‘j’ or ‘z’
-  **'[^jz]**': Gives all the names not containing ‘j’ or ‘z’
-  **'^[ns]'**:Gives all the names starting with ‘n’ or ‘s’ 


## Advanced Select
### The PADS
Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).  

Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:
There are a total of [occupation_count] [occupation]s.  

where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.  

<img width="737" alt="Screenshot 2023-10-06 at 13 15 29" src="https://github.com/chanhobong/IWannaBeTheDataScientist/assets/118742537/f07a4a8e-823a-44e6-9a66-ea94f16a8e22">

- **CONCAT**: adds two or more strings together
- **LEFT**: extracts a number of characters from a string (starting from left), of course you can use **RIGHT** as same way

This problems is quit tricky, when you see the result, 'There are a total of **_n_ _occupation_** uisng **lower not capital**

