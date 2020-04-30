# HTTP-API ROCK PAPER SCISSORS

This is a ASP.NET Core WEB API project build in Visual Studio 2017.
I built a simple Rock,Paper and Scissors API where you can easily settle differences between you and your friend. 

### Tech

* [Visual Studio 2017] - Development enviroment
* [ASP.NET Core] - Web Framework

### Installation

Launch the CygniGame.sln file in visual studio. 
Run the project to start the API. 
Use Postman(What I use) or similiar to interact with the API.

### Requests
All requests are to be made with raw body and JSON. see below for example.
Replace the "localhost:xxxx" to fit your own.

| Create game | Route |
| ------ | ------ |
| POST | https://localhost:44398/api/Game |
Parameter: name
Value: string
Description: /api/Game is used to create a game. Name of the player creating the game is required. Id for the game created will be returned.
Exmample request:
```sh
POST https://localhost:44398/api/Game
    {
    "name": "axel"
    }
```

| Join game | Route |
| ------ | ------ |
| POST | https://localhost:44398/api/Game/{id}/join |
Parameter: name
Value: string
Description: /api/Game/{id}/join is used to join a game. Name of the player joining the game is required. Id for the game you want to join is required in the request address.
Exmample request:
```sh
POST https://localhost:44398/api/Game/567/Join
    {
    "name": "erik"
    }
```
| Make a move | Route |
| ------ | ------ |
| POST | https://localhost:44398/api/Game/{id}/move |
Parameter: name, move
Value: string
Description: /api/Game/{id}/move is used to make a move. Name of the player and what move is required. Move parameters: Rock, Paper or Scissors are to be used.
A id is required in the request address aswell.
Exmample request:
```sh
POST https://localhost:44398/api/Game/567/Move
    {
    "name": "axel",
    "move": "Rock"
    }
```
| Get game status | Route |
| ------ | ------ |
| GET | https://localhost:44398/api/Game/{id} |
Parameter: 
Value: 
Description: /api/Game/{id}/ is used to get status and result of a game. No parameters needed, only the id in the request address. 
Exmample response:
```sh
GET https://localhost:44398/api/Game/567
    {
    "id": 567,
    "firstPlayerName": "Axel",
    "firstPlayerMove": "Paper",
    "secondPlayerName": "Adam",
    "secondPlayerMove": "Paper",
    "result": "DRAW"
    }
```
