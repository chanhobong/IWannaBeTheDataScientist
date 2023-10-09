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


### Occupations
**Pivot** the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.

1st 
Make a partition, grouping each occupations and order alphabetically in names, so that, it makes 
ROW_NUMBER makes an order each occupations, so that's why it has numbers
<img width="650" alt="Screenshot 2023-10-09 at 21 22 43" src="https://github.com/chanhobong/IWannaBeTheDataScientist/assets/118742537/97acf706-5e7e-4e31-8711-501871fba4d1">
<img width="254" alt="Screenshot 2023-10-09 at 21 24 54" src="https://github.com/chanhobong/IWannaBeTheDataScientist/assets/118742537/1be07169-5eec-4677-8298-df26ebefa0d2">

2nd
Seperating names are matched by occupations
<img width="739" alt="Screenshot 2023-10-09 at 21 28 54" src="https://github.com/chanhobong/IWannaBeTheDataScientist/assets/118742537/a1c71966-c0c7-4303-b1fa-6e809ae23dc1">

retrieve the name in occupations using 1st results as sub quary, using MIN for alpabetically order
- 알파벳의 최소값(a)부터 가져오게 하기 위해 MIN을 사용했다
  - 순서가 필요 없으면 아무 집계함수나 넣어도 된다
  - name의 값이 숫자가 아니기 때문에 사실상 집계되는 건 없음
  - 피벗은 반드시 집계함수를 함께 써야한다! (값이 2개일 수도 있기 때문!)

3rd, 
GROUP BY: to eliminate the NULL and matching the rank to make a one row.


Note: Print NULL when there are no more names corresponding to an occupation.
- **ROW_NUMBER()**: partitions somewhere you want and order it
- E.G: SELECT __, ROW_NUMBER() OVER (PARTITION BY ___ ORDER BY ___ ASC)
- https://velog.io/@hyeh/CASE-%EB%AC%B8-PIVOT#pivot


