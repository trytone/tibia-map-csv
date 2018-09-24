# Import into MySQL
1. Unzip file "map.zip"
2. Create table 
`CREATE TABLE `map` ( `x` INT NOT NULL , `y` INT NOT NULL , `z` INT NOT NULL , `id` INT NOT NULL , INDEX `all` (`x`, `y`, `z`));`

3. Import into MySQL by query :
`LOAD DATA LOCAL INFILE 'C:/Users/{UserName}/Desktop/map.csv' INTO TABLE map FIELDS TERMINATED BY ';' LINES TERMINATED BY '\n';`
