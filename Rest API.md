# Upload a Sound File

Uploads a sound file to the current user’s profile.

## URL

    POST https://api.sounddate.com/profile/sound

## Headers

|  **Header Name** | **Description** | **Required** | **Values** |
|---|---|---|---|
| **Bearer** | Access token | Required | See Authorization Section |
| **Content-Type** |  Sound file format | Optional | audio.mpeg, audio/x-wav. Default is audio/mpeg. |
| **Accept** | Response format | Optional | application/xml, application/json. Default is application/json. |

## POST or PUT Body

The sound file.

**Note**: The sound file must be 5 minutes or shorter.

## Sample Request

    POST https://api.sounddate.com/profile/sound
    
    Bearer: {accessToken}
    Content-Type: audio/mpeg
    Accept: application/json
    {soundFile}

## Response

| **Element** | **Description** | **Type** | **Notes** |
|---|---|---|---|
| **id** | ID of the new sound file | integer |
| **length** | Length of the sound file | float | Duration in seconds |

## Sample Response

    {
    	"id":1234,
    	"length=":20.6
    }

# Retrieve a List of Sound Files

Retrieves a list of sound file URLs and their lengths for a specified user.

## URL

    GET  https://api.sounddate.com/user/{user id}/profile/sound

**where** {user id} is the ID of the user whose profile contains the sound files.

## Query Parameters

|**Parameter** | **Description** | **Type** | **Required** | **Notes** |
|---|---|---|---|---|
| **sortOrder** | Order to return the sounds in | string | Optional | Valid values: mostRecent, earliest, shortest, longest. Default is mostRecent. |

**Note:**

· **mostRecent** returns the most recent to the earliest.

· **earliest** returns the earliest sound files to the most recent.

· **shortest** returns the shortest sound files to the longest.

· **longest** returns the longest sound files to the shortest.

## Headers

| **Header Name** | **Description** | **Required** | **Values** |
|---|---|---|---|
| **Bearer** | Access token | Required | See Authorization Section |
| **Accept** | Format of returned data | Optional |application/xml, application/json. Default is application/json.|

## Sample Request

    GET https://api.sounddate.com/user/35632/profile/sound?sortOrder=earliest
    
    Bearer: {access token}
    Accept: application/json

## Response

| **Element** | **Description** | **Type** | **Notes** | 
|---|---|---|---|
| **soundFiles** | List of the sound file information | array||
|&nbsp;&nbsp;id | ID of the sound file | integer ||
|&nbsp;&nbsp;url | URL for the sound file | string ||
|&nbsp;&nbsp;length | Length of the sound file | float | Duration in seconds|

## Sample Response

    {
	    "soundFiles": [
		    {
			    "id": 23456,
			    "url": "https://api.sounddate.com/profile/sound/23456.mp3",
				"length": 11.2
		    },
		    {
			    "id": 24559,
			    "url": "https://api.sounddate.com/profile/sound/24559.mp3",
			    "length": 19.8
		    }
	    ]

	}

## Status Codes and Errors

The following table lists the returned HTTP status codes.

| **Code** | **Description** | **Notes** |
|---|---|---|
| **200** | OK | Sound file was successfully added.|
| **401** | Forbidden | Access token is invalid. |
| **413** | Request Entity Too Large |Sound file length exceeded 5 minutes.|
