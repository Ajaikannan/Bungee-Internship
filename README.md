# Bungee-Internship
Bungee Coding Round file submission

Source code folder has a input file which consist of the queries used in the step 1 and step 2 .

output folder consist of filteredCountry.csv and lowestPrice.csv and these are the expected output respectively for step 1 and step 2.

Step 1 (using power query) :

1 . open main.csv and then find the cells that has USA and note down the different provinces using find and replace function .

2 . open a new excel sheet and create a new column enter the country with provinces in bracket as mentioned in the main.csv and save it as country.csv.

3 . Again open a new sheet name filteredCountry.csv and load the country.csv using get data > from file > from text/csv > country.csv and load it .

4 . Also load main.csv using same get data > from file > from text/csv > main.csv and transform using power query merge function 

5 . transform > merge queries >select COUNTRY column > then select country in dropdown > inner join > transform

power query :
= Table.NestedJoin(#"Changed Type", {"COUNTRY"}, Country, {"Column1"}, "Country.1", JoinKind.Inner)

using the column value in country.csv that matches column COUNTRY in main.csv and inner joining them and then close & load and transform then .

6 . Now the sheet will consist of only USA data and save it as filteredCountry.csv

Step 2(using Excel functions)

1 . open filteredCountry.csv and filter each SKU that has more than one price value manually .

2 . Now create a leastPrice.csv sheet with 3 columns (SKU , FIRST_MINIMUM_PRICE , SECOND_MINIMUM_PRICE)

3 .For each filtered SKU find minimum using =min(range) and second minimum using =small(range,2) function
