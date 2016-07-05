# Rust server that runs inside a Docker container

NEW: We've written a guide on how to use this image [here](http://rust.didscraft.com/rust-server-on-linux-using-docker/).

**NOTE**: This image will install/update on startup. The path ```/steamcmd/rust``` can be mounted on the host for data persistence.  
Also note that this image provides the new web-based RCON, so you should set ```RUST_RCON_PASSWORD``` to a more secure password.

# How to run the server
1. Set the environment variables you wish to modify from below (note the RCON password!)
2. Optionally mount ```/steamcmd/rust``` somewhere on the host or inside another container to keep your data safe
3. Enjoy!

The following environment variables are available:
```
RUST_SERVER_STARTUP_ARGUMENTS (DEFAULT: "-batchmode -load -logfile /dev/stdout +server.secure 1")
RUST_SERVER_IDENTITY (DEFAULT: "docker" - Mainly used for the name of the save directory)
RUST_SERVER_SEED (DEFAULT: "12345" - The server map seed, must be an integer)
RUST_SERVER_NAME (DEFAULT: "Rust Server [DOCKER]" - The publicly visible server name)
RUST_SERVER_DESCRIPTION (DEFAULT: "This is a Rust server running inside a Docker container!" - The publicly visible server description)
RUST_SERVER_URL (DEFAULT: "https://hub.docker.com/r/didstopia/rust-server/" - The publicly visible server website)
RUST_SERVER_BANNER_URL (DEFAULT: "" - The publicly visible server banner image URL)
RUST_RCON_WEB (DEFAULT "1" - Set to 1 or 0 to enable or disable the web-based RCON server)
RUST_RCON_PORT (DEFAULT: "28016" - RCON server port)
RUST_RCON_PASSWORD (DEFAULT: "docker" - RCON server password, please change this!)
RUST_BRANCH (DEFAULT: Not set - Sets the branch argument to use, eg. set to "-beta prerelease" for the prerelease branch)
RUST_UPDATE_CHECKING (DEFAULT: "0" - Set to 1 to enable fully automatic update checking, notifying players and restarting to install updates)
RUST_UPDATE_BRANCH (DEFAULT: "public" - Set to match the branch that you want to use for updating, ie. "prerelease" or "public", but do not specify arguments like "-beta")
RUST_START_MODE (DEFAULT: 0 - Determines if the server should update and then start (0), only update (1) or only start (2))
```

If you need help, have questions or bug submissions, feel free to contact me **@Dids** on Twitter, and on the *Rust Server Owners* Slack community.
