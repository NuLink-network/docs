# NuLink Worker Update

The NuLink worker node need to be updated when a new version is released. The update in docker is simple: stop the node, pull the latest image and restart the node.

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


