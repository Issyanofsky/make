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


   ![Sceanrio Inputs](pic/l4scenariodesignex3get.gif)    


<div align="center">


# [<-- BACK](l4scenariodesign.md) --- [NEXT -->](l4.md)
</div>
