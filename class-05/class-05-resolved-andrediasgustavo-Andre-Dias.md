# MongoDB - Aula 05 - Exercício
autor: André Dias


## Importar as collections restaurantes e pokemons ##

```

andredias@andre-dias-skywalker:~$ mongoimport --host 127.0.0.1 --db be-mean-pokemons --collection pokemons --drop --file ~/BE-MEAN/pokemons.json 
2015-12-04T16:41:42.614-0200	connected to: 127.0.0.1
2015-12-04T16:41:42.614-0200	dropping: be-mean-pokemons.pokemons
2015-12-04T16:41:42.632-0200	imported 620 documents

```

## Distinct por `cuisine` na restaurantes. ##

```

andre-dias-skywalker(mongod-3.0.7) test> db.restaurantes.distinct('cuisine')
[
  "Bakery",
  "American ",
  "Jewish/Kosher",
  "Delicatessen",
  "Ice Cream, Gelato, Yogurt, Ices",
  "Chinese",
  "Other",
  "Hamburgers",
  "Chicken",
  "Turkish",
  "Caribbean",
  "Donuts",
  "Bagels/Pretzels",
  "Sandwiches/Salads/Mixed Buffet",
  "Continental",
  "Irish",
  "Pizza",
  "Italian",
  "Steak",
  "Polish",
  "Latin (Cuban, Dominican, Puerto Rican, South & Central American)",
  "German",
  "French",
  "Pizza/Italian",
  "Mexican",
  "Spanish",
  "Café/Coffee/Tea",
  "Tex-Mex",
  "Pancakes/Waffles",
  "Soul Food",
  "Seafood",
  "Hotdogs",
  "Greek",
  "Not Listed/Not Applicable",
  "African",
  "Japanese",
  "Indian",
  "Armenian",
  "Thai",
  "Chinese/Cuban",
  "Mediterranean",
  "Korean",
  "Bottled beverages, including water, sodas, juices, etc.",
  "Russian",
  "Eastern European",
  "Middle Eastern",
  "Asian",
  "Ethiopian",
  "Vegetarian",
  "Barbecue",
  "Egyptian",
  "English",
  "Sandwiches",
  "Portuguese",
  "Indonesian",
  "Chinese/Japanese",
  "Filipino",
  "Juice, Smoothies, Fruit Salads",
  "Brazilian",
  "Afghan",
  "Vietnamese/Cambodian/Malaysia",
  "CafÃ©/Coffee/Tea",
  "Soups & Sandwiches",
  "Tapas",
  "Moroccan",
  "Pakistani",
  "Peruvian",
  "Bangladeshi",
  "Czech",
  "Salads",
  "Creole",
  "Fruits/Vegetables",
  "Iranian",
  "Cajun",
  "Scandinavian",
  "Polynesian",
  "Soups",
  "Australian",
  "Hotdogs/Pretzels",
  "Southwestern",
  "Nuts/Confectionary",
  "Hawaiian",
  "Creole/Cajun",
  "Californian",
  "Chilean"
]


```

## Distinct por `types` na pokemons.##

```
andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.pokemons.distinct('types')
[
  "flying",
  "normal",
  "bug",
  "poison",
  "electric",
  "water",
  "fighting",
  "psychic",
  "grass",
  "fairy",
  "fire",
  "rock",
  "ice",
  "ground",
  "steel",
  "ghost",
  "dark",
  "dragon"
]


```

## As primeiras 3 páginas com `.limit()` e `.skip()` de pokemons (5 em 5). ##

