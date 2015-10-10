
## Rest Api Documentation for VolunteeRide App

### Center Resource Apis:

1. Retrieve All Centers
  * Description : Retrieves information about all centers.
  * URL : ** GET http://localhost:8080/volunteeride/centers
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
  
