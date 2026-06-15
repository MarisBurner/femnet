# FemNet Internet Service
A service for providing internet in RCC through both radio and modem.

## Routers
Routers are a paid service which implement a wired modem router network at a location of your choosing for your convenience. They provide a mock-modem system which imitates modem connections by opening connections at a wired modem channel and then sharing data through messages on the local network. This requires no setup by the user. Be advised to setup the router to listen to that channel and relay connections through the official FemNet router interface.

You can also import the official FemNet client API to send encrypted packets through the router using the FRTP protocol. (Note: Be sure that you trust the local network you are on because all of the encryption is router-side. Everybody in the local network can read your traffic. Though, they would need to be listening in and connected into the wired modem network.)

### Example of Client-Side FRTP Connection
```lua
local femnet = require("femnet.client")

res = femnet.get("RandomHostname",{page = "Content"}) -- This will yield the program until a response

if res.c == 200 then
 --Response success
 print(textutils.serialize(res))
else
 --Response failure
 print("FRTP connection failed: " .. textutils.serialize(res))
end
```

## About the systems
All of the actual relay/router scripts are not shared for safety reasons and are to be handled by Femcorp. Below is information about the systems which might or might not be applicable for your use-case, but will not further go in-depth on any mechanisms which could compromise user safety.

