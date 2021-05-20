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
description: Administratoren erfahren, wie Sie die Konfigurationsanalyse verwenden, um Sicherheitsrichtlinien zu finden und zu beheben, die unterhalb der vordefinierten Sicherheitsrichtlinien standard protection und Strict protection liegen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd0cf4f3194a7a8eec39f2d0c447dca2dae5948b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537931"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="c3f5b-103">Konfigurationsanalyse für Schutzrichtlinien in EOP und Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="c3f5b-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3f5b-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-104">**Applies to**</span></span>
- [<span data-ttu-id="c3f5b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c3f5b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c3f5b-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="c3f5b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c3f5b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3f5b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c3f5b-108">Die Konfigurationsanalyse im Security & Compliance Center bietet einen zentralen Ort zum Suchen und Beheben von Sicherheitsrichtlinien, an denen die Einstellungen unter den Einstellungen Standardschutz und Strenge Schutzprofileinstellungen in vordefinierten Sicherheitsrichtlinien [liegen.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c3f5b-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="c3f5b-109">Die folgenden Richtlinientypen werden von der Konfigurationsanalyse analysiert:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="c3f5b-110">**Exchange Online Protection (EOP)-Richtlinien:** Dies umfasst Microsoft 365 Organisationen mit Exchange Online postfächern und eigenständigen EOP-Organisationen ohne Exchange Online Postfächer:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="c3f5b-111">[Antispamrichtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="c3f5b-112">[An malware-Richtlinien](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="c3f5b-113">[EOP-Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-113">[EOP anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="c3f5b-114">**Microsoft Defender für Office 365:** Dies umfasst Organisationen mit Microsoft 365 E5 oder Defender for Office 365-Add-On-Abonnements:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="c3f5b-115">Antiphishingrichtlinien in Microsoft Defender for Office 365, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="c3f5b-116">Dieselben [Spoofeinstellungen,](set-up-anti-phishing-policies.md#spoof-settings) die in den EOP-Antiphishingrichtlinien verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="c3f5b-117">Identitätswechseleinstellungen</span><span class="sxs-lookup"><span data-stu-id="c3f5b-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="c3f5b-118">Erweiterte Phishingschwellenwerte</span><span class="sxs-lookup"><span data-stu-id="c3f5b-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="c3f5b-119">[Richtlinien für sichere Links](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>

  - <span data-ttu-id="c3f5b-120">[Richtlinien für sichere Anlagen](set-up-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="c3f5b-121">Die **Standard-** und Strict-Richtlinieneinstellungswerte, die als Basiswerte verwendet werden, werden unter Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365 [beschrieben.](recommended-settings-for-eop-and-office365.md) </span><span class="sxs-lookup"><span data-stu-id="c3f5b-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3f5b-122">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="c3f5b-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3f5b-123">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c3f5b-124">Um direkt zur Seite **Konfigurationsanalyse zu** wechseln, verwenden Sie <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="c3f5b-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="c3f5b-125">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c3f5b-126">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c3f5b-127">Um die **Konfigurationsanalyse** zu verwenden und Sicherheitsrichtlinien zu aktualisieren, müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c3f5b-128">Für den schreibgeschützten Zugriff auf die Konfigurationsanalyse müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Security Reader"** sein.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c3f5b-129">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="c3f5b-130">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c3f5b-131">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="c3f5b-132">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="c3f5b-133">Verwenden der Konfigurationsanalyse im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="c3f5b-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="c3f5b-134">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Configuration analyzer**.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Konfigurationsanalyse-Widget auf der Seite \> Bedrohungsverwaltungsrichtlinie](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="c3f5b-136">Die Konfigurationsanalyse verfügt über zwei Hauptregisterkarten:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="c3f5b-137">**Einstellungen und Empfehlungen**: Sie wählen Standard oder Strict aus, und vergleichen Sie diese Einstellungen mit Ihren vorhandenen Sicherheitsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="c3f5b-138">In den Ergebnissen können Sie die Werte Ihrer Einstellungen anpassen, um sie auf die gleiche Stufe wie Standard oder Strict zu bringen.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="c3f5b-139">**Konfigurationsdriftanalyse und -verlauf:** Mit dieser Ansicht können Sie Richtlinienänderungen im Laufe der Zeit nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="c3f5b-140">Registerkarte "Einstellungen und Empfehlungen" in der Konfigurationsanalyse</span><span class="sxs-lookup"><span data-stu-id="c3f5b-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="c3f5b-141">Standardmäßig wird die Registerkarte im Vergleich zum Standardschutzprofil geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="c3f5b-142">Sie können zum Vergleich des Strikten Schutzprofils wechseln, indem Sie **auf Strenge Empfehlungen anzeigen klicken.**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="c3f5b-143">Wählen Sie Standardempfehlungen anzeigen aus, um **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-143">To switch back, select **View Standard recommendations**.</span></span>

![Einstellungen und Empfehlungen in der Konfigurationsanalyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="c3f5b-145">Standardmäßig enthält die Spalte **Richtliniengruppe/Einstellungsname** eine reduzierte Ansicht der verschiedenen Typen von Sicherheitsrichtlinien und der Anzahl der Einstellungen, die verbessert werden müssen (falls welche).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="c3f5b-146">Die Richtlinientypen sind:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-146">The types of policies are:</span></span>

- <span data-ttu-id="c3f5b-147">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-147">**Anti-spam**</span></span>
- <span data-ttu-id="c3f5b-148">**Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-148">**Anti-phishing**</span></span>
- <span data-ttu-id="c3f5b-149">**An malware**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-149">**Anti-malware**</span></span>
- <span data-ttu-id="c3f5b-150">**ATP Sichere Anlagen** (wenn Ihr Abonnement Microsoft Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="c3f5b-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="c3f5b-151">**ATP Safe Links** (wenn Ihr Abonnement Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="c3f5b-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="c3f5b-152">In der Standardansicht wird alles reduziert.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="c3f5b-153">Neben jeder Richtlinie finden Sie eine Zusammenfassung der Vergleichsergebnisse aus Ihren Richtlinien (die Sie ändern können) und den Einstellungen in den entsprechenden Richtlinien für die Standard- oder Strict-Schutzprofile (die Sie nicht ändern können).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="c3f5b-154">Es werden die folgenden Informationen für das Schutzprofil angezeigt, mit dem Sie vergleichen:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="c3f5b-155">**Grün**: Alle Einstellungen in allen vorhandenen Richtlinien sind mindestens so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="c3f5b-156">**Gelb**: Eine kleine Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="c3f5b-157">**Rot**: Eine beträchtliche Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="c3f5b-158">Dies können einige Einstellungen in vielen Richtlinien oder viele Einstellungen in einer Richtlinie sein.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="c3f5b-159">Für vorteilhafte Vergleiche wird der Text angezeigt: **Alle Einstellungen folgen** \<**Standard** or **Strict**\> **Empfehlungen**.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="c3f5b-160">Andernfalls wird die Anzahl der empfohlenen Einstellungen angezeigt, die geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="c3f5b-161">Wenn Sie **richtliniengruppen-/einstellungsnamen** erweitern, werden alle Richtlinien und die zugehörigen Einstellungen in jeder bestimmten Richtlinie angezeigt, die Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="c3f5b-162">Sie können auch einen bestimmten Richtlinientyp (z. B. **Antispam)** erweitern, um genau diese Einstellungen in den Richtlinientypen zu sehen, die Ihre Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="c3f5b-163">Wenn der Vergleich keine Verbesserungsempfehlungen enthält (grün), zeigt die Erweiterung der Richtlinie nichts an.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="c3f5b-164">Wenn es eine Reihe von Verbesserungsempfehlungen gibt (gelb oder rot), werden die Einstellungen aufgedeckt, die Aufmerksamkeit erfordern, und entsprechende Informationen werden in den folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="c3f5b-165">Der Name der Einstellung, die Ihre Aufmerksamkeit erfordert.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="c3f5b-166">Im vorherigen Screenshot ist dies beispielsweise der Schwellenwert für **Massen-E-Mails** in einer Antispamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="c3f5b-167">**Richtlinie**: Der Name der betroffenen Richtlinie, die die Einstellung enthält.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="c3f5b-168">**Angewendet auf**: Die Anzahl der Benutzer, auf die die betroffenen Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="c3f5b-169">**Aktuelle Konfiguration:** Der aktuelle Wert der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="c3f5b-170">**Letzte Änderung:** Das Datum, an dem die Richtlinie zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="c3f5b-171">**Empfehlungen**: Der Wert der Einstellung im Standard- oder Strict-Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="c3f5b-172">Klicken Sie auf Übernehmen, um den Wert der Einstellung in Ihrer Richtlinie so zu ändern, dass sie mit dem empfohlenen Wert im Schutzprofil **übereinstimmen.**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="c3f5b-173">Wenn die Änderung erfolgreich ist, wird die Meldung angezeigt: **Empfehlungen erfolgreich übernommen.**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="c3f5b-174">Klicken **Sie auf Aktualisieren,** um die reduzierte Anzahl von Empfehlungen und das Entfernen der spezifischen Einstellung/Richtlinienzeile aus den Ergebnissen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="c3f5b-175">Registerkarte Konfigurationsdriftanalyse und Verlauf in der Konfigurationsanalyse</span><span class="sxs-lookup"><span data-stu-id="c3f5b-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="c3f5b-176">Auf dieser Registerkarte können Sie die Änderungen nachverfolgen, die Sie an Ihren benutzerdefinierten Sicherheitsrichtlinien vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="c3f5b-177">Standardmäßig werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="c3f5b-178">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-178">**Last modified**</span></span>
- <span data-ttu-id="c3f5b-179">**Geändert von**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-179">**Modified by**</span></span>
- <span data-ttu-id="c3f5b-180">**Einstellungsname**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-180">**Setting Name**</span></span>
- <span data-ttu-id="c3f5b-181">**Policy**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-181">**Policy**</span></span>
- <span data-ttu-id="c3f5b-182">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-182">**Type**</span></span>

<span data-ttu-id="c3f5b-183">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="c3f5b-184">Im **angezeigten Flyout** Filter können Sie aus den folgenden Filtern auswählen:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="c3f5b-185">**Startzeit** und **Endzeit** (Datum)</span><span class="sxs-lookup"><span data-stu-id="c3f5b-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="c3f5b-186">**Standardschutz oder** **strenger Schutz**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="c3f5b-187">Klicken Sie auf Exportieren, um die Ergebnisse in .csv **exportieren.**</span><span class="sxs-lookup"><span data-stu-id="c3f5b-187">To export the results to a .csv file, click **Export**.</span></span>

![Konfigurationsdriftanalyse und Verlaufsansicht in der Konfigurationsanalyse](../../media/configuration-analyzer-configuration-drift-analysis-view.png)