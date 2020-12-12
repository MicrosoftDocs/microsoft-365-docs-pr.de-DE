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
ms.openlocfilehash: ad06bf90f1ecb93d671bfcad6fad0b4f2a952cb2
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663607"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="5ef31-104">Benutzer Tags in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="5ef31-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="5ef31-105">Das Feature "Benutzer Tags" befindet sich in der Vorschau, steht nicht allen zur Verfügung und kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5ef31-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="5ef31-106">Weitere Informationen zum Veröffentlichungszeitplan finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="5ef31-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="5ef31-107">Benutzer Tags sind Bezeichner für bestimmte Benutzergruppen in [Microsoft Defender für Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="5ef31-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="5ef31-108">Es gibt zwei Arten von Benutzer Tags:</span><span class="sxs-lookup"><span data-stu-id="5ef31-108">There are two types of user tags:</span></span>

- <span data-ttu-id="5ef31-109">**System-Tags**: derzeit ist [Priority Accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) der einzige Typ des System Tags.</span><span class="sxs-lookup"><span data-stu-id="5ef31-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="5ef31-110">**Benutzerdefinierte Tags**: Sie erstellen diese Benutzer Tags selbst.</span><span class="sxs-lookup"><span data-stu-id="5ef31-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="5ef31-111">Wenn Ihre Organisation Defender für Office 365 Plan 2 (in Ihrem Abonnement oder als Add-on enthalten) verfügt, können Sie benutzerdefinierte Benutzer Tags zusätzlich zur Verwendung des Tags Priority Accounts erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ef31-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="5ef31-112">Nachdem Sie System Tags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="5ef31-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="5ef31-113">Warnungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5ef31-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="5ef31-114">Threat Explorer und Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="5ef31-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="5ef31-115">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="5ef31-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="5ef31-116">Kampagnenansichten</span><span class="sxs-lookup"><span data-stu-id="5ef31-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="5ef31-117">Für Prioritäts Konten können Sie den [Bericht über e-Mail-Probleme für Priority-Konten](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) im Exchange Admin Center (EAC) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ef31-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="5ef31-118">In diesem Artikel wird erklärt, wie Sie Benutzer Tags im Security & Compliance Center konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5ef31-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="5ef31-119">Es gibt keine Cmdlets in Security & Compliance Center zum Verwalten von Benutzer Tags.</span><span class="sxs-lookup"><span data-stu-id="5ef31-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ef31-120">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="5ef31-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5ef31-121">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="5ef31-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5ef31-122">Wenn Sie direkt zur Seite **Benutzer Tags** wechseln möchten, öffnen Sie <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="5ef31-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="5ef31-123">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="5ef31-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5ef31-124">Zum Erstellen, ändern und Löschen von Benutzer Tags müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="5ef31-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="5ef31-125">Zum Hinzufügen und Entfernen von Mitgliedern aus vorhandenen Benutzer Tags müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung**", " **Sicherheits Administrator**" oder " **Sicherheits Operator** " sein.</span><span class="sxs-lookup"><span data-stu-id="5ef31-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="5ef31-126">Für den schreibgeschützten Zugriff auf Benutzer Tags müssen Sie ein Mitglied der Rollengruppen " **globaler Leser** " oder " **Sicherheits Leser** " sein.</span><span class="sxs-lookup"><span data-stu-id="5ef31-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="5ef31-127">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5ef31-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="5ef31-128">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="5ef31-128">**Notes**:</span></span>

  - <span data-ttu-id="5ef31-129">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ef31-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5ef31-130">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="5ef31-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="5ef31-131">Die Verwaltung von Benutzer Tags wird von den Rollen " **Transponderleser**", " **Tag mitwirk** enden" und " **Tag-Manager** " gesteuert.</span><span class="sxs-lookup"><span data-stu-id="5ef31-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="5ef31-132">Sie können auch Prioritäts Konten im Microsoft 365 Admin Center verwalten und überwachen.</span><span class="sxs-lookup"><span data-stu-id="5ef31-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5ef31-133">Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritäts Konten](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="5ef31-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="5ef31-134">Erstellen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="5ef31-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="5ef31-135">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="5ef31-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="5ef31-136">Klicken Sie auf der Seite **Benutzer Tags** , die geöffnet wird, auf **Tag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="5ef31-137">Der Assistent zum **Erstellen von Tags** wird in einem neuen Fly Out geöffnet. Konfigurieren Sie auf der Seite **Tag definieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="5ef31-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="5ef31-138">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="5ef31-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="5ef31-139">Dies ist der Wert, den Sie sehen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ef31-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="5ef31-140">**Beschreibung**: Geben Sie eine optionale Beschreibung für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="5ef31-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="5ef31-141">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="5ef31-142">Führen Sie auf der Seite **Benutzer zuweisen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5ef31-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="5ef31-143">Klicken Sie auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-143">Click **Add users**.</span></span> <span data-ttu-id="5ef31-144">Führen Sie im angezeigten Fenster einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="5ef31-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="5ef31-145">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste aus, um einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5ef31-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="5ef31-146">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5ef31-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="5ef31-147">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="5ef31-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="5ef31-148">Wenn Sie einzelne Einträge aus dem Feld entfernen möchten **, klicken Sie** ![ im Feld auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) für den Benutzer oder die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="5ef31-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="5ef31-149">Wenn Sie vorhandene Einträge aus der Liste unter dem Feld entfernen möchten  , klicken Sie auf Remove ![ Icon ](../../media/scc-remove-icon.png) the entry entfernen.</span><span class="sxs-lookup"><span data-stu-id="5ef31-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="5ef31-150">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="5ef31-151">Klicken Sie auf **importieren** , um eine Textdatei auszuwählen, die die e-Mail-Adressen der Benutzer oder Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="5ef31-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="5ef31-152">Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="5ef31-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="5ef31-153">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="5ef31-154">Überprüfen Sie auf der Seite **Tag überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="5ef31-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="5ef31-155">Sie können auf **Bearbeiten** im bestimmten Abschnitt klicken, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="5ef31-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="5ef31-156">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="5ef31-157">Verwenden des Sicherheitscenters zum Anzeigen von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="5ef31-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="5ef31-158">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="5ef31-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="5ef31-159">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten (Klicken Sie nicht auf das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="5ef31-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="5ef31-160">Überprüfen Sie die Einstellungen in den angezeigten Details im Bereich Schreibschutz.</span><span class="sxs-lookup"><span data-stu-id="5ef31-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="5ef31-161">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="5ef31-162">Verwenden des Sicherheitscenters zum Ändern von Benutzer Tags</span><span class="sxs-lookup"><span data-stu-id="5ef31-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="5ef31-163">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="5ef31-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="5ef31-164">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **Tag bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="5ef31-165">Der Richtlinien-Assistent wird in einem **Edit-Tag** geöffnet, um zu fliegen. Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5ef31-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="5ef31-166">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="5ef31-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="5ef31-167">Entfernen von Benutzer Tags mithilfe des Sicherheitscenters</span><span class="sxs-lookup"><span data-stu-id="5ef31-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="5ef31-168">**Hinweis**: Sie können das integrierte **Priority-Konto** -Tag nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="5ef31-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="5ef31-169">Wechseln Sie im Sicherheits Center zu Benutzer Tags für die **Bedrohungs Verwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="5ef31-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="5ef31-170">Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf **Tag löschen**, und wählen Sie dann **Ja, entfernen** in der angezeigten Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="5ef31-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
