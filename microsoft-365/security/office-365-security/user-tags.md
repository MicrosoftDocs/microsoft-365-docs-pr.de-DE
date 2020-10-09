---
title: Benutzertags in Office 365 ATP
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
description: Administratoren können erfahren, wie bestimmte Benutzergruppen mit Benutzer Tags in Office 365 ATP-Plan 2 identifiziert werden. Die Tag-Filterung ist für Warnungen, Berichte und Untersuchungen in Office 365 ATP verfügbar, um die getaggten Benutzer schnell zu identifizieren.
ms.openlocfilehash: 16e756b95e16e40f4df738e825e842681c67e22c
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399385"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="f835a-104">Benutzertags in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f835a-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="f835a-105">Benutzer Tags sind Bezeichner für bestimmte Benutzergruppen in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="f835a-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="f835a-106">Es gibt zwei Arten von Benutzer Tags:</span><span class="sxs-lookup"><span data-stu-id="f835a-106">There are two types of user tags:</span></span>

- <span data-ttu-id="f835a-107">**System-Tags**: derzeit ist [Priority Accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) der einzige Typ des System Tags.</span><span class="sxs-lookup"><span data-stu-id="f835a-107">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="f835a-108">**Benutzerdefinierte Tags**: Sie erstellen diese Benutzer Tags selbst.</span><span class="sxs-lookup"><span data-stu-id="f835a-108">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="f835a-109">Wenn Ihre Organisation Office 365 ATP-Plan 2 (in Ihrem Abonnement oder als Add-on enthalten) hat, können Sie benutzerdefinierte Benutzer Tags zusätzlich zur Verwendung des Tags Priority Accounts erstellen.</span><span class="sxs-lookup"><span data-stu-id="f835a-109">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="f835a-110">Nachdem Sie System Tags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="f835a-110">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="f835a-111">Warnungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f835a-111">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="f835a-112">Threat Explorer und Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="f835a-112">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="f835a-113">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="f835a-113">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="f835a-114">Kampagnenansichten</span><span class="sxs-lookup"><span data-stu-id="f835a-114">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="f835a-115">In diesem Artikel wird erklärt, wie Sie Benutzer Tags im Security & Compliance Center konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f835a-115">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="f835a-116">Es gibt keine Cmdlets in Security & Compliance Center zum Verwalten von Benutzer Tags.</span><span class="sxs-lookup"><span data-stu-id="f835a-116">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f835a-117">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f835a-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f835a-118">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f835a-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f835a-119">Wenn Sie direkt zur Seite **Benutzer Tags** wechseln möchten, öffnen Sie <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="f835a-119">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="f835a-120">Zum Erstellen, ändern oder entfernen **benutzerdefinierter Benutzer Tags**müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="f835a-120">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="f835a-121">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f835a-121">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f835a-122">Zum Konfigurieren von Prioritäts Konten (System-Tags) müssen Sie ein [globaler Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) oder ein [Exchange-Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)sein.</span><span class="sxs-lookup"><span data-stu-id="f835a-122">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="f835a-123">Sie können auch Prioritäts Konten im Microsoft 365 Admin Center verwalten und überwachen.</span><span class="sxs-lookup"><span data-stu-id="f835a-123">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f835a-124">Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritäts Konten](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="f835a-124">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="f835a-125">Erstellen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="f835a-125">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="f835a-126">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="f835a-126">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="f835a-127">Klicken Sie auf der Seite **Benutzer Tags** , die geöffnet wird, auf **Tag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f835a-127">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="f835a-128">Der Assistent zum **Erstellen von Tags** wird in einem neuen Fly Out geöffnet. Konfigurieren Sie auf der Seite **Tag definieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f835a-128">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="f835a-129">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="f835a-129">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="f835a-130">Dies ist der Wert, den Sie sehen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="f835a-130">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="f835a-131">**Beschreibung**: Geben Sie eine optionale Beschreibung für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="f835a-131">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="f835a-132">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f835a-132">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f835a-133">Führen Sie auf der Seite **Postfächer zuweisen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f835a-133">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="f835a-134">Klicken Sie auf **Postfächer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f835a-134">Click **Add mailboxes**.</span></span> <span data-ttu-id="f835a-135">Führen Sie im angezeigten Fenster einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f835a-135">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="f835a-136">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste aus, um einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f835a-136">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="f835a-137">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f835a-137">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="f835a-138">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="f835a-138">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="f835a-139">Wenn Sie einzelne Einträge aus dem Feld entfernen möchten **, klicken Sie** ![ im Feld auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) für den Benutzer oder die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="f835a-139">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="f835a-140">Wenn Sie vorhandene Einträge aus der Liste unter dem Feld entfernen möchten **Remove** , klicken Sie auf Remove ![ Icon ](../../media/scc-remove-icon.png) the entry entfernen.</span><span class="sxs-lookup"><span data-stu-id="f835a-140">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="f835a-141">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f835a-141">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="f835a-142">Klicken Sie auf **importieren** , um eine Textdatei auszuwählen, die die e-Mail-Adressen der Benutzer oder Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="f835a-142">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="f835a-143">Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="f835a-143">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="f835a-144">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f835a-144">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f835a-145">Überprüfen Sie auf der Seite **Tag überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f835a-145">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="f835a-146">Sie können auf **Bearbeiten** im bestimmten Abschnitt klicken, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f835a-146">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="f835a-147">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="f835a-147">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="f835a-148">Verwenden des Sicherheitscenters zum Anzeigen von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="f835a-148">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="f835a-149">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="f835a-149">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="f835a-150">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten (Klicken Sie nicht auf das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="f835a-150">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="f835a-151">Überprüfen Sie die Einstellungen in den angezeigten Details im Bereich Schreibschutz.</span><span class="sxs-lookup"><span data-stu-id="f835a-151">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="f835a-152">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f835a-152">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="f835a-153">Verwenden des Sicherheitscenters zum Ändern von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="f835a-153">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="f835a-154">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="f835a-154">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="f835a-155">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **Tag bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f835a-155">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="f835a-156">Der Richtlinien-Assistent wird in einem **Edit-Tag** geöffnet, um zu fliegen. Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f835a-156">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="f835a-157">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="f835a-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="f835a-158">Entfernen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="f835a-158">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="f835a-159">**Hinweis**: Sie können das integrierte **Priority-Konto** -Tag nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="f835a-159">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="f835a-160">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="f835a-160">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="f835a-161">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf **Tag löschen**, und wählen Sie dann **Ja, entfernen** in der angezeigten Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="f835a-161">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
