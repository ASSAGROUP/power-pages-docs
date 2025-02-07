---
title: Invite contacts to your Power Pages site
description: Learn how to create and configure invitations in a Power Pages site.
author: sandhangitmsft

ms.topic: conceptual
ms.custom: 
ms.date: 3/23/2023
ms.author: sandhan
ms.reviewer: kkendrick
contributors:
    - nickdoelman
    - sandhangitmsft
    - ProfessorKendrick
---

# Invite contacts to your Power Pages site

Use the invitation feature of Power Pages to invite contacts to your website through automated email(s) created in your Microsoft Dataverse. The people you invite receive an email, fully customizable by you, with a link to your website and an invitation code. This code can be used to gain special access configured by you. With this feature, you have the ability to:

- Send Single or Group Invitations
- Specify an expiry date if desired
- Specify a user or website contact as the inviter if desired
- Automatically assign the invited contact(s) to an account upon invite redemption
- Automatically execute a workflow upon invite redemption
- Automatically assign the invited contact(s) to a Web Role(s) upon redemption

> [!NOTE] 
> You can also invite contacts in Power Pages. More information: [What is Power Pages](/power-pages/introduction)

Invitation redemption can be accomplished using any of our many authentication options. For documentation regarding website authentication, see [Local authentication, registration, and other settings](authentication/set-authentication-identity.md)and choose the model applicable to your version and configuration. The user will adopt any settings provided by the administrator upon redemption. An Invite Redemption Activity will be created for the Invite and Contact.

Invitations are sent via the **Send Invitation** workflow. By default, the workflow creates an email with a generic message and sends it to the invited Contact's primary email address. The email addresses in the CC and BCC fields are ignored to ensure secure communication. The **Send Invitation** workflow contains an email template that will need to be edited to contain a specific message for your website and the correct hyperlink to your website's **Invite Redemption Page**.

To edit the **Send Invitation** workflow email template, locate it and deactivate it. After it's deactivated, edit the email template to send the message you want and provide a link to the **Invite Redemption Page** of your website.

> [!IMPORTANT]
> Converting the **Send Invitation** workflow to a [Real-time workflow](/power-apps/maker/data-platform/overview-realtime-workflows) is **not supported** and will cause issues with the invitation process.

> [!NOTE]
> The invitation is sent only to the primary email (emailaddress1) of the contact. The invitation will not be sent to the secondary email (emailaddress2) or alternate email (emailaddress3) of the contact record.

## Create invitations from Portal Management app

1.  Open the [Portal Management app overview](../configure/portal-management-app.md).

2.	Go to **Portals** > **Contacts**.

3.	Select a contact or open the contact record to be invited.

4.	On the command bar, select **Create Invitation**.

5.	On the **Invitation** page, enter appropriate values in the fields. More information: [Invitation attributes](#invitation-attributes)

6.	Select **Save**.

7.	On the command bar, select **Flow** > **Send Invitation**.

8.	In the confirmation window, select **OK**. The invitation will be sent to the selected contact.

### Send multiple invitations

You can create invitations for your contacts and then send all invitations at once.

1.	Create invitations for the required contacts and then go to **Portals** > **Invitations**.

2.	Select the created invitations.

3.	On the command bar, select **Flow** > **Send Invitation**.

4.	In the confirmation window, select **OK**. The invitations will be sent to the selected contacts.

## Invitation attributes

The table below explains the attributes of the **Invitation** page:


|  Name    |    Description    |
|-------|------------|
|                 Name                  |                                                                                                      A descriptive name for helping recognize the invitation.                                                                                                      |
|                 Type                  |                                             **Single** or **Group**. Single will allow only one contact to be invited and only one redemption. Group allows multiple contacts to be invited and multiple redemptions.                                              |
|             Owner/Sender              | The user that will be the sender of the email when the invitation is sent. This can be overridden in the **Send Invitation** workflow if the created email already contains someone in the from field. |
|            Invitation Code            |                                                                 A unique code for the invitation that only the invitee will know. This is automatically generated when creating a new invitation.                                                                  |
|              Expiry Date              |                                                                                     The date that represents when the invitation will become invalid for redemption. Optional.                                                                                     |
|                Inviter                |                                                                                               Can be used when a contact is the sender of the invitation. Optional.                                                                                                |
|          Invited Contact(s)           |                                                                                                             The contact(s) to be invited to a website.                                                                                                              |
|           Assign to Account           |                                                                        An account record to be associated as the redeeming contact's parent customer when the invite is redeemed. Optional.                                                                        |
| Execute Workflow on Redeeming Contact |                                                         A workflow process to be executed when the invite is redeemed. The workflow will be passed the redeeming contact as the primary entity. Optional.                                                          |
|          Assign to Web Roles          |                                                                               A set of web roles to be associated with the redeeming contact when the invite is redeemed. Optional.                                                                                |
|          Redeemed Contact(s)          |                                                                                                   The contact(s) that have successfully redeemed the invitation.                                                                                                   |
|      Maximum Redemptions Allowed      |                                                                                   The number of times the invitation can be redeemed. Available for Group type invitations only.                                                                                   |
|                                       |                                                                                                                                                                                                                                                                    |

### See also

- [Configure contacts as site users](external-access.md#configure-contacts-as-site-users)  
- [Local authentication, registration, and other settings](authentication/set-authentication-identity.md)
