---
title: Android Activity Lifecycle
description: Details of Android Activity life cycle, Backstack
date: 2021-01-12
layout: layouts/post.njk
tags:
 - Software development
---

When an activity is first launched ,its created and then started and then resumed.Now the activity is active and the user can interact with it but as soon as the user moves to a different activity or a different application,then this activity moves into a paused state and then to a stop state and it it is close out,then it becomes destroyed.If the user comes back to this activity then it gets started and we move back into the start state and now the user can interact with it once again.This is just a simplified activity diagram and explanation to let you understand whats going on under .Now lets dive into the bigger picture.

Each activity state is associate with some states and an android system is responsible for transitioning your activity into each of these states where as we as a developer can’t control which state we are in

When our activity is first launched,the activity is moved into a create state using the onCreate method and then its moved into the start state using the onStart method and at this point,it becomes visible to the user.

Then its moved into the resume state via the onResume method and in this state,the activity is still visible to the user but the user can now start interacting with the activity .so here we can display animations,use sensors like location sensors or even use a camera on the device.So the activity can stay in this resume state for however long the user is looking at the screen rather for 1 hour or 10 hours.

Now as soon as the user switches to a different activity ,then activity is paused via the onPause method and from there it moves into a stop state via the onStop method.So at this point,the activity is no longer visible to the user. Now if the system determines that your activity is no longer needed,the system may destroy your activity via the onDestroy method in order to free up resources on the device and then our activity would enter the destroy state.But otherwise,the activity could stay in the stop state.

Then if the user decides to come back to the activity before it’s destroyed,then the activity is restarted via the onRestart method and it moves back into the start state via the onStart method.