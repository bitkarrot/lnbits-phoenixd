# LNBits-phoenixd

## What this is:

This is a docker-compose.yml for lnbits dev branch at LNBITS_COMMIT_HASH=0076a85fdb557552f51c5ec11e0f8ff8df2e17de
and phoenixd Dockerfile, source: https://github.com/ACINQ/phoenixd, v0.1.4

On initial docker launch, you will need to update the LNBits wallet endpoint in the server
settings with the corresponding phoenixd http key and the phoenixd endpoint: http://localhost:9740/ 
The https key will be in the phoenixd container at phoenixd.conf

Remember to backup your phoenixd seed words.

## To run:

git clone this directory.

```
docker-compose up
```

## Note:

This is a pre-release, for those who want test out and deploy before next lnbits release.
p.s. I am not super familiar with Docker, so if there is a better way to do this, please do suggest. 