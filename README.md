# Local TV Extras Agent

This agent detects local trailer and extra videos in a TV Show directory and adds them to Plex. It can contribute to the default Personal Media Shows, TheTVDB and The Movie Database TV Agents as well as the HAMA TV Agent.

## Settings

### How extras are organised on the server

Although the Plex Media Server supports adding, and serving, extras at all levels in a TV Show – episode, season and show – not all of the Plex clients do. Therefore, by default the agent will add any extras that are found to the TV Show level only.

However, if you have a client that supports extras at the episode or season level, then you can enable the setting **Assign Extras to Episodes, Seasons or Shows based on folder structure**.

### TV Show folder structure

In order to associate extras only with the show that they belong to, and also to add then at the correct level. The agent needs to have some idea of the folder structure used to organise your files.

Based on the Plex requirements, the agent will classify folders named "Season" or "Specials" as season folders. If you use any other names ("Series", for example), then you may add them as a comma separated list in the **Alternative names for season folders, comma separated** setting.

## Extra File Naming and Folder Structure

File naming is similar to the naming for [Local Movie Trailers and Extras](https://support.plex.tv/articles/200220677-local-media-assets-movies/?_ga=2.40982114.1159795442.1544650582-1727179431.1482687957) using the Plex agents, but has some specific requirements to help organise the files.

### Inline Show Extras

Inline show extras should be added alongside any season folders in the Show directory. They will be detected if the end of the filename includes specific text, as follows:

* `TV Shows/TVShowName/Descriptive Name-Extra_Type.ext`

Where `-Extra_Type` is one of:

* -behindthescenes
* -deleted
* -featurette
* -interview
* -scene
* -short
* -trailer
* -other
* -extra

### Show Extras Organised in Subdirectories

Show extras may also be organised in subdirectories in the Show directory. In this case, the entire filename is the descriptive name, and the folders must be specifically named:

* `TV Shows/TVShowName/Extra_Directory_Type/Descriptive_name.ext`

Where `-Extra_Type` is one of:

* `Behind The Scenes`
* `Deleted Scenes`
* `Featurettes`
* `Interviews`
* `Scenes`
* `Shorts`
* `Trailers`
* `Other`
* `Extra`

### Season Extras

If you have extras that belong to a single season, then you can organise them in the season folder rather than the show folder. In this case, they should be named:

* `TV Shows/TVShowName/Season number/Descriptive Name-Extra_Type.ext`

Or 

* `TV Shows/TVShowName/Season number/Extra_Directory_Type/Descriptive_name.ext`

If the **Assign Extras to Episodes, Seasons or Shows based on folder structure** setting is enabled, then these will be assigned to that season when scanned into Plex. Otherwise, they will be added at the show level.

### Episode Extras

There are three methods by which an extra can be named connecting it to an episode. The first two methods require the episode to be given its own subdirectory. This directory must be named identically to the file name of the episode, e.g:

* `TV Shows/TVShowName/Season number/TVShowName - S##E## - Episode Name/TVShowName - S##E## - Episode Name.ext`

Inline extras, or extras organised in subdirectories may then be added in the `TV Shows/TVShowName/Season number/TVShowName - S##E## - Episode Name/` directory.

&nbsp;

The third method is inline, and does not require a directory for each episode which has extras. The beginning of the extra's filename must be identical to the episode filename, and the descriptive name and extra type are then added at the end.

For an episode named:

* `TV Shows/TVShowName/Season number/TVShowName - S##E## - Episode Name.ext`

An extra should be named:

* `TV Shows/TVShowName/Season number/TVShowName - S##E## - Episode Name-Descriptive_name-Extra_Type.ext`

## Thumbnails

If you have an image that you would like to use as the thumbnail for your local extra video, then it will be detected if it is placed in the same directory as the extra, and with the same filename except for the extension (which, at the moment, should be jpg).