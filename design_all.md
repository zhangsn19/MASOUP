# Design of the Techniques in the Evaluation Study

We detailed the designs and the functions of all techniques in the evaluation study. 

## Proactive Setting

For the proactive setting, users have control on both the memories emerging on the side panel, and the memory management panel in the settings page. 

For the memories emerging on the side panel, users could view the visualization, that contained the information category, the confidence, and the background color. The background color's opacity represents the confidence, and the background color (i.e., from red to blue) represents the sensitivity (i.e., with red being the most sensitive and blue the least sensitive). The private memories were ranked in a descending order according to the confidence.

For the memory management panel in the settings page, users should click the setting in the left bottom corner to open, which mimicks ChatGPT's UI and interaction flow. The settings are all mimicking the interactions of ChatGPT, where users can (1) prioritize specific memory to use that memory first in subsequent chats, (2) delete specific memory, (3) reorder the memory according to the modification time, (4) view modification histories of the memories, (5) delete all memory, (6) see the contributing chats of the memory. 

Specifically, to achieve (4), we locally maintained historical versions of specific memories and log the changes of the memories. To achieve (6), when adding a memory, and further modifying a memory, we tracked the changes and the source chats.

## ChatGPT Setting

Similar to the proactive setting, the ChatGPT setting enables the users to see the memory management panel. Besides, when adding or updating a memory, the chat panel would visualize a notification. The memory management panel for the ChatGPT setting is identical to the proactive setting. 

When the user hovers on the chat panel, the notification would expand to a tooltip showing users the added memories, and the users could click on the notification to view the memory management panel.

## Cluster Setting 

In the cluster setting, we are inspired by Memolet when implementing the interaction. Users could expand the side panel to use the cluster feature. The clustered memories would automatically be used in subsequent chats. Users could choose different recluster granularity through dragging the slider. They could load historical clusters and reuse these versions. They could select two or more memory cluster (i.e., memolet) to group them, or delete specific memory. 

## Drag Setting

In the drag setting, we are inspired by Memory Sandbox when implementing the interaction. Users could tune the chat invisible, edit the chat, or delete the chat. They could drag the chat to other dialogues or within that dialogue. The chat could be dragged to any place, either before the first message, between messages, or after the last message. They could also click the summarize button to summarize chats.

## Overall

Overall, besides the four settings, the historical chats supported editing and saving, which mimicked commercial systems (e.g., ChatGPT). Users could click on the chats to edit the input, and press enter, or save to re-initiate output.
