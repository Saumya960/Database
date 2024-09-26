#week3
###Exercise2

#Question1
select * from goal;
![Ex2-Q1.PNG](Ex2-Q1.PNG)

#Question2
select name, type from airport where iso_country = "FI";
![Ex2-Q2.PNG](Ex2-Q2.PNG)

#Question3
select name from airport where iso_country ="FI" order by name asc;
![Ex2-Q3.PNG](Ex2-Q3.PNG)

#Question4
select name, type from airport where iso_country = "FI" order by type asc, name asc;
![Ex2-Q4.PNG](Ex2-Q4.PNG)

#Question5
select name from country where name like "F%";
![Ex2-Q5.PNG](Ex2-Q5.PNG)

#Question6
select name from country where name like "%F%";
![Ex2-Q6.PNG](Ex2-Q6.PNG)

#Question7
select location from game where screen_name = "Vesa";
![Ex2-Q7.PNG](Ex2-Q7.PNG)

#Question8
select CO2_consumed from game where screen_name = "Ilkka";
![Ex2-Q8.PNG](Ex2-Q8.PNG)

#Question9
select distinct co2_budget from game;
![Ex2-Q9.PNG](Ex2-Q9.PNG)

#Question10
select screen_name, co2_budget, co2_consumed, co2_budget-co2_consumed as co2_left from game where screen_name= "Ilkka";
![Ex2-Q10.PNG](Ex2-Q10.PNG)



###Exercise3

#Question1
SELECT country.name AS "country name", airport.name AS "airport name"  
FROM country JOIN airport ON country.iso_country = airport.iso_country  
WHERE country.name = 'Iceland';
![Ex3-Q1.PNG](Ex3-Q1.PNG)

#Question2
SELECT airport.name AS "airport name"  
FROM airport INNER JOIN country  
ON airport.iso_country = country.iso_country  
WHERE country.name = 'France' AND airport.type = 'large_airport';
![Ex3-Q2.PNG](Ex3-Q2.PNG)

#Question3
SELECT country.name AS "country_name", airport.name AS "airport_name" 
FROM airport INNER JOIN country  
ON airport.iso_country = country.iso_country  
WHERE country.continent = 'an';
![Ex3-Q3.PNG](Ex3-Q3.PNG)

#Question4
select airport.elevation_ft from game, 
airport where airport.ident = game.location 
and game.screen_name = "heini";
![Ex3-Q4.PNG](Ex3-Q4.PNG)

#Question5
select airport.elevation_ft * 0.3048 as elevation_m from game,
airport where airport.ident = game.location  
and game.screen_name = "heini";
![Ex3-Q5.PNG](Ex3-Q5.PNG)

#Question6
select airport.name from game,
airport where airport.ident = game.location 
and game.screen_name = "Ilkka";
![Ex3-Q6.PNG](Ex3-Q6.PNG)

#Question7
SELECT country.name FROM game 
JOIN airport ON airport.ident = game.location 
INNER JOIN country ON country.iso_country = airport.iso_country 
WHERE game.screen_name = "Ilkka";
![Ex3-Q7.PNG](Ex3-Q7.PNG)

#Question8
select goal.name from goal
INNER JOIN goal_reached ON goal.id = goal_reached.goal_id 
INNER JOIN game on goal_reached.game_id = game.id
WHERE game.screen_name = "heini";
![Ex3-Q8.PNG](Ex3-Q8.PNG)

#Question9
select airport.name FROM airport 
INNER JOIN game ON airport.ident = game.location   
INNER JOIN goal_reached ON game.id = goal_reached.game_id 
INNER JOIN goal ON goal_reached.goal_id = goal.id 
WHERE goal.name = 'clouds' AND game.screen_name = 'Ilkka'; 
![Ex3-Q9.PNG](Ex3-Q9.PNG)

#Question10
SELECT country.name FROM airport  
INNER JOIN game ON airport.ident = game.location  
INNER JOIN goal_reached ON game.id = goal_reached.game_id  
INNER JOIN goal ON goal_reached.goal_id = goal.id  
INNER JOIN country ON airport.iso_country = country.iso_country  
WHERE goal.name = 'clouds' AND game.screen_name = 'Ilkka';
![Ex3-Q10.PNG](Ex3-Q10.PNG)