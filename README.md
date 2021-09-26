# Thingsboard
## HW2 for MIT 1.125
### Question 1: Immages of rule chains
*For the Root Rule chain, no major change to the default. The basic function is to pusblish the data to the device telemetry*
    ![Root Rule Chain](Img/RootRuleChain.JPG)

Two Generators were used to generate outdoor and indoor temperatures respectively
- *Outdoor Generator rule chain image*
  ![Outdoor temperature generator](Img/OutdoorTempGen.JPG)
  
  Code for the outdoor generator: 
  > var msg = {
  >            	ODtemperature: (28 + 10 * Math.random()).toFixed(1)
  >           };
  >           
  >           return {
  >           	msg: msg,
  >           	metadata: {
  >           		deviceType: "outdoor thermometer"
  >           	},
  >           	msgType: "POST_TELEMETRY_REQUEST"
  >           };
  
  
  push to firebase is achieved with the "rest api call"
  ![Push outdoor temperature to Firebase](Img/PushODTemptoFirebase.JPG)
- *Indoor Generator rule chain image*
  ![Inddor Temperature Generator](Img/IndoorTempGen.JPG)
  
  Code for the indoor generator: 
  
  >
  > var msg = {
  >           	IDtemperature: (18 + 10 * Math.random()).toFixed(1)
  >           };
  >       
  >           return {
  >           	msg: msg,
  >           	metadata: {
  >           		deviceType: "indoor thermometer"
  >           	},
  >           	msgType: "POST_TELEMETRY_REQUEST"
  >           };


  push to firebase is achieved with the "rest api call"
  ![Push indoor temperature to Firebase](Img/PushIDTemptoFirebase.JPG)
  
### Question 2: Image of Firebase
Two data channels were setup in firebase realtime database to record the indoor and outdoor temperature:

  ![Firebase data channels](Img/Firebase output.JPG)
  
- The outdoor temperature datachannel in Firebase realtime database is named "temperature"
    ![Firebase outdoor temperature data](Img/Firebase_ODTemp.JPG)
    
- The indoor temperature datachannel in Firebase realtime database is named "temperature2"
    ![Firebase indoor temperature data](Img/Firebase_IDTemp.JPG)

### Dashboard view of indoor and outdoor temperatures

The outdoor temperature should be 10 degrees higher than indoor by design. 

  ![Dashboard view](Img/WarehouseDashboard.JPG)
