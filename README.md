# PC Ignition

One guarded switch that wakes my home PC from anywhere. Tap once to lift the
safety cover, tap again to fire.

Static page, no backend. The wake goes to an ntfy topic that an ESP8266 on the
home network listens on (it then sends the Wake-on-LAN packet). The button is
green when the PC is on and red when it is off, read live from the ESP's status topic.

**No credentials live in this repo.** On first open the page asks for the ntfy
wake link and status topic, and keeps them in the browser's localStorage only.
They can also be passed in the URL fragment (`#w=<topic>&m=<message>&s=<status>`),
which browsers never send to the server; the page strips it after reading.
