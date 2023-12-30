# Service Bonus Statistics

To navigate to the Service Bonus page, simply click the `Service Bonus` button located in the dashboard menu. The displayed data is categorized by batches, with the default view set to the current batch. Users can easily scroll down to explore information from other batches.

![Service Bonus](../../miscellaneous/img/dashboard/serviceBonus.png)

## Service Bonus

The left panel displays the `Service Bonus` information: 
* `CURRENT BATCH BONUS` indicates the bonus amount generated in the user selected batch.
* `CUMULATIVE BATCH BONUS` represents the total bonus amount generated across all batches.

## Batches
The right panel showcases the `Batches` details:
* `CURRENT BATCH` shows the user selected batch number.
* `TOTAL BATCH` represents the total count of all batches.

## Service bonus from each blockchain

The image below presents the service bonus collected from each blockchain.

![Bonus from each chain](../../miscellaneous/img/dashboard/bonusChain.png)

Currently, only BSC is supported, and other chains will gradually become available.

## Service bonus distribution

The following image illustrates the Service bonus distribution for the active stakers in the displayed batch. All the active stakers in this batch can share the pool of 80% of the `Service Bonus` based on their reputation score quota.

![Bonus from each chain](../../miscellaneous/img/dashboard/bonusDistribution.png)

   * `Address`: The account address where the user engages in staking activities.
   * `Node IP`: Node IP records the corresponding IP address of the worker nodes that the staker bonds
   * `Reputtion score`: A metric in the NuLink network assesses a staker's historical contribution within a single batch. It counts the number of active epochs within a batch, considering epochs with a living ratio higher than a specified threshold (currently set to 0.8) as active. The reputation score serves as an indicator of a staker's reliability and positive engagement with the NuLink network.
   * `Reputtion score quota`: A measurement represents the proportion of an individual user's reputation score relative to the total user's reputation score within the NuLink network. The metric provides insights into the relative contribution of a user's reputation to the overall reputation dynamics of the NuLink ecosystem.
   * `Quantity(NLK)`: This calculates the user's service bonus based on the reputtion score quota.
   

## Foundation Distribution
The image below demonstrates the Foundation Distribution, where 15% of the service bonus generated in each Batch is allocated to the NuLink Network Foundation's account.

![Foundation Distribution](../../miscellaneous/img/dashboard/foundation.png)

## Burning Record

This image illustrates the Burning Record, where 5% of the service bonus from each Batch is burned.

![Burning Record](../../miscellaneous/img/dashboard/burning.png)
