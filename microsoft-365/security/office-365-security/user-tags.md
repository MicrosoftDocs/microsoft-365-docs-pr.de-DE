---
title: Benutzertags in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie bestimmte Benutzergruppen mit Benutzertags in Microsoft Defender für Office 365 Plan 2 identifizieren. Die Tagfilterung ist in Warnungen, Berichten und Untersuchungen in Microsoft Defender für Office 365 verfügbar, um die markierten Benutzer schnell zu identifizieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4c439dcb91831475bc10da4a01d0fa29e7aae359
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632202"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3653f-104">Benutzertags in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="3653f-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="3653f-105">Das Feature für Benutzertags befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3653f-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="3653f-106">Informationen zum Veröffentlichungszeitplan finden Sie in [der Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="3653f-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="3653f-107">Benutzertags sind Bezeichner für bestimmte Benutzergruppen in [Microsoft Defender für Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="3653f-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="3653f-108">Es gibt zwei Arten von Benutzertags:</span><span class="sxs-lookup"><span data-stu-id="3653f-108">There are two types of user tags:</span></span>

- <span data-ttu-id="3653f-109">**Systemtags**: Derzeit sind [Prioritätskonten](../../admin/setup/priority-accounts.md) der einzige Systemtagtyp.</span><span class="sxs-lookup"><span data-stu-id="3653f-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="3653f-110">**Benutzerdefinierte Tags:** Sie erstellen diese Benutzertags selbst.</span><span class="sxs-lookup"><span data-stu-id="3653f-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="3653f-111">Wenn Ihre Organisation Defender für Office 365 Plan 2 (in Ihrem Abonnement oder als Add-On enthalten) hat, können Sie zusätzlich zum Prioritätskontotag benutzerdefinierte Benutzertags erstellen.</span><span class="sxs-lookup"><span data-stu-id="3653f-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="3653f-112">Derzeit können Sie Benutzertags nur auf Postfachbenutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="3653f-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="3653f-113">Nachdem Sie Systemtags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="3653f-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="3653f-114">Warnungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="3653f-114">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="3653f-115">Bedrohungs-Explorer und Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="3653f-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="3653f-116">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="3653f-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="3653f-117">Kampagnenansichten</span><span class="sxs-lookup"><span data-stu-id="3653f-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="3653f-118">Für Prioritätskonten können Sie den Bericht [E-Mail-Probleme für Prioritätskonten](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) im Exchange Admin Center (EAC) verwenden.</span><span class="sxs-lookup"><span data-stu-id="3653f-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="3653f-119">In diesem Artikel wird erläutert, wie Sie Benutzertags im Security & Compliance Center konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3653f-119">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="3653f-120">Es gibt keine Cmdlets im Security & Compliance Center zum Verwalten von Benutzertags.</span><span class="sxs-lookup"><span data-stu-id="3653f-120">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="3653f-121">Informationen dazu, wie Benutzertags Teil der Strategie zum Schutz von Benutzerkonten mit hoher Auswirkung sind, finden Sie unter Sicherheitsempfehlungen für Prioritätskonten [in Microsoft 365](security-recommendations-for-priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="3653f-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3653f-122">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="3653f-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3653f-123">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3653f-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3653f-124">Öffnen Sie , um direkt zur **Seite Benutzertags zu** <https://protection.office.com/userTags> wechseln.</span><span class="sxs-lookup"><span data-stu-id="3653f-124">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="3653f-125">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3653f-125">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3653f-126">Zum Erstellen, Ändern und Löschen von Benutzertags müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="3653f-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3653f-127">Zum Hinzufügen und Entfernen von Mitgliedern aus vorhandenen Benutzertags müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung,** Sicherheitsadministrator **oder** **Sicherheitsoperator** sein.</span><span class="sxs-lookup"><span data-stu-id="3653f-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="3653f-128">Für den schreibgeschützten Zugriff auf Benutzertags müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="3653f-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="3653f-129">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3653f-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="3653f-130">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="3653f-130">**Notes**:</span></span>

  - <span data-ttu-id="3653f-131">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3653f-131">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3653f-132">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3653f-132">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="3653f-133">Die Verwaltung von Benutzertagen wird durch die **Rollen Tag Reader und** Tag **Manager** gesteuert.</span><span class="sxs-lookup"><span data-stu-id="3653f-133">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="3653f-134">Sie können auch Prioritätskonten im Microsoft 365 Admin Center verwalten und überwachen.</span><span class="sxs-lookup"><span data-stu-id="3653f-134">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3653f-135">Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritätskonten](../../admin/setup/priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="3653f-135">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="3653f-136">Informationen zum Sichern _privilegierter Konten_ (Administratorkonten) finden Sie [in diesem Thema.](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="3653f-136">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="3653f-137">Erstellen von Benutzertags mithilfe & Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="3653f-137">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="3653f-138">Wechseln Sie im Security & Compliance Center zu **Benutzertags für die Bedrohungsverwaltung.** \> </span><span class="sxs-lookup"><span data-stu-id="3653f-138">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="3653f-139">Klicken Sie **auf der** geöffneten Seite Benutzertags auf **Tag erstellen.**</span><span class="sxs-lookup"><span data-stu-id="3653f-139">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="3653f-140">Der **Assistent zum Erstellen** von Tag wird in einem neuen Fly-Out geöffnet. Konfigurieren Sie **auf** der Seite Tag definieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3653f-140">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="3653f-141">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="3653f-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="3653f-142">Dies ist der Wert, den Sie sehen und verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="3653f-142">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="3653f-143">**Beschreibung**: Geben Sie eine optionale Beschreibung für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="3653f-143">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="3653f-144">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3653f-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3653f-145">Gehen Sie **auf der** Seite Benutzer zuweisen wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="3653f-145">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="3653f-146">Klicken **Sie auf Benutzer hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="3653f-146">Click **Add users**.</span></span> <span data-ttu-id="3653f-147">Gehen Sie in dem angezeigten Fly-Out wie folgt vor, um einzelne Benutzer oder Gruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="3653f-147">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="3653f-148">Klicken Sie in das Feld, und scrollen Sie durch die Liste, um einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3653f-148">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="3653f-149">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3653f-149">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="3653f-150">Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3653f-150">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="3653f-151">Klicken Sie zum Entfernen einzelner  Einträge aus dem Feld auf Entfernen (Symbol entfernen) für den Benutzer ![ oder die Gruppe im ](../../media/scc-remove-icon.png) Feld.</span><span class="sxs-lookup"><span data-stu-id="3653f-151">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="3653f-152">Wenn Sie vorhandene Einträge aus der Liste unterhalb des Felds entfernen möchten, klicken Sie auf **Entfernen** ![ Symbol für den ](../../media/scc-remove-icon.png) Eintrag.</span><span class="sxs-lookup"><span data-stu-id="3653f-152">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="3653f-153">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3653f-153">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="3653f-154">Klicken **Sie auf Importieren,** um eine Textdatei auszuwählen, die die E-Mail-Adressen der Benutzer oder Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="3653f-154">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="3653f-155">Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="3653f-155">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="3653f-156">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3653f-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3653f-157">Überprüfen Sie **auf der** Seite Tag überprüfen Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3653f-157">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="3653f-158">Sie können **im** jeweiligen Abschnitt auf Bearbeiten klicken, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="3653f-158">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="3653f-159">Klicken Sie nach Abschluss des Abschlusses auf **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="3653f-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="3653f-160">Verwenden des Security & Compliance Center zum Anzeigen von Benutzertags</span><span class="sxs-lookup"><span data-stu-id="3653f-160">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="3653f-161">Wechseln Sie im Security & Compliance Center zu **Benutzertags für die Bedrohungsverwaltung.** \> </span><span class="sxs-lookup"><span data-stu-id="3653f-161">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="3653f-162">Wählen Sie **auf** der geöffneten Seite Benutzertags das Benutzertag aus, das Sie anzeigen möchten (klicken Sie nicht auf das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="3653f-162">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="3653f-163">Überprüfen Sie in den angezeigten schreibgeschützten Details die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3653f-163">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="3653f-164">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3653f-164">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="3653f-165">Verwenden des Security & Compliance Center zum Ändern von Benutzertags</span><span class="sxs-lookup"><span data-stu-id="3653f-165">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="3653f-166">Wechseln Sie im Security & Compliance Center zu **Benutzertags für die Bedrohungsverwaltung.** \> </span><span class="sxs-lookup"><span data-stu-id="3653f-166">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="3653f-167">Wählen Sie **auf der** geöffneten Seite Benutzertags das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **Tag bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3653f-167">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="3653f-168">Der Richtlinien-Assistent wird in einem **Edit-Tag** geöffnet. Klicken **Sie auf Weiter,** um die Einstellungen zu überprüfen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3653f-168">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="3653f-169">Klicken Sie nach Abschluss des Abschlusses auf **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="3653f-169">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="3653f-170">Verwenden des Security & Compliance Center zum Entfernen von Benutzertags</span><span class="sxs-lookup"><span data-stu-id="3653f-170">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="3653f-171">**Hinweis:** Sie können das integrierte Prioritätskontotag **nicht** entfernen.</span><span class="sxs-lookup"><span data-stu-id="3653f-171">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="3653f-172">Wechseln Sie im Security & Compliance Center zu **Benutzertags für die Bedrohungsverwaltung.** \> </span><span class="sxs-lookup"><span data-stu-id="3653f-172">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="3653f-173">Wählen Sie **auf** der geöffneten Seite Benutzertags das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf Tag **löschen,** und wählen Sie dann **Ja,** entfernen in der angezeigten Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="3653f-173">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>