# Import into MySQL

1. Unzip file "map.zip"

2. Create table : 

`CREATE TABLE map ( x INT NOT NULL , y INT NOT NULL , z INT NOT NULL , id INT NOT NULL , INDEX all (x, y, z));`

3. Import into MySQL by query : 

`LOAD DATA LOCAL INFILE 'C:/Users/{UserName}/Desktop/map.csv' INTO TABLE map FIELDS TERMINATED BY ';' LINES TERMINATED BY '\n';`

# Example

Load all tiles from Carlin Town (item_id):

`SELECT x-32286 as xr,y-31744 as yr,z-7 as zr, id FROM map WHERE x > 32286 AND x < 32415 AND y > 31744 AND y < 31860`

Load all tiles from Carlin Town (sprite_id)

`SELECT m.x-32286,m.y-31744,m.z-7,s.sprite_id FROM map m 
INNER JOIN (SELECT item_id,sprite_id FROM sprites GROUP BY item_id) AS s ON s.item_id = m.id
WHERE m.x > 32286 AND m.x < 32415 AND m.y > 31744 AND m.y < 31860`

Count tiles repeat from Carlin Town : 

`SELECT COUNT(id),id FROM map WHERE x > 32286 AND x < 32415 AND y > 31744 AND y < 31860 AND z = 7 GROUP BY (id) ORDER BY COUNT(id) DESC`

Load some tree items from Carlin Town : 

`SELECT x-32286,y-31744,id FROM items WHERE x > 32286 AND x < 32415 AND y > 31744 AND y < 31860 AND z = 7 AND id IN (2700,2708,2768)`

