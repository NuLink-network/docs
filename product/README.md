
# Overview

The NuLink network integrates the Application Layer, the Cryptography Layer, the Storage Layer, the Blockchain Layer and the Watcher Network.

![image](../miscellaneous/img/architecture.png)

The Application Layer acts as an interface between the system and the application, facilitating direct communication with the application while also liaising with the Cryptography Layer to validate access to the application's confidential information.

Here are the application layer components:

* [**NuLink Agent:**](nulink_agent.md) The plug in to handle the local cryptographic operation of the NuLink users.

* [**NuLink Agent SDK:**](../dev/agent_sdk.md) The SDK for third party integration with NuLink Agent.

* [**NuLink SDK:**](../dev/nulink_sdk.md) The SDK to support  NuLink network.

* [**File Transfer:**](agent_usecase.md) The third party demo that how to use agent sdk to interact with NuLink Agent.

The relationships between these components are shown in the diagram.

![Operation Flow](../miscellaneous/img/flow.png)

