# VTS_from_Jmeter
Integrating VTS With JMeter

What is VTS?
This is a place where you can store your variables.

It is convenient to use it to exchange data between scripts or even between tests. For example, if you are testing a banking application, you can generate accounts in one test today (and put them in VTS during the test), and tomorrow, in another test, you can use these accounts for any actions.
Or you can put there unique variables that need to be processed, and then take them away, and you will be sure that each variable has been processed only once.

VTS is a free tool that was made for LoadRunner, but it has an HTTP API, which means it can be used with other load testing tools that do not have such a convenient data warehouse.
But these APIs are hidden under the DSL in LoadRunner, so for your convenience, I have added the main calls in this example JMX file. Just download and use

VTS is a table (or several tables) where you can add rows, take rows (with or without deletion). You can work both with the whole row and with individual columns.
VTS is good because it has a GUI that makes it easy to understand what is in the repository, and thus understand whether you are ready for the next test.
![VTS](./screenshot.png "VTS")


How to use it:
1) Download and Install VTS:
Latest version here free (registration required, available for business emails only)
https://marketplace.opentext.com/appdelivery/content/virtual-table-server   
or here (because official registration is terrible):  
[Windows](https://disk.yandex.ru/d/7NPAbQv1226sSA), [Linux](https://disk.yandex.ru/d/c8YJTcNYtgi68g)  

3) After installation, you need to enable API access:
Open "http://localhost:4000/", switch "Disable" to "Enable" in the "Access from Script" menu.

4) Add the columns and data (you can do this manually, or upload the CSV files, or from the command line or via the API)
Also, you can import "sample data" from the "Options" menu

5) Add the HTTP requests from my example to get the data from VTS and use them inside the JMeter

List of ALL VTS functions available here:  
https://admhelp.microfocus.com/vugen/en/24.1-24.3/help/function_reference/Content/FuncRef/VTS/etc/VTS_Parent_Functions.htm

But this is the list of DSL functions that are ONLY available in Virtual User Generator  
https://marketplace.opentext.com/appdelivery/content/virtual-user-generator-vugen

In fact, all these functions can be called via HTTP. I added the most used calls to my example.
To figure out how to call functions that I didn't added to my example, you need to install Virtual User Generator, add this function to Vugen script and run the script via the proxy server to see the HTTP API.
If you need a specific API call, you can ask me via Telegram (@GAneles) and I will help you.

To get any data from VTS, you need to do a handshake (one time per thread) first, and then call other requests to get and put data to/from VTS. 
