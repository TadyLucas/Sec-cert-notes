
#### Categories:
- **Technical** - Use technology to protect systems and data
- **Managerial** - Focus on security **policies, processes, and oversight**
- **Operational** - Focus on **day-to-day operational activities** that enhance security, do it by person 
- **Physical** - Protect the **physical environment** and prevent unauthorized access to facilities, equipment, or systems
![[Pasted image 20250116054305.png]]
#### AIC/CIA Triad
- fundamentals of security
- Confidentiality - prevent information disclosure
	- Encryption
		- when sending to someone Encode it and the other person will decode it
	- Access controls
	- MFA
- Integrity - Message can't be modified without detection
	- Hashing
		- you perform hash function and get hash and send it with it to the person and the person will perform same hashing function and see if the data was modified
	- Digital signatures
		- this will encrypt hash key with **asymmetric encryption algorithm**
	- Certificates
		- to verify an individual
- Availability - Systems and networks must be up and running
	- Redundancy
	- Fault tolerance
	- Patching
#### Non-repudiation
**Proof of integrity**
- Verify data doesn't change
- **Hashing**
	- we are calling that **message digest**, a **fingerprint**
- when we will download some file there might be a hash, when you perform the hashing function on the file you will see if the hash matches, if yes that means the file wan't changed
**Proof of origin**
- the file is sign with **private** key
	- when you want to send the file you will make **hash** and than encrypt it with **private** key and send it with the file. The people who want to verify integrity will take **digital signaiture**(hash) and **decrypt** it with **public** key and check the hash of the signature and of the file
#### AAA framework
**Authentication**
- prove you are who you say you are 
- password, username, MFA
**Authorization**
- system check if the user have permissions for it
- determine what action you can do
**Accounting**
- Resources used: Login time, data sent, recived, logout time
##### Authenticating people
- when you want to sign you will send request to firewall, you will enter username & password, than it will send credentials to AAA Server to check if the credentials are found and verified it will let you access internal server 
##### Authenticating system
- put digital signed certificate on the device 
- checking if the devices is from the organization
**Certificate Authority**(CA)
  - organization will create certificate for device and sign it with CA
  - signature is validated by root CA
##### Authorization models
- Put authorization model in the middle
	- define it by roles, orgs, Attributes
- add an abstraction(make groups)
	- create relationship between user and resource
#### Gap Analysis
- comparing where you are and where you want to be
- Determine the end goal - choose framework
	- NIST Special Publication
	- ISO/IEC 27001]
- Evaluate
	- baseline of employees
		- experience
		- training
	- current processes
		- research existing IT systems
		- security policies
- Compare
	- comparison
	- Identify weaknesses
	- detailed analysis
		- break it into smaller segments
- create path
 -  final comparison
	![[Pasted image 20250116064934.png]]
	 - red -> yellow -> green
	 - give reason why the color
#### Zero trust
- you have to authenticate every time
- nothing is trusted
- MFA, encryption, systems encryption
- Data plane
	- process the frames, packets
	- Router switch
- Control Planes
	- define policies and rules
	- determine how packets should be forwarded
	- Adaptive identity
		- identify user with authentication
			- e.g. consider source location
			- role
			- IP address
		- limit entry point to only in the building
	- Security zones
		- looking where are you coming from and where are you going
			- trusted, untrusted
			- internal, external network
	- Policy Enforcement point
		- gatekeeper
		- allow, monitor
		- ![[Pasted image 20250116193434.png]]
		-  Policy Engine
			- Evaluates each access decision based on policy
			- Grant, deny, revoke
		- Policy Administrator
			- generates access tokens or credentials
			- tells the PEP to allow or disallow access
			- 