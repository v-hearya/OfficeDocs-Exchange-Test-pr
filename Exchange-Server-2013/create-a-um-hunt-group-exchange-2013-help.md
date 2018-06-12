﻿---
title: 'Create a UM hunt group: Exchange 2013 Help'
TOCTitle: Create a UM hunt group
ms:assetid: 43ecb1ec-5f82-4516-9010-de8f954d3758
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Aa997679(v=EXCHG.150)
ms:contentKeyID: 49315401
ms.date: 12/10/2017
mtps_version: v=EXCHG.150
f1_keywords:
- Microsoft.Exchange.Management.SnapIn.Esm.Servers.UnifiedMessaging.CreateUMHuntGroupWizardForm.CreateUMHuntGroupWizardPage1
---

# Create a UM hunt group

 

_**Applies to:** Exchange Online, Exchange Server 2013, Exchange Server 2016_


A Unified Messaging (UM) hunt group is a logical representation of a Private Branch eXchange (PBX) or IP PBX hunt group. A UM hunt group acts as a connection or link between a UM IP gateway and a UM dial plan.


> [!NOTE]
> If you associate a UM dial plan with the UM IP gateway when you create a UM IP gateway, a UM hunt group will also be created.




> [!NOTE]
> If you want to change the settings for a UM hunt group, you must delete the hunt group and then create another hunt group that has the appropriate settings.



For additional management tasks related to UM hunt groups, see [UM hunt group procedures](um-hunt-group-procedures-exchange-2013-help.md).

## What do you need to know before you begin?

  - Estimated time to complete: 2 minutes.

  - You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "UM hunt groups" entry in the [Unified Messaging permissions](unified-messaging-permissions-exchange-2013-help.md) topic.

  - Before you perform these procedures, confirm that a UM dial plan has been created. For detailed steps, see [Create a UM dial plan](create-a-um-dial-plan-exchange-2013-help.md).

  - Before you perform these procedures, confirm that a UM IP gateway has been created. For detailed steps, see [Create a UM IP gateway](create-a-um-ip-gateway-exchange-2013-help.md).

  - For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](keyboard-shortcuts-in-the-exchange-admin-center-exchange-online-protection-help.md).


> [!TIP]
> Having problems? Ask for help in the Exchange forums. Visit the forums at <A href="https://go.microsoft.com/fwlink/p/?linkid=60612">Exchange Server</A>, <A href="https://go.microsoft.com/fwlink/p/?linkid=267542">Exchange Online</A>, or <A href="https://go.microsoft.com/fwlink/p/?linkid=285351">Exchange Online Protection</A>..



## What do you want to do?

## Use the EAC to create a UM hunt group

1.  In the EAC, navigate to **Unified Messaging** \> **UM dial plans**. In the list view, select the UM dial plan you want to modify, and then click **Edit** ![Edit icon](images/JJ218640.6f53ccb2-1f13-4c02-bea0-30690e6ea71d(EXCHG.150).gif "Edit icon").

2.  On the **UM Dial Plan** page, under **UM Hunt Groups**, click **New** ![Add Icon](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "Add Icon").

3.  On the **New UM hunt group** page, enter the following information:
    
      - **Name**   Use this box to create the display name for the UM hunt group. A UM hunt group name is required and must be unique, but it's used only for display purposes in the EAC and the Shell. If you have to change the display name of the hunt group after it’s been created, you must first delete the existing hunt group and then create another hunt group that has the appropriate name.
        
        If your organization uses multiple hunt groups, we recommend that you use meaningful names for your hunt groups. The maximum length of a UM hunt group name is 64 characters, and it can include spaces. However, it can't include any of the following characters: " / \\ \[ \] : ; | = , + \* ? \< \>.
    
      - **UM IP gateway**   Use this box to specify the UM IP gateway to be used. Click **Browse** to select the UM IP gateway, and then click **OK**.
    
      - **Pilot identifier**   Use this box to specify a string that uniquely identifies the pilot identifier configured on the PBX or IP PBX.
        
        An extension number or a Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) can be used in this box. Alphanumeric characters are accepted in this box. For legacy PBXs, a numeric value is used as a pilot identifier. However, some IP PBXs can use SIP URIs.

4.  
    
    Click **Save**.

## Use the Shell to create a UM hunt group

This example creates a UM hunt group named `MyUMHuntGroup` that has a pilot identifier of 12345.

    New-UMHuntGroup -Name MyUMHuntGroup -PilotIdentifier 12345 -UMDialplan MyUMDialPlan -UMIPGateway MyUMIPGateway

This example creates a UM hunt group named `MyUMHuntGroup` that has multiple pilot identifiers.

    New-UMHuntGroup -Name MyUMHuntGroup -PilotIdentifier 5551234,55555 -UMDialplan MyUMDialPlan -UMIPGateway MyUMIPGateway
