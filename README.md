# ilo-sendfile
Send a binary file to the server via HP iLO serial console. 

Use case/why I wrote this: imagine your server lost network connectivity after updating a linux network driver. 
This is a quick hack to upload the new binary driver via iLO serial console CLI (vsp). 
It uploads the base64-encoded file slowly with rate-limiting allowing for a successful upload.
