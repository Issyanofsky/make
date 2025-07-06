<div align="center">



# Text Parser & Regex

</div>

This chaper will show you how to use regular expressions (aka "regex") in Make's Text Parser app. Please understand, that our goal is not to teach you regex from scratch but we rather want you to get inspired. You would need to go through a standalone course to learn regex alone. 

Sample data is here: 
https://hook.eu1.make.com/mvoybmpjdjj4qbillvv6aasorypv811c

__Try yourself:__

1. Get the sample data with our HTTP app.
2. Work with the __json_description__ variable inside the Text Parser app.
3. Follow Manuel in determining whether the text starts with/ends with/contains specific strings.
4. Then try to also extract the text before/behind the ".".
5. And finally, you can test replacing the first word of the first sentence ("This") with something else.
6. __PRO TIP__: Did you know the Text Parser app is not just about regex?
   1. You can e.g. use the __Get content from HTML table__ module to return an array of rows and columns from an HTML table.
   2. You can also use the __Match elements__ module to extract the following items from text strings without writing any regex:
      1. Emails
      2. HTML tags
      3. HTML addresses
      4. Phone numbers
      5. IP addresses
      6. Emojis
      7. ...and even key:value pairs
         
   3. Try these 2 modules on your own - they can save a lot of time in the future :)

__Things to remember:__

1. Regex inside Text Parser app is powerful for:
   1. Validations
   2. Extractions
   3. Text manipulations
      
2. __Regular expressions = regex = regexp__ all mean the same thing.
3. While our example is showing very basic use regex cases, your regexes can get significantly more complex!
4. Regex is not specific to Make - it's a general concept that can be found in many APIs for different purposes.
5. We strongly recommend you take at least a basic Regex course online - it's a worthy investment.
6. You may wonder are the differences between __Match pattern__ vs __Match pattern (Advanced) modules__ so let us address the question right away:  the advanced module also lets you __map__ your regex.
7. Make is using __ECMAScript__ flavor of regex.


__Chacking the Regexp__ 

You can check the expressions in this site (Note that Make is using __ECMAScript__ flavor of regex)

https://regex101.com/

## Example

   ![Scenario](pic/l4textparserall.gif)     
   
__HTTP (Make a request)__

this module retrive the data

   ![HTTP (Make a request)](pic/l4textparserhttp.gif)    

__Tools Module (Set variables)__

Set the JSON description to input the sentance in order to modify it afterwards. this way we can update the sentence here without changing the rst of the modules.

   ![Tools Module (Set variables)](pic/l4textparsersetvar.gif)    

After setting the routers (see diagram of scenario)

we set the test:
### Finding match in a String

__1. String start with "This" or "That"__

Using Match pattern module to check if the script start with "This" or "That".

   ![String start with "This" or "That"](pic/l4textparsermatch1.gif)    

For using the result we add a Tools (Set variable) with a filter that only let pass if the result exsist ( do the same to the next moduls in order to use the results).

 ![Filter](pic/l4textparserfilter1.gif)    

 ![Set Variable](pic/l4textparservar1.gif)  
 
__2. String ends with "Enjoy" or "Enjoy!"__

Using Match pattern module to check if the script ends with "Enjoy" or "Enjoy!".

   ![String ends with "Enjoy" or "Enjoy!](pic/l4textparsermatch2.gif)  

__3. Substring "for" in the middle of the sentance__

Using Match pattern module to check if the word "for" exists in the middle of the sentance.

   ![Substring "for" in the middle of the sentance](pic/l4textparsermatch3.gif)  

### you can use router and filter in order to set condition for pattern match or not

   ![condition for pattern match or not](pic/l4textparservar2.gif) 
   
   ![Filter if exist](pic/l4textparserfilter2.gif) 

   ![Filter if NOT exist](pic/l4textparserfilter3.gif) 

__4. Substring "for" in the middle of the sentance__

Using Match pattern module to check if the letter "y" exist inside the text and __how many times it exsist__ (we turn the "Global match" to yes. that let it find in all the senence not only the first match)

   ![Substring "for" in the middle of the sentance](pic/l4textparsermatch4.gif)  

filter to see if the result is greater then "0" (there are result - "for" exsist in the String)

   ![Substring "for" in the middle of the sentance](pic/l4textparsermatch4.gif)  
   
__To count the number of output matches__

we add a Numeric aggragator to count the boudles created (how many times "y" exsist)

   ![count the boudles created](pic/l4textparservar3.gif)  

Filtering if there are result

   ![count the boudles created](pic/l4textparservar4.gif)  

### Extracting text from the String


__1. Extract all chars Before the dot (".")__

This will extract the all letters __before__ the dot (".")

   ![Extract all chars before the dot (".")](pic/l4textparserextract1.gif)  


__2. Extract all chars After the dot (".")__

This will extract the all letters __After__ the dot (".")

   ![Extract all chars After the dot (".")](pic/l4textparserextract2.gif)  

__3. Extract all chars After the dot (".") and before the "!"__

This will extract the all letters __After__ the dot (".") and befor the "!"

   ![Extract all chars After the dot (".") and befor the "!"](pic/l4textparserextract3.gif)     

 ### Replacing charecters

We can use the Replace module to replace the matches (it will replace the all string to the new one because we had on the serch pattern the "*" (indicate all) to only replace the word "This" or "That" and leave the rest of the string we have to remove the "*" from the pattern).

   ![Replacing charecters](pic/l4textparserreplace1.gif)  

   ![Replacing charecters](pic/l4textparserreplace2.gif)  
   
   ![Replacing charecters](pic/l4textparserreplace.gif)  

   
<div align="center">


# [<-- BACK](l4scenariodesign.md) --- [NEXT -->](l4makedevtool.md)
</div>
