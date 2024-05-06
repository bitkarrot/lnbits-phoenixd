
This Dockerfile is not the same as the default released with lnbits. 

Modifications made: 

- copies the env.txt and uses it in the Docker container
- in env config, the admin panel is set to true, so master user can be created on initial load
- Dockerfile exposes /app directory
- Dockerfile clones the latest dev commit from lnbits 
