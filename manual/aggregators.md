<div align="center">

# Aggregators 
</div>


1. The Array Aggregator is not the only aggregator module you can use in Make. There are other lesser-known apps that also allow you to run aggregations (CSV, JSON, Archive).
2. The Numeric Aggregator takes numeric values, performs an aggregation function (SUM, AVG, COUNT, MAX, MIN), and returns the result in one bundle.
3. The Text Aggregator merges values from the selected fields of received bundles into a single text.
4. The Table Aggregator merges values from the selected fields of received bundles into a single bundle using a specified column and row separator (which allows you to create a table).
5. The Array Aggregator merges several bundles into one single bundle as items in an array.
6. Source module - the module from which the bundle aggregation will start.
7. Aggregators allow you to create one output bundle from multiple input bundles but it may not always be the case. If you use the "GROUP BY" option, it's still possible the aggregator will produce more than one output bundle.
8. Target structure type - structure into which the output data will be aggregated.

![Aggregators](pic/aggregators.gif)

__The 3 main Aggregatots:__

  * __Array Aggregator__
    The Array Aggregator merges several bundles into one single bundle as items in an array.
    
![Array Aggregator](pic/arryaggragator.gif)
    
  * __Text aggregator__

![Text aggregator](pic/textaggregator.gif)
    
  * __Numeric aggragator:__
    The Numeric Aggregator takes numeric values, performs an aggregation function (SUM, AVG, COUNT, MAX, MIN), and returns the result in one bundle.

![Numeric aggragator](pic/numericaggregator.gif)



## Other Aggragators 

There are other lesser-known apps that also allow you to run aggregations (CSV, JSON, Archive). here some examples;

  * __CSV__
 
    allow to create or pass csv.

![CSV](pic/csvaggragator.gif)
    

  * __JSON__
 
    pass boundels into one json file
   

![JSON](pic/jsonaggrigator.gif)

## Source module

The module from which the bundle aggregation will start.

![Source module](pic/aggragationbundle.gif)

### Grupping (GroupBy)

In any aggrigator (in his settings) there is a groupBy field. where we can chose from our income values. it will group the list into bundles by the value we set (in the groupBy field).

![Grupping (GroupBy)](pic/aggregatorgrupby.gif)


### Data structure (in aggregators)

In the module (aggragators) we have a "Target structure Type" field (by default it set to Custom).

auto-structure can ve set sometimes (if the module allow). in this case the array will arrange the data in the structure needed by the pulling moudle.

![data structure](pic/aggregatorsdatastructure.gif)

in order to do that:

         1. first create the aggegator 

![Create the aggragation first](pic/aggragatorstep1.gif)


         2. create the module till the point of polling the data and link it in his setting to the array

![link the module to the Aggregator](pic/aggragatorstep2.gif)


         3. go back to the Aggregator and set it "Target structure Type" to the moudle to set the correct data structure
         
![link the module to the Aggregator](pic/aggragatorstep3.gif)

__note__ not every moudle where you add multiple Items has this option. if it has a mapping switch in his sttings it probebly has.

<div align="center">

# [<-- BACK](plans_and_operations.md) --- [NEXT -->](aiassistant.md)
</div>
