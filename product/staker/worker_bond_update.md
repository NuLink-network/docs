# NuLink Worker Update

After a user unstakes or unbonds a NuLink worker node, it is necessary to restart the NuLink worker node once the user rebonds it in order to complete the process successfully. The update procedure could be different for the docker environment and local environment.

**Make sure putting a small amount of BNB(test) to the worker account for sending one confirmation transaction.**




## Update in docker environment

Restart the running node 
```shell
$ docker restart  <container ID>

```

## Update in local environment

Restart the running node
```shell
screen -x nulink-worker // use this command if you run the worker node in a screen session

press ctrl+c

nulink ursula run --rest-port 9151 --no-block-until-ready
```