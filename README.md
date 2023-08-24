# Peer-to-Peer Group Based File Sharing System

## Architecture Overview

The Following entities will be present in the network :

- Tracker
    - It will maintain all the information of clients with their files(shared by client) to assist 
      the clients for the communication between peers.
- Clients
    - User will create an account and register with tracker
    - Login Using The User Credentials
    - Create Group and hence will become owner of that group
    - Fetch list of all Groups in server
    - Request to Join Group
    - Leave Group
    - Accept Group join requests(if owner)
    - Share file across group: Share the filename and SHA1 hash of the complete file as well as 
      piecewise SHA1 with the tracker
    - Fetch list of all sharable files in a Group
    - Download file
        - Retrieve peer information from tracker for the file
        - Core Part: Download file from multiple peers (different pieces of file from different 
          peers - piece selection algorithm) simultaneously and all the files which client downloads 
          will be shareable to other users in the same group. Ensure file integrity from SHA1 comparison.