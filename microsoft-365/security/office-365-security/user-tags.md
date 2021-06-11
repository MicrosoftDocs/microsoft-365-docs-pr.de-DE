---
title: Benutzertags in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie sie bestimmte Benutzergruppen mit Benutzertags in Microsoft Defender für Office 365 Plan 2 identifizieren. Die Tagfilterung ist für Warnungen, Berichte und Untersuchungen in Microsoft Defender verfügbar, damit Office 365 die markierten Benutzer schnell identifizieren können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1fb948d63f7bc42839d6fae8a2138d4ad48d81f6
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879168"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e8816-104">Benutzertags in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="e8816-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="e8816-105">Das Feature "Benutzertags" befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e8816-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="e8816-106">Informationen zum Veröffentlichungszeitplan finden Sie in der [Roadmap Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="e8816-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="e8816-107">Benutzertags sind Bezeichner für bestimmte Benutzergruppen in [Microsoft Defender für Office 365.](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="e8816-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="e8816-108">Es gibt zwei Arten von Benutzertags:</span><span class="sxs-lookup"><span data-stu-id="e8816-108">There are two types of user tags:</span></span>

- <span data-ttu-id="e8816-109">**Systemtags:** Derzeit sind [Prioritätskonten](../../admin/setup/priority-accounts.md) der einzige Typ von Systemtag.</span><span class="sxs-lookup"><span data-stu-id="e8816-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="e8816-110">**Benutzerdefinierte Tags:** Sie erstellen diese Benutzertags selbst.</span><span class="sxs-lookup"><span data-stu-id="e8816-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="e8816-111">Wenn Ihre Organisation über Defender for Office 365 Plan 2 verfügt (in Ihrem Abonnement oder als Add-On enthalten), können Sie zusätzlich zur Verwendung des Prioritätskontentags benutzerdefinierte Benutzertags erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8816-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="e8816-112">Derzeit können Sie Benutzertags nur auf Postfachbenutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="e8816-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="e8816-113">Nachdem Sie Systemtags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e8816-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="e8816-114">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e8816-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="e8816-115">Bedrohungs-Explorer und Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="e8816-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="e8816-116">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e8816-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="e8816-117">Kampagnenansichten</span><span class="sxs-lookup"><span data-stu-id="e8816-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="e8816-118">Für Prioritätskonten können Sie den [Bericht "E-Mail-Probleme bei Prioritätskonten"](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) im Exchange Admin Center (EAC) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8816-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="e8816-119">In diesem Artikel wird erläutert, wie Sie Benutzertags im Microsoft 365 Defender-Portal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e8816-119">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="e8816-120">Es gibt keine Cmdlets in Microsoft 365 Defender-Portal zum Verwalten von Benutzertags.</span><span class="sxs-lookup"><span data-stu-id="e8816-120">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="e8816-121">Informationen dazu, wie Benutzertags Teil der Strategie zum Schutz von Benutzerkonten mit hoher Auswirkung sind, finden Sie in den [Sicherheitsempfehlungen für Prioritätskonten in Microsoft 365.](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="e8816-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8816-122">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="e8816-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8816-123">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="e8816-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="e8816-124">Um direkt zur Seite **"Benutzertags"** zu wechseln, öffnen Sie <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="e8816-124">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="e8816-125">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Microsoft 365 Defender-Portal Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="e8816-125">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e8816-126">Um Benutzertags zu erstellen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="e8816-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e8816-127">Um Mitglieder zu vorhandenen Benutzertags hinzuzufügen und daraus zu entfernen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung",** **"Sicherheitsadministrator"** oder **"Sicherheitsoperator"** sein.</span><span class="sxs-lookup"><span data-stu-id="e8816-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="e8816-128">Für den schreibgeschützten Zugriff auf Benutzertags müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="e8816-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e8816-129">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="e8816-129">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="e8816-130">Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8816-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e8816-131">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e8816-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="e8816-132">Die Verwaltung von Benutzertags wird durch die Rollen **"Tag-Reader"** und **"Tag-Manager"** gesteuert.</span><span class="sxs-lookup"><span data-stu-id="e8816-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="e8816-133">Sie können Prioritätskonten auch im Microsoft 365 Admin Center verwalten und überwachen.</span><span class="sxs-lookup"><span data-stu-id="e8816-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e8816-134">Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritätskonten.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="e8816-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="e8816-135">Informationen zum Schützen _privilegierter Konten_ (Administratorkonten) finden Sie in [diesem Thema.](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="e8816-135">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="e8816-136">Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Benutzertags</span><span class="sxs-lookup"><span data-stu-id="e8816-136">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="e8816-137">Wechseln Sie im Microsoft 365 Defender-Portal zu **Einstellungen** \> **E-Mail-&** \> **Benutzertags** für die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="e8816-137">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="e8816-138">Klicken Sie auf der Seite **"Benutzertags"** auf das ![ Symbol "Tag ](../../media/m365-cc-sc-create-icon.png) **erstellen"**.</span><span class="sxs-lookup"><span data-stu-id="e8816-138">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="e8816-139">Der Assistent **zum Erstellen von Tags** wird in einem neuen Flyout geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e8816-139">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="e8816-140">Konfigurieren Sie auf der Seite **"Tag definieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="e8816-140">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="e8816-141">**Name:** Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="e8816-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="e8816-142">Dies ist der Wert, den Sie sehen und verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="e8816-142">This is the value that you'll see and use.</span></span> <span data-ttu-id="e8816-143">Beachten Sie, dass Sie ein Tag nach der Erstellung nicht umbenennen können.</span><span class="sxs-lookup"><span data-stu-id="e8816-143">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="e8816-144">**Beschreibung:** Geben Sie eine optionale Beschreibung für das Tag ein.</span><span class="sxs-lookup"><span data-stu-id="e8816-144">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="e8816-145">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e8816-145">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e8816-146">Führen Sie auf der Seite **"Mitglieder zuweisen"** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e8816-146">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="e8816-147">Klicken Sie auf ![ "Mitglieder hinzufügen" auf symbol ](../../media/m365-cc-sc-create-icon.png) **"Mitglieder hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="e8816-147">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="e8816-148">Führen Sie im angezeigten Flyout einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="e8816-148">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="e8816-149">Klicken Sie in das Feld, und scrollen Sie durch die Liste, um einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e8816-149">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="e8816-150">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e8816-150">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="e8816-151">Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e8816-151">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="e8816-152">Um einzelne Einträge zu entfernen, klicken Sie auf</span><span class="sxs-lookup"><span data-stu-id="e8816-152">To remove individual entries, click</span></span> ![Eintragssymbol entfernen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e8816-154">neben dem Eintrag im Feld.</span><span class="sxs-lookup"><span data-stu-id="e8816-154">next to the entry in the box.</span></span>
     - <span data-ttu-id="e8816-155">Um alle Einträge zu entfernen, klicken Sie ![ auf das Symbol "Eintrag entfernen" ](../../media/m365-cc-sc-remove-selection-icon.png) im Element **"Ausgewählte nn Benutzer" und "nn Gruppen"** unterhalb des Felds.</span><span class="sxs-lookup"><span data-stu-id="e8816-155">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="e8816-156">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e8816-156">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="e8816-157">Zurück auf der Seite **"Mitglieder zuweisen"** können Sie einträge auch entfernen, indem Sie neben dem Eintrag auf ![ das Symbol "Löschen" ](../../media/m365-cc-sc-delete-icon.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="e8816-157">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="e8816-158">Klicken Sie auf **"Importieren",** um eine Textdatei auszuwählen, die die E-Mail-Adressen der Benutzer oder Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="e8816-158">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="e8816-159">Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="e8816-159">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="e8816-160">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e8816-160">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e8816-161">Überprüfen Sie auf der daraufhin angezeigten Seite des **Überprüfungstags** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e8816-161">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="e8816-162">Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e8816-162">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="e8816-163">Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="e8816-163">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="e8816-164">Wenn Sie fertig sind, klicken Sie auf **"Absenden"** und dann auf **"Fertig".**</span><span class="sxs-lookup"><span data-stu-id="e8816-164">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="e8816-165">Verwenden des Microsoft 365 Defender-Portals zum Anzeigen von Benutzertags</span><span class="sxs-lookup"><span data-stu-id="e8816-165">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="e8816-166">Wechseln Sie im Microsoft 365 Defender-Portal zu **Einstellungen** \> **E-Mail-&** \> **Benutzertags** für die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="e8816-166">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="e8816-167">Auf der Seite **"Benutzertags"** werden die folgenden Eigenschaften in der Liste der Benutzertags angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e8816-167">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="e8816-168">**Tag:** Der Name des Benutzertags.</span><span class="sxs-lookup"><span data-stu-id="e8816-168">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="e8816-169">Beachten Sie, dass dies das integrierte **Prioritätskonto-Systemtag** enthält.</span><span class="sxs-lookup"><span data-stu-id="e8816-169">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="e8816-170">**Angewendet auf**: Die Anzahl der Mitglieder</span><span class="sxs-lookup"><span data-stu-id="e8816-170">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="e8816-171">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="e8816-171">**Last modified**</span></span>
   - <span data-ttu-id="e8816-172">**Erstellt am**</span><span class="sxs-lookup"><span data-stu-id="e8816-172">**Created on**</span></span>

3. <span data-ttu-id="e8816-173">Wenn Sie ein Benutzertag auswählen, indem Sie auf den Namen klicken, werden die Details in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e8816-173">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="e8816-174">Verwenden des Microsoft 365 Defender-Portals zum Ändern von Benutzertags</span><span class="sxs-lookup"><span data-stu-id="e8816-174">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="e8816-175">Wechseln Sie im Microsoft 365 Defender-Portal zu **Einstellungen** \> **E-Mail-&** \> **Benutzertags** für die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="e8816-175">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="e8816-176">Wählen Sie auf der Seite **"Benutzertags"** das Benutzertag aus der Liste aus, und klicken Sie dann auf ![ "Tag bearbeiten" auf ](../../media/m365-cc-sc-edit-icon.png) **"Tag bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="e8816-176">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="e8816-177">Im angezeigten Detail-Flyout sind derselbe Assistent und dieselben Einstellungen verfügbar, wie im Abschnitt ["Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Benutzertags"](#use-the-microsoft-365-defender-portal-to-create-user-tags) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8816-177">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="e8816-178">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="e8816-178">**Notes**:</span></span>

   - <span data-ttu-id="e8816-179">Die Seite **"Tag definieren"** ist für das integrierte Systemtag des **Prioritätskontos** nicht verfügbar, daher können Sie dieses Tag nicht umbenennen oder die Beschreibung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="e8816-179">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="e8816-180">Sie können ein benutzerdefiniertes Tag nicht umbenennen, aber Sie können die Beschreibung ändern.</span><span class="sxs-lookup"><span data-stu-id="e8816-180">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="e8816-181">Verwenden des Microsoft 365 Defender-Portals zum Entfernen von Benutzertags</span><span class="sxs-lookup"><span data-stu-id="e8816-181">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="e8816-182">Sie können das integrierte **Prioritätskonto-Systemtag** nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="e8816-182">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="e8816-183">Wechseln Sie im Microsoft 365 Defender-Portal zu **Einstellungen** \> **E-Mail-&** \> **Benutzertags** für die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="e8816-183">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="e8816-184">Wählen Sie auf der Seite **"Benutzertags"** das Benutzertag aus der Liste aus, und klicken Sie dann auf ![ "Tag löschen" auf ](../../media/m365-cc-sc-delete-icon.png) **"Tag löschen".**</span><span class="sxs-lookup"><span data-stu-id="e8816-184">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="e8816-185">Lesen Sie die Warnung im daraufhin angezeigten Bestätigungsdialogfeld, und klicken Sie dann auf **"Ja", entfernen Sie**.</span><span class="sxs-lookup"><span data-stu-id="e8816-185">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
