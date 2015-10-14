
## Rest Api Documentation for VolunteeRide App

### Center Resource Apis:

1. Retrieve All Centers
  * Description : Retrieves information about all centers.
  * URL : ** GET http://localhost:8080/volunteeride/centers**
  * Sample Response : 
  ```
    [
        {
            "id": "560b374c0364a639df428bac",
            "createdDatetime": "2015-09-30T01:13:48+0000",
            "version": 0,
            "location":
            {
                "city": "Falls Church",
                "state": "Virginia",
                "streetAddress": null,
                "zipcode": null,
                "houseNumber": 0,
                "locationName": null
            },
            "pickUpLocations":
            [
                {
                    "city": "Fairfax",
                    "state": "Virginia",
                    "streetAddress": null,
                    "zipcode": null,
                    "houseNumber": 0,
                    "locationName": null
                }
            ]
        },
        {
            "id": "560b396d03647d860857cd9e",
            "createdDatetime": "2015-09-30T01:22:53+0000",
            "version": 0,
            "location":
            {
                "city": "Falls Church",
                "state": "Virginia",
                "streetAddress": null,
                "zipcode": null,
                "houseNumber": 0,
                "locationName": null
            },
            "pickUpLocations":
            [
                {
                    "city": "Fairfax",
                    "state": "Virginia",
                    "streetAddress": null,
                    "zipcode": null,
                    "houseNumber": 0,
                    "locationName": null
                }
            ]
        }
    ]
  ```
2. Get Center Details :
  * Description : Retrieves details for a specific Center.
  * URL : **GET http://localhost:8080/volunteeride/centers/{center_id}**
  * Sample Response : 
  ```
    {
        "id": "560b396d03647d860857cd9e",
        "createdDatetime": "2015-09-30T01:22:53+0000",
        "version": 0,
        "location":
        {
            "city": "Falls Church",
            "state": "Virginia",
            "streetAddress": null,
            "zipcode": null,
            "houseNumber": 0,
            "locationName": null
        },
        "pickUpLocations":
        [
            {
                "city": "Fairfax",
                "state": "Virginia",
                "streetAddress": null,
                "zipcode": null,
                "houseNumber": 0,
                "locationName": null
            }
        ]
    }
  ```

### Ride Resource Apis:

1. Request Ride Api
  * Description : Saves Ride request from volunteer.
  * URL : **POST http://localhost:8080/volunteeride/centers/{center_id}/rides**
  * Content Type Header : application/json
  * Sample Request :
  ```
  {
           "volunteerId": null,
           "rideSeekerIds":
           [
               "560b396d03647d860857cd9f"
           ],
           "pickupLoc":
           {
               "city": "Newyork",
               "state": "Newyork",
               "streetAddress": null,
               "zipcode": null,
               "houseNumber": 0,
               "locationName": null
           },
           "dropoffLoc":
           {
               "city": "Jersey City",
               "state": "Jersey",
               "streetAddress": null,
               "zipcode": null,
               "houseNumber": 0,
               "locationName": null
           },
           "pickupTime": "2015-10-02T02:36:04.000+0000",
           "status": null,
           "centerId": "ignoredCenterId",
           "totalNoOfRiders": 0
  }
  ```
  * Sample Response :
  ```
    {
        "id": "56196a620364e69ad3d1d8a0",
        "createdDatetime": "2015-10-10T19:43:30+0000",
        "version": 0,
        "volunteerId": null,
        "rideSeekerIds":
        [
            "560b396d03647d860857cd9f"
        ],
        "pickupLoc":
        {
            "city": "Newyork",
            "state": "Newyork",
            "streetAddress": null,
            "zipcode": null,
            "houseNumber": 0,
            "locationName": null
        },
        "dropoffLoc":
        {
            "city": "Jersey City",
            "state": "Jersey",
            "streetAddress": null,
            "zipcode": null,
            "houseNumber": 0,
            "locationName": null
        },
        "pickupTime": "2015-10-11T02:36:04+0000",
        "status": "REQUESTED",
        "centerId": "560b396d03647d860857cd9e",
        "totalNoOfRiders": 0
    }
  ```
