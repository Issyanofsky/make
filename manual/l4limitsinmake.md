<div align="center">



# Limits in Make
</div>

Let's focus on limits in Make. In the chapter, we'll discuss two important topics (max. scenario size and max. number of bundles returned by Search/List modules). Also, make sure to read through the other limits listed below.

__Things to remember:__

1. There is __no maximum number__ of modules that your scenario can have. What matters is the total size of your scenario.
2. The size of your scenario comes down to two things: __the number of your modules and the apps used within the scenario__. Some apps can have bigger modules than other apps.
3. The maximum size of a scenario can be 2 MBs. It's not the blueprint size that matters - it's the data that Make stores to its servers when you save your scenario. You can get the current size of the scenario in __two ways__:
  1. You can use __DevTool (Tools>Get Blueprint Size)__ which will give you an approximate size in bytes - you need to add around 100-200 kb on the top of the number to get close to the exact size.
  2. In Chrome on Windows, you can locate the __exact size__ by following these steps:
     * Press F12
     * Navigate to Network
     * Save your scenario
     * Locate the scenario ID which just appeared and click it
     * Go to the Headers tab
     * Find the "__content-length__" value = the number is the size of the scenario in bytes. If this number is getting close to 2,000,000, you may need to make your scenario smaller soon.
  
4. If you are trying to search or list potentially a LOT of bundles in one module, __make sure__ the module is actually returning all results which you would expect because __various limits can apply__ - especially in the case of apps based on paginated APIs. There are 3 common patterns that can occur:
   1. The app is not working with paginated results => the main limit here will be the general timeout limit on HTTP calls (__40 seconds__) regardless of the number of returned results by the API.
   2. The app is working with paginated results and the API does not have any limits - here you will get __max. 3200 results (=bundles)__ returned by the module. In very rare instances, this 3200 bundle limit can be set to a higher number by the Make team.
   3. The app is working with paginated results and the API does have limits - even though Make would be able to get up to 3200 results, the API can return e.g. only 1000 results and so the module will return only 1000 results.
   
Now, let's look at other limits:

1. Maximum number of active scenarios in a paying organization - unlimited
2. Maximum file size processed by a scenario - depends on the plan. Refer to our pricing page below.
3. Maximum scenario execution time in a paying organization - 40 minutes
4. Maximum members in an organization - unlimited
5. Minimum interval between scheduled scenarios in a paying organization - 1 minute
6. Maximum number of Data Stores in an organization - 1000
7. Minimum size of a Data Store - 1 MB
8. Data transfer - each 10,000 purchased operations adds 0.5 GB of data transfer allowance to your organization
9. Minimum sleep time in Tools>Sleep - 1 second
10. Maximum sleep time in Tools>Sleep - 5 minutes (though you can add multiple Sleep modules after each other to "buy more time")
11. Minimum wait time of Break module - 1 minute
12. Execution log storage duration - depends on the plan. Refer to our pricing page below.
13. Detailed webhook log storage duration - 3 days on standard Core, Pro, and Teams plan. Enterprise plan can be customized. To see detailed webhook logs, find your webhook URL in the main Webhooks menu, click it > Logs > click Detail of a payload > examine the raw detailed webhook payload.
14. Background limit on API calls - 40 seconds. In very rare instances, this limit can be increased by up to 5 minutes by the Make team.
15. Maximum runtime for custom IML functions - 10 seconds

__Extra resources:__

1. [Pricing page on Make.com](https://www.make.com/en/pricing)
2. [Pricing parameters and usage allowance in Help Center](https://www.make.com/en/help/general/pricing-parameters)
3. [Limits for modules returning paginated results in Make's documentation for app building](https://docs.integromat.com/apps/app-blocks/api/pagination#limits)
4. [Custom IML functions in Make's API documentation](Custom IML functions in Make's API documentation)

    ![Example 8](pic/l4commonmistakeex8.gif)


<div align="center">


# [<-- BACK](l4commonmistakes2.md) --- [NEXT -->](l4.md)
</div>

