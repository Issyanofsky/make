<div align="center">



# Advanced Scenario Design Patterns

</div>

Let's look at a few advanced scenario design patterns which you will sooner or later need when solving complex problems with Make.

Sample data used in the video:
https://hook.eu1.make.com/kjk2vjhwj8h3s8ff8ss4njgo5r0q14fj?data_requested=country_areas

__Try yourself:__

1. Follow Manuel in building the "duplicate check" logic. Create a Google Sheet yourself. Also, make sure to implement the __error handling__ mentioned in chapter 25 otherwise your scenario will occasionally fail :)
2. Try to get the __max, min, and avg__ values of the country areas by using the two methods (aggregators vs array functions).
3. Try passing any data between scenarios while using __Make app__ and __Scenario inputs__ in the "receiving scenario" (for this, you will need a Pro plan or above).

__Things to remember:__

1. __Preventing duplicates__
   1. It's likely that when you are creating new records in an app, you should check whether such a particular already exists in the target app so you don't create a duplicated record.
   2. If you find an existing value, then you should either stop your creation process OR you should update the existing value in the target app depending on your business logic.
   3. It's extremely important to define the right "key" for determining whether the record exists or not - it can be an ID, email, phone number, user ID, or any other value which would be unique in the target app. The key always depends on the app you are working with.
      
2. __Passing data between routes__ (sometimes known as Converger workaround)
   1. Set/Get Variables modules to allow you to pass data between routes but you need to make sure the order of your routes is set correctly.
  
3. __Calculation of "aggregated" values__ such as Min, Max, Avg, or concatenated strings.
   1. There can be multiple solutions to your problem
   2. If you know how to use inline array functions, you may save yourself from using aggregators but it depends on the specific problem you are trying to solve. Sometimes you may simply need to use aggregators.
      
4. __Passing data between scenarios__
   1. You can use HTTP POST requests and Custom Webhooks to send data between scenarios.
   2. However, you can also use __Make app>Make an API Call__ and __Scenario inputs__ to pass data in a __more secure authorized way__ between your scenarios!
      1. By default, the receiving scenario will be executed in parallel but you can switch it to sequential processing in the scenario's settings.

5. __Scenario inputs__ not only allow you to pass data between scenarios but they also simplify inputs for end users. For example, if you need to allow your coworkers to run certain scenarios on demand while having the coworkers provide many inputs, you can use Scenario inputs to allow them to __enter all the inputs just in one place__ instead of forcing them to go to various modules in the scenario.

   ![Array](pic/l4arrayadvanced.gif) 
   
<div align="center">


# [<-- BACK](l4arrayoperations.md) --- [NEXT -->](l4.md)
</div>