```
*andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.pokemons.find().limit(5).skip(5 * 0)*
{
  "_id": ObjectId("564a7c362c153ed825a69056"),
  "attack": 60,
  "created": "2013-11-03T15:05:41.301609",
  "defense": 55,
  "height": "11",
  "hp": 63,
  "name": "Pidgeotto",
  "speed": 71,
  "types": [
    "normal",
    "flying"
  ]
}
{
  "_id": ObjectId("564a7c362c153ed825a69057"),
  "attack": 80,
  "created": "2013-11-03T15:05:41.303569",
  "defense": 75,
  "height": "15",
  "hp": 83,
  "name": "Pidgeot",
  "speed": 101,
  "types": [
    "normal",
    "flying"
  ]
}
{
  "_id": ObjectId("564a7c362c153ed825a69054"),
  "attack": 90,
  "created": "2013-11-03T15:05:41.297180",
  "defense": 40,
  "height": "10",
  "hp": 65,
  "name": "Beedrill",
  "speed": 75,
  "types": [
    "poison",
    "bug"
  ]
}
{
  "_id": ObjectId("564a7c362c153ed825a69058"),
  "attack": 81,
  "created": "2013-11-03T15:05:41.308092",
  "defense": 60,
  "height": "7",
  "hp": 55,
  "name": "Raticate",
  "speed": 97,
  "types": [
    "normal"
  ]
}
{
  "_id": ObjectId("564a7c362c153ed825a6905a"),
  "attack": 55,
  "created": "2013-11-03T15:05:41.317235",
  "defense": 40,
  "height": "4",
  "hp": 35,
  "name": "Pikachu",
  "speed": 90,
  "types": [
    "electric"
  ]
}
Fetched 5 record(s) in 3ms

*andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.pokemons.find().limit(5).skip(5 * 1)*
{
  "_id": ObjectId("564a7c362c153ed825a69059"),
  "attack": 90,
  "created": "2013-11-03T15:05:41.312310",
  "defense": 65,
  "height": "12",
  "hp": 65,
  "name": "Fearow",
  "speed": 100,
  "types": [
    "normal",
    "flying"
  ]
}
{
  "_id": ObjectId("564a7c362c153ed825a6905b"),
  "attack": 60,
  "created": "2013-11-03T15:05:41.313816",
  "defense": 44,
  "height": "20",
  "hp": 35,
  "name": "Ekans",
  "speed": 55,
  "types": [
    "poison"
  ]
}
{
  "_id": ObjectId("564a7c362c153ed825a6905c"),
  "attack": 90,
  "created": "2013-11-03T15:05:41.318944",
  "defense": 55,
  "height": "8",
  "hp": 60,
  "name": "Raichu",
  "speed": 110,
  "types": [
    "electric"
  ]
}
{
  "_id": ObjectId("564a7c362c153ed825a6905d"),
  "attack": 85,
  "created": "2013-11-03T15:05:41.315504",
  "defense": 69,
  "height": "35",
  "hp": 60,
  "name": "Arbok",
  "speed": 80,
  "types": [
    "poison"
  ]
}
{
  "_id": ObjectId("564a7c372c153ed825a6905e"),
  "attack": 50,
  "created": "2013-11-03T15:05:41.388462",
  "defense": 40,
  "height": "6",
  "hp": 40,
  "name": "Poliwag",
  "speed": 90,
  "types": [
    "water"
  ]
}
Fetched 5 record(s) in 2ms

*andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.pokemons.find().limit(5).skip(5 * 2)*
{
  "_id": ObjectId("564a7c372c153ed825a6905f"),
  "attack": 65,
  "created": "2013-11-03T15:05:41.390744",
  "defense": 65,
  "height": "10",
  "hp": 65,
  "name": "Poliwhirl",
  "speed": 90,
  "types": [
    "water"
  ]
}
{
  "_id": ObjectId("564a7c372c153ed825a69060"),
  "attack": 95,
  "created": "2013-11-03T15:05:41.393388",
  "defense": 95,
  "height": "13",
  "hp": 90,
  "name": "Poliwrath",
  "speed": 70,
  "types": [
    "fighting",
    "water"
  ]
}
{
  "_id": ObjectId("564a7c372c153ed825a69061"),
  "attack": 20,
  "created": "2013-11-03T15:05:41.396006",
  "defense": 15,
  "height": "9",
  "hp": 25,
  "name": "Abra",
  "speed": 90,
  "types": [
    "psychic"
  ]
}
{
  "_id": ObjectId("564a7c372c153ed825a69062"),
  "attack": 35,
  "created": "2013-11-03T15:05:41.398045",
  "defense": 30,
  "height": "13",
  "hp": 40,
  "name": "Kadabra",
  "speed": 105,
  "types": [
    "psychic"
  ]
}
{
  "_id": ObjectId("564a7c372c153ed825a69063"),
  "attack": 80,
  "created": "2013-11-03T15:05:41.402119",
  "defense": 50,
  "height": "8",
  "hp": 70,
  "name": "Machop",
  "speed": 35,
  "types": [
    "fighting"
  ]
}
Fetched 5 record(s) in 5ms

```

## Group ou Aggregate contando a quantidade de pokemons de cada tipo. ##

```
andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.pokemons.group({
... initial: {total: 0},
... reduce:function(curr,result) { 
... curr.types.forEach(function(type){ 
... if(result[type]){ 
... result[type]++;
... }else{
... result[type]=1
... }
... result.total++
... });
... }
... });
[
  {
    "total": 934,
    "normal": 79,
    "flying": 81,
    "poison": 54,
    "bug": 58,
    "electric": 47,
    "water": 101,
    "fighting": 42,
    "psychic": 61,
    "grass": 70,
    "fairy": 31,
    "fire": 53,
    "rock": 42,
    "ice": 28,
    "ground": 53,
    "steel": 35,
    "ghost": 34,
    "dark": 35,
    "dragon": 30
  }
]


```

## Realizar 3 counts na collection pokemons.##

```
andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.restaurantes.count()
0
andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.pokemons.count()
620
andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.pokemons.count({types : 'rock'})
42
andre-dias-skywalker(mongod-3.0.7) be-mean-pokemons> db.pokemons.count({defense : {$gte : 50}})
481


```
