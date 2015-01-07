**List Available Spaces**
	Returns json list of all spaces with availability

* **URL**

	/api/v2/spaces

* **Method:**

	`GET`

* **URL Params**

	None

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
	    		name: [string],
	    		avatar [string (absolute URL)]
    		},
    		name: [string],
	    	description : [string],
        	summary : [string],
	    	location : {lat: [number], lon: [number]},
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
	    	offices : [
	    		{
	    			id: [integer],
	    			name : [string],
	    			capacity : [integer],
	    			minPeople : [integer],
	    			maxPeople : [integer],
	    			price : [number],
	    			priceType : [string (Price Per Person OR Total Price)],
	    			spaceType : [string (Hot Desk OR Shared OR Private)],
	    			full : [boolean],
			    	availableFrom: [date],
    			    	url: [string (absolute URL)]
	    		}
	    	]
	    }, {
	    ... [another space]
	    }, {
	    ... [another space]
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
      url: "https://hubblehq-api.herokuapp.com/api/v2/spaces/?api_key=your_api_key",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
* **Example Response Code:** 200 <br />

* **Notes:**
