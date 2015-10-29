
## Api Access Control ##

*  **Retrieve Ride Details**
   * Use Case 1 : 
     * User A is registered in the system as Ride Seeker.
     * Ride 1, User A is a ride seeker for this ride.
     * User A Tries to access this ride.
     * Success
   * Use Case 2:
     * User A tries to access Ride 2 in which he is not a ride seeker.
     * Access Denied.
   * Use Case 3:
     * User A is registered as Volunteer.
     * User A is the assigned volunteer for Ride 2.
     * User A tries to access Ride 2.
     * Success.
   * Use Case 4:
     * User A is registered as a volunteer.
     * User B is the Assigned volunteer for Ride 2.
     * User A tries to access ride 2.
     * Access denied.
   * Use Case 5: 
     * Ride 2 has no volunteer assigned.
     * User A is registered as a volunteer.
     * User A tries to access Ride 2.
     * Success.
    
   
  
