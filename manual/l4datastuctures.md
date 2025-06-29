<div align="center">



# Data Structures

</div>

eo
Enable fullscreen

We'll explain why you should care about Data Structures.

Sample country areas data is here: 
https://hook.eu1.make.com/kjk2vjhwj8h3s8ff8ss4njgo5r0q14fj?data_requested=country_areas

__Try yourself:__

1. Get the country areas with our HTTP app.
2. Aggregate the results to a CSV (make sure to use the "advanced module") while using a data structure.
3. Send an email with the CSV attachment to yourself.
   
__Things to remember:__

1. __Data Structures__ are a very important part of Make. They serve 3 main purposes:
   1. They allow you to specify the structure (or format) of data that is flowing through your Make scenarios. Depending on the use case, DaStr can be used to correctly __parse incoming data or to correctly compile output data__ in your modules.
   2. Within Webhooks>Custom Webhook module you can even use them as a __form of validation!__
   3. They describe the structure of __data stored in Data Stores__. A Data Structure is basically equivalent to a table schema in the standard database world.

2. You can re-use Data Structures across multiple modules and scenarios within Make - essentially setting a __single source of truth__ about the structure of certain chunks of data which you frequently work with.
3. __Most__ of the modules in Make __won't require__ you to use Data Structures. Some of the modules require you to use Data Structures (for example CSV>Create CSV [advanced]), and some of the modules make Data Structures only __optional__ (for example JSON>Parse JSON).
4. Existing Data Structures can be edited. Make sure you know what you are doing - if you remove or rename keys from an existing Data Structure that is already used in active scenarios, such change __may break the scenarios__ using that particular Data Structure.
5. Existing Data Structures can be also __cloned__.
6. If you have a sample JSON with real data, you can __generate your Data Structure automatically__ thanks to Make's "Generate" feature during Data Structure's setup.
7. The most commonly used apps and modules involving Data Structures:
   1. Data Stores app
   2. JSON>Aggregate to JSON
   3. JSON>Parse JSON
   4. JSON>Create JSON
   5. CSV>Create CSV (advanced)
   6. XML>Create XML
   7. XML>Parse XML
   8. Webhooks>Custom Webhook
   


![Filter](pic/l4repeatertotackleex32.gif)

<div align="center">
  
# [<-- BACK](l4repeatertotackle.md) --- [NEXT -->](l4.md)
</div>

