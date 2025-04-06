---
tags:
  - API
completed: 1
parent: "[[Data Source|Data Source]]"
type: sub
---
# IGDB API Integration


## Run-down
1. First, Obtain Client ID and Client Secret from the [IGDB API documentation](https://api-docs.igdb.com/#authentication)
2. Figure out a way to obtain the *x* most recent games from the database
3. In python, use this information to create a dictionary of games with their info (the [IGDB API Python Integration](https://github.com/twitchtv/igdb-api-python#code-examples) may be a useful shortcut)

## Items
- Client ID: iandccesnxkg8eos8outaqkdjmcxkl
- Client Secret: g8oxp6dd9lxcx7rt0t3naa8ag3rkah
- access_token: uzjcv1er26qvwwyawqsqwjx4ghio13

````ad-example
```python
# To return games from API

r = requests.post("https://api.igdb.com/v4/games", headers={"Client-ID":"iandccesnxkg8eos8outaqkdjmcxkl","Authorization":"Bearer uzjcv1er26qvwwyawqsqwjx4ghio13"}, data="fields *; limit 1;") #id, name, genres, themes, age_ratings, platforms, involved_companies, player_perspectives, game_modes, summary, url

print(r.status_code, r.reason)
print(r.text)
````

````ad-example
```python
# To return convert genre id into genre
r = requests.post("https://api.igdb.com/v4/genres", headers={"Client-ID":"iandccesnxkg8eos8outaqkdjmcxkl","Authorization":"Bearer uzjcv1er26qvwwyawqsqwjx4ghio13"}, data="fields *; where id=32;")
````
