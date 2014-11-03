**List Available Spaces**
----
	Returns json list of all spaces with availability

* **URL**

	/api/spaces-list

* **Method:**

	`GET`

* **URL Params**

	None

* **Data Params**

	None

* **Success Response:**
	* **Code:** 200 <br />
	* **Content:**
  ```
    [
    	{
	    	id : [integer],
	    	title : [string],
	    	description : [string],
	    	address : [string],
	    	postcode : [string],
	    	is_active : [boolean],
	    	is_promoted : [boolean],
	    	geocoordinates : [string (latitude, longitude)],
	    	images : [
	    		{
	    			url : [string (absolute URL)],
	    			thumbnail : [boolean],
	    			cover : [boolean]
	    		},
	    		{
	    			url : [string (absolute URL)],
	    			thumbnail : [boolean],
	    			cover : [boolean]
	    		},
	    		{
	    			url : [string (absolute URL)],
	    			thumbnail : [boolean],
	    			cover : [boolean]
	    		}
	    	],
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
	    			title : [string],
	    			capacity : [integer],
	    			min_people : [integer OR null],
	    			max_people : [integer OR null],
	    			base_price : [number],
	    			price_type : [string],
	    			available_from : [string (date in ISO 8601 format)],
	    			minimum_stay_months : [number],
	    			space_type : [string (Private Office OR )],
	    			comments : [string],
	    			is_filled : [boolean]
	    		}
	    	]
	    }, {
	    ... [more spaces]
	    }]
  ```

* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Example Call:**

  ```javascript
    $.ajax({
      url: "/users/1",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
* **Example Response:**
	* **Code:** 200 <br />
	* **Content:**
  ```
    [
    	{
	    	id : 412,
	    	title : "Quirky Shared Space near Farringdon Tube Station",
	    	description : "We have a lovely bright office building with a fun environment and creative people. Amazing herbal tea provided and occasional visits from the masseuse!",
	    	address : "142 Clerkenwell Road, London",
	    	postcode : "EC4 8BV",
	    	is_active : 1,
	    	is_promoted : 1,
	    	geocoordinates : "51.5096281,-0.17035409999999998",
	    	images : [
	    		{
	    			url : "https://spaciousapp.s3.amazonaws.com/cache/ec/d1/ecd1274539caa68412c701df850a5556.png",
	    			thumbnail : 1,
	    			cover : 0
	    		},
	    		{
	    			url : "https://spaciousapp.s3.amazonaws.com/cache/8b/28/8b282d529d2aba0f98c466257bf54948.png",
	    			thumbnail : 0,
	    			cover : 1
	    		},
	    		{
	    			url : "https://spaciousapp.s3.amazonaws.com/cache/94/9d/949db03e10d6f1995d91612e7ca5acf8.png",
	    			thumbnail : 0,
	    			cover : 0
	    		}
	    	],
	    	facilities : [
	    		{
	    			icon: "https://spaciousapp.s3.amazonaws.com/features/pingpong.png",
	    			id: 8,
	    			name: "Ping pong"
	    		},
	    		{
	    			icon: "https://spaciousapp.s3.amazonaws.com/features/24h.png",
	    			id: 6,
	    			name: "24h access"
	    		}
	    	],
	    	offices : [
	    		{
	    			title : "Shared Desk Space",
	    			capacity : 15,
	    			min_people : 3,
	    			max_people : null,
	    			base_price : 225,
	    			price_type : "price_per_person",available_from : "2014-10-31T16:34:49+00:00",
	    			minimum_stay_months : 3,
	    			space_type : "Private",
	    			comments : "A private office which would suit growing creative businesses.",
	    			is_filled : 0
	    		}
	    	]
	    }, {
	    ... [more spaces]
	    }]
  ```

* **Notes:**
	* available_from date will be provided in ISO 8601 format