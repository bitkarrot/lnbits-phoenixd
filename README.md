# LNBits-phoenixd

## What this is:

This is a docker-compose.yml for lnbits dev branch at LNBITS_COMMIT_HASH=0076a85fdb557552f51c5ec11e0f8ff8df2e17de
and phoenixd Dockerfile, source: https://github.com/ACINQ/phoenixd, v0.1.4

## To run:

git clone this repository.

```
docker-compose up
```
On initial docker launch, you will need to update the LNBits wallet endpoint in the server
settings with the corresponding phoenixd http key and the phoenixd endpoint: 

- Default phoenixd endpoint: http://localhost:9740/ 
- The phoenixd http key will be located in the phoenixd container at phoenixd.conf

Inside of LNBits Admin panel, use the name of the phoenix docker container instead of localhost:

<img width="732" alt="Screenshot 2024-05-05 at 10 55 39 PM" src="https://github.com/bitkarrot/lnbits-phoenixd/assets/73979971/fbd565b0-d660-411e-bb68-0ba6c6923050">

## Remember to backup your phoenixd seed words.


## Note:

This is a pre-release, for those who want test out and deploy before next lnbits release.
p.s. I am not super familiar with Docker, so if there is a better way to do this, please do suggest. 
