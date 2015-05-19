##Hubble Search API

Returns a json list of available offices

* **URL**

    /api/v2/query

* **Method:**

    `GET`

* **URL Params**

    facilities, spaceType, people, locations, budget

* **Data Params**

    None

* **Success Response:**
    * **Code:** 200 <br />
    * **Content:**
  ```javascript
    [
        {
            id : [integer],
            url: [string (absolute URL)],
            host: {
                id: [integer],
                name: [string],
                avatar: [string (absolute URL)],
                has_phone_numer: [boolean]
            },
            name: [string],
            description : [string],
            summary : [string],
            location : {lat: [number], lon: [number]},
            neighbourhood: [string],
            photos : [string (absolute URL), ],
            facilities : [
                {
                    icon: [string (absolute URL)],
                    id: integer,
                    name: [string]
                },
                {
                    icon: [string (absolute URL)],
                    id: integer,
                    name: [string]
                }
            ],
            office : {
                    id: [integer],
                    building: [integer],
                    name : [string],
                    verboseName: [string],
                    capacity : [integer],
                    minPeople : [integer],
                    maxPeople : [integer],
                    price : [number],
                    priceType : [string (PPP OR TP)],
                    spaceType : [string (Hot Desk OR Shared Office OR Private Office)],
                    full : [boolean],
                    availableFrom: [date],
                    url: [string (absolute URL)]
            }
        }, {
        ... [another building]
        }, {
        ... [another building]
        }]
  ```

* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "API key is invalid."}`
  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "API key not provided."}`

* **Example Call:**

  ```javascript
    $.ajax({
      url: "https://hubblehq-api.herokuapp.com/api/v2/query?api_key=your_api_key&budget=small&people=1&locations=shoreditch,clerkenwell&spaceType=Shared%20Office&facilities=Wi-fi",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
* **Example Response Code:** 200 <br />

* **Notes:**
