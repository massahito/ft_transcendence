# Start Game
```mermaid
sequenceDiagram

actor player as Player

participant web as GameWeb
participant api as GameAPI
participant server as GameServer

player ->>+ web: Set user name
web ->>+ api: POST/api/users/create
api ->>+ server: create a user_id
server -->>- api: OK
api -->>- web: OK
web -->>- player: Success message<br>user_id<br> get user id
