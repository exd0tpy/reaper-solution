## welcome to unhacked

post-paradigm ctf, things feel a little dull, don't they? 

what do you say we bring some of that energy back into normal life?

_unhacked_ is a just-for-fun weekly challenge where you get a chance to go back in time before real exploits were committed to recover the funds. you are a whitehat, right anon?

## meet reaper

after a weekend of brain pain, let's start things off on easy mode.

[reaper farm](https://www.reaper.farm/) is a yield aggregator on fantom. their V2 vaults were hacked on 8/2.

there were a number of implementations of the vaults with damages totalling $1.7mm, but the exploit was the same on all of them, so let's just focus on one — a DAI vault hacked for over $400k.

- vault: [0x77dc33dC0278d21398cb9b16CbFf99c1B712a87A](https://ftmscan.com/address/0x77dc33dc0278d21398cb9b16cbff99c1b712a87a)
- fantom dai: [0x8D11eC38a3EB5E956B052f67Da8Bdc9bef8Abf3E](https://ftmscan.com/address/0x8D11eC38a3EB5E956B052f67Da8Bdc9bef8Abf3E)

review the code in this repo, find the exploit, and recover > $400k.

## how to play

1. update the .env file with an environment variable for FANTOM_RPC (already preset to the public RPC endpoint, which should work fine, in which case you can skip this).

2. review the code in the `src/` folder, which contains all the code at the time of the hack. you can explore the state of the contract before the hack using block 44000000. ex: `cast call --rpc-url ${FANTOM_RPC} --block 44000000 0x77dc33dC0278d21398cb9b16CbFf99c1B712a87A "totalAssets()" | cast 2d`

3. when you find an exploit, code it up in `ReaperHack.t.sol`. the test will pass if you succeed.

4. post on twitter for bragging rights and tag @unhackedctf. no cheating.