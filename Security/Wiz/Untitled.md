 SKIP_TO_MAIN_CONTENT

![Microsoft Logo](https://www.wiz.io/_next/static/media/social_share_image.537ea7b6.jpg)

|

SPL - AWS Connector Deployment & Workload Scanning

00h : 26m : 57s

|

       

en

- **Lab Guide**
- **Environment**
- **Lab Validation**
- **Resources**

# Task: Verify and Analyze your Cloud Environment

---

## Overview

In this lab we will look into findings and discoveries made by the Workload Scanner triggered by the deployment of the Wiz Cloud connectors (AWS, Azure, OCI, GCP). More specifically, we will look into resources discovered, its technologies, vulnerabilities, and network insights.

---

If you have just finished the Wiz OCI Connector deployment, you may have to wait until resources are fetched and ingested into the Graph. (approximately 30min)

---

## Exercise 1. Seek & Find

Once the Cloud connector is deployed, Wiz begins to scan the environment using its agentless read-only APIs approach. With that, if during the Cloud scan the connector finds VMs, Functions, and Containers, it will trigger a workload scan for further analysis. In this lab we will navigate through the scan findings, its details, how to analyze and address issues identified by the workload scanner.

### Time Requirements

This lab is expected to take approximately 20-30 minutes.

### Instructions

1. In Wiz, navigate to **Settings > Deployments**.
    
2. Find your Cloud connector on the list, or use the Search by name field
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/settings-deployments.png)
    
3. Here you can already see some information about your Cloud connector:
    
    - Health Issues: usually tied to permission errors in the Cloud account. Some are informational and don't affect the connector operations, but some (High/Critical) may prevent the connector to work properly.
    - Status: Active/Inactive
    - Source: Cloud account (AWS Account, Azure Subscription, OCI, GCP Project, etc)
    - Last Activity: last time the Cloud account was scanned
4. Click on the connector to expand the details
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/connector-details.png)
    
    - The **Details** show more information about the connector including its ID, creation date, Cloud Subscription details, and the Wiz Managed Identity used to make the API calls.
5. Still in the Details tab of your connector, and click on Subscriptions
    
6. The portal will show all of the Subscriptions attached to the connector
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/subs.png)
    
    It can take some time for all aspects of the connector findings to populate through the Wiz UI. If you do not see your subscription listed at this point, expand the following *Manual query to locate your subscription* section for a direct link to a Security Graph query to locate it.
    
    Manual query to locate your subscription
    
7. Click on your Subscription to open the details drawer, navigate through its details. Here you can begin to see the power of Wiz, where in a matter of minutes, you have visibility into your Cloud environment.
    
    ---
    
    **Details**
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/acct-details.png)
    
    ---
    
    **Issues**
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/acct-issues.png)
    
    ---
    
    **Configuration**
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/acct-config.png)
    
    ---
    
8. Close the Subscription details drawer. In the Resources column, click on the **"view virtual machines on the graph"** link.
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/vmlink.png)
    
    If you do not see your subscription on the **Subscriptions** page and you used the previous manual link to locate your subscription on the Security Graph, expand the following *Manual query to locate your VM* section for a direct link to a Security Graph query to locate the VM for the following steps.
    
    Manual query to locate your VM
    
9. Note that this graph query is tailored to your environment, using the Virtual Machine as the root object, filtering by an specific Subscription ID (in this case an AWS Account).
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/vmquery.png)
    
10. Click on MyVM to open the details drawer. In the Overview tab, you begin to see all the information collected by the Cloud Connector scanner, workload scanner, plus the Wiz enrichments.
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/vm-overview.png)
    
11. Scroll down to the **Technologies** section and click on **Linux Ubuntu**
    
12. Here we see Linux Ubuntu as a **Hosted Technology** and all of the information collected by the workload scanner.
    
13. Click on the Vulnerability tab, and see that the Hosted Technology's version, which happens to be MYVM's Operating System, is End-of-Life.
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/ht.png)
    
14. You can further investigate by clicking on the Finding (End-of-Life Linux Ubuntu 18.04.6).
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/ht-finding.png)
    
15. Go back to the VM's detail drawer and browse other details. Try to find:
    
    - the workload scan results;
    - all technologies installed in the VM;
    - network exposure paths;
    - VM's data inventory

## Troubleshooting Your Connector

Since this is a fresh deployment, your connector should not have any health issues. If you see errors, refer to [Troubleshooting Your Connector](#troubleshooting-your-connector) for guidance on resolving them.

![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/connector-healthissues.png)

- The **Health Issues** tab shows the list of issues, severities, and total count.
    
- Some factors that lead to issues include:
    
    - SCP policies in AWS: strict policies disallowing API calls needed for the connector;
    - Outdated Wiz Role: as Wiz adds the ability to scan news services, existing Cloud roles, service accounts, service principal permissions need to be updated accordingly;
    - Resource-based policies: AWS KMS Vault, S3 Buckets, Azure Key Vaults, are a good example of it.
- If you have any issues listed, click in one of them and examine the details.
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/issue-detail1.png)
    
    ![](https://docs-api.cloudlabs.ai/repos/raw.githubusercontent.com/wiz-training/wiz-tech-foundations/main/module-4/images/issue-detail2.png)
    
- The issue details will always have a description, along with severity, status, and region impacted. It will also have a Remediation section where you can see possible causes and initiate your troubleshooting.