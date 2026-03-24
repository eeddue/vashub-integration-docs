---
sidebar_position: 2
---

# Game Launch

Available games - **`Aviator`**, **`Avionix`**, **`Crash Arena`**, **`Tower`**, **`Mines`**, **`Classic Dice`**, **`Hash Dice`**, **`Limbo`**, **`Wheel`**,

To launch a game, an online casino should generate launch link with appropriate parameters and open it in browser.

```json
{
  "operator": "The provider id provided by us",
  "token": "The players's token from the casino's side",
  "game": "aviator-next" | "avionix" | "crash-arena" | "tower"| "mines" | "classic-dice" | "hash-dice" | "limbo" | "wheel",
  "return_url": "URL to redirect a player from the game",
}
```

The above parameters are passed to the game's launch url as below;

```
  https://{game}.spribegaming.live/?operator={operator}&token={token}&return_url={return_url}
```

Example launch url;

```
  https://aviator-next.spribegaming.live/?operator=vashub&token=4512bb329301b0842eae1c4e5441d1909eb7108ee79a09a07f64ee86fa318e09&return_url=https://abccasino.com
```
