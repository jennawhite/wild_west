#homework 4: chipotle
### HW 4 - Questions   
by Jenna White  

#### 1. Look at the head and the tail of chipotle.tsv in the data subdirectory of this repo.
Think for a minute about how the data is structured. What do you think each column means?
What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.)

  **Answer:**
  Each line is a different menu item.  
  The columns mean the following:
  * order_id - what is the order number
  * quantity - how many of the menu item
  * item_name - the name of the menu item
  * choice_description - this includes any modifications and specification of the menu item (including chosen ingredients)
  * item_price - how much the menu item costs


#### 2. How many orders do there appear to be?

**Answer:** 1834
```
$ tail chipotle.tsv
```

#### 3. How many lines are in this file?

**Answer:** 4623
```
$ wc -l chipotle.tsv
```

#### 4. Which burrito is more popular, steak or chicken?

**Answer:** Chicken
```
$ grep 'Chicken' chipotle.tsv | wc -l # 1565 results
$ grep 'Steak' chipotle.tsv | wc -l # 706 results
```

#### 5. Do chicken burritos more often have black beans or pinto beans?

**Answer:** Black Beans
```
$ grep 'Chicken' chipotle.tsv | grep 'Black Beans' | wc -l # 759 results
$ grep 'Chicken' chipotle.tsv | grep 'Pinto Beans' | wc -l # 265 results
```
#### 6. Make a list of all of the CSV or TSV files in the our class repo. repo (using a single command). You will be working on your local repo on your laptop. Think about how wildcard characters can help you with this task.

**Answer:**
```
# I am already in the repo
$ find . -type f -iname "*.csv" -o -iname "*.tsv"
# result below
./data/Airline_on_time_west_coast.csv
./data/airlines.csv
./data/bank-additional.csv
./data/bikeshare.csv
./data/chipotle.tsv
./data/citibike_feb2014.csv
./data/denversitters.csv
./data/drinks.csv
./data/drones.csv
./data/hitters.csv
./data/icecream.csv
./data/imdb_1000.csv
./data/mtcars.csv
./data/NBA_players_2015.csv
./data/ozone.csv
./data/pronto_cycle_share/2015_station_data.csv
./data/pronto_cycle_share/2015_trip_data.csv
./data/pronto_cycle_share/2015_weather_data.csv
./data/rossmann.csv
./data/rt_critics.csv
./data/sms.tsv
./data/stores.csv
./data/syria.csv
./data/time_series_train.csv
./data/titanic.csv
./data/ufo.csv
./data/vehicles_test.csv
./data/vehicles_train.csv
./data/yelp.csv
```

#### 7. Count the approximate number of occurrences of the word "dictionary" (regardless of case) across all files of our class repo.

**Answer:** 80
```
# starting in main repo folder
$ grep -r -i "dictionary" . | wc -l
```
<br></br>
#### *Optional:* ####
Use the the command line to discover something "interesting" about the Chipotle data. Try using the commands from the "advanced" section!

**Answer:** There are 1337 unique ordering combinations that include "Black Beans"
```
$ grep "Black Beans" chipotle.tsv | uniq -c | wc -l
```
