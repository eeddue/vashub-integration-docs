---
sidebar_position: 4
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Withdraw

This request is used to withdraw a given amount from a player's wallet

| path    | **`/withdraw`** |
| ------- | --------------- |
| method  | **`POST`**      |
| headers | **`x-api-key`** |

### Request

<Tabs>
  <TabItem value="parameters" label="Parameters">
    | Parameter   | Description                                                        |
    | ----------- | ------------------------------------------------------------------ |
    | user_id       | **String** - Player's id on the operator's side                 |
    | amount      | **Number** - Amount to be withdrawed from the player's wallet        |
    | action      | **`bet`** / **`rain`** / **`gift`** - Reason for amount withdrawion  |
  </TabItem>
  
  <TabItem value="example" label="Example">

    ```json
    {
      "user_id": "123456",
      "amount": 100,
      "action": "bet"
    }

    ```

  </TabItem>

</Tabs>

### Response

<Tabs>
  <TabItem value="parameters" label="Parameters">

    | Parameter | Description                                                                                         |
    | --------- | --------------------------------------------------------------------------------------------------- |
    | code      | **Number** - response status code                                                                       |
    | message   | **String** - response explanation                                                                       |
    | data      | **Object** <ul><li>user_id - ***String*** player id</li> <li>old balance - ***Number*** old player balance</li> <li>new balance - ***Number*** new player balance</li></ul>|

  </TabItem>

  <TabItem value="success" label="Success Example">

    ```json
    {
        "code": 200,
        "message": "ok",
        "data": {
            "user_id": "123456",
            "new_balance": 1000,
            "old_balance": 1100,
        }
    }
    ```

  </TabItem>

  <TabItem value="error" label="Error Example">

    ```json
    {
        "code": 401,
        "message": "Insufficient balance",
        "data": {}
    }
    ```

  </TabItem>
</Tabs>
