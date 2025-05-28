<div align="center">

# Get+Map Functions to Perform Data Lookups
</div>

__Things to remember:__

* get(map(..)) combination of functions is Make's equivalent to Excel's or Google Sheet's VLOOKUP function.
* Remember that map(..) function outputs an array of all found matches and therefore you will likely need to use either get(...;1) or first(...) to get just the first matched value from the array. 


    Using __ONLY__ map function will result in a Array type
  
![map](pic/l3arraygetmapmap.gif)

    By adding __get__ you can convert the result to text type (for use in later moduls).
  
![get + map](pic/l3arraygetmapgetmap.gif)

<div align="center">
  
# [<-- BACK](l3arrayfunctions.md) --- [NEXT -->](l3iterator.md)
</div>
