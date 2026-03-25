---
sidebar_position: 2
---

# Game Launch

Available games - **`Aviator`**, **`Avionix`**, **`Crash Arena`**, **`Tower`**, **`Mines`**, **`Classic Dice`**, **`Hash Dice`**, **`Limbo`**, **`Wheel`**,

To launch a game, an online casino should generate launch link with appropriate parameters and open it in browser.

```json
{
  "game": "aviator-next" | "avionix" | "crash-arena" | "tower"| "mines" | "classic-dice" | "hash-dice" | "limbo" | "wheel",
  "operator": "operator key name provided by us",
  "user" : "ID of a player on the operators side",
  "lang": "Game interface language",
  "currency" : "Game currency (currency code)",
  "token": "The players's token from the casino's side",
  "return_url": "URL to redirect a player from the game",
}
```

The above parameters are passed to the game's launch url as below;

```
  https://{game}.spribegaming.live/?operator={operator}&user={user_id}&token={token}&lang={lang}&currency={currency}&return_url={return_url}
```

Example launch url;

```
   https://aviator-next.spribegaming.live/?operator=demo&user=12345678&token=5af5ed1f4651218c13d3d8ebdbe2150f755de2b71de39409&lang=EN&currency=KES&return_url=123casino.com
```
