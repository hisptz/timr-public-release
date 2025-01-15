## Offline encounter
The support for the offline encounter feature. This feature allows the user to record services provided to a client even if there is no registration information for the client (The user is offline and cannot access the server). 

How it works:

**Conditions:**
1. The user must be offline. (This will be further improved later to check for server availability rather than just connection) 
2. The user has to search the client by the use of the barcode
3. The searched client must not exist in the offline data

When all conditions are met, a button labeled 'Offline encounter' will appear on the search results page. 

**Steps:** 
1. Click the 'Offline encounter' button.
2. A form with 2 fields, ID number (disabled) and date of birth, will appear. Enter the date of birth. It must be entered correctly as seen on the client's immunization card. Then click 'Encounter'.
3. A form with Facility selector, Weight, Supplements, and Immunization information fields will appear. Check on the provided services ONLY and fill in their information accurately. Click on the 'Save and discharge' button to save the information

Synchronization of offline encounters
When the app has some unsynced offline encounters and goes online, an area in the 'Data synchronization' tab of the synchronization module called 'Offline encounters summary' will appear. This section shows the count of offline encounters that have not been synchronized. To synchronize, click on the 'Sync offline encounters'. 


**Notes:**
The immunization services that will be seen in step 3 are determined by the age of the child and vaccine configuration. The form will only show the vaccines that are viable for the child's age. The form, however, does not have skip logic to control the dose number. This is due to the lack of history of the child immunization information. 

A client can only have one offline encounter per day.  If in case the barcode is scanned again on the same day, the form in Step 3 will appear prefilled with the previous information and the button will change to 'Update'. This will only update the previously entered data instead of creating  a new one

**How sync works**
Offline encounter sync works in the following steps:
1. The client data for all offline encounter entries is obtained from the server and saved to the device. 
2. For each offline encounter entry,  a list of services provided is obtained. Each service in the list is then transformed to either an existing event or a new event. The events are then linked to the entity enrollment
3. If the process of transforming all services in an entity to events, the entity is deleted from the device. If any of the services have issues with the transformation, the entry will not be deleted. The corresponding issue will be logged in the application logs.
