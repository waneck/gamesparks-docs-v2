---
nav_sort: 1
src: /Tutorials/Cloud Code and the Test Harness/Using Cloud Code.md
---

# How to Create and Use Cloud Code

In this tutorial, you can follow an example and learn how to create and work with Cloud Code:
* We'll use the Configurator to create an Event that will then trigger a simple piece of Cloud Code.
* The Event will contain three attributes - a String, a Number, and a JSON field.
* The Cloud Code (a piece of JavaScript) will manipulate these values and echo them back in the Event response.
* We'll then use the Test Harness to try out the Cloud Code script and the Event.

## Create an Event

*1.* Go to *Configurator > Events* and click to *Add* an Event. The *Add Event* page appears.

*2.* Enter the Event details - *Short Code*, *Name*, and *Description* - and click to *Save and Close*:

![](img/CreateCloud/18.png)

You are taken back to the *Events* page where the new Event is listed.

*3.* To edit the new Event, click the *Edit* ![](/img/icons/editicon.png) icon. The *Edit Event* page appears.

*4.* Next, on the *Attributes* panel click to *Add* an Event Attribute.

*5.* Enter the Event Attribute details:
* Enter a *Name* for the Attribute.
* The *Short Code* will be used as the key for the value that you post into the GameSparks platform from your game code.
* Set the *Data Type* to *String*.
* For *Default Aggregation Type* select *Used in Script*.

![](img/CreateCloud/19.png)

*6.* Click to *Save* the Attribute.

*7.* Repeat this step and create another two Attributes for this Event, one with *Number* for its *Data Type*, the other with *JSON* for its *Data Type*.

![](img/CreateCloud/20.png)

*8.* Click to *Save and Close* the editing changes you've made for the Event.

## Create a Cloud Code Script

In this section, we'll create a Cloud Code script linked to the Event that we've just created.

<q>**Cloud Code Editor Shortcuts?** For a list of the keyboard shortcuts you can use in the Cloud Code Editor, go [here](/Documentation/Configurator/Cloud Code.md).</q>

*9.* Go to *Configurator > Cloud Code*.

*10.* Select *Events* in the *Scripts* section.

*11.* Select the Event we've just created - *CC_EVT*. We'll now bind Cloud Code to it.

![](img/CreateCloud/21.png)

*12.* Copy and paste the following JavaScript code into the editor section.

```  
    var eventAttr1 = Spark.getData().CC_ATTR
    var eventAttr2 = Spark.getData().CC_ATTR_2
    var eventAttr3 = Spark.getData().CC_ATTR_3
    Spark.setScriptData("eventAttr1", eventAttr1.toUpperCase());
    Spark.setScriptData("eventAttr2", eventAttr2 * 10);
    eventAttr3.won = true
    Spark.setScriptData("eventAttr3", eventAttr3);

```

*13.* Click *Save* at the bottom left-hand corner of the editor. Your page should now look like this.

![](img/CreateCloud/22.png)

Let's review this Cloud Code script:
* The first three lines of the script use the *Spark.getData* function to access the attribute values of the incoming Event. Notice how these attributes match the values we entered for the 3 Event Attribute Short Codes in the previous section.
* The remaining lines use the *Spark.setScriptData* function to add three new fields to the response that is delivered to the calling client:
  * The first line takes the first Attribute and converts it to uppercase.
  * The second line multiplies the second Attribute value by 10.
  * The final two lines add a new property to an incoming JSON object and assign that to the response.

We're now ready to test the code via the Test Harness.

## Testing the Cloud Code Script and Event

In this section, we'll:
* Use the Test Harness to register a test player with the preview version of the game.
* Authorize this player.
* Post an Event that will trigger our Cloud Code script.
* We'll then see the JSON requests and responses containing the data inserted by the script.

### Register Test players

*1.* Go to *Test Harness > Authentication* and select [RegistrationRequest](/API Documentation/Request API/Authentication/RegistrationRequest.md).

*2.* Then change the *displayName*, *password*, and *userName* as shown here:

![](img/CreateCloud/23.png)

*3.* To send this JSON request to the GameSparks platform, click *Send Request*. In this example for *Player Ten*:

![](img/CreateCloud/24.png)

The *Inspector* shows the request (in green text) that was sent to the GameSparks platform via the WebSocket and shows the response (in blue text).

![](img/CreateCloud/25.png)

### Log Event

*4.* Go to *Test Harness > LogEvent* section and select the *Cloud Code Event* that we created above.

*5.* Set each of the Attribute values in the JSON request as below. Note that:
  * The key names are the Short Codes of the Event Attributes that we created at the start of the exercise.
  * Attribute data types:
    * The first must be a String.
    * The second must be a Number.
    * The third must be a JSON object.

![](img/CreateCloud/26.png)

*6.* Click the *Send Request* to send the request to the GameSparks platform:

![](img/CreateCloud/27.png)

The response is displayed in the *Inspector* in blue text:
* The scriptData property contains the fields that we added from within our Cloud Code script.
* The keys are *eventAttr1*, *eventAttr2*, and *eventAttr3*.

![](img/CreateCloud/28.png)


### Constructing a Script Message

Here's an example of how to construct a script message:

```
//Parameter is kept null if no custom script message is being used
var msg = Spark.message(null);
//Include player IDs of players you wish to receive message
msg.setPlayerIds([Spark.getPlayer().getPlayerId()]);
//Set the data object for the message
msg.setMessageData({"title":"I am testing title","body":"I am testing body"});
//Send message
msg.send();
```

To learn more about constructing messages and seeing an example use, please check out the [chat tutorial](/Tutorials/Social Features/Setting Up Chat Messages.md).
