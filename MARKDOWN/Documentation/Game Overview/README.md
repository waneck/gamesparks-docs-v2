---
nav_sort: 4
src: /Documentation/Game Overview/README.md
---

# Game Overview

The Game Overview page is designed to help you perform your initial game set up and any continuing game management tasks throughout the life of your game - from here you can:

* Log out from the portal and manage your GameSparks account.
* Switch between dark and light UI themes.
* Quickly open another game you've created on the portal, add a game, or open the game Recycle Bin.
* Check daily log summaries for both the Preview and Live stages of your game.
* View and edit the top-level information and settings of your game.
* Create and manage versions of your game configurations as [Snapshots](#Snapshots).
* Publish Snapshots of your game to the live servers.
* Inspect access secrets for your game connection types.
* Perform [User Management](#User Management) and create Collaborators for your game and configure their security settings through Groups.
* Change the [Game Owner](#Changing the Game Owner).

![](img/GameOverview/7.png)

## Logging Out and Managing your GameSparks Account

You can use the drop-down *Account* menu at top-right:

![](img/GameOverview/17.png)

* *Game Owner* - The game-owner e-mail address is shown.
* *Feedback* - Click to report a problem or give us feedback on the portal.
* *Dark/Light Theme* - Click to change the UI theme.
* *Manage Account* - Click to manage your GameSparks account.
* *Change Password* - Click to change your GameSparks account password.
* *Log Out* - Click to log out of the platform.

### Posting an Avatar

If you want to post an avatar for your GameSparks account, go to https://en.gravatar.com/

## Using the Games Menu

You can use the drop-down *Games* menu at top-right:

![](img/GameOverview/18.png)

* *Open Game* - Select another game from your list of games and switch over to that game.
* *Add Game* - Click to add a new game.
* *Recycle Bin* - Click to open the game Recycle Bin. When you delete a game it is sent to the *Recycle Bin* but you can restore deleted games from here.

## Main Options

You can use two main options at the top-right of the page:
* ![](img/GameOverview/19.png) - Edit your game's details. See section [below](#Editing Top-Level Game Information).
* ![](img/GameOverview/20.png) - Delete your game and send it to the *Recycle Bin* - you can use the [Games](#Using the Games Menu) menu to access the Recycle Bin and restore games you've deleted.

<q>**Recycle Bin - Game Retrieval Grace Period?** Games you've deleted are held in the Recycle Bin for 10 days before being automatically removed. At this point they become *PERMANENTLY DELETED*  and can no longer be retrieved.</q> 

## Checking Game Log summaries

The *Notifications* panel contains daily log summaries for both the *Preview* and *Live* stages of your game:

![](img/GameOverview/21.png)

If you want to view the log summaries for all your games, click *View Logs*. The *Logs* page opens with the current game's log summary expanded. The daily log summary is shown but you can change the range of the log summary using a date range drop-down:

![](img/GameOverview/23.png)

To return to the current game's Overview page, click *Game Overview*:

![](img/GameOverview/22.png)


## Viewing and Copying Game API Key and Secrets

You can view and copy your game's *API Key* and *API Secret*:
* Your game's *API Key* is shown and you can *Copy* this when required:

![](img/GameOverview/11.png)

* Your game's *API Secret* is hidden when the page first opens, but you can *Show* the secret:

![](img/GameOverview/12.png)

  * And then *Copy* when required:

![](img/GameOverview/13.png)

## Checking Security Credentials

If you need to check the security Credentials for your game, you can click *All Credentials* to go directly to the *Credentials* page:

![](img/GameOverview/14.png)


## Editing Top-Level Game Information

When you click to *Edit* your game's top-level details, you'll see three tabs:
* [Game Details](#Editing Game Details)
* [Features & Integrations](#Selecting Features and Integrations)
* [Geographical Setup](#Configuring Geographical Setup)

### Editing Game Details

To edit your game's details, click ![](img/GameOverview/19.png). The page adjusts for editing the game and the *Game Details* tab is selected:

![](img/GameOverview/8.png)

* On the this tab, you can edit the following:
  * *Name* \- The name of your game, used to identify the game in the portal if you have several games.
  * *Description* \- A description of the game.
  * *Currencies* \- Configure the [Currencies and Signup Bonuses](#Configuring Game Currencies) for your game.
  * *Game Settings* \- Set an [End Player Session Timeout](#Setting End Player Session Timeout).


#### Configuring Game Currencies

Under *Currencies* you can configure:
* *Hiding/Showing Currencies* - If you clear the checkbox for a currency, it's hidden in the portal. Note that this capability doesn't *disable* the currency in your game but simply hides it across the portal interface - for example, you will not see the currency when you Create/Edit a Virtual Good.
* *Currency Signup Bonuses* \- The amount of each Currency to award a new player when a new account is created.
* *Currency Segmentation* - If you want to segment your *Currencies* at the game-level, click *Segment* at top-right:

![](img/GameOverview/15.png)

For more details, see [Segments](/Documentation/Configurator/Segments.md).


#### Setting End Player Session Timeout

Currently, player sessions are only timed if an [EndSessionRequest](/API Documentation/Request API/Analytics/EndSessionRequest.md) is sent when a player disconnects. If you don’t set things up so that an End Session Request is sent when a player disconnects, their session will not be properly timed. Therefore, your Analytics data will be distorted due to these unended sessions.

Under *Game Settings* you can select to automatically end a player session after a player disconnects from your game:
* Select the *Automatically end player sessions* check box and enter the period in minutes that you want to elapse before this happens:

![](img/GameOverview/28.png)

### Selecting Features and Integrations

To select the platform features and integrations you want to use for your game, select the *Features & Integrations* tab:

![](img/GameOverview/9.png)

* On the this tab, you can select check boxes for:
  * *Platform Features* - The GameSparks features you want to enable.
  * *Integrations* - The 3rd party providers you want to integrate your game with.


### Configuring Geographical Setup

To select which geographical regions you want to allow access to your game, click the *Geographical Setup* tab:

![](img/GameOverview/10.png)

* On the this tab, you can configure for the geographical distribution of your game:
  * *Primary Region* - Select the geographical region where your game will be published.
  * *Geo Restrictions* - Select by country the geographical regions that you want to allow access to your game. By default, all countries are selected under *Allow Access*. To deny access to users in a specific country, select the country to move it across to the *Deny Access* box. You can use the double arrows at the top of each box to move all in one box to the other.

## Snapshots

![](img/GameOverview/16.png)

Click *Create* to create a new Snapshot for the current configuration of your game.

You can use icon button options in the Snapshots panel:
  * ![](/img/icons/previewicon.png) - Preview this Snapshot.
  * ![](/img/icons/copyicon.png) - Copy this Snapshot to another game.
  * ![](/img/icons/deleteicon.png) - Delete this Snapshot.
  * ![](/img/icons/publishicon.png) - Publish this Snapshot to the live servers.
  * ![](/img/icons/reverticon.png) - Revert the portal to the version contained in the Snapshot.
  * ![](/img/icons/unpublishicon.png) - Unpublish this Snapshot from the live servers.

Click [here](/Documentation/Key Concepts/Snapshots.md) for more information about Snapshots, Versioning and Publishing.

## User Management

You can use the *User Management* panel to create *Groups* and *Collaborators* for your game:
* *Groups* - When you create a Group for your game, you define a Read/Write permissions set for Collaborators to control which parts of the portal users assigned to that Group will have. You can create multiple Groups and then assign others to become Collaborators on your game and assign them to one or more of these permissions Groups.
* *Collaborators* - Collaborators are people that can log in with their user credentials and view/edit your game - just what a Collaborator can see and do when logged into your game depends on the permissions you have given them by assigning them to one or more permissions Groups.

An in-depth tutorial explaining how to create and configure Groups and assign them to your game Collaborators can be found [here](/Tutorials/Capabilities/README.md).

## Changing the Game Owner

As the game owner, you can change the ownership of your game by selecting one of the game's Collaborator's as the new game owner:
* When you do this, the Collaborator acquires full ownership permissions for the game, regardless of the permissions they had under the Groups assigned to them as a game Collaborator.
* The Collaborator you give game ownership to remains as a Collaborator on the game.
* If you're the game owner and also a Collaborator on the game when you change the ownership, you'll remain logged into the game and assume the permissions assigned to you as a Collaborator.
* If you're the game owner but you're not a Collaborator on the game when you change the ownership:
  * You'll be switched to the another one of your games.
  * If you don't have any other games, you'll be taken to Step 1 of the *Add New Game* wizard.

Game Collaborators can also change the ownership of a game, but they must have the *Change Game Owner* permission under the Groups they've been assigned:
* If you're logged into a game as a Collaborator with *Change Game Owner* permission, you can change the game ownership to yourself:
  * You'll assume all game ownership permissions for the game and you will remain as a Collaborator on the game.

To change a game's owner:

*1.* Go to the *Game Overview* page and on the *User Management* panel, click *Change*:

![](img/GameOverview/24.png)
* The *Change* button will appear only if you have added at least one Collaborator to your game.
* In this example, we are logged in as the game owner and the game owner hasn't also been made a Collaborator on the game.

The *Change Owner* page opens.

*2.* Select the Collaborator you want to change game ownership to from the drop-down and click *Change Owner*

![](img/GameOverview/25.png)

A confirmation dialog appears warning you that the *Change Owner* action cannot be undone:

![](img/GameOverview/26.png)

*3.* If you want to continue, click *Change Owner*:
* In this example, because we logged in as the game owner at the outset we remain logged in as that user. Because that user no longer has access to the game - they were not listed as a Collaborator on the game - they are switched to another one of their games or, if that was their last game, they are taken to the *Add New Game* wizard.

*4.* Log in as the Collaborator that was given ownership of the game and open the game. In *User Management* on the *Game Overview* page, this user will now show as the game owner and remain as a Collaborator on the game:

![](img/GameOverview/27.png)
