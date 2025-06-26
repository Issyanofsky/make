<div align="center">



# Webhooks for Advanced

</div>

   
__Things to remember:__

eo
Enable fullscreen

This will introduce some of the lesser-known tips and tricks which you can use when working with webhooks in Make.

Sample data used:
https://hook.eu1.make.com/kjk2vjhwj8h3s8ff8ss4njgo5r0q14fj?data_requested=country_list&page=page_1

__Try yourself:__

1. Get the country list data via the HTTP app.
2. Follow Manuel in building a webpage returning the first page of our country list.
3. Would you ever have guessed you would be using Make to build web pages?
   
__Things to remember:__

1. Understand the differences between having your webhooks ON/OFF and having scenarios using webhooks ON/OFF! If you want to be sure that Make will not reject any incoming payloads, your webhook status must be ON and the webhook queue cannot be full!
2. Sometimes you may need to prevent Make from parsing the incoming webhook payloads - you can do that by going to webhook's advanced settings and setting the JSON pass-through option to YES
3. When using webhooks together with HTTP app, you can use Make to "forward" data to a different webhook.
   * Data can be forwarded as JSON payloads
   * Data can be forwarded in query strings
   * Data can be forwarded even as files - you will need to use Multipart/form-data as Body type
     
4. By taking the forwarding concept to the next level, you can use the schema below to introduce multiple real-time triggers into your workflow. Your scenario "listeners" would be representing "multiple triggers" and they would simply forward the incoming payloads to the "master scenario" with would process the main business logic:

![Multi Trigger](pic/l4webhooksmultitrigger.gif)

5. You can even use webhooks to build simple web pages with Make if you know HTML. Again, our goal is not to teach you HTML from scratch (there are free many courses for that) but we want you to be inspired by our simple use case. For this trick to work, your scenario should contain the following:
    1. Webhooks>Custom webhook is the first module
    2. Your main logic compiling dynamic parts of your HTML
    3. Webhooks>Webhook response as the last module presenting the compiled HTML back to the user

=> All you need to do at the end is to visit the webhook URL in your browser and the browser will turn your compiled HTML code into a webpage.


<div align="center">
  
# [<-- BACK](l4advancederrorhandling.md) --- [NEXT -->](l4.md)
</div>
