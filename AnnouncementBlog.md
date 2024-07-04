# RHEL 8 Is Here — What Does That Mean for You?

**IBM Cloud Satellite and Red Hat OpenShift on IBM Cloud recently added support for the RHEL 8 OS.**

With the release of RHEL 8, the RHEL 7 OS will be deprecated and unsupported in some cluster versions. Depending on your cluster version and the current OS of your worker nodes, you may need to migrate your worker nodes to another OS. This blog will help you determine what steps you need to take to migrate worker nodes in your Red Hat OpenShift on IBM Cloud cluster or your IBM Cloud Satellite control plane.

## For worker nodes on clusters

Review the migration steps for your cluster version.

<dl>
<dt>Version 4.11</dt>
<dd>RHEL 8 is the only RHEL OS version supported for clusters that run Version 4.11. If you provision a new cluster at version 4.11, you do not need to take any additional action. However, if you upgrade a 4.10 cluster with RHEL 7 worker nodes to 4.11, you must migrate your worker nodes to RHEL 8.
</dd>

<dt>Version 4.10</dt>
<dd>Now that RHEL 8 is available, any new clusters that run on version 4.10 are created with worker nodes that run on RHEL 8. No additional action is necessary for these clusters. However, RHEL 7 is deprecated for version 4.10, so if you have an existing 4.10 cluster that was created before RHEL 8 was released, you must migrate your worker nodes to RHEL 8 by the end of October 2022.</dd>
    
<dt>Version 4.9</dt> 
<dd>Both RHEL 7 and RHEL 8 are supported on clusters that run version 4.9 until the cluster version becomes unsupported, so you do not need to migrate your worker nodes to a new OS to keep using your cluster. However, beginning in October 2022, any 4.9 clusters with worker nodes that run on RHEL 7 cannot be upgraded to version 4.10. If you want to upgrade your cluster to 4.10, you must migrate your worker nodes to RHEL 8. RHEL 7 will remain the default RHEL version for 4.9, so any new 4.9 clusters will have worker nodes that run on RHEL 7 unless you specify otherwise.</dd>
    
<dt>Versions 4.8, 4.7 and 4.6</dt>
<dd>If your cluster runs on version 4.8, 4.7 or 4.6, you do not need to take any action. RHEL 8 is not available for these cluster versions, so you can continue to run RHEL 7 until these versions are unsupported. Note that if you ever upgrade your clusters to version 4.10+, you must migrate your worker nodes to RHEL 8 when your cluster is at version 4.9.</dd>
</dl>

## For worker nodes assigned to a Satellite control plane

RHEL 7 will become unsupported for Satellite control plane hosts in March 2023. If you have RHEL 7 hosts assigned to a control plane, you will need to migrate them to a different OS. For locations with CoreOS enabled, you can migrate to either RHEL 8 or RHCOS. For locations without CoreOS enabled, you must migrate to RHEL 8.
