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

Exemplo

`https://drive.usercontent.google.com/download?id=1qbFkIzSsJbV1nVwZxKj6XU1emIe9jMiN&export=download&authuser=1&confirm=t&uuid=99a9b46c-48a2-48b7-8be6-f44e7f754d3a&at=APZUnTXOkgwlUyAhr9F1VPVl3HBF:1713291661477

wget -o lock.jpg --no-check-certificate -r https://drive.google.com/file/d/1qbFkIzSsJbV1nVwZxKj6XU1emIe9jMiN/view?usp=sharing


+++


wget -o lock.jpg --no-check-certificate https://drive.usercontent.google.com/download?id=1qbFkIzSsJbV1nVwZxKj6XU1emIe9jMiN
mv download?id=1qbFkIzSsJbV1nVwZxKj6XU1emIe9jMiN background.jpg`
  
