# Encrytion-Algorithm
Algorithm for Creating an Encrypted Network
*******************************************************************************************
Developer: Gurudatt Shenoy
Website: www.invisocial.com/about
Email:invisocial.com@gmail.com
DEMO SITE: http://www.freespeech.tk
*******************************************************************************************

The developer is the inventor of the algorithm enabling encryption and sharing of user data
by securely saving and sharing the encryption key among peers.

The developer does not hold any copyright or any other form of rights and provides the information
as open source knowledge.
*******************************************************************************************

The encryption method being employed by InviSocial ensures that data at rest on the servers database is encrypted using the strongest encryption method (AES 256) and uses a unique algorithm that assures greater security of the encrypted data:

Authentication – Securing the gateway to accessing data: The key to securing the entire process of offering hack proof encryption is greatly dependent on the process of user authentication. 

The user enters username (UID) and password (PID) on the login page of a website.

The authentication server verifies if the account (username) is already registered.

On Registration, a unique system generated encryption key (SID) is generated which is encrypted using the PID and the eSID is stored on the server. 

eSID=encrypt(SID,PID)

The PID is never stored on the server. 

All user profile data captured at time of registration or thereafter is encrypted using SID.

On Login, the UID and PID is securely transmitted to the web server where the the UID is first authenticated and then the eSID retrieved from the server database.

The eSID is then decrypted to retrieve the SID.

SID=decrypt(eSID,PID)

The SID is then encrypted using the device id (DID) generated for the session. The DID can be a unique browser ID or a true device identity using the hardware signature of the device.

sSID =  encrypt(SID,DID)

Thereafter the user can access their account and is able to access all the data by using the sSID from the active device.

When the User selects to share their User Data with another user, the SID of the user is encrypted using the SID of the user with whom it has decided to share their data. 

eSID = encrypt(SID1,SID2) 

The eSID is stored in the shared Users table record and referred to when accessing the shared User data.

Vulnerabilities
---------------
1. By capturing the login credentials of the user which is the UID and PID. Multi Factor Out of Band authentication can plug this vulnerability.

2. By gaining access to server and change the server side code of the application and introducing code to capture the DID of a user and then use the DID to decrypt sSID in Session and thus retrieve the SID of the user which is used to encrypt all the server side data. This can be prevented by encrypting/obfusicating the server side code besides strenghtening server side security.

