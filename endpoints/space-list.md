**List Available Spaces**
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
  ```javascript
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
	    			min_people : [integer],
	    			max_people : [integer],
	    			base_price : [number],
	    			price_type : [string],
	    			available_from : [string (date in ISO 8601 format)],
	    			minimum_stay_months : [number],
	    			space_type : [string (Hot Desk OR Shared OR Private)],
	    			comments : [string],
	    			is_filled : [boolean]
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
      url: "http://host.spaciousapp.com/api/space-list/?api_key=your_api_key",
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
  ```javascript
    [
        {
            "id": 330,
            "title": "Runway East - vibrant workspace for creators",
            "description": "<img src=\"https://spaciousapp.s3.amazonaws.com/uploads/spaces/330/RunwayEast-Logo-%28BY%29%29-LoRes.jpg\" /> <br> <p>Runway East is a vibrant co-working space at the heart of London\u0027s Silicon Roundabout. Focused on eCommerce & IOT (Internet of Things), this huge 8,000sq foot space has already attracted rising start-up stars Blaze, Indiegogo & many others.</p>  <p>Hardware: </p> <ul> <li>Prime location right above Old Street <li>Incredible panoramic views of London\u0027s skyline  <li>Ultra fast fibre-optic internet <li>65-100 person event space with flexible space for larger numbers as needed <li>Multiple meeting rooms  <li>Chill out room with ping pong table <li>Open 24/7, 365 days a year with porters <li>Secure indoor bike parking  <li>Fully stocked kitchen with unlimited coffee and.... beer fridge!!  </ul>",
            "address": "207 Old Street",
            "postcode": "EC1V 9NR",
            "is_active": true,
            "is_promoted": false,
            "geocoordinates": "51.5258309000000025, -0.0891406000000000",
            "images": [
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/330/P1010934.JPG",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/330/P1010904.JPG",
                    "thumbnail": true,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/330/P1010906.JPG",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/330/P1010877.JPG",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/330/P1010927.JPG",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/330/P1010914.JPG",
                    "thumbnail": false,
                    "cover": false
                }
            ],
            "facilities": [
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/wifi.png",
                    "id": 1,
                    "name": "Wi-fi"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/furniture.png",
                    "id": 2,
                    "name": "Furniture"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/lockers.png",
                    "id": 3,
                    "name": "Lockers"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/showers.png",
                    "id": 4,
                    "name": "Showers"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/meeting.png",
                    "id": 5,
                    "name": "Meeting room"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/24h.png",
                    "id": 6,
                    "name": "24h access"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/kitchen.png",
                    "id": 7,
                    "name": "Kitchen"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/pingpong.png",
                    "id": 8,
                    "name": "Ping pong"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/bikeStorage.png",
                    "id": 9,
                    "name": "Bike storage"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/eventSpace.png",
                    "id": 10,
                    "name": "Event space"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/mailingAddress.png",
                    "id": 11,
                    "name": "Mailing address"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/get_image_path/accessibility.png",
                    "id": 12,
                    "name": "Disabled Access"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/get_image_path/animals.png",
                    "id": 13,
                    "name": "Pets Allowed"
                }
            ],
            "offices": [
                {
                    "title": "Jumpseat",
                    "capacity": 5,
                    "min_people": 0,
                    "max_people": 5,
                    "base_price": "299.00",
                    "price_type": "Price Per Person",
                    "available_from": "2014-09-01T00:00:00+0000",
                    "minimum_stay_months": 1,
                    "space_type": "Shared",
                    "comments": "a.k.a - a hotdesk!",
                    "is_filled": false
                },
                {
                    "title": "Standard",
                    "capacity": 12,
                    "min_people": 0,
                    "max_people": 12,
                    "base_price": "325.00",
                    "price_type": "Price Per Person",
                    "available_from": "2014-09-01T00:00:00+0000",
                    "minimum_stay_months": 3,
                    "space_type": "Shared",
                    "comments": "",
                    "is_filled": false
                },
                {
                    "title": "Premium",
                    "capacity": 10,
                    "min_people": 0,
                    "max_people": 10,
                    "base_price": "375.00",
                    "price_type": "Price Per Person",
                    "available_from": "2014-09-01T00:00:00+0000",
                    "minimum_stay_months": 3,
                    "space_type": "Shared",
                    "comments": "",
                    "is_filled": false
                }
            ]
        },
        {
            "id": 359,
            "title": "Containerville: Great home inside Shipping Containers for start-ups and pop-ups",
            "description": "<p> Containerville is a new great home for start-ups and pop-ups. 30 shipping containers up-cycled into modern work spaces by the Regents Canal. Each container can comfortably accommodate six desks. </p>  <p> Each container is fitted out to function perfectly as a clean, modern work space with great views out over the canal. This is a destination and a work-place, a place for tenants to work and trade - with easy access to collaborators, partners, clients and customers alike. </p>  <p> Rent a container for \u00a31,200 pcm including high speed 100 MB internet access, electricity, water and service charge. </p>  <p> Anyone who signs up for a container for a year or more gets a 10% discount! </p>",
            "address": "5\u201310 Corbridge Crescent, London",
            "postcode": "E2 9DS",
            "is_active": true,
            "is_promoted": false,
            "geocoordinates": "51.5338818000000032, -0.0586251000000000",
            "images": [
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/359/2014-10-01_15%2B56%2B39%2B751211__DSF1040.jpg",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/359/2014-10-01_15%2B56%2B39%2B751211__DSF0997.jpg",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/359/2014-10-01_15%2B56%2B39%2B751211__DSF0990.jpg",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/359/2014-10-01_15%2B56%2B39%2B751211__DSF0991.jpg",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/359/2014-10-01_15%2B56%2B39%2B751211__DSF1006.jpg",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/359/2014-10-01_15%2B56%2B39%2B751211__DSF1017.jpg",
                    "thumbnail": false,
                    "cover": false
                },
                {
                    "url": "https://spaciousapp.s3.amazonaws.com/uploads/spaces/359/2014-10-01_15%2B56%2B39%2B751211__DSF1045.jpg",
                    "thumbnail": false,
                    "cover": false
                }
            ],
            "facilities": [
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/wifi.png",
                    "id": 1,
                    "name": "Wi-fi"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/showers.png",
                    "id": 4,
                    "name": "Showers"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/24h.png",
                    "id": 6,
                    "name": "24h access"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/features/bikeStorage.png",
                    "id": 9,
                    "name": "Bike storage"
                },
                {
                    "icon": "https://spaciousapp.s3.amazonaws.com/get_image_path/accessibility.png",
                    "id": 12,
                    "name": "Disabled Access"
                }
            ],
            "offices": [
                {
                    "title": "Container Unit Price",
                    "capacity": 8,
                    "min_people": 6,
                    "max_people": 8,
                    "base_price": "1200.00",
                    "price_type": "Total Price",
                    "available_from": "2014-10-01T00:00:00+0000",
                    "minimum_stay_months": 1,
                    "space_type": "Shared",
                    "comments": "",
                    "is_filled": false
                }
            ]
        }
    ];
  ```

* **Notes:**