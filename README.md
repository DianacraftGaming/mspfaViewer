# mspfaViewer
This script was made to let you host your mspfa or original comic on it's own site.

## Setup
Each folder contains all the files necessary to view your adventure when hosted. Download the folders contents and host them on your own site.

`adventure.json` is the file that contains all your adventure data. If you want to host an existing MSPFA adventure simply past in it's adventure object overtop of the template. Else copy the contents of `template.json` file and fill it out with your own adventure data.

`adventure.json` should have at least these values:
```json
{
  "n": "Adventure name",
  "o": "Link to adventure Icon",

  "p": [ ... ]
}
```
- _**n**ame_ is the name of your adventure
- _ic**o**n_ is the icon of your adventure, this will be it's favicon in the viewer
- _**p**ages_ is an array of page objects for each page of your adventure

Page objects have these values:
```json
{
  "d": 1671518387574,
  "c": "Page 1 title",
  "b": "Page 1 content",
  "n": [ 2 ],
  "theme": "scratch",
  "banner": "./assets/scratchbanner.gif",
  "dual": [
    {
      "c": "Left side title",
      "b": "Left side content",
    },
    {
      "c": "Right side title",
      "b": "Right side content",
    }
  ]
}
```
- _**d**ate_ is the date the page was published in as a unix timestamp
- _**c**ommand_ is the page's command or title, using html and/or mspfa bbcode
- _**b**ody_ is the content of the page, using html and/or mspfa bbcode
- _**n**ext_ is an array of page indexes pointing to the next page (Page indexes start at 1)
- **theme** is optional, can be used to override css of a page
- **banner** is optional, adds a banner on top of a page
- **dual** is optional, completely hides the normal page content and replaces it with 2 new pages if present. The inner "c" and "b" are the command and body respectively for each of the pages

