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
