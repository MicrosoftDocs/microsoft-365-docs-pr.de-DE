---
title: Verwalten der Berechtigungen der Administratorrollen-Gruppenberechtigungen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratoren können erfahren, wie Sie Berechtigungen in der Exchange-Verwaltungskonsole (EAC) in Exchange Online Protection zuweisen oder entfernen.
ms.openlocfilehash: 01676fab3ed69120a35687d1c6939cb466b8d672
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082914"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="f5953-103">Verwalten der Berechtigungen der Administratorrollen-Gruppenberechtigungen in EOP</span><span class="sxs-lookup"><span data-stu-id="f5953-103">Manage admin role group permissions in EOP</span></span>

<span data-ttu-id="f5953-p101">In Microsoft Exchange Online Protection (EOP) können Sie die Exchange-Verwaltungskonsole verwenden, um einen Benutzer als Mitglied zu einer oder mehreren Rollengruppen hinzuzufügen, sodass er die Berechtigungen für bestimmte Verwaltungsaufgaben erhält. Darüber hinaus können Sie einen Benutzer über die Exchange-Verwaltungskonsole aus Rollengruppen entfernen.</span><span class="sxs-lookup"><span data-stu-id="f5953-p101">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f5953-106">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f5953-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f5953-107">Geschätzte Zeit bis zum Abschließen des Vorgangs: 5-10 Minuten</span><span class="sxs-lookup"><span data-stu-id="f5953-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="f5953-108">Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f5953-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f5953-p102">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Benutzer, Kontakte und Rollengruppen" im Thema [Featureberechtigungen in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f5953-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="f5953-111">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="f5953-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f5953-112">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="f5953-112">Having problems?</span></span> <span data-ttu-id="f5953-113">Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="f5953-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="f5953-114">Zuweisen von Mitgliedern zu Administratorrollengruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="f5953-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="f5953-115">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, klicken Sie auf die Rollengruppe, der Sie den Benutzer oder die Benutzer hinzufügen möchten,](../../media/ITPro-EAC-EditIcon.gif)und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![.</span><span class="sxs-lookup"><span data-stu-id="f5953-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="f5953-116">Klicken Sie unter Mitglieder auf Add-](../../media/ITPro-EAC-AddIcon.gif)Symbol **Hinzufügen** ![.</span><span class="sxs-lookup"><span data-stu-id="f5953-116">Under Members, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="f5953-117">Das Fenster zur Auswahl von Mitgliedern wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5953-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="f5953-118">Suchen Sie nach den Benutzern, die hinzugefügt werden sollen, oder wählen Sie die Benutzer aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="f5953-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="f5953-p105">Wenn Sie die Benutzer ausgewählt haben, die hinzugefügt werden sollen, klicken Sie auf **Hinzufügen** und anschließend auf **OK**. Das Fenster zur Auswahl von Mitgliedern wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="f5953-p105">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>

5. <span data-ttu-id="f5953-p106">Wie Sie sehen, wurde der Benutzer zum Fenster **Mitglieder** hinzugefügt. Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f5953-p106">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f5953-123">Nachdem Sie Mitglieder hinzugefügt oder aus der Rollengruppe entfernt haben, müssen sich die betroffenen Benutzer möglicherweise abmelden und dann erneut anmelden, um die Änderung ihrer Administratorrechten zu sehen.</span><span class="sxs-lookup"><span data-stu-id="f5953-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="f5953-124">Entfernen von Mitgliedern aus Administratorrollengruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="f5953-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="f5953-125">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, klicken Sie auf die Rollengruppe, aus der Sie einen Benutzer oder Benutzer entfernen möchten, und](../../media/ITPro-EAC-EditIcon.gif)klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![.</span><span class="sxs-lookup"><span data-stu-id="f5953-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="f5953-126">Wählen Sie unter Mitglieder die Benutzer aus, die Sie entfernen möchten, und klicken \*\*\*\* ![Sie auf Entfernen](../../media/ITPro-EAC-RemoveIcon.gif)-Symbol entfernen.</span><span class="sxs-lookup"><span data-stu-id="f5953-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="f5953-p107">Klicken Sie auf **Speichern**, um die Änderung an der Rollengruppe zu speichern und zur Seite **Administratorrollen** zurückzukehren. Überprüfen Sie im Detailfenster für die ausgewählte Rollengruppe, ob das Mitglied nicht länger unter Mitglieder aufgeführt wird, um sicherzustellen, dass der Benutzer erfolgreich aus der Administratorrollengruppe entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="f5953-p107">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f5953-129">Nachdem Sie Mitglieder hinzugefügt oder aus der Rollengruppe entfernt haben, müssen sich die betroffenen Benutzer möglicherweise abmelden und dann erneut anmelden, um die Änderung ihrer Administratorrechten zu sehen.</span><span class="sxs-lookup"><span data-stu-id="f5953-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f5953-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5953-130">For more information</span></span>

[<span data-ttu-id="f5953-131">Featureberechtigungen in EOP</span><span class="sxs-lookup"><span data-stu-id="f5953-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
