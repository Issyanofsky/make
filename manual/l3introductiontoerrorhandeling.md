<div align="center">

# Introduction to Error Handling


![RepeaIntroduction to error handlingter](pic/l3introductiontoerrorhandeling.gif)

</div>

__Things to remember:__

1. Your scenarios may generate random errors which will not be your fault. For example, it's possible that one of the modules in the scenario fails because the API of the particular app is not responding for a very short period of time.
2. You can solve these situations by using error-handling modules such as Ignore, Break, or Resume.
3. You can even create alternate routes with a series of steps to solve the error. Right-click a potentially failing module > Add error handler > Select any app on Make.
4. Error handlers are especially useful when you know certain errors will be repeatedly happening and when you already know how to handle these errors.


  * If an error occured the all scenario may stop working (turn off) (on a warning it allow more to occure before stoping (turn off) the scenario.)
  * __notification__ you can get notificatins both on errors and warning by setting them under Team --> Notifications --> set the roles to get the notification )
  * by checking to "Yes" for the "Allow storing of Incomplete Executions" you can insted of canceling out. youll get a warning and the scenario will continue processing all the bundles:

![Allow storing of Incomplete Executions](pic/l3introductiontoerrorhandelingallowstoring.gif)

Every scenario has it error handling list. under "INCOPMLETE EXECUTIONS" you can see all the detailes of the incomplete execution.

![INCOPMLETE EXECUTIONS](pic/l3introductiontoerrorhandelingincompleteexecutions.gif)

## Error handler

a route that will be trigger if an error occured.

![Error handler](pic/l3introductiontoerrorhandelingadderrorhandler.gif)

![Error handler](pic/l3introductiontoerrorhandelingerrorhandler.gif)

there are some build error handlers (if you dont use a moudle):

![Error handler](pic/l3introductiontoerrorhandelingadderrorhandlertypes.gif)

  * __Rollback__ - requier that all the modules will be __Asid__ (Atomic, Consitent, Isolated and Durable - can easyly undone without doing problems to the Data). in order to know it the opject is "ASID" there is a tag next to each module.
 * __Commit__ - requier that all the modules will be __Asid__ (Atomic, Consitent, Isolated and Durable - can easyly undone without doing problems to the Data). in order to know it the opject is "ASID" there is a tag next to each module.
   
![Asid](pic/l3introductiontoerrorhandelingasid.gif)
    
 
  * __Break__
    
    ![Break](pic/l3introductiontoerrorhandelingbreak.gif)
    
  * __Resume__
  * __Ignore__


<div align="center">


  
# [<-- BACK](l3built-inapps.md) --- [NEXT -->](.md)
</div>
