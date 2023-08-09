# VTS_from_Jmeter
Integrating VTS With JMeter

How to use it:
1) Download and Install VTS:
Latest version here (free, registratation required)
https://www.microfocus.com/marketplace/appdelivery/content/virtual-table-server
or here:
https://disk.yandex.ru/d/7NPAbQv1226sSA

2) After installation, you need to enable API access:
open "http://localhost:4000/", switch "Disable" to "Enable" in the "Access from Script" menu.

3) Add the columns and data (you can do this manually, or upload the CSV files or from command line or via the API)

4) Add the http requests from my example to get the data from VTS and use them inside the Jmeter

List of the ALL VTS functions available here:
https://admhelp.microfocus.com/vugen/en/2023-2023-r1/help/function_reference/Content/FuncRef/VTS/etc/VTS_Parent_Functions.htm

But this is the list of DSL-functions that are ONLY available in Virtual User Generator 
(https://www.microfocus.com/marketplace/appdelivery/content/virtual-user-generator-vugen).

In fact, all these functions can be called via HTTP. I added most used calls to my example.
To figure out how to call functions that I didn't added to my example, you need to install Virtual User Generator, add this function to Vugen script and run the script via the proxy server to see the HTTP API.

To get any data from VTS at first you need to do handshake (one time per thread) and after that call other requests to get and put any data to/from VTS. 
