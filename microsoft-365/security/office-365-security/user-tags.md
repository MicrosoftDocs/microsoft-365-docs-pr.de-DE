---
title: Benutzer Tags
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
description: Administratoren können erfahren, wie bestimmte Benutzergruppen mit Benutzer Tags in Oiffce 365 ATP Plan 2 identifiziert werden. Die Tag-Filterung ist für Warnungen, Berichte und Untersuchungen in Office 365 ATP verfügbar, um die getaggten Benutzer schnell zu identifizieren.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210026"
---
# <a name="user-tags-in-the-microsoft-security-center"></a><span data-ttu-id="69114-104">Benutzer Tags im Microsoft-Sicherheits Center</span><span class="sxs-lookup"><span data-stu-id="69114-104">User tags in the Microsoft Security Center</span></span>

<span data-ttu-id="69114-105">Benutzer Tags sind Bezeichner für bestimmte Benutzergruppen in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="69114-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="69114-106">[Priority Accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sind ein Typ von User-Tag.</span><span class="sxs-lookup"><span data-stu-id="69114-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="69114-107">Wenn Ihre Organisation Office 365 ATP-Plan 2 (in Ihrem Abonnement oder als Add-on enthalten) hat, können Sie benutzerdefinierte Benutzer Tags zusätzlich zur Verwendung des Tags Priority Accounts erstellen.</span><span class="sxs-lookup"><span data-stu-id="69114-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="69114-108">Nachdem Sie Tags auf bestimmte Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="69114-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="69114-109">Warnungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="69114-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="69114-110">Threat Explorer und Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="69114-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="69114-111">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="69114-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="69114-112">Kampagnenansichten</span><span class="sxs-lookup"><span data-stu-id="69114-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="69114-113">In diesem Artikel wird erläutert, wie Benutzer Tags im Sicherheits Center konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="69114-113">This article explains how to configure user tags in the Security Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="69114-114">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="69114-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="69114-115">Sie öffnen das Sicherheits Center unter <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="69114-115">You open the Security Center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="69114-116">Wenn Sie direkt zur Seite **Benutzer Tags** wechseln möchten, öffnen Sie <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="69114-116">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="69114-117">Um Benutzer Tags zu erstellen, zu ändern oder zu entfernen, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="69114-117">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="69114-118">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="69114-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="69114-119">Sie können auch Prioritäts Konten im Microsoft 365 Admin Center verwalten und überwachen.</span><span class="sxs-lookup"><span data-stu-id="69114-119">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="69114-120">Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritäts Konten](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="69114-120">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="69114-121">Erstellen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="69114-121">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="69114-122">Wechseln Sie im Sicherheits Center zu **Einstellungen** \> **e-Mail-& Collaboration-** \> **Benutzer Tags**.</span><span class="sxs-lookup"><span data-stu-id="69114-122">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="69114-123">Klicken Sie auf der Seite **Benutzer Tags** , die geöffnet wird, auf **Tag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="69114-123">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="69114-124">Der Assistent zum **Erstellen von Tags** wird in einem neuen Fly Out geöffnet. Konfigurieren Sie auf der Seite **Tag definieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="69114-124">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="69114-125">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="69114-125">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="69114-126">Dies ist der Wert, den Sie sehen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="69114-126">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="69114-127">**Beschreibung**: Geben Sie eine optionale Beschreibung für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="69114-127">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="69114-128">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="69114-128">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="69114-129">Führen Sie auf der Seite **Postfächer zuweisen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="69114-129">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="69114-130">Klicken Sie auf **Postfächer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="69114-130">Click **Add mailboxes**.</span></span> <span data-ttu-id="69114-131">Führen Sie im angezeigten Fenster einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="69114-131">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="69114-132">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste aus, um einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="69114-132">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="69114-133">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="69114-133">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="69114-134">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="69114-134">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="69114-135">Wenn Sie einzelne Einträge aus dem Feld entfernen möchten **, klicken Sie** ![ im Feld auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) für den Benutzer oder die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="69114-135">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="69114-136">Wenn Sie vorhandene Einträge aus der Liste unter dem Feld entfernen möchten **Remove** , klicken Sie auf Remove ![ Icon ](../../media/scc-remove-icon.png) the entry entfernen.</span><span class="sxs-lookup"><span data-stu-id="69114-136">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="69114-137">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="69114-137">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="69114-138">Klicken Sie auf **importieren** , um eine Textdatei auszuwählen, die die e-Mail-Adressen der Benutzer oder Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="69114-138">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="69114-139">Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="69114-139">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="69114-140">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="69114-140">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="69114-141">Überprüfen Sie auf der Seite **Tag überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="69114-141">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="69114-142">Sie können auf **Bearbeiten** im bestimmten Abschnitt klicken, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="69114-142">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="69114-143">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="69114-143">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="69114-144">Verwenden des Sicherheitscenters zum Anzeigen von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="69114-144">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="69114-145">Wechseln Sie im Sicherheits Center zu **Einstellungen** \> **e-Mail-& Collaboration-** \> **Benutzer Tags**.</span><span class="sxs-lookup"><span data-stu-id="69114-145">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="69114-146">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten (Klicken Sie nicht auf das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="69114-146">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="69114-147">Überprüfen Sie die Einstellungen in den angezeigten Details im Bereich Schreibschutz.</span><span class="sxs-lookup"><span data-stu-id="69114-147">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="69114-148">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="69114-148">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="69114-149">Verwenden des Sicherheitscenters zum Ändern von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="69114-149">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="69114-150">Wechseln Sie im Sicherheits Center zu **Einstellungen** \> **e-Mail-& Collaboration-** \> **Benutzer Tags**.</span><span class="sxs-lookup"><span data-stu-id="69114-150">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="69114-151">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **Tag bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="69114-151">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="69114-152">Der Richtlinien-Assistent wird in einem **Edit-Tag** geöffnet, um zu fliegen. Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="69114-152">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="69114-153">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="69114-153">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="69114-154">Entfernen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="69114-154">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="69114-155">**Hinweis**: Sie können das integrierte **Priority-Konto** -Tag nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="69114-155">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="69114-156">Wechseln Sie im Sicherheits Center zu **Einstellungen** \> **e-Mail-& Collaboration-** \> **Benutzer Tags**.</span><span class="sxs-lookup"><span data-stu-id="69114-156">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="69114-157">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf **Tag löschen**, und wählen Sie dann **Ja, entfernen** in der angezeigten Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="69114-157">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
