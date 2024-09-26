#week3
###Exercise2

#Question1
select * from goal;
![Ex2-Q1.PNG](Ex2-Q1.PNG)

#Question2
select name, type from airport where iso_country = "FI";
![Task2 -SS.PNG](Task2%20-SS.PNG)

#Question3
select name from airport where iso_country ="FI" order by name asc;
![Task3 - SS.PNG](Task3%20-%20SS.PNG)

#Question4
select name, type from airport where iso_country = "FI" order by type asc, name asc;
![Task4 - SS.PNG](Task4%20-%20SS.PNG)

#Question5
select name from country where name like "F%";
![Task5 - SS.PNG](Task5%20-%20SS.PNG)

#Question6
select name from country where name like "%F%";
![Task6 - SS.PNG](Task6%20-%20SS.PNG)

#Question7
select location from game where screen_name = "Vesa";
![Task7 - SS.PNG](Task7%20-%20SS.PNG)

#Question8
select CO2_consumed from game where screen_name = "Ilkka";
![Task8 - SS.PNG](Task8%20-%20SS.PNG)

#Question9
select distinct co2_budget from game;
![Task9 - SS.PNG](Task9%20-%20SS.PNG)

#Question10
select screen_name, co2_budget, co2_consumed, co2_budget-co2_consumed as co2_left from game where screen_name= "Ilkka";
![Task10 - SS.PNG](Task10%20-%20SS.PNG)



###Exercise3

#Question1
SELECT country.name AS "country name", airport.name AS "airport name"  
FROM country JOIN airport ON country.iso_country = airport.iso_country  
WHERE country.name = 'Iceland';
![Ques1 - SS.PNG](Ques1%20-%20SS.PNG)

#Question2
SELECT airport.name AS "airport name"  
FROM airport INNER JOIN country  
ON airport.iso_country = country.iso_country  
WHERE country.name = 'France' AND airport.type = 'large_airport';
![Ques2 - SS.PNG](Ques2%20-%20SS.PNG)

#Question3
SELECT country.name AS "country_name", airport.name AS "airport_name" 
FROM airport INNER JOIN country  
ON airport.iso_country = country.iso_country  
WHERE country.continent = 'an';
![Ques3 - SS.PNG](Ques3%20-%20SS.PNG)

#Question4
select airport.elevation_ft from game, 
airport where airport.ident = game.location 
and game.screen_name = "heini";
![Ques4 - SS.PNG](Ques4%20-%20SS.PNG)

#Question5
select airport.elevation_ft * 0.3048 as elevation_m from game,
airport where airport.ident = game.location  
and game.screen_name = "heini";
![Ques5 - SS.PNG](Ques5%20-%20SS.PNG)

#Question6
select airport.name from game,
airport where airport.ident = game.location 
and game.screen_name = "Ilkka";
![Ques6 - SS.PNG](Ques6%20-%20SS.PNG)

#Question7
SELECT country.name FROM game 
JOIN airport ON airport.ident = game.location 
INNER JOIN country ON country.iso_country = airport.iso_country 
WHERE game.screen_name = "Ilkka";
![Ques7 - SS.PNG](Ques7%20-%20SS.PNG)

#Question8
select goal.name from goal
INNER JOIN goal_reached ON goal.id = goal_reached.goal_id 
INNER JOIN game on goal_reached.game_id = game.id
WHERE game.screen_name = "heini";
![Ques8 - SS.PNG](Ques8%20-%20SS.PNG)

#Question9
select airport.name FROM airport 
INNER JOIN game ON airport.ident = game.location   
INNER JOIN goal_reached ON game.id = goal_reached.game_id 
INNER JOIN goal ON goal_reached.goal_id = goal.id 
WHERE goal.name = 'clouds' AND game.screen_name = 'Ilkka'; 
![Ques9 - SS.PNG](Ques9%20-%20SS.PNG)

#Question10
SELECT country.name FROM airport  
INNER JOIN game ON airport.ident = game.location  
INNER JOIN goal_reached ON game.id = goal_reached.game_id  
INNER JOIN goal ON goal_reached.goal_id = goal.id  
INNER JOIN country ON airport.iso_country = country.iso_country  
WHERE goal.name = 'clouds' AND game.screen_name = 'Ilkka';
![Ques10 -SS.PNG](Ques10%20-SS.PNG)