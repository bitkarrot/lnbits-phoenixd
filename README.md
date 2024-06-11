# LNBits-phoenixd

## What this is:

Run a super light, simple Lightning node (phoenixd) together with LNBits within Docker.

This is a docker-compose.yml for lnbits dev branch at LNBITS_COMMIT_HASH=2db5a83f4ed5dd21d99123a0947238f0674270c0, release 0.12.8
and phoenixd Dockerfile, source: https://github.com/ACINQ/phoenixd, v0.1.5

This repo will be updated to latest LNBits release when it comes out. 

## New to Docker? 

No problem, here's a guide on how to get started on a vps
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04

## To run:

git clone this repository.

```
docker-compose up
```
On initial docker launch, you will need to update the LNBits wallet endpoint in the server
settings with the corresponding phoenixd http key and the phoenixd endpoint: 

- Default phoenixd endpoint: http://localhost:9740/ 
- The phoenixd http key will be located in the phoenixd container at phoenixd.conf

Inspect your docker containers:

<img width="600" alt="Screenshot 2024-05-06 at 12 12 16 AM" src="https://github.com/bitkarrot/lnbits-phoenixd/assets/73979971/11126b8a-908a-4a64-b08a-74fb19ad2c8b">


Inside of LNBits Admin panel, use the name of the phoenix docker container instead of localhost:
<img width="600" alt="Screenshot 2024-05-05 at 10 55 39 PM" src="https://github.com/bitkarrot/lnbits-phoenixd/assets/73979971/f8a9f888-54d5-47b6-b39c-b1e78b388347">

- Save and Restart the LNBits server.
- Check your logs to see if connected to phoenixd wallet.
  
<img width="600" alt="Screenshot 2024-05-06 at 12 12 41 AM" src="https://github.com/bitkarrot/lnbits-phoenixd/assets/73979971/e61ed7ef-c2ef-4704-897c-5d6f4b719409">

  
---

## Remember to backup your phoenixd seed words.

--- 
## To give access with a domain name

Ok, now that you have your Docker containers running on your VPS,
To Make LNbits install accessible over clearnet with a domain, follow these instructions: 

https://github.com/lnbits/lnbits/blob/dev/docs/guide/installation.md#reverse-proxy-with-automatic-https-using-caddy

### Don't have a vps? Here's a short list:
https://gist.github.com/bitkarrot/e394556e6d11028e8af5c4d435ba230e


## Where to get more help

- Phoenixd discussions: https://github.com/ACINQ/phoenixd/discussions
- LNBits Telegram: @lnbits

## Original Source

- https://github.com/lnbits/lnbits
- https://github.com/ACINQ/phoenixd

## Note:

This is a pre-release, for those who want test out and deploy before next lnbits release. 
There are some docker customizations which are not default to lnbits. 
p.s. I am not super familiar with Docker, so if there is a better way to do this, please do suggest.
