---
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Player Info

This request is used to request for player details.

| path    | **`/info`**     |
| ------- | --------------- |
| method  | **`POST`**      |
| headers | **`x-api-key`** |

### Request

<Tabs>
  <TabItem value="parameters" label="Parameters">
    | Parameter   | Description |
    | ------ | ------- |
    | user_id | **String** - Player's id on the operator's side  |
  </TabItem>
  
  <TabItem value="example" label="Example">

    ```json
    {
      "user_id": "123456"
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
    | data      | **Object** <ul><li>id - ***String*** player id</li><li>name - ***String*** player name</li><li>balance - ***Number*** player balance</li></ul> |

  </TabItem>

  <TabItem value="success" label="Success Example">

    ```json
    {
        "code": 200,
        "message": "ok",
        "data": {
            "user_id": "12345",
            "username": "johndoe",
            "balance": 1000
        }
    }
    ```

  </TabItem>

  <TabItem value="error" label="Error Example">

    ```json
    {
        "code": 401,
        "message": "Invalid user",
        "data": {}
    }
    ```

  </TabItem>
</Tabs>
