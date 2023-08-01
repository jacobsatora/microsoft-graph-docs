---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

mgc teams create --body '{\
    "template@odata.bind": "https://graph.microsoft.com/v1.0/teamsTemplates('standard')",\
    "visibility": "Private",\
    "displayName": "Sample Engineering Team",\
    "description": "This is a sample engineering team, used to showcase the range of properties supported by this API",\
    "channels": [\
        {\
            "displayName": "Announcements 📢",\
            "isFavoriteByDefault": true,\
            "description": "This is a sample announcements channel that is favorited by default. Use this channel to make important team, product, and service announcements."\
        },\
        {\
            "displayName": "Training 🏋️",\
            "isFavoriteByDefault": true,\
            "description": "This is a sample training channel, that is favorited by default, and contains an example of pinned website and YouTube tabs.",\
            "tabs": [\
                {\
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",\
                    "displayName": "A Pinned Website",\
                    "configuration": {\
                        "contentUrl": "https://learn.microsoft.com/microsoftteams/microsoft-teams"\
                    }\
                },\
                {\
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",\
                    "displayName": "A Pinned YouTube Video",\
                    "configuration": {\
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?videoId=X8krAMdGvCQ",\
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"\
                    }\
                }\
            ]\
        },\
        {\
            "displayName": "Planning 📅 ",\
            "description": "This is a sample of a channel that is not favorited by default, these channels will appear in the more channels overflow menu.",\
            "isFavoriteByDefault": false\
        },\
        {\
            "displayName": "Issues and Feedback 🐞",\
            "description": "This is a sample of a channel that is not favorited by default, these channels will appear in the more channels overflow menu."\
        }\
    ],\
    "memberSettings": {\
        "allowCreateUpdateChannels": true,\
        "allowDeleteChannels": true,\
        "allowAddRemoveApps": true,\
        "allowCreateUpdateRemoveTabs": true,\
        "allowCreateUpdateRemoveConnectors": true\
    },\
    "guestSettings": {\
        "allowCreateUpdateChannels": false,\
        "allowDeleteChannels": false\
    },\
    "funSettings": {\
        "allowGiphy": true,\
        "giphyContentRating": "Moderate",\
        "allowStickersAndMemes": true,\
        "allowCustomMemes": true\
    },\
    "messagingSettings": {\
        "allowUserEditMessages": true,\
        "allowUserDeleteMessages": true,\
        "allowOwnerDeleteMessages": true,\
        "allowTeamMentions": true,\
        "allowChannelMentions": true\
    },\
    "discoverySettings": {\
        "showInTeamsSearchAndSuggestions": true\
    },\
    "installedApps": [\
        {\
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"\
        },\
        {\
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"\
        }\
    ]\
}\
'
=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc teams create --'standard')" {'standard')"-id} --\
    "visibility": "Private" {\
    "visibility": "Private"-id} --\
    "displayName": "Sample Engineering Team" {\
    "displayName": "Sample Engineering Team"-id} --\
    "description": "This is a sample engineering team {\
    "description": "This is a sample engineering team-id} -- used to showcase the range of properties supported by this API" { used to showcase the range of properties supported by this API"-id} --\
    "channels": [\
        {\
            "displayName": "Announcements 📢" {\
    "channels": [\
        {\
            "displayName": "Announcements 📢"-id} --\
            "isFavoriteByDefault": true {\
            "isFavoriteByDefault": true-id} --\
            "description": "This is a sample announcements channel that is favorited by default. Use this channel to make important team {\
            "description": "This is a sample announcements channel that is favorited by default. Use this channel to make important team-id} -- product { product-id} -- and service announcements."\
        } { and service announcements."\
        }-id} --\
        {\
            "displayName": "Training 🏋️" {\
        {\
            "displayName": "Training 🏋️"-id} --\
            "isFavoriteByDefault": true {\
            "isFavoriteByDefault": true-id} --\
            "description": "This is a sample training channel {\
            "description": "This is a sample training channel-id} -- that is favorited by default { that is favorited by default-id} -- and contains an example of pinned website and YouTube tabs." { and contains an example of pinned website and YouTube tabs."-id} --\
            "tabs": [\
                {\
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps {\
            "tabs": [\
                {\
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps-id}  --body '{\
    "template@odata.bind": "https://graph.microsoft.com/v1.0/teamsTemplates-with-'standard')"-with-\
    "visibility": "Private"-with-\
    "displayName": "Sample Engineering Team"-with-\
    "description": "This is a sample engineering team-with- used to showcase the range of properties supported by this API"-with-\
    "channels": [\
        {\
            "displayName": "Announcements 📢"-with-\
            "isFavoriteByDefault": true-with-\
            "description": "This is a sample announcements channel that is favorited by default. Use this channel to make important team-with- product-with- and service announcements."\
        }-with-\
        {\
            "displayName": "Training 🏋️"-with-\
            "isFavoriteByDefault": true-with-\
            "description": "This is a sample training channel-with- that is favorited by default-with- and contains an example of pinned website and YouTube tabs."-with-\
            "tabs": [\
                {\
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

```