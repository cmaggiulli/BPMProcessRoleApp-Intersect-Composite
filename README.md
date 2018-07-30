# ICS-Intersect-Composite

### About
This is an OIC integration used to retrieve the membership intersect between two OracleBPMProcessRoleApp roles.  For example, suppose we had the following two roles with their respective members.

* NewYorkOffice
  * chris@example.com
  * jen@example.com
  * tod@example.com
  
* ITEmployees
  * chris@example.com
  * jack@example.com
  * randall@example.com
  * shashank@example.com
  
This integration would return *chris@example.com* as the only intersect member.

### Usage

The integrations endpoint is as follows: 

     /ic/api/integration/v1/flows/rest/GET_USER_INTERSECT/1.0/first/{firstRole}/second/{secondRole}

It takes in two template parameters: *firstRole* and *secondRole*

Given the example above, a GET request would be sent to the following url
https://base:443/ic/api/integration/v1/flows/rest/GET_USER_INTERSECT/1.0/first/NewYorkOffice/second/ITEmployees
  
 The response JSON response in this example would be
 
    {
       "users":
          [
             "chris@example.com"
         ]
    {
     
### Package and Deploy

Simply zip the contents of this directory and give the compressed file an \*.iar extension.  
Adding this integration to your OIC instance can be done simply by issuing a POST request to 

    /ic/api/integration/v1/integrations/archive 
    
with a multipart/form-data file:file form parameter

### Additional Information
This Integration was built specifically for Oracle Cloud's Integration Cloud Service to be used with Oracle Process Cloud service.  However this is a valid SOA Composite that will also work with Oracle SOA / BPM 12c
