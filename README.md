This Node.JS code starts up a very simple microserver (using express) to provide an API for the homebridge-thermostat module by PCJzx.

https://github.com/PJCzx/homebridge-thermostat

It translates the API calls to command-line calls to heatmiser_json.pl from

https://github.com/thoukydides/heatmiser-wifi

The code is based on the 'fake.js' example from PJCzx. If it works for you, that's at least two of us!

I am using iOS 11.2.1 and homebridge.

Basic steps to get going:

1. Install homebridge and homebridge-thermostat
2. Confgure and test the above
3. Install and configure https://github.com/thoukydides/heatmiser-wifi
4. Make sure running 'heatmiser_json.pl' without arguments gives you valid results (hint - set up ~/.heatmiser to avoid needing to specify -h and -p)
5. Edit this heatmiser.pl to check the path of the heatmiser_json.pl
6. Start this microserver with 'node heatmiser.js'

Note that I am not a software developer, and had not touched any Node.JS code until trying this out. The code does very little error checking. It works for me :)

Setting / reading Relative Humidity is not implemented and returns dummy values as per fake.js.

Only 'Heat' and 'Off' modes are possible. If HomeKit sets to Cool or Auto, Heat will be selected. 'Off' sets frost mode.
