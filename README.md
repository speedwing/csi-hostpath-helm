# csi-hostpath-helm

Helm repository of CSI Driver and related hostpath services

The `csi-hostpath` helm chart will install all the moving parts required 
to run a localhost CSI driver.
A minimum Kubernetes v1.17 is required.
The PersistentVolumes created with such driver, can then be user as 
source for VolumeSnapshot.

# Chart source

Manifests in this chart have been build by following instructions [here](https://github.com/kubernetes-csi/csi-driver-host-path/blob/master/docs/deploy-1.17-and-later.md)
and then have been customised to run on microk8s (see Gotcha section below for more details.)

## Usage

helm repo add csi-hostpath https://speedwing.github.io/csi-hostpath-helm
helm install csi-hostpath csi-hostpath/csi-hostpath

## Gotcha

This chart is currently optimised to run on microk8s.

The two issues below, detail how to customize the CSIDriver in order to make it to run on
microk8s:

* https://github.com/hetznercloud/csi-driver/issues/92
* https://github.com/kubernetes-csi/csi-driver-host-path/issues/71
