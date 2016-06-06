This auomator runs rake market_date:use_latest at fixed time.


To configure this automator:
	1. Put Market-Data-Update.app to wherever convenient, and change [PATH_TO_APP] in com.nextcapital.load_market_data.plist file to absolute path to this app. Note that relative path will not be resolved, so ~/ or ./ and even $HOME should not be used.
	
	2. Put com.nextcapital.load_market_data.plist to  ~/Library/LaunchAgents/ 
	
	3. Restart computer or run "launchctl load [PATH_TO_PLIST]" in command line to load. This plist should be seen in "launchctl list" with status 0. And run "launchctl start com.nextcapital.market-data-updater" should run the update command immediately. 
	
	
Note: 
	1. The scheduled job will be skipped if computer is shut down, but may run if sleep. To change scheduled time, change com.nextcapital.load_market_data.plist file accordingly. The default time is set to 13:00 each day.
	
	2. Market-Date-Updater try to find appserver code at ~/code/appserver, so configuration is required if your appserver code is located elsewhere. Change this app using Application/Utilities/Automator.