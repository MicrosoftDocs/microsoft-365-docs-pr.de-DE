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
ms.openlocfilehash: 9522499b3861f0f0e44fcbf09896a5c93feed95d
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337253"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="c3460-104">Benutzertags in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="c3460-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="c3460-105">Benutzer Tags sind Bezeichner für bestimmte Benutzergruppen in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c3460-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="c3460-106">[Priority Accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sind ein Typ von User-Tag.</span><span class="sxs-lookup"><span data-stu-id="c3460-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="c3460-107">Wenn Ihre Organisation Office 365 ATP-Plan 2 (in Ihrem Abonnement oder als Add-on enthalten) hat, können Sie benutzerdefinierte Benutzer Tags zusätzlich zur Verwendung des Tags Priority Accounts erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3460-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="c3460-108">Nachdem Sie Tags auf bestimmte Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="c3460-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="c3460-109">Warnungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="c3460-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="c3460-110">Threat Explorer und Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="c3460-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="c3460-111">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="c3460-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="c3460-112">Kampagnenansichten</span><span class="sxs-lookup"><span data-stu-id="c3460-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="c3460-113">In diesem Artikel wird erklärt, wie Sie Benutzer Tags im Security & Compliance Center konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c3460-113">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="c3460-114">Es gibt keine Cmdlets in Security & Compliance Center zum Verwalten von Benutzer Tags.</span><span class="sxs-lookup"><span data-stu-id="c3460-114">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3460-115">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="c3460-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3460-116">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c3460-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c3460-117">Wenn Sie direkt zur Seite **Benutzer Tags** wechseln möchten, öffnen Sie <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="c3460-117">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="c3460-118">Um Benutzer Tags zu erstellen, zu ändern oder zu entfernen, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="c3460-118">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="c3460-119">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c3460-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="c3460-120">Sie können auch Prioritäts Konten im Microsoft 365 Admin Center verwalten und überwachen.</span><span class="sxs-lookup"><span data-stu-id="c3460-120">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c3460-121">Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritäts Konten](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="c3460-121">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="c3460-122">Erstellen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="c3460-122">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="c3460-123">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="c3460-123">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="c3460-124">Klicken Sie auf der Seite **Benutzer Tags** , die geöffnet wird, auf **Tag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c3460-124">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="c3460-125">Der Assistent zum **Erstellen von Tags** wird in einem neuen Fly Out geöffnet. Konfigurieren Sie auf der Seite **Tag definieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c3460-125">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="c3460-126">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="c3460-126">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="c3460-127">Dies ist der Wert, den Sie sehen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3460-127">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="c3460-128">**Beschreibung**: Geben Sie eine optionale Beschreibung für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="c3460-128">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="c3460-129">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c3460-129">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c3460-130">Führen Sie auf der Seite **Postfächer zuweisen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c3460-130">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="c3460-131">Klicken Sie auf **Postfächer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c3460-131">Click **Add mailboxes**.</span></span> <span data-ttu-id="c3460-132">Führen Sie im angezeigten Fenster einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="c3460-132">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="c3460-133">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste aus, um einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c3460-133">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="c3460-134">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c3460-134">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="c3460-135">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="c3460-135">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="c3460-136">Wenn Sie einzelne Einträge aus dem Feld entfernen möchten **, klicken Sie** ![ im Feld auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) für den Benutzer oder die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="c3460-136">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="c3460-137">Wenn Sie vorhandene Einträge aus der Liste unter dem Feld entfernen möchten **Remove** , klicken Sie auf Remove ![ Icon ](../../media/scc-remove-icon.png) the entry entfernen.</span><span class="sxs-lookup"><span data-stu-id="c3460-137">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="c3460-138">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c3460-138">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="c3460-139">Klicken Sie auf **importieren** , um eine Textdatei auszuwählen, die die e-Mail-Adressen der Benutzer oder Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="c3460-139">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="c3460-140">Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="c3460-140">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="c3460-141">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c3460-141">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c3460-142">Überprüfen Sie auf der Seite **Tag überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c3460-142">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="c3460-143">Sie können auf **Bearbeiten** im bestimmten Abschnitt klicken, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c3460-143">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="c3460-144">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="c3460-144">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="c3460-145">Verwenden des Sicherheitscenters zum Anzeigen von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="c3460-145">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="c3460-146">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="c3460-146">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="c3460-147">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten (Klicken Sie nicht auf das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="c3460-147">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="c3460-148">Überprüfen Sie die Einstellungen in den angezeigten Details im Bereich Schreibschutz.</span><span class="sxs-lookup"><span data-stu-id="c3460-148">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="c3460-149">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="c3460-149">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="c3460-150">Verwenden des Sicherheitscenters zum Ändern von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="c3460-150">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="c3460-151">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="c3460-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="c3460-152">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **Tag bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c3460-152">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="c3460-153">Der Richtlinien-Assistent wird in einem **Edit-Tag** geöffnet, um zu fliegen. Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c3460-153">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="c3460-154">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="c3460-154">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="c3460-155">Entfernen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="c3460-155">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="c3460-156">**Hinweis**: Sie können das integrierte **Priority-Konto** -Tag nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="c3460-156">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="c3460-157">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="c3460-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="c3460-158">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf **Tag löschen**, und wählen Sie dann **Ja, entfernen** in der angezeigten Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="c3460-158">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
