# How to update nexus node no-gui
---
## Delete old folder
- rm -fr  LLL-TAO
## Clone branch
- git clone -b 5.0.4 https://github.com/Nexusoft/LLL-TAO
## Change directory
- cd LLL-TAO

## stop nexus daemon(if running)
- ./nexus system/stop

---

## GIT
After we move to the directory with the old code, we need to sync with the branch on Github.

### Check branch

- git branch

we should be on *5.0.4* branch (update)

### Fetch new branches
we may need to check for new branches, to do it, please do a:

- git fetch

### checkout
now we must check for changes on remote server.

- git checkout

As a result you will find that you are *several* commits behind remote branch.

### Pull
Now our local system knows we are behind the branch, we can fix it and upgrade the packages using:
- git pull 
---

### Ok now you should be up to date, now we need to recompile the code to update our node.

## Clean

First of all we need to clean our files to compile without problems do:
-  make clean -f makefile.cli -j1 AMD64=1

*if you have a limited device such as a rasperry change last argument to **ARM64=1***

Now wait for the cleaning, after some minutes you will be able to compile.

## Make

finally you can compile the new source code, it will take many minutes, start it by using:

- make -f makefile.cli -j1 AMD64=1 NO_WALLET=1

*if you have a limited device such as a rasperry change AMD64=1 argument to **ARM64=1***

**Cogratulations you have upgraded your node correctly.**

---

### Start Node 

Now you can start using the nexus binary to start your node, do some staking or tests, that's up to you, because you are upgrading all the config files will keep working.

If you have doubts on how to do this, please look at the guide in this page  	[Tritium++](https://thedigitalfuture.net/2021/08/25/tritium-private-testnet-5-1-rc1/) starting from point 4.

---

## FIN




