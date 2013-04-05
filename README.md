The following scripts are contained in this repository

LoadBalanceByDevice.sh ( Tested on ubuntu 12.11 with multiple bfl singles, cgminer 12.11.4, and bfgminer 3.0 alpha2
	--Choosing load balance type --
	This script allows the user to setup an array of devices and pools, and runs an instance of cgminer or bfgminer for each device. Each device will have a seperate pool in the array as its Master pool. 
	All other pools left in the array will be set to backup on failover. To use one instance for each device, set instancePerDevice to 1

	It is also possible to use the script with standard cgminer and bfgminer load balancing, but I don't reccomend it. Load balancing functionality in both miners is not evenly distributed. Furthermore, a bad pool connection may 
	possibly cause your single miner instance to hang. To use only one instance with standard load balancing, set instancePerDevice to 0

	--Choosing a miner--
	Uncomment your miner of choice = bfg or cg

	--Setting miner path--
	Define an absolute path to each miner binary on your system

	--Configuring devices--
	Define device arrays for each miner type, noting that bfg miner uses serial scanning and cgminer uses libusb

	--Configuring pools--
	Setup the following for each array item up to the number of pools you want defined
	
	Define a poolName for each array item. This is the name that will be displayed for the screen session. Once you run the script, you can resume a screen with the followning command
	screen -r poolName

	Define a poolAddress. This is the address and port, seperated by colon

	Define poolCredentials. This is your username and password for the mining device on the specified pool

	
	-- Running the Script--
	Make sure the script is executable by your account (chmod 755 LoadBalanceByDevice.sh)
	
	Run the script: ./LoadBalance.sh

	If running load balanced by device, you will have a screen session for each device.

	If running one instance, you will have one screen session named combined.
