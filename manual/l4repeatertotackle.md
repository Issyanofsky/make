<div align="center">



# Repeater to Tackle Pagination Challenges

</div>

   



We'll look at how to tackle pagination in Make with Repeater after getting paginated results from the HTTP app.

Sample country list data is here: 
https://hook.eu1.make.com/kjk2vjhwj8h3s8ff8ss4njgo5r0q14fj?data_requested=country_list

__Try yourself:__
1. Get country lists with our HTTP app.
2. If you don't include &page=... in the query strings, you'll get the first page.
3. If you include &page=page_X in the query strings, you'll get the specific page (page_1, page_2, page_3, page_4, page_5)
4. Follow Manuel's solution to retrieve paginated results.
5. Are you able to tell how many countries are there on the list across all our pages in less than 15 minutes from now?

__Things to remember:__

1. Generally speaking, Make will automatically handle pagination for you in all public apps on Make.
2. When you work with custom APIs via the HTTP app, it's possible you will need to deal with paginated data yourself. In that case, you will need to use __Repeater__.
3. There are several common patterns of paginated API responses:
   1. The API will tell you __how many pages of results__ there are in total and you need to iterate through all the results based on different parameters.
   2. The API will provide you with a reference for the "next page" or "next result" but will __not tell you__ how many pages/results there are in total. In this case, you will need to arbitrarily set a high enough number (yet reasonable) of __repeats__ in __Repeater__ so you will always get all the results as presented in our video (we used 100 repeats).
   3. The API works with an __offset__ - you need to repeatedly ask for "ranges of results" - e.g. for 0-500 results, then for 501-1000, then for 1001-1500, and so on.
   4. The API will tell you whether there are "__more items__" of the results waiting for you on the next page (e.g. until the "has_more_items" parameter "becomes" false on the last page).
   5. The API will not tell you whether there are more results waiting on the next page at all - you just need to keep asking for the next pages __until you get an empty response__.
      
4. __You should always study the API's documentation first__ to understand how exactly the pagination works in the particular API so you don't miss any important nuances. E.g,
   1. Are there any limits on the number of provided results? Maybe just 1000 records?
   2. Do you need to include any query string parameters to get the first page of results?
   3. How is the "next page" token parameter identified?
   4. Does the API tell you how many pages of results are there in total?
      
5. If you need to aggregate bundles with Array Aggregator and __you don't see items available for aggregation__ within the module, you can build a JSON via Text Aggregator, then parse the text with JSON>Parse JSON module, and finally, you can use Array Aggregator to aggregate the results from the Parse JSON module.
   1. You just need to make sure you properly escape special characters such as " or" /  (example to escape ": replace(your_mapped_value_here;";\") function in case your mapped values contain them.
   2. Stay tuned for 2 more tricks to solve this problem in an upcoming chapters around arrays :)


## scenario - get all pages to a single Array

![Scenario)](pic/l4repeatertotacklescenario.gif)

__HTTP (make request) moudle__

firts module is the HTTP (make request) where we retreving the data.

you can see there are more pages then it shows on the results (there are 5 pages and we got only 1).

![HTTP (make request)](pic/l4repeatertotacklehttp.gif)

![HTTP (make request) - result](pic/l4repeatertotacklehttpresult.gif)


__Note:__ 

there are some cases you can get to the pages by using query string (adding to the http request line).


![Repeater Page](pic/l4repeatertotacklerepetaerpage.gif)

the result will be:

![Repeater Page 3](pic/l4repeatertotacklerepetaerpage3.gif)

__Repeater module__

in order to move between the pages we add a repeater. we set it to repeat for the total pages we recived.


![Repeater module](pic/l4repeatertotacklerepetaer.gif)

__* Array aggragator__

We can use an Array aggrarator to combine the pages together to one bundle and the __Repetaer__ as a source. the only problem is that __Make__ does'nt know the data structure, and therefore it does not contain the actual variables that you want to combine.

![ Array aggragator](pic/l4repeatertotacklehttparrayagg.gif)


A __Workaround__ is by using __Text Aggrigator__ and building a __JSON__ structure manualy.

__Iterator__

iterate the data. page by page. to extract the data in each page and pas it to the Text aggrigator

![Iterator](pic/l4repeatertotackleiterator.gif)

__Text aggregator__

combine all the data in a __JSON__ structure.
 
 __*Note__ we add a coma "," seperator because the JSON files has many rows and we divid them by that (coma ",").
 
![Text aggregator](pic/l4repeatertotackletextagg.gif)


__parse the output__

using Parse Jason module to parse theJSON file we just created.

__* Note__ we add the __square brackets__ ("[]") in order to pass it as an array.

![Parse Json](pic/l4repeatertotacklejson.gif)

__Array aggregator__

And lastly we parse the JSON into a array aggragetor in order to combine all into one array.

![Array aggregator](pic/l4repeatertotackleharrayagg.gif)

## Note


### passing with next page

in some cases where we cant implement the page (like in the former example) we mite use some advanced logic to solve the issue (run throw pages as in the example).

here is an example for workaround pages that need the next page command to move between the pages (not by number in the query string).

we gona use two variable tools to implify the correct query string  (placing one on each side of the "pulling" data module (HTTP make request).

__after__ Set Variable module (after the HTTP module).

here we set a variablefor the query string that will change accordenly to the page needed (note the "+1" that incriment the page number).

![After](pic/l4repeatertotackleafter.gif)

__before__ Get variable module (before the HTTP module).

this one set the query string (if it empty nothing added). we add the "page_next" variable we creating in the tool after the HTTP make request (there for we create it first (the after 

![Before](pic/l4repeatertotacklebefore.gif)

__set the HTTP__ 

adding to the HTTP request the varible for the query string.

![HTTP request](pic/l4repeatertotacklehttpa.gif)

__*__ the rest of the scenario remain the same

![Total scenario](pic/l4repeatertotackletotal.gif)


### passing without knowing the number of pages

there are cases we dont recive the date for the pages. so in order to go throw we :
 1. first we set the repeater to run multipletimes (much more then the pages we expect to get - like 100 for example). this is to see the responce we get on an empty page.

![Repeater](pic/l4repeatertotackleex30.gif)

2. we add an __if__ statment to the tool (Set variable module) that add to the "page_next" variable value acording (ifthe page exsist it will has to the query string else it will get "Stop" value).


![if statement](pic/l4repeatertotackleex31.gif)

 3. we set a filter (between the Get variable and the HTTPS module) that allow to pass only if the value of the "page_next" is not "Stop" ( allow to pass only pages that with data).

![Filter](pic/l4repeatertotackleex32.gif)

<div align="center">
  
# [<-- BACK](l4advancedwebhooks.md) --- [NEXT -->](l4datastuctures.md)
</div>
