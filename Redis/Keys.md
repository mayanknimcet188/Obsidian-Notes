## Keys
- Primary way to access data values within Redis
- Majority of redis commands operate a key or keys
- Redis Keys are unique,binary safe,can be upto 512MB in size.
- Key spaces are logical databases, are flat key spaces and no automatic namespacing.
- Logical databases are identified by : zeo based index,default is the database zero 
- Example of a key:
	- user:id:followers
		- "user:100:followers"
		- user is the object name
		- 100 is the unique identifier or the instance
		- followers: composed object
- Key names are case sensitive as they are Binary Safe
- Redis Commands
	- `SET key value [EX seconds] [PX milliseconds] [NX|XX]`
	- `GET key`
	- eg
		```bash
		>>> set customer:1000 fred
		>>> get customer:1000
		"fred"
		```
	-