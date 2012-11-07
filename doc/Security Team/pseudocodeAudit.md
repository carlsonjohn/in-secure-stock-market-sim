#Pseudocode
##Password Recovery
* GET EnteredUserName
* IF (EnteredUserName == UserName) THEN
* 	New Password Sent to registered email	
* ELSE						
* 	UserName Failed
* ENDIF

// should send a link to password re-setting URL so they have to access to the email in order to re-set the password.


##Initial Account Access
* GET EnteredUserName
* GET EnteredPassword
* 	IF (EnteredUsername == Username && EnteredPassword == Password) THEN
* 		Login Successful
* 		CALL Password Change
* 	ELSE
* 		Login Failed.
* 	ENDIF

##Password Change
* GET EnteredUserName
* GET EnteredPassword
* IF (EnteredUsername == Username && EnteredPassword == Password) THEN	
*   GET NewPassword
*   Sanitize (NewPassword)
*   IF (NewPassword) THEN
*     change password
*   ELSE
*     Display error message
*   ENDIF
* ELSE
* 	Password Change Failed
* ENDIF

// looks pretty good.

##Login 
* GET EnteredUserName
* GET EnteredPassword								
* IF (EnteredUsername == Username && EnteredPassword == Password) THEN		
* 	Set session cookie and enter site					
*	ELSE
*		Display error message
*	ENDIF

// Test that login doesn't contain bad chars. Must test before queuerying the database.



##Sanitize
* IF (infoType == string)
* 	Remove whitespaces
* 	Remove ASCII characters <32 //FILTER_SANITIZE_STRING 	 
* 	Remove ASCII characters >127				
* 	Return info						 
* ELSE IF (infoType == float) //FILTER_SANITIZE_FLOAT
* 	Remove all characters except digits, +-.		 
* 	Return info						
* ELSE IF (infoType == integer) //FILTER_SANITIZE_INT		
* 	Remove all characters except digits, +-			
* 	Return info					
* ELSE								
* 	Return infoType error					
* ENDIF


// great job removing <32 and >127 but additional chars should be removed as well: ASCII 34 ", ASCII 39 ', ASCII 96 `, ASCII 45 -, ASCII 47 /, ASCII 92 \, ASCII 60 <, ASCII 62 >

// Should require passwords to have a minimum length, and a combination of upper-case\lower-case letters and numbers some additional special characters may be added

// should we be working with the password or the hash of the password? We could hash the passwords and compare hashes of the enteredPassword and the storedPassword.



##Securities Info
* do
* if there are result in mysql
* while(row  = result) //inner loop in if statement
* foreach(row as value) 
* printf() and echo <br/>
* while mysql has more results //end loop
