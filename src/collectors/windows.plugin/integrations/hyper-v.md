<!--startmeta
custom_edit_url: "https://github.com/netdata/netdata/edit/master/src/collectors/windows.plugin/integrations/hyper-v.md"
meta_yaml: "https://github.com/netdata/netdata/edit/master/src/collectors/windows.plugin/metadata.yaml"
sidebar_label: "Hyper-V"
learn_status: "Published"
learn_rel_path: "Collecting Metrics/Windows Systems"
most_popular: False
message: "DO NOT EDIT THIS FILE DIRECTLY, IT IS GENERATED BY THE COLLECTOR'S metadata.yaml FILE"
endmeta-->

# Hyper-V


<img src="https://netdata.cloud/img/windows.svg" width="150"/>


Plugin: windows.plugin
Module: PerflibHyperV

<img src="https://img.shields.io/badge/maintained%20by-Netdata-%2300ab44" />

## Overview

This collector monitors website requests and logins.


It queries the 'HyperV' object from Perflib in order to gather the metrics.


This collector is only supported on the following platforms:

- windows

This collector only supports collecting metrics from a single instance of this integration.


### Default Behavior

#### Auto-Detection

The collector automatically detects all of the metrics, no further configuration is required.


#### Limits

The default configuration for this integration does not impose any limits on data collection.

#### Performance Impact

The default configuration for this integration is not expected to impose a significant performance impact on the system.


## Metrics

Metrics grouped by *scope*.

The scope defines the instance that the metric belongs to. An instance is uniquely identified by a set of labels.



### Per Hyper-V

These metrics refer to the Hyper-V instance.

This scope has no labels.

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| hyperv.vms_health | ok, critical | vms |
| hyperv.root_partition_io_tlb_flush | gpa | flushes/s |
| hyperv.root_partition_virtual_tlb_flush_entries | flushes | flushes/s |
| hyperv.root_partition_virtual_tlb_pages | used | pages |
| hyperv.root_partition_address_space | address_spaces | address spaces |
| hyperv.root_partition_attached_devices | attached | devices |
| hyperv.root_partition_device_dma_errors | illegal_dma | requests |
| hyperv.root_partition_device_interrupt_errors | illegal_interrupt | requests |
| hyperv.root_partition_device_interrupt_throttle_events | throttling | events |
| hyperv.root_partition_deposited_pages | gpa | pages |
| hyperv.root_partition_device_space_pages | 4K, 2M, 1G | pages |
| hyperv.root_partition_gpa_space_pages | 4K, 2M, 1G | pages |
| hyperv.root_partition_gpa_space_modifications | gpa | modifications/s |

### Per Virtual Machine

These metrics refer to the Virtual Machine.

Labels:

| Label      | Description     |
|:-----------|:----------------|
| vm_name | The name of the Virtual Machine. |

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| hyperv.vm_cpu_usage | usage | percentage |
| hyperv.vm_cpu_usage_by_run_context | guest, hypervisor, remote | percentage |
| hyperv.vm_memory_physical | assigned | bytes |
| hyperv.vm_memory_physical_guest_visible | visible, available | bytes |
| hyperv.vm_memory_pressure_current | pressure | percentage |
| hyperv.vm_vid_physical_pages_allocated | allocated | pages |
| hyperv.vm_vid_remote_physical_pages | remote_physical | pages |

### Per Virtual Machine Storage Device

These metrics refer to the Virtual Machine Storage Device.

Labels:

| Label      | Description     |
|:-----------|:----------------|
| vm_storage_device | The name of the Storage Device. |

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| hyperv.vm_storage_device_bytes | read, write | bytes/s |
| hyperv.vm_storage_device_operations | read, write | operations/s |
| hyperv.vm_storage_device_errors | errors | errors/s |

### Per Virtual Machine Network Interface

These metrics refer to the Virtual Machine Network Interface.

Labels:

| Label      | Description     |
|:-----------|:----------------|
| vm_net_interface | The name of the Network Interface. |

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| hyperv.vm_net_interface_traffic | received, sent | kilobits/s |
| hyperv.vm_net_interface_ipsec_traffic | received, sent | kilobits/s |
| hyperv.vm_net_interface_packets | received, sent | packets/s |
| hyperv.vm_net_interface_directed_packets | received, sent | packets/s |
| hyperv.vm_net_interface_broadcast_packets | received, sent | packets/s |
| hyperv.vm_net_interface_multicast_packets | received, sent | packets/s |
| hyperv.vm_net_interface_packets_dropped | incoming, outgoing | drops/s |

### Per Virtual Switch

These metrics refer to the Virtual Switch.

Labels:

| Label      | Description     |
|:-----------|:----------------|
| vswitch | The name of the Virtual Switch. |

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| hyperv.vswitch_traffic | received, sent | kilobits/s |
| hyperv.vswitch_packets | received, sent | packets/s |
| hyperv.vswitch_directed_packets | received, sent | packets/s |
| hyperv.vswitch_broadcast_packets | received, sent | packets/s |
| hyperv.vswitch_multicast_packets | received, sent | packets/s |
| hyperv.vswitch_dropped_packets | incoming, outgoing | drops/s |
| hyperv.vswitch_extensions_dropped_packets | incoming, outgoing | drops/s |
| hyperv.vswitch_packets_flooded | flooded | packets/s |
| hyperv.vswitch_learned_mac_addresses | learned | mac addresses/s |
| hyperv.vswitch_purged_mac_addresses | purged | mac addresses/s |



## Alerts

There are no alerts configured by default for this integration.


## Setup

### Prerequisites

No action required.

### Configuration

#### File

The configuration file name for this integration is `netdata.conf`.
Configuration for this specific integration is located in the `[plugin:windows]` section within that file.

The file format is a modified INI syntax. The general structure is:

```ini
[section1]
    option1 = some value
    option2 = some other value

[section2]
    option3 = some third value
```
You can edit the configuration file using the [`edit-config`](https://github.com/netdata/netdata/blob/master/docs/netdata-agent/configuration/README.md#edit-a-configuration-file-using-edit-config) script from the
Netdata [config directory](https://github.com/netdata/netdata/blob/master/docs/netdata-agent/configuration/README.md#the-netdata-config-directory).

```bash
cd /etc/netdata 2>/dev/null || cd /opt/netdata/etc/netdata
sudo ./edit-config netdata.conf
```
#### Options



| Name | Description | Default | Required |
|:----|:-----------|:-------|:--------:|
| PerflibHyperV | An option to enable or disable the data collection. | yes | no |

#### Examples
There are no configuration examples.

