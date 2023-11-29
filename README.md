# An Eagler client in the browser
Like my serverless client, this is 1.5.2 and may or may not be updated.
There is full support for both singleplayer and multiplayer, though the latter is still in development.

Fork this repo and deploy it if it gets blocked.

# Running a multiplayer server
1) Download this repo (the Java folder is what you need)
2) Run `run.bat` or `run_unix.sh` in both bungee and bukkit folders
3) Open the browser client
4) Connect to ws://127.0.0.1:25565 to play on localhost

# LAN Worlds [^1]
Eaglercraft fully supports LAN worlds, you can share your world with any player and they can connect directly to it as if you are running a server in your browser.
LAN worlds will work between any two devices connected to the internet, you are not limited to only players connected to your Wi-Fi network

To open your world to LAN, go to the pause menu and click 'Open to LAN'. You can configure the gamemode and cheats and if you would like to hide your LAN world. When you do not hide your LAN world, it will appear on the Multiplayer screen from the main menu to anybody else also on your Wi-Fi network. Set the world hidden if you are at school or something and don't want everyone else in your class to join as well and start griefing.

When you open the world to LAN it will give you a 'join code'. Simply share the code with your friends and they can visit the Multiplayer screen from the main menu and click 'Direct Connect' and enter the code and they will be able to join your world.

Make sure they add the relay server your game opens the LAN world on to their "Network Settings" menu accessable from the Multiplayer screen. You simply must send them the URL indicated in the pause menu once the world is opened and they can use the "Add Relay" option to add the URL to their list.

THIS IS A REQUIRED STEP FOR A PERSON TO JOIN YOUR WORLD, IF THEY DO NOT HAVE THE RELAY YOUR WORLD IS HOSTED ON ADDED TO THEIR "Network Settings" THE GAME WILL BE UNABLE TO LOCATE THE WORLD

# Creating a LAN Relay [^2]
Simply download `sp-relay.jar` and run `java -jar sp-relay.jar`
Run `java -jar sp-relay.jar --debug` to view debug info like all the IPs of incoming connections, as it is not shown by default because logging all that info will reduce performance when the relay is being pinged many times a second depending on it's popularity.

Edit the `relayConfig.ini` file generated on first launch to change the port and configure ratelimiting and such, and relays.txt to change the list of STUN and TURN relays reported to clients connecting to the relay, which are required to correctly establish a P2P LAN world connection in browsers

The origin-whitelist config variable is a semicolon (;) seperated list of domains used to restrict what sites are to be allowed to use your relay. When left blank it allows all sites. Add offline to allow offline download clients to use your relay as well, and null to allow connections that do not specify an Origin: header. Use * as a wildcard, for example: *.deev.is allows all domains ending with "deev.is" to use the relay.

[^1]: https://github.com/lDEVinux/eaglercraft#lan-worlds
[^2]: https://github.com/lDEVinux/eaglercraft#creating-a-lan-relay
