# Parallel Processing Nodes

## Start Parallel Processing

This node can be used when there is a need to invoke more than one stream of processing at the same time. This is commonly used with [human tasks](/esp-config/automation/human-task) that can be assigned and worked on independently, but they must all be completed before the workflow can continue.

![Parallel Processing](/_books/esp-config/images/parallel-processing.png)

:::tip
The use of [Suspend automations](/servicemanager-config/customize/workflows/service-manager-workflows#suspend) is not recommended within a parallel process. Suspend automations are designed to suspend the entire workflow and not an individual stream within a parallel process.
:::

### Settings

Open the settings by clicking on the node and selecting the cog icon or double-click on the node.

Two settings are available:

* **Positioning**. Lets you change the orientation of the node.
* **Size**.  Change the size to better accommodate the number of streams.

![Parallel Processing Settings](/_books/esp-config/images/parallel-processing-settings.png)

## Finish Parallel Processing

Use this node to bring together and finish the individual process streams that had been initiated from a Start Parallel Processing node.

* The workflow will not progress past this node until all process streams have reached this point.
* When designing a parallel process it is important to design each stream with a successful path or outcome to reach the Finish Parallel Processing node.

    :::important
    If a human task fails due to an error in one stream, all other tasks within the parallel processing will be canceled.
    :::
* Each stream should be kept separate from other streams.  Do not connect one stream to another stream.

#### Settings

Open the settings by clicking on the node and selecting the cog icon or double-click on the node.

Two settings are available:

* **Positioning**. Lets you change the orientation of the node.
* **Size**.  Change the size to better accommodate the number of streams.

![Parallel Processing Settings](/_books/esp-config/images/parallel-processing-settings.png)

