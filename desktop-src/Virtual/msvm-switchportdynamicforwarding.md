---
title: Msvm\_SwitchPortDynamicForwarding class
description: Connects a switch port to a dynamic forward entry (learned MAC address).
ms.assetid: a903b8d4-b42e-4cb6-96ea-f40ed29e266c
keywords:
- Msvm_SwitchPortDynamicForwarding class Hyper-V
- Msvm_SwitchPortDynamicForwarding class Hyper-V , described
topic_type:
- apiref
api_name:
- Msvm_SwitchPortDynamicForwarding
- Msvm_SwitchPortDynamicForwarding.Antecedent
- Msvm_SwitchPortDynamicForwarding.Dependent
api_location:
- Root\Virtualization
api_type:
- Schema
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Msvm\_SwitchPortDynamicForwarding class

Connects a switch port to a dynamic forward entry (learned MAC address). This is useful in finding all of the learned MAC addresses for a specified port.

The following syntax is simplified Managed Object Format (MOF) code, and it includes all of the inherited properties.

## Syntax

``` syntax
[Association, Dynamic, Provider("VmmsWmiInstanceAndMethodProvider"), AMENDMENT]
class Msvm_SwitchPortDynamicForwarding : CIM_SwitchPortDynamicForwarding
{
  Msvm_SwitchPort             REF Antecedent;
  Msvm_DynamicForwardingEntry REF Dependent;
};
```

## Members

The **Msvm\_SwitchPortDynamicForwarding** class has these types of members:

-   [Properties](#properties)

### Properties

The **Msvm\_SwitchPortDynamicForwarding** class has these properties.

<dl> <dt>

**Antecedent**
</dt> <dd> <dl> <dt>

Data type: **[**Msvm\_SwitchPort**](msvm-switchport.md)**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Override**](https://msdn.microsoft.com/library/aa393650) ("Antecedent")
</dt> </dl>

A reference to the switch port.

</dd> <dt>

**Dependent**
</dt> <dd> <dl> <dt>

Data type: **[**Msvm\_DynamicForwardingEntry**](msvm-dynamicforwardingentry.md)**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Override**](https://msdn.microsoft.com/library/aa393650) ("Dependent")
</dt> </dl>

A reference to the dynamic forwarding entry of the forwarding database.

</dd> </dl>

## Remarks

Access to the **Msvm\_SwitchPortDynamicForwarding** class might be restricted by UAC Filtering. For more information, see [User Account Control and WMI](https://msdn.microsoft.com/library/aa826699).

## Examples

See [Querying Networking Objects](querying-networking-objects.md).

## Requirements



|                                     |                                                                                                      |
|-------------------------------------|------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                            |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                                       |
| End of client support<br/>    | None supported<br/>                                                                            |
| End of server support<br/>    | Windows Server 2012 R2<br/>                                                                    |
| Namespace<br/>                | Root\\Virtualization<br/>                                                                      |
| MOF<br/>                      | <dl> <dt>WindowsVirtualization.mof</dt> </dl> |



## See also

<dl> <dt>

[**CIM\_SwitchPortDynamicForwarding**](cim-switchportdynamicforwarding.md)
</dt> <dt>

[**CIM\_SwitchPortDynamicForwarding**](https://msdn.microsoft.com/library/mt146273)
</dt> <dt>

[Networking Classes](networking-classes.md)
</dt> </dl>

 

 




