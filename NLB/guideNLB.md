# NLB Guide

## Requirement

+ account local admin of all servers
+ 1 IP Address
+ DNS resolution on this IP
+ At least 2 Windows Servers

This documentation is based on Microsoft Documentation  (<https://docs.microsoft.com/en-us/iis/extensions/configuring-application-request-routing-arr/achieving-high-availability-and-scalability-arr-and-nlb>)

Schema : </br>

<img src="capture\ecl_nlb.png" alt="ecl_nlb" width="600"/>

## NLB Configuration

The NLB configuration is divided into the following steps:

1. Install the NLB feature on all ARR servers.
2. Create NLB cluster for ARR.
3. Configure NLB for active/passive deployment.

</br>

### Install the NLB feature on **all** ARR Servers

1. Launch Server Manager

<img src="capture/0_add-roles-features.png" alt="add-roles-features" width="300"/>

2. Click Next on default page

<img src="capture/1_default.png" alt="default" width="300"/>

3. Select **Role-based or feature-based installation**

<img src="capture/2_rolebased-features.png" alt="rolebased-features" width="300"/>

4. Select the server

<img src="capture/3_server.png" alt="server" width="300"/>

5. Go to Features and select **Network Load Balancing**

<img src="capture/4_nlbfeature.png" alt="nlbfeature" width="300"/>

6. Add required Features for NLB

<img src="capture/5_requiredfeatures.png" alt="requiredfeatures" width="300"/>

7. Confirm Installation

<img src="capture/6_confirm.png" alt="confirm" width="300"/>

Do the same for all servers involve in the network load balancing.

### Create NLB cluster for ARR

1. open the Network Load Balancing Manager from the Server Manager

<img src="capture\7_manager.png" alt="manager" width="300"/>

2. Right-click on Network Load Balancing Clusters, and then select New Cluster.

<img src="capture\8_new.png" alt="new" width="300"/>

3. In the New Cluster dialog box, in the Host text box, type the server address of one of the ARR servers.

<img src="capture\9_connecthost.png" alt="connecthost" width="300"/>

4. Set the priority to 1.

<img src="capture\10_hostconfig.png" alt="hostconfig" width="300"/>

5. Add the IP Address of the newload balancing cluster

<img src="capture\11_addclusterip.png" alt="addclusterip" width="300"/>

6. Accept the default values

<img src="capture\12_defaultconfig.png" alt="defaultconfig" width="300"/>

7. Click Finish to complete the creation of the NLB cluster.

### Add Host to the cluster

From the NLB manager, **Right-Click** on the cluster and select **Add Host to Cluter**

<img src="capture\13_Addhost.png" alt="addhost" width="300"/>

Follow the assistant to add the host to NLB Cluster like before.

### Configure the cluster for active / passive

From the NLB manager, **Right-Click** on the cluster and select **Cluster Properties**

<img src="capture\14_clusterproperty.png" alt="clusterproperty" width="300"/>

Go the **Port Rules** tab

<img src="capture\15_portrules.png" alt="portrules" width="300"/>

Click on **Edit** button

On the new window, select **Single Host** 

<img src="capture\16_singlehost.png" alt="singlehost" width="300" />

Click on **Ok** on the 2 windows to confirm the new configuration.