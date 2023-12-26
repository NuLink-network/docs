# NuLink Worker Update

The NuLink worker node need to be updated when a new version is released.The update procedure could be different for the docker environment and local environment.

**Make sure putting a small amount of native token(tBNB) to the worker account for sending one confirmation transaction.**




## Update in docker environment

Make sure you still hold your staking account and worker account. The update in docker is simple: stop the node, pull the latest image and restart the node.

1. Stop the running node in Docker: 
    ```shell
    docker kill <container ID>
    ```
    Delete the container:
    ```shell
    docker rm <container ID>
    ```

3. Pull the latest NuLink image.  
    ```shell
    docker pull nulink/nulink:latest
    ```

4.  Re-launch the worker node.  
    ```shell
    docker run --restart on-failure -d \
    --name ursula \
    -p 9151:9151 \
    -v /root/nulink:/code \
    -v /root/nulink:/home/circleci/.local/share/nulink \
    -e NULINK_KEYSTORE_PASSWORD \
    -e NULINK_OPERATOR_ETH_PASSWORD \
    nulink/nulink nulink ursula run --no-block-until-ready
    ```

## Update in local environment
The update procedure in local environment is: 

1. Access to your virtual environment  
   ```shell
   source /root/nulink-venv/bin/activate
   ```

2. Stop the running node   
   ```shell
   screen -x nulink-worker // use this command if you run the worker node in a screen session

   press ctrl+c
   ```

3. Uninstall the old package and install the new package   
   ```shell
   pip uninstall nulink-0.2.0-py3-none-any.whl // make sure the package name matches your installed package
      
   wget https://download.nulink.org/release/core/nulink-0.5.0-py3-none-any.whl
      
   pip install nulink-0.5.0-py3-none-any.whl
   ```

4.   Verify Installation use the same command when install the first time.  Check [Here](https://docs.nulink.org/products/nulink_worker/worker_install#local-install) 

5.  Launch the node use the same config file   
   ```shell
   screen -S nulink-worker // use this command if you want to run the worker node in a screen session
      
   nulink ursula run --no-block-until-ready
   ```

