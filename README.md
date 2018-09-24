# tibia-map-csv
1. Unzip "map.zip" file
2. Import into MySQL by query :

LOAD DATA LOCAL INFILE 'C:/Users/userName/Desktop/map.csv' INTO TABLE map FIELDS TERMINATED BY ';' LINES TERMINATED BY '\n';