---
title: Konfigurationsanalyse für Sicherheitsrichtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie mithilfe der Konfigurationsanalyse Sicherheitsrichtlinien finden und beheben, die unterhalb der voreingestellten Sicherheitsrichtlinien "Standardschutz" und "Strenger Schutz" liegen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04027e78a2683c6c33954bb548c502497c5e8323
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029478"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="656cc-103">Konfigurationsanalyse für Schutzrichtlinien in EOP und Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="656cc-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="656cc-104">Die Konfigurationsanalyse im Security & Compliance Center bietet einen zentralen Ort zum Suchen und Beheben von Sicherheitsrichtlinien, in denen sich die Einstellungen unter den Standardschutz- und Strengschutzprofileinstellungen in vordefinierten Sicherheitsrichtlinien [befinden.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="656cc-104">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="656cc-105">Die folgenden Richtlinientypen werden von der Konfigurationsanalyse analysiert:</span><span class="sxs-lookup"><span data-stu-id="656cc-105">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="656cc-106">**Exchange Online Protection (EOP)-Richtlinien:** Dazu gehören Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständige EOP-Organisationen ohne Exchange Online-Postfächer:</span><span class="sxs-lookup"><span data-stu-id="656cc-106">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="656cc-107">[Antispamrichtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="656cc-107">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="656cc-108">[Richtlinien für An malware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="656cc-108">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="656cc-109">[EOP Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="656cc-109">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="656cc-110">**Microsoft Defender für Office 365-Richtlinien:** Dazu gehören Organisationen mit Microsoft 365 E5- oder Defender für Office 365-Add-On-Abonnements:</span><span class="sxs-lookup"><span data-stu-id="656cc-110">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="656cc-111">Antiphishingrichtlinien in Microsoft Defender für Office 365, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="656cc-111">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="656cc-112">Die gleichen [Spoofeinstellungen,](set-up-anti-phishing-policies.md#spoof-settings) die in den EOP-Anti-Phishing-Richtlinien verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="656cc-112">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="656cc-113">Identitätswechseleinstellungen</span><span class="sxs-lookup"><span data-stu-id="656cc-113">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="656cc-114">Erweiterte Phishingschwellenwerte</span><span class="sxs-lookup"><span data-stu-id="656cc-114">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="656cc-115">[Richtlinien für sichere Links](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="656cc-115">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="656cc-116">[Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="656cc-116">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="656cc-117">Die **Standard-** und Strict-Richtlinieneinstellungswerte, die als Basiswerte verwendet werden, werden in den empfohlenen Einstellungen für EOP und [Microsoft Defender für Office 365-Sicherheit beschrieben.](recommended-settings-for-eop-and-office365-atp.md) </span><span class="sxs-lookup"><span data-stu-id="656cc-117">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="656cc-118">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="656cc-118">What do you need to know before you begin?</span></span>

- <span data-ttu-id="656cc-119">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="656cc-119">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="656cc-120">Um direkt zur Seite **"Konfigurationsanalyse" zu** wechseln, verwenden Sie <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="656cc-120">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="656cc-121">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="656cc-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="656cc-122">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="656cc-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="656cc-123">Um die Konfigurationsanalyse **zu** verwenden und Sicherheitsrichtlinien zu aktualisieren, müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="656cc-123">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="656cc-124">Für den schreibgeschützten Zugriff auf die Konfigurationsanalyse müssen  Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="656cc-124">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="656cc-125">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="656cc-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="656cc-126">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="656cc-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="656cc-127">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="656cc-127">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  > 
  > - <span data-ttu-id="656cc-128">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="656cc-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="656cc-129">Verwenden der Konfigurationsanalyse im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="656cc-129">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="656cc-130">Wechseln Sie im Security & Compliance Center zu **"Richtlinienkonfigurationsanalyse für** die \>  \> **Bedrohungsverwaltung".**</span><span class="sxs-lookup"><span data-stu-id="656cc-130">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Konfigurationsanalyse-Widget auf der Seite \> "Bedrohungsverwaltungsrichtlinie"](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="656cc-132">Die Konfigurationsanalyse verfügt über zwei Hauptregisterkarten:</span><span class="sxs-lookup"><span data-stu-id="656cc-132">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="656cc-133">**Einstellungen und Empfehlungen:** Sie wählen "Standard" oder "Streng" aus und vergleichen diese Einstellungen mit Ihren vorhandenen Sicherheitsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="656cc-133">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="656cc-134">In den Ergebnissen können Sie die Werte Ihrer Einstellungen anpassen, um sie auf die gleiche Stufe wie "Standard" oder "Streng" zu bringen.</span><span class="sxs-lookup"><span data-stu-id="656cc-134">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="656cc-135">**Konfigurations-Drift-Analyse und -Verlauf:** In dieser Ansicht können Sie Richtlinienänderungen im Laufe der Zeit nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="656cc-135">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="656cc-136">Registerkarte "Einstellung und Empfehlungen" in der Konfigurationsanalyse</span><span class="sxs-lookup"><span data-stu-id="656cc-136">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="656cc-137">Standardmäßig wird die Registerkarte im Vergleich zum Standardschutzprofil geöffnet.</span><span class="sxs-lookup"><span data-stu-id="656cc-137">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="656cc-138">Sie können zum Vergleich des Strengschutzprofils wechseln, indem Sie auf **"Strenge Empfehlungen anzeigen" klicken.**</span><span class="sxs-lookup"><span data-stu-id="656cc-138">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="656cc-139">Um zurück zu wechseln, wählen **Sie "Standardempfehlungen anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="656cc-139">To switch back, select **View Standard recommendations**.</span></span>

![Ansicht "Einstellungen und Empfehlungen" in der Konfigurationsanalyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="656cc-141">Standardmäßig enthält  die Spalte "Richtliniengruppe/Einstellungsname" eine reduzierte Ansicht der verschiedenen Typen von Sicherheitsrichtlinien und die Anzahl der Einstellungen, die gegebenenfalls verbessert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="656cc-141">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="656cc-142">Die Richtlinientypen sind:</span><span class="sxs-lookup"><span data-stu-id="656cc-142">The types of policies are:</span></span>

- <span data-ttu-id="656cc-143">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="656cc-143">**Anti-spam**</span></span>
- <span data-ttu-id="656cc-144">**Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="656cc-144">**Anti-phishing**</span></span>
- <span data-ttu-id="656cc-145">**Ansoftware**</span><span class="sxs-lookup"><span data-stu-id="656cc-145">**Anti-malware**</span></span>
- <span data-ttu-id="656cc-146">**ATP-sichere Anlagen** (wenn Ihr Abonnement Microsoft Defender für Office 365 umfasst)</span><span class="sxs-lookup"><span data-stu-id="656cc-146">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="656cc-147">**ATP Safe Links** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)</span><span class="sxs-lookup"><span data-stu-id="656cc-147">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="656cc-148">In der Standardansicht ist alles reduziert.</span><span class="sxs-lookup"><span data-stu-id="656cc-148">In the default view, everything is collapsed.</span></span> <span data-ttu-id="656cc-149">Neben jeder Richtlinie gibt es eine Zusammenfassung der Vergleichsergebnisse aus Ihren Richtlinien (die Sie ändern können) und den Einstellungen in den entsprechenden Richtlinien für die Standard- oder Strict -Schutzprofile (die Sie nicht ändern können).</span><span class="sxs-lookup"><span data-stu-id="656cc-149">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="656cc-150">Für das Schutzprofil, mit dem Sie einen Vergleich erstellen, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="656cc-150">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="656cc-151">**Grün:** Alle Einstellungen in allen vorhandenen Richtlinien sind mindestens so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="656cc-151">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="656cc-152">**Neu:** Eine kleine Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="656cc-152">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="656cc-153">**Rot:** Eine erhebliche Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="656cc-153">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="656cc-154">Dies können einige Einstellungen in vielen Richtlinien oder viele Einstellungen in einer Richtlinie sein.</span><span class="sxs-lookup"><span data-stu-id="656cc-154">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="656cc-155">Für vorteilhafte Vergleiche wird der Text angezeigt: **Alle Einstellungen folgen** \<**Standard** or **Strict**\> **Empfehlungen.**</span><span class="sxs-lookup"><span data-stu-id="656cc-155">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="656cc-156">Andernfalls wird die Anzahl der empfohlenen Einstellungen angezeigt, die geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="656cc-156">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="656cc-157">Wenn Sie den Namen **der Richtliniengruppe/-einstellung** erweitern, werden alle Richtlinien und die zugehörigen Einstellungen in jeder bestimmten Richtlinie angezeigt, die Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="656cc-157">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="656cc-158">Sie können auch einen bestimmten Richtlinientyp (z. B. **Antispam)** erweitern, um nur die Einstellungen in den Richtlinientypen zu sehen, die Ihre Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="656cc-158">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="656cc-159">Wenn der Vergleich keine Verbesserungsempfehlungen enthält (grün), wird durch das Erweitern der Richtlinie nichts offen.</span><span class="sxs-lookup"><span data-stu-id="656cc-159">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="656cc-160">Wenn es eine Reihe von Verbesserungsempfehlungen gibt (rot oder rot), werden die Einstellungen aufgedeckt, die Aufmerksamkeit erfordern, und entsprechende Informationen werden in den folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="656cc-160">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="656cc-161">Der Name der Einstellung, die Ihre Aufmerksamkeit erfordert.</span><span class="sxs-lookup"><span data-stu-id="656cc-161">The name of the setting that requires your attention.</span></span> <span data-ttu-id="656cc-162">Im vorherigen Screenshot ist dies beispielsweise der Schwellenwert für Massen-E-Mails **in** einer Antispamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="656cc-162">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="656cc-163">**Richtlinie:** Der Name der betroffenen Richtlinie, die die Einstellung enthält.</span><span class="sxs-lookup"><span data-stu-id="656cc-163">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="656cc-164">**Angewendet auf:** Die Anzahl der Benutzer, auf die die betroffenen Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="656cc-164">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="656cc-165">**Aktuelle Konfiguration:** Der aktuelle Wert der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="656cc-165">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="656cc-166">**Letzte Änderung:** Das Datum, an dem die Richtlinie zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="656cc-166">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="656cc-167">**Empfehlungen:** Der Wert der Einstellung im Standard- oder Strict-Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="656cc-167">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="656cc-168">Klicken Sie auf "Übernehmen", um den Wert der Einstellung in Ihrer Richtlinie an den empfohlenen Wert im Schutzprofil **zu ändern.**</span><span class="sxs-lookup"><span data-stu-id="656cc-168">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="656cc-169">Wenn die Änderung erfolgreich ist, wird die Meldung angezeigt: **Empfehlungen wurden erfolgreich angenommen.**</span><span class="sxs-lookup"><span data-stu-id="656cc-169">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="656cc-170">Klicken **Sie auf** "Aktualisieren", um die reduzierte Anzahl von Empfehlungen und das Entfernen der spezifischen Einstellung/Richtlinienzeile aus den Ergebnissen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="656cc-170">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="656cc-171">Registerkarte "Konfigurations-Driftanalyse und Verlauf" in der Konfigurationsanalyse</span><span class="sxs-lookup"><span data-stu-id="656cc-171">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="656cc-172">Auf dieser Registerkarte können Sie die Änderungen nachverfolgen, die Sie an Ihren benutzerdefinierten Sicherheitsrichtlinien vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="656cc-172">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="656cc-173">Standardmäßig werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="656cc-173">By default, the following information is displayed:</span></span>

- <span data-ttu-id="656cc-174">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="656cc-174">**Last modified**</span></span>
- <span data-ttu-id="656cc-175">**Geändert von**</span><span class="sxs-lookup"><span data-stu-id="656cc-175">**Modified by**</span></span>
- <span data-ttu-id="656cc-176">**Einstellungsname**</span><span class="sxs-lookup"><span data-stu-id="656cc-176">**Setting Name**</span></span>
- <span data-ttu-id="656cc-177">**Policy**</span><span class="sxs-lookup"><span data-stu-id="656cc-177">**Policy**</span></span>
- <span data-ttu-id="656cc-178">**Typ**</span><span class="sxs-lookup"><span data-stu-id="656cc-178">**Type**</span></span>

<span data-ttu-id="656cc-179">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="656cc-179">To filter the results, click **Filter**.</span></span> <span data-ttu-id="656cc-180">Im **angezeigten Filterf** flyout können Sie aus den folgenden Filtern auswählen:</span><span class="sxs-lookup"><span data-stu-id="656cc-180">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="656cc-181">**Startzeit und** **Endzeit** (Datum)</span><span class="sxs-lookup"><span data-stu-id="656cc-181">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="656cc-182">**Standardschutz oder** **strenger Schutz**</span><span class="sxs-lookup"><span data-stu-id="656cc-182">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="656cc-183">Klicken Sie auf "Exportieren", um die Ergebnisse in eine **CSV-Datei zu exportieren.**</span><span class="sxs-lookup"><span data-stu-id="656cc-183">To export the results to a .csv file, click **Export**.</span></span>

![Konfigurations-Driftanalyse und Verlaufsansicht in der Konfigurationsanalyse](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
