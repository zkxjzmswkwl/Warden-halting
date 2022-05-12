# Warden exercise
Blizzard's anti-cheat, Warden, is fairly interesting. Being bound to userland, the team behind it has been forced to be a touch more creative than usual.

# Why this is interesting to me
Warden downloads and executes shell code at runtime. The functionality consists of two(ish) components.

1. General detection/monitoring
2. Heartbeat

If the heartbeat isn't sent, you're disconnect from the game. The natural reaction would be to cut the detection/monitoring while leaving the heartbeat intact, no?
Only the detection/monitoring component of this is responsible for populating the buffer of the heartbeat packets. Meaning if one isn't working as it should, the other will fail as well.
Resulting in disconnection. Any attempt at bypassing this check must be perfect, or it won't work at all. To me, this is very interesting, so I'd like to take a crack at implementing it myself.