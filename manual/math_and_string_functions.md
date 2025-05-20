
<div align="center">

# Math and String functions
</div>



1. Inline functions allow you to transform inputs into different outputs in a very efficient manner.
2. Inline functions used within a module don't cost any extra operations.
3. Inline functions on Make work similarly to functions in Microsoft Excel or Google Sheets.
4. It's not important to memorize all the inline functions but it's important to know where to find all the available inline functions on Make.
5. Please note that when summing decimal numbers such as 16.22+9.2, the result presented in Make will be 25.419999999999998 and not exactly 25.42. The solution is to round the number e.g. to 2 decimal points with our __round()__ function. __This is not a Make error__. It's related to how computers store and work with floats (=numbers with decimal points). If you are interested in this subject, read this article for more information.


### usfull variables:

__Under text:__

  * __"trim"__ - remove the spaces in a string.
  * __length"__ - count the number of charecters in a string.
  * __"replace"__ - replace text with some other text.
  * __"substring"__ - grabing some text from a larger text.
  * __"indexOf"__ - find a charecter in a text string.
  * __"toString"__ - convert a value into a string.
  * __"stripHTML"__ - strip the HTML format and return just the content.
  * __"contains"__ - varifies if the array contain value (ex. conains( is there a 1 or 2 in here? ; 2) - if there is 2 it return true).
  * __"split"__ - devide text base of some seperator (ex. split (issy yanofsky; space) - will seperate issy from yanofsky in to 2 variables) - it will put it in an array. to avoid this you can use the "get" function and it will pull it into a variable (not a lit array).
    
  * 
