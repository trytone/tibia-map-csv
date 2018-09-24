# Import into MySQL

1. Unzip file "map.zip"

2. Create table : 

`CREATE TABLE map ( x INT NOT NULL , y INT NOT NULL , z INT NOT NULL , id INT NOT NULL , INDEX all (x, y, z));`

3. Import into MySQL by query : 

`LOAD DATA LOCAL INFILE 'C:/Users/{UserName}/Desktop/map.csv' INTO TABLE map FIELDS TERMINATED BY ';' LINES TERMINATED BY '\n';`

# Example

Load all tiles from Level-0 Carlin Town : 

`SELECT COUNT(id),id FROM map WHERE x > 32286 AND x < 32415 AND y > 31744 AND y < 31860 AND z = 7 GROUP BY (id) ORDER BY COUNT(id) DESC`
