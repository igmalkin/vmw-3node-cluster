# Список ролей и привилегий для установки кластера OpenShift на платформу VMware

## ocp_vCenter_Cluster

**Host**
> Configuration

> Storage partition configuration

**Resource**
> Assign virtual machine to resource pool

**vApp**
> Assign resource pool

> Import

**Virtual machine**

> Change Configuration

> Add new disk

## ocp_Virtual_Machine_Folder

**Resource**
> Assign virtual machine to resource pool

**Storage views**
> View
 
**vApp**
> Import

**Virtual machine**
> **Change Configuration**
>> Acquire disk lease

>> Add existing disk

>> Add new disk

>> Add or remove device

>> Advanced configuration

>> Change CPU count

>> Change Memory

>> Change Settings

>> Change resource

>> Extend virtual disk

>> Modify device settings

>> Remove disk

>> Rename

>> Reset guest information

>> Set annotation

>> Upgrade virtual machine compatibility

> **Edit Inventory**

>> Create from existing

>> Create new

>> Remove

> **Interaction**

>> Guest operating system management by VIX API

>> Power off

>> Power on

>> Reset

> **Provisioning**

>> Clone virtual machine

## ocp_vSphere_Datastore

**Datastore**
> Allocate space

> Browse datastore

> Low level file operations

## ocp_vSphere_Port_Group

**Network**
> Assign network

## ocp_vSphere_vCenter

**Cns**
> Searchable

**vSphere Tagging**
> Assign or Unassign vSphere Tag

> Create vSphere Tag

> Create vSphere Tag Category

> Delete vSphere Tag

> Delete vSphere Tag Category

> Edit vSphere Tag

> Edit vSphere Tag Category

**Sessions**
> Validate session

**Profile-driven storage**
> Profile-driven storage view 
>>   данная привилегия отсутствует в документации, однако ее добавление является обязательным (на момент написания статьи, отсутствие данной привилегии [приводило к ошибке Terraform](https://github.com/hashicorp/terraform-provider-vsphere/issues/966) при клонировании диска шаблона виртуальной машины).   

**Storage views**
> View

## ocp_vSphere_vCenter_Datacenter

**Folder**
> Create folder

> Delete folder

**Resource**
> Assign virtual machine to resource pool

**vApp**
> Import

**Virtual machine**
> **Change Configuration**
>> Acquire disk lease

>> Add existing disk

>> Add new disk

>> Add or remove device

>> Advanced configuration

>> Change CPU count

>> Change Memory

>> Change Settings

>> Change resource

>> Extend virtual disk

>> Modify device settings

>> Remove disk

>> Rename

>> Reset guest information

>> Set annotation

>> Upgrade virtual machine compatibility

> **Edit Inventory**

>> Create from existing

>> Create new

>> Remove

> **Interaction**

>> Guest operating system management by VIX API

>> Power off

>> Power on

>> Reset

> **Provisioning**

>> Clone virtual machine
