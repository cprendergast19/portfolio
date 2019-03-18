# Overview

This document is an instructional guide outlining how to add a new comic issue to the iOS application and host it.

## Adding a Comic Issue to the iOS Project

 1. Create a directory for the issue, using the title of the issue as the name of the directory.
 2. Within the new issue directory created, create a new directory named  `Contents`. Ensure the correct spelling as the code specifically searches for a directory named  `Contents`. It is case sensitive.
 3. Add the Image, Sound and Video assets to the  `Contents` directory.
 4. Create two JSON files, one for the iPad and one for the iPhone. Naming is as follows  `xxxxiphone.json`and  `xxxxipad.json`. These are case sensitive as the parser searches for files ending with  `ipad.json` and  `iphone.json`. Below is an example of a JSON comic file, followed by the API guide.
    	    
    		
    	 {
    	 "comics": {
    	    "comic": {
    			    "productId": "com.comic.issue2",
    			    "title": "Issue 2",
    			    "coverImg": "Comic-iPad-00.jpg",
    			    "themeTune": "Name of music file without extension",
    			    "description": "Issue 2",
    			    "price": 1.99,
    			    "thumbnail": "Comic-iPad-00.jpg",
    			    "pageSoundOnImg": "btn_audio.png",
    			    "pageSoundOffImg": "btn_audio.png",
    			    "popupImg": "btn_overlay.png",
    			    "movieImg": "btn_video.png",
    			    "pageCount": 1,
    			    "popupTypes": {
    				    "popupType":  [{"name": "Page Sound","code": "PS"},
    					    {"name": "URL","code": "UR"},
    					    {"name": "Sound Clip","code": "SC"},
    					    {"name": "Movie Clip","code": "MC"}]
    					    },
    					    "pages": {
    							"page": [{
    								"pageNumber": 0,
    								"img": {
    									"src": "Comic-iPad-00b.jpg",
    									"x": 0,
    									"y": 0
    							    },
    							    "popup": [{
    								    "type": "MC",
    								    "pX": 56.0,
    								    "pY": 90.0,
    								    "pWidth": 140.0,
    								    "pHeight": 140.0,
    								    "movieWidth": 320.0,
    								    "movieHeight": 190.0,
    								    "moviePX": 244.0,
    								    "moviePY": 210.0,
    								    "src": "introsoundclip.mp4",
    								    "btnSrc": "buttonImg-160-ipad.png"
    							    },
    							    {
    								    "type": "SC",
    								    "pX": 440.0,
    								    "pY": 350.0,
    								    "pWidth": 100.0,
    								    "pHeight": 100.0,
    								    "src": "Soundclip.wav",
    									"soundImgSrc": "Comic-PU-p04-iPad.png"
    							    },
    							    {
    								    "type": "UR",
    								    "pX": 226.0,
    								    "pY": 72.0,
    								    "pWidth": 100.0,
    								    "pHeight": 200.0,
    								    "src": "http://www.yoururlhere.com"
    							    }]
    					    }]
    				    }
    				}
    		    }
        }


### Comic API

