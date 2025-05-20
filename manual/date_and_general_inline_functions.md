
<div align="center">

# Date and General Inline Functions
</div>

1. You can "chain" or "nest" functions together. You are not limited to using just one function for an item. For example: addMonths(addSeconds({{now}};2);13).
2. Beware of all possible date/time tokens which can be used for date/time formatting - full list on the link below.
3. Please check advanced use cases of date/time functions here. The article covers:
   1. How to calculate days between dates - extremely useful!
   2. How to calculate the nth day of the week in a month.
   3. How to transform seconds into hours and minutes.
      
4. General functions such as if(...), ifempty(...), switch(...) allow you to build conditional logic within your mapping. 

![Inline date functions](pic/inline_date_functions.gif)

__under Date Functions:__

   __VARIABLES__
   * __now__ - output the current date is now.
   * __timestamp__ - a uniqe code (number) representing the time (since 1/1/1970 GMT)

   __FUNCTIONS__
   * __add__ (addSeconds, addYears, addMonths....etc) - add months to the calculation (ex. addMonths (now ; 2) - will add 2 months from today)
   * __set__ (serSeconds, setMinuts, setYear...etc) - set the date to a specific date (ex. set day to monday (2) - setDay(now;2) - will retrive the 2 day of the week of the now date value).
   * __parseDate__ - will take a date and try to understand it (ex. parseDate(date; format; [timezone] (optional)) - will try to convert a variable into a date in the format set).
   * __formatDate__ - format the date in a specific format you wish (ex. formatDate(parseDate(2022 15---2; YYY DD---M); Do MMM YY -  will return 15th Feb 22).

<div align="center">

# [<-- BACK](math_and_string_functions.md) --- [NEXT -->](date_and_general_inline_functions.md)
</div>
