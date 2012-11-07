#Pseudocode
##Password Recovery
* GET EnteredUserName
* IF (EnteredUserName == UserName) THEN
* 	New Password Sent to registered email	\\ should send a link to password re-setting URL so they have to have
* ELSE						\\ access to the email in order to re-set the password.
* 	UserName Failed
* ENDIF

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
* IF (EnteredUsername == Username && EnteredPassword == Password) THEN		\\ looks pretty good.
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


##Login 
* GET EnteredUserName
* GET EnteredPassword								\\ Test that login doesn't contain bad chars.
* IF (EnteredUsername == Username && EnteredPassword == Password) THEN		\\ Must test before queuerying the database.
* 	Set session cookie and enter site					
*	ELSE
*		Display error message
*	ENDIF


##Sanitize
* IF (infoType == string)
* 	Remove whitespaces
* 	Remove ASCII characters <32 //FILTER_SANITIZE_STRING 	\\ great job removing <32 and >127 but additional chars should 
* 	Remove ASCII characters >127				\\ be removed as well: ASCII 34 ", ASCII 39 ', ASCII 96 `,
* 	Return info						\\ ASCII 45 -, ASCII 47 /, ASCII 92 \, ASCII 60 <, ASCII 62 >
* ELSE IF (infoType == float) //FILTER_SANITIZE_FLOAT
* 	Remove all characters except digits, +-.		\\ Should require passwords to have a minimum length, and 
* 	Return info						\\ a combination of upper-case\lower-case letters and numbers
* ELSE IF (infoType == integer) //FILTER_SANITIZE_INT		\\ some additional special characters may be added
* 	Remove all characters except digits, +-			
* 	Return info						\\ should we be working with the password or the hash of the 
* ELSE								\\ password? We could hash the passwords and compare hashes
* 	Return infoType error					\\ of the enteredPassword and the storedPassword.
* ENDIF

##Securities Info
* do
* if there are result in mysql
* while(row  = result) //inner loop in if statement
* foreach(row as value) 
* printf() and echo <br/>
* while mysql has more results //end loop
