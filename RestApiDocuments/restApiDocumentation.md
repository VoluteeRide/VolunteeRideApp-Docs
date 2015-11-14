
## Rest Api Documentation for VolunteeRide App

### Authentication for All apis

1. Kindly add **Basic authentication** header when calling any of the below mentioned apis with the username and password for     the registered user.
2. Once the user the logged in, server will create a session and respond with session id which will be stored as JSESSIONID 
   cokkie on your browser.
3. Basic Authentication header will not be required in susbsequent api calls once the user is logged in as the server will use    this session id to retrieve the logged in user information and roles.
4. The user can be ended by logging user out using a **POST http://localhost:8080/volunteeride/logout** api.

### User Resource Apis:

1. Register VOLUNTEER
   * Description : Registers volunteer into the system.
   * URL : **POST http://localhost:8080/volunteeride/users**
    
   * Sample Request :
   ```
   {
        "username": "volusr3",
         "password":"password",
        "firstName": "volunteer3 First Name",
        "lastName": "volunteer3 last name",
        "email": "volusr3@gmail.com",
        "phone": "123-456-8792",
        "ownedVehicles":
        [
            {
                "make": "Toyota",
                "model": "Camry",
                "totalRiderCapacity": 4,
                "type": "SEDAN",
                "color": "Black"
            }
        ],
        "centerId": "564798040364519acbc255b1",
        "userRoles":
        [
            "VOLUNTEER"
        ]
    }

   
   ```
   * Sample Response :
   ```
    {
        "id": "56479ca903646d1ea2a2edd7",
        "createdDatetime": "2015-11-14T20:42:17+0000",
        "version": 0,
        "username": "volusr3",
        "firstName": "volunteer3 First Name",
        "lastName": "volunteer3 last name",
        "email": "volusr3@gmail.com",
        "phone": "123-456-8792",
        "ownedVehicles":
        [
            {
                "make": "Toyota",
                "model": "Camry",
                "totalRiderCapacity": 4,
                "type": "SEDAN",
                "color": "Black"
            }
        ],
        "centerId": "564798040364519acbc255b1",
        "userRoles":
        [
            "VOLUNTEER"
        ]
    }

   
   
   ```
   
2. Register RIDE_SEEKER
   * Description : Registers ride seeker into the system.
   * URL : **POST http://localhost:8080/volunteeride/users**
    
   * Sample Request :
   ```
   {
        "username": "rideusr3",
        "password":"password",
        "firstName": "rideseeker 3 First Name",
        "lastName": "rideseeker 3 last name",
        "email": "rideusr3@gmail.com",
        "phone": "123-456-8792",
        "ownedVehicles": null,
        "centerId": "5647897e03649b1e013c90ed",
        "userRoles":
        [
            "RIDE_SEEKER"
        ]
    }

   ```
   * Sample Response :
   ```
      {
        "id": "56479d6103646d1ea2a2edd8",
        "createdDatetime": "2015-11-14T20:45:21+0000",
        "version": 0,
        "username": "rideusr3",
        "firstName": "rideseeker 3 First Name",
        "lastName": "rideseeker 3 last name",
        "email": "rideusr3@gmail.com",
        "phone": "123-456-8792",
        "ownedVehicles": null,
        "centerId": "5647897e03649b1e013c90ed",
        "userRoles": [
          "RIDE_SEEKER"
        ]
      }

   ```

3. Retrieve User Details:
  * Description : Retrieves information about the user.
  * URL : **GET http://localhost:8080/volunteeride/user/{user_id}**
  * Sample Response : 
    ```
    {
        "id": "56479ca903646d1ea2a2edd7",
        "createdDatetime": "2015-11-14T20:42:17+0000",
        "version": 0,
        "username": "volusr3",
        "firstName": "volunteer3 First Name",
        "lastName": "volunteer3 last name",
        "email": "volusr3@gmail.com",
        "phone": "123-456-8792",
        "ownedVehicles":
        [
            {
                "make": "Toyota",
                "model": "Camry",
                "totalRiderCapacity": 4,
                "type": "SEDAN",
                "color": "Black"
            }
        ],
        "centerId": "564798040364519acbc255b1",
        "userRoles":
        [
            "VOLUNTEER"
        ]
    }
    
    ```

### Center Resource Apis:

1. Retrieve All Centers
  * Description : Retrieves information about all centers.
  * URL : **GET http://localhost:8080/volunteeride/centers**
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
               "5639aef103649dac603407a2"
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
           "pickupTime": "2015-11-09T12:36:04.000+0000",
           "status": null,
           "centerId": "ignoredCenterId",
           "totalNoOfRiders": 0
   }
  ```
  
  * Sample Response :
  ```
    {
        "id": "564007f30364a91408c89b45",
        "createdDatetime": "2015-11-09T02:41:55+0000",
        "version": 0,
        "volunteerId": null,
        "rideSeekerIds":
        [
            "5639aef103649dac603407a2"
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
        "pickupTime": "2015-11-09T12:36:04+0000",
        "status": "REQUESTED",
        "centerId": "5639aef003649dac603407a1",
        "totalNoOfRiders": 0,
        "nextRideUserOperations": null
    }


  ```
2. Get Ride details api:
  * Description : Gets Ride details for a specific ride along with next user operations on the ride based on logged in user 
    role.
  * URL : **GET http://localhost:8080/volunteeride/centers/{center_id}/rides/{ride_id}**
  * Sample Response :
  ```
    {
        "id": "564007f30364a91408c89b45",
        "createdDatetime": "2015-11-09T02:41:55+0000",
        "version": 0,
        "volunteerId": null,
        "rideSeekerIds":
        [
            "5639aef103649dac603407a2"
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
        "pickupTime": "2015-11-09T12:36:04+0000",
        "status": "REQUESTED",
        "centerId": "5639aef003649dac603407a1",
        "totalNoOfRiders": 0,
        "nextRideUserOperations":
        [
            "CANCEL"
        ]
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
4. Execute Ride Operation api:
   * Description : Execute different ride operations based on State Transition Model which can found at  
     (https://github.com/VoluteeRide/VolunteeRideApp-Docs/blob/master/README.md)
   * URL : **PUT http://localhost:8080/volunteeride/centers/{center_id}/rides/{ride_id}/operation/{OPERATION_NAME}**
   * The operations currently supported are as follows:
     * ACCEPT
     * CANCEL
     * ACKNOWLEDGE
   * Sample Response :
   ```
    {
        "id": "564007f30364a91408c89b45",
        "createdDatetime": "2015-11-09T02:41:55+0000",
        "version": 1,
        "volunteerId": "5639aef103649dac603407a3",
        "rideSeekerIds":
        [
            "5639aef103649dac603407a2"
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
        "pickupTime": "2015-11-09T12:36:04+0000",
        "status": "ACCEPTED",
        "centerId": "5639aef003649dac603407a1",
        "totalNoOfRiders": 0,
        "nextRideUserOperations":
        [
            "CANCEL"
        ]
   }
   ```
 

  
