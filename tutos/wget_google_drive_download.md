## How to download files from Google Drive with WGET

### Step 1. Get the ID of the file to download
1. Get a shareable link from Google Drive by right-clicking the file and selecting `Get Shareable Link`.
2. Examine the link to get the file's ID. Example:
   
   `https://docs.google.com/open?id=[ID]`

### Step 2. Download the file with WGET
1. Build the download URL using the ID obtained in Step 1. Example: 
   
      `https://drive.google.com/uc?export=download&id=[ID]`

2. Run WGET with the URL. Usage: `wget [OPTION]... [URL]...`. Example: 
     
      `wget -O [filename] --no-check-certificate -r 'https://drive.google.com/uc?export=download&id=[ID]'`

         Options used:
         -O, --output-document=FILE  writes document to FILE
         --no-check-certificate      don't validate the server's certificate
         -r                          recursive
  
  ---
  
  _These instructions were inspired by the Gist and comments at https://gist.github.com/iamtekeste/3cdfd0366ebfd2c0d805_
  