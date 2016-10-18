##Hubble Search API

Returns a json list of available offices

* **URL**

    /api/v2/browse

* **Method:**

    `GET`

* **URL Params**

    * `facilities` comma-separated list of facilities e.g. `24h_access,showers`
    * `maxPrice` minimum monthly price in GBP e.g. `250`
    * `minPrice` maximum monthly price in GBP e.g. `1950`
    * `people` the number of desks required in an office e.g. `6`
    * `spaceType` comma-separated list of space types to accept e.g. `private_office,coworking`. Options: `private_office`, `coworking`, `shared_office`
    * `lat` latitude of search area e.g. `51.5133`. Must be used in combination with `lon`
    * `lon` longitude of search area e.g. `-0.0886`. Must be used in combination with `lat`
    * `radius` the search area radius, only used in combination with `lon` and `lat`. e.g. `1km`
    * `polygon` HTML-encoded array of lat / lon pairs (in GEOjson style) e.g. `%5B%5B51.52393808750874,-0.07171154022216797%5D,%5B51.50943692143851,-0.07171154022216797%5D,%5B51.50943692143851,-0.09123802185058592%5D,%5B51.52393808750874,-0.09166717529296875%5D%5D`. Cannot be used in combination with `lat`, `lon`, `radius` or `indexed_shape`
    * `indexed_shape` Mongo object ID of stored location in Hubble locations service e.g. `56d09042f8bc8d0300834cd6`

* **Data Params**

    None

* **Success Response:**
    * **Code:** 200 <br />
    * **Content:**
  ```javascript
    [
        {
            id : [integer],
            activationState: [string],
            url: [string (absolute URL)],
            name: [string],
            description : [string],
            summary : [string],
            hideFromSearch: [boolean],
            location : {lat: [number], lon: [number]},
            location_geoshape: { type: "point", coordinates: [number, number] }
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
                url: [string (absolute URL)],
                created_at: [string],
                updated_at: [string],
                archived: [boolean],
                draft: [boolean],
                minStay: [integer (num months)]
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
      url: "https://api.hubblehq.com/api/v2/browse?api_key=your_api_key&minPrice=350&maxPrixe=2000&people=11&spaceType=Shared%20Office&facilities=Wi-fi",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
* **Example Response Code:** 200 <br />

* **Notes:**
    * If no search area parameters are specified (e.g. `lat,`, `lon`, `radius`, `polygon`, `indexed_shape`), results from all locations will be returned.