| Element | Description | Type | Notes |
| ---- | ---- | ---- | ----|
| comic | comic object | object ||
| &nbsp; &nbsp; productId | Unique product identifier representing the issue in the app store | String | e.g. `com.comics.issue2` |
| &nbsp; &nbsp; title |  Title of the comic | String ||
| &nbsp; &nbsp; coverImg | JPEG file | String | requires extension e.g. `Comic-iPad-00.jpg` |
| &nbsp; &nbsp; themeTune | Music file | String | doesn’t require file extension in the name |
| &nbsp; &nbsp; description | Issue description | String ||
| &nbsp; &nbsp; price | Issue price | Number | Price to be sold in the app store |
| &nbsp; &nbsp; thumbnail | Image displayed in the overview of the app for individual issue | String | JPEG file |
| &nbsp; &nbsp; pageSoundOnImg | Image displayed on page sound on button | String | JPEG file |
| &nbsp; &nbsp; pageSoundOffImg | Image displayed on page sound off button | String | JPEG file |
| &nbsp; &nbsp; popupImg | Image displayed on generic popup button | String | JPEG file |
| &nbsp; &nbsp; movieImg | Image displayed on the movie popup button | String | JPEG file |
| &nbsp; &nbsp; pageCount | Number of pages | Number ||
| &nbsp; &nbsp; popupTypes | A list of current popup types and their descriptions | Array | e.g. `{"name": "Page Sound","code": "PS"}` |
| &nbsp; &nbsp; page | page object | object ||
| &nbsp; &nbsp; &nbsp; &nbsp; pageNumber | Page number | Number | Starting at 0 |
| &nbsp; &nbsp; &nbsp; &nbsp; img | The image for the page | String | Contains the image file and the XY co-ordinates, these should always be 0,0 e.g. `img : {"src": "Comic-iPad-00b.jpg","x": 0, "y": 0}` |
| &nbsp; &nbsp; &nbsp; &nbsp; popup | Object array of artifacts that appear on the screen | Array | These are optional, there are 4 types of popup currently, these are  **SC**(sound clip),  **MC** (movie clip)**,**  **UR** (URL) and  **PS** (Page Sound) |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; type | URLs, Audio Clips, Images, Movie Clips | String | There are 4 types of popup currently, these are  **SC**  (sound clip),  **MC** (movie clip)**,**  **UR** (URL) and  **PS** (Page Sound) e.g. `"popup": [{"type": "MC",` |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; pX | The X coordinate for the popup button | Number ||
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; pY | The Y coordinate for the popup button | Number ||
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; pWidth | The width of the popup button | Number ||
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; pHeight | The height of the popup button | Number ||
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; btnSrc | The image file for the popup button | String | JPEG file | 
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; src | The asset name | String | This can be either a URL, movie clip or sound clip e.g. `"src": "introsoundclip.mp4"` or `"src":  http://www.yoururlhere.com or "src": "Soundclip.wav"` |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; soundImgSource | Image for sound clip | String | JPEG file to be displayed with a  **SC** (sound clip) | 
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; movieWidth | Width of the movie popup | Number | Used with  **MC**(movie clip) |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; movieHeight | Height of the movie popup | Number | Used with  **MC**(movie clip) |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; moviePX | Movie X co-ordinate | Number |The X co-ordinate to display the movie pop up at, used with  **MC**  (movie clip) |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; moviePY | Movie Y co-ordinate | Number | The Y coordinate to display the movie pop up at, used with  **MC**  (movie clip) |

5. Validate the JSON files at  [http://jsonlint.com](http://jsonlint.com/).
6. Copy the  `Contents` directory and add it to the iOS project temporarily to enable testing. Build the project and ensure the issue appears in the app. Once this has been tested remove the  `Contents` directory from the project to prevent it being added to the live build.
7. Compress the `Contents` directory. Once compressed rename the zip file to reflect the name of the issue within the app. A separate zip file is required for th.e iPad and the iPhone as the assets are different.

## Upload Issues to the Parse Server

1. Follow these instructions  [https://parse.com/apps/quickstart#hosting/unix](https://parse.com/apps/quickstart#hosting/unix)  to install and configure parse.
2. Copy the issue zip files to the public directory in the parse directory structure `public/issues/xxxx/xxxx.zip`.
3. Add the new comic issue(s) to the `iphoneIssues.plist` or the  `issues.plist`(iPad). Each issue is separate for each device type. Some issues are iPad only.
4. If the issue is a new comic title, it also requires a category to be added to the  `issues.plist`and  `issues.plist`.
5. Execute the `parse deploy` command.

## Add Issues to the Parse Database

The issue has been created, it needs to be added to the parse database. Follow the steps below to complete this.

1. Sign in to parse website  `http://www.parse.com`  username `comicscreator` password `letmein!`
3. Select the `Comics` app
4. Select `Core`
5. Select  `issues`  table
6. Add an entry for the new issue

## Common Issues

1. To test the JSON, the issue must be listed in the `issues/iphoneIssues.plist`. To test without making it live, test using a product id and title of an existing app on the server. Remember to replace the product id and title before zipping it up and submitting to the app store.
2. URLs in JSON require  `http://` prefix.
3. The `Contents`  directory name is case sensitive.
4. Issue titles must be identical in the JSON file and `issues.plist/iphoneIssues.plist`  files.