2. Get Ride details api:
  * Description : Gets Ride details for a specific ride.
  * URL : **GET http://localhost:8080/volunteeride/centers/{center_id}/rides/{ride_id}**
  * Sample Response :
  ```
    {
        "id": "560de6590364a04f3d689038",
        "createdDatetime": "2015-10-02T02:05:13+0000",
        "version": 0,
        "volunteerId": null,
        "rideSeekerIds":
        [
            "560b396d03647d860857cd9f"
        ],
        "pickupLoc":
        {
            "city": "Newyork",
            "state": "Newyork",
            "streetAddress": null,
            "zipcode": null,
            "houseNumber": 0,
            "locationName": null
        },
        "dropoffLoc":
        {
            "city": "Jersey City",
            "state": "Jersey",
            "streetAddress": null,
            "zipcode": null,
            "houseNumber": 0,
            "locationName": null
        },
        "pickupTime": "2015-10-02T02:36:04+0000",
        "status": "REQUESTED",
        "centerId": "560b396d03647d860857cd9e",
        "totalNoOfRiders": 0
    }
  ```
3. Search Rides Api Details :
  * Description : Gets Ride details for a specific ride. This api provides paged results.
  * URL : **GET http://localhost:8080/volunteeride/centers/{center_id}/rides?status=REQUESTED&rideseeker_id=560b396d03647d860857cd9f&page=1&size=2**
  * Search Parameters currently supported:
    * **center_id** -- Part of Url Path Param
    * **rideseeker_id** -- Represents rideseeker id to be searched upon. Multiple rideseekers can be specified by repeating this parameter with different values in the search url.
    * **status** -- Following values are currently supported **REQUESTED, ACKNOWLEDGED, CANCELLED, ACCEPTED, ARCHIVED**
    * **page** -- Represents page number. Please note that this parameter is zero indexed. So First page should have value 0. This defaults to 0 if nothing is specified.
    * **size** -- Represents page size. This defaults to 20 if nothing is specified.
  * Sample Response :
  ```
    {
        "content":
        [
            {
                "id": "560b667503645d46d6f52275",
                "createdDatetime": "2015-09-30T04:35:01+0000",
                "version": 0,
                "volunteerId": null,
                "rideSeekerIds":
                [
                    "560b396d03647d860857cd9f"
                ],
                "pickupLoc":
                {
                    "city": "Newyork",
                    "state": "Newyork",
                    "streetAddress": null,
                    "zipcode": null,
                    "houseNumber": 0,
                    "locationName": null
                },
                "dropoffLoc":
                {
                    "city": "Jersey City",
                    "state": "Jersey",
                    "streetAddress": null,
                    "zipcode": null,
                    "houseNumber": 0,
                    "locationName": null
                },
                "pickupTime": "2015-10-01T23:36:04+0000",
                "status": "REQUESTED",
                "centerId": "560b396d03647d860857cd9e",
                "totalNoOfRiders": 0
            },
            {
                "id": "560de6590364a04f3d689038",
                "createdDatetime": "2015-10-02T02:05:13+0000",
                "version": 0,
                "volunteerId": null,
                "rideSeekerIds":
                [
                    "560b396d03647d860857cd9f"
                ],
                "pickupLoc":
                {
                    "city": "Newyork",
                    "state": "Newyork",
                    "streetAddress": null,
                    "zipcode": null,
                    "houseNumber": 0,
                    "locationName": null
                },
                "dropoffLoc":
                {
                    "city": "Jersey City",
                    "state": "Jersey",
                    "streetAddress": null,
                    "zipcode": null,
                    "houseNumber": 0,
                    "locationName": null
                },
                "pickupTime": "2015-10-02T02:36:04+0000",
                "status": "REQUESTED",
                "centerId": "560b396d03647d860857cd9e",
                "totalNoOfRiders": 0
            }
        ],
        "totalPages": 3,
        "totalElements": 6,
        "last": false,
        "size": 2,
        "number": 1,
        "sort": null,
        "first": false,
        "numberOfElements": 2
    }
  ```

  
