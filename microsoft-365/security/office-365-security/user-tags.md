---
title: Benutzer Tags in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie bestimmte Benutzergruppen mit Benutzer Tags in Microsoft Defender für Office 365 Plan 2 identifiziert werden. Die Tag-Filterung steht in Warnungen, Berichten und Untersuchungen in Microsoft Defender für Office 365 zur Verfügung, um die getaggten Benutzer schnell zu identifizieren.
ms.openlocfilehash: 9c83a323a3116b3da61a133c7fb449978ca13841
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945318"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e57ba-104">Benutzer Tags in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="e57ba-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="e57ba-105">Das Feature "Benutzer Tags" befindet sich in der Vorschau, steht nicht allen zur Verfügung und kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e57ba-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="e57ba-106">Weitere Informationen zum Veröffentlichungszeitplan finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="e57ba-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="e57ba-107">Benutzer Tags sind Bezeichner für bestimmte Benutzergruppen in [Microsoft Defender für Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="e57ba-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="e57ba-108">Es gibt zwei Arten von Benutzer Tags:</span><span class="sxs-lookup"><span data-stu-id="e57ba-108">There are two types of user tags:</span></span>

- <span data-ttu-id="e57ba-109">**System-Tags** : derzeit ist [Priority Accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) der einzige Typ des System Tags.</span><span class="sxs-lookup"><span data-stu-id="e57ba-109">**System tags** : Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="e57ba-110">**Benutzerdefinierte Tags** : Sie erstellen diese Benutzer Tags selbst.</span><span class="sxs-lookup"><span data-stu-id="e57ba-110">**Custom tags** : You create these user tags yourself.</span></span>

<span data-ttu-id="e57ba-111">Wenn Ihre Organisation Defender für Office 365 Plan 2 (in Ihrem Abonnement oder als Add-on enthalten) verfügt, können Sie benutzerdefinierte Benutzer Tags zusätzlich zur Verwendung des Tags Priority Accounts erstellen.</span><span class="sxs-lookup"><span data-stu-id="e57ba-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="e57ba-112">Nachdem Sie System Tags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e57ba-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="e57ba-113">Warnungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e57ba-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="e57ba-114">Threat Explorer und Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="e57ba-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="e57ba-115">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e57ba-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="e57ba-116">Kampagnenansichten</span><span class="sxs-lookup"><span data-stu-id="e57ba-116">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="e57ba-117">In diesem Artikel wird erklärt, wie Sie Benutzer Tags im Security & Compliance Center konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e57ba-117">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="e57ba-118">Es gibt keine Cmdlets in Security & Compliance Center zum Verwalten von Benutzer Tags.</span><span class="sxs-lookup"><span data-stu-id="e57ba-118">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e57ba-119">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="e57ba-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e57ba-120">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e57ba-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e57ba-121">Wenn Sie direkt zur Seite **Benutzer Tags** wechseln möchten, öffnen Sie <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="e57ba-121">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="e57ba-122">Zum Erstellen, ändern oder entfernen **benutzerdefinierter Benutzer Tags** müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="e57ba-122">To create, modify, or remove **custom user tags** , you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="e57ba-123">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e57ba-123">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e57ba-124">Zum Konfigurieren von Prioritäts Konten (System-Tags) müssen Sie ein [globaler Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) oder ein [Exchange-Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)sein.</span><span class="sxs-lookup"><span data-stu-id="e57ba-124">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="e57ba-125">Sie können auch Prioritäts Konten im Microsoft 365 Admin Center verwalten und überwachen.</span><span class="sxs-lookup"><span data-stu-id="e57ba-125">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e57ba-126">Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritäts Konten](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="e57ba-126">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="e57ba-127">Erstellen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="e57ba-127">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="e57ba-128">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-128">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="e57ba-129">Klicken Sie auf der Seite **Benutzer Tags** , die geöffnet wird, auf **Tag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-129">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="e57ba-130">Der Assistent zum **Erstellen von Tags** wird in einem neuen Fly Out geöffnet. Konfigurieren Sie auf der Seite **Tag definieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="e57ba-130">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="e57ba-131">**Name** : Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="e57ba-131">**Name** : Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="e57ba-132">Dies ist der Wert, den Sie sehen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="e57ba-132">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="e57ba-133">**Beschreibung** : Geben Sie eine optionale Beschreibung für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="e57ba-133">**Description** : Enter an optional description for the tag.</span></span>

   <span data-ttu-id="e57ba-134">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-134">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e57ba-135">Führen Sie auf der Seite **Postfächer zuweisen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e57ba-135">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="e57ba-136">Klicken Sie auf **Postfächer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-136">Click **Add mailboxes**.</span></span> <span data-ttu-id="e57ba-137">Führen Sie im angezeigten Fenster einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="e57ba-137">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="e57ba-138">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste aus, um einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e57ba-138">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="e57ba-139">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e57ba-139">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="e57ba-140">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="e57ba-140">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="e57ba-141">Wenn Sie einzelne Einträge aus dem Feld entfernen möchten **, klicken Sie** ![ im Feld auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) für den Benutzer oder die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="e57ba-141">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="e57ba-142">Wenn Sie vorhandene Einträge aus der Liste unter dem Feld entfernen möchten **Remove** , klicken Sie auf Remove ![ Icon ](../../media/scc-remove-icon.png) the entry entfernen.</span><span class="sxs-lookup"><span data-stu-id="e57ba-142">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="e57ba-143">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-143">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="e57ba-144">Klicken Sie auf **importieren** , um eine Textdatei auszuwählen, die die e-Mail-Adressen der Benutzer oder Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="e57ba-144">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="e57ba-145">Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="e57ba-145">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="e57ba-146">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-146">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e57ba-147">Überprüfen Sie auf der Seite **Tag überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e57ba-147">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="e57ba-148">Sie können auf **Bearbeiten** im bestimmten Abschnitt klicken, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="e57ba-148">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="e57ba-149">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-149">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="e57ba-150">Verwenden des Sicherheitscenters zum Anzeigen von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="e57ba-150">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="e57ba-151">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="e57ba-152">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten (Klicken Sie nicht auf das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="e57ba-152">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="e57ba-153">Überprüfen Sie die Einstellungen in den angezeigten Details im Bereich Schreibschutz.</span><span class="sxs-lookup"><span data-stu-id="e57ba-153">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="e57ba-154">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-154">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="e57ba-155">Verwenden des Sicherheitscenters zum Ändern von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="e57ba-155">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="e57ba-156">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-156">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="e57ba-157">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **Tag bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-157">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="e57ba-158">Der Richtlinien-Assistent wird in einem **Edit-Tag** geöffnet, um zu fliegen. Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e57ba-158">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="e57ba-159">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="e57ba-160">Entfernen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="e57ba-160">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="e57ba-161">**Hinweis** : Sie können das integrierte **Priority-Konto** -Tag nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="e57ba-161">**Note** : You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="e57ba-162">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="e57ba-162">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="e57ba-163">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf **Tag löschen** , und wählen Sie dann **Ja, entfernen** in der angezeigten Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="e57ba-163">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag** , and then select **Yes, remove** in the warning that appears.</span></span>
