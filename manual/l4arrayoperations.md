<div align="center">



# Advanced Operations with Arrays

</div>

It's inevitable that you will need to perform advanced transformations of arrays during your projects. In this chapter, we are going to show a few examples of such array challenges.

__Sample data is here:__

1. Full country list: https://hook.eu1.make.com/kjk2vjhwj8h3s8ff8ss4njgo5r0q14fj?data_requested=country_list
   1. Keep in mind this dataset is paginated - you need to get the full list of all 240 countries, not just the first page.
   2. The pagination works as follows:
      * If you don't include the __page=__ parameter in the URL, you will always get the first page.
      * If you include the __page=__ parameter in the URL, you will get the page you ask for.
      * There are 5 pages of the results so you will need to call the endpoint 5 times with these extra parameters in the URL: page=page_1 (only optional as per above), page=page_2, page=page_3, page=page_4, page=page_5. 

2. Portuguese-speaking countries: https://hook.eu1.make.com/kjk2vjhwj8h3s8ff8ss4njgo5r0q14fj?data_requested=portuguese_speaking_countries
3. Country areas: https://hook.eu1.make.com/kjk2vjhwj8h3s8ff8ss4njgo5r0q14fj?data_requested=country_areas (this endpoint will randomly __fail__ with 429 - make sure to implement error handling!)


__Try yourself:__

1. Get the full __country_list__ of 240 countries and then compare the set with __portuguese_speaking_countries__. Can you tell which country from __portuguese_speaking_countries__ is NOT in __country_list__?
2. Create a sorted text string based on the __country_list__ data which will tell you counts of countries where each language from country_list is spoken. The string needs to be sorted by language. You should get:
   1. English: 7
   2. Hindi: 1
   3. Portuguese: 2
   4. Spanish: 6

3. Create a text string based on the __country_list__ data where each row of the string will be Country: Language. You should get 16 rows from 15 countries (India has 2 languages assigned so that means 2 rows for India).
4. Get the __country_areas__ list and look up ISO codes from the __country_list__ and send the result of the matching via email to yourself. Also, use JSON>Aggregate to JSON module to create a JSON attachment containing the result of the matching for your email.
5. If you want to save time, you can follow Manuel's approach in using the static __country_list__ data via JSON>Parse JSON module, but make sure that in real projects you don't forget to switch from static data back to dynamic data.
   
__Things to remember:__

1. Mastering scenarios involving array transformations is an important skill to have when solving complex challenges in Make.
2. It will take a bit of practicing - so make sure to follow our examples if you are not yet confident with advanced array transformations and lookups. __You will need these concepts for the practical challenge which is coming at the end of the course__.
3. It's all about iterations, aggregations, and the right formulas - everything needs to be used at the __right time and in the right places__.
4. Knowing how to efficiently process arrays can __save__ you a lot of __operations__ and __reduce the run times__ of your scenarios.
   
   ![Transform to JSON](pic/l4arrayforadvarray2.gif) 
   
<div align="center">


# [<-- BACK](l4arrayforadvanced.md) --- [NEXT -->](l4.md)
</div>
