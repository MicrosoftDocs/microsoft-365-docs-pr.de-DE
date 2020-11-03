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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie mithilfe der Konfigurationsanalyse Sicherheitsrichtlinien finden und beheben können, die unter den vordefinierten Sicherheitsrichtlinien für Standard Schutz und strenge Schutzbedingungen liegen.
ms.openlocfilehash: 1429bddc5ae5f8409ad4f3593f7ea236b13f854c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846472"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="ccbc9-103">Konfigurationsanalyse für Schutzrichtlinien in EoP und Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ccbc9-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="ccbc9-104">Die in diesem Thema beschriebenen Funktionen befinden sich in der Vorschau, sind nicht in allen Organisationen verfügbar und können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="ccbc9-105">Weitere Informationen zum Veröffentlichungszeitplan finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="ccbc9-106">Configuration Analyzer im Security & Compliance Center bietet einen zentralen Standort, um Sicherheitsrichtlinien zu finden und zu beheben, bei denen die Einstellungen unter den Standard mäßigen Schutz-und strengen Schutzprofil Einstellungen in [vordefinierten Sicherheitsrichtlinien](preset-security-policies.md)liegen.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="ccbc9-107">Die folgenden Richtlinientypen werden vom Configuration Analyzer analysiert:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="ccbc9-108">**Exchange Online Protection (EoP)-Richtlinien** : Dies umfasst Microsoft 365-Organisationen mit Exchange Online Postfächern und eigenständigen EoP-Organisationen ohne Exchange Online Postfächern:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-108">**Exchange Online Protection (EOP) policies** : This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="ccbc9-109">[Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="ccbc9-110">[Anti-Malware-Richtlinien](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="ccbc9-111">[EoP-Anti-Phishing-Richtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="ccbc9-112">**Microsoft Defender für Office 365-Richtlinien** : Dies umfasst Organisationen mit Microsoft 365 E5 oder Defender für Office 365 Add-on-Abonnements:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-112">**Microsoft Defender for Office 365 policies** : This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="ccbc9-113">Anti-Phishing-Richtlinien in Microsoft Defender für Office 365, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-113">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="ccbc9-114">Dieselben [spoofeinstellungen](set-up-anti-phishing-policies.md#spoof-settings) , die in den EoP-Richtlinien zum Schutz vor Phishing verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="ccbc9-115">Einstellungen für Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="ccbc9-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="ccbc9-116">Erweiterte Phishing-Schwellenwerte</span><span class="sxs-lookup"><span data-stu-id="ccbc9-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="ccbc9-117">[Richtlinien für sichere Links](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="ccbc9-118">[Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="ccbc9-119">Die **Standard mäßigen** und **strengen** Richtlinien Einstellungswerte, die als Baselines verwendet werden, werden in den [empfohlenen Einstellungen für EoP und Microsoft Defender für Office 365 Sicherheit](recommended-settings-for-eop-and-office365-atp.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ccbc9-120">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ccbc9-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ccbc9-121">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ccbc9-122">Wenn Sie direkt zur Seite **Configuration Analyzer** wechseln möchten, verwenden Sie <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="ccbc9-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="ccbc9-123">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ccbc9-124">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Artikel ausführen können:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="ccbc9-125">Sie müssen Mitglied einer der folgenden Rollengruppen sein, um die Konfigurationsanalyse verwenden **und** Updates für Sicherheitsrichtlinien vornehmen zu können:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ccbc9-126">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ccbc9-127">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="ccbc9-128">Für den schreibgeschützten Zugriff auf die Konfigurationsanalyse müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ccbc9-129">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ccbc9-130">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="ccbc9-131">Verwenden des Configuration Analyzer im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ccbc9-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="ccbc9-132">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Configuration Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Configuration Analyzer-Widget auf der Seite "Threat Management- \> Richtlinie"](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="ccbc9-134">Die Konfigurationsanalyse verfügt über zwei Hauptregisterkarten:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="ccbc9-135">**Einstellungen und Empfehlungen** : Sie wählen Standard oder Strict aus und vergleichen diese Einstellungen mit Ihren vorhandenen Sicherheitsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-135">**Settings and recommendations** : You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="ccbc9-136">In den Ergebnissen können Sie die Werte Ihrer Einstellungen anpassen, um Sie auf die gleiche Stufe wie Standard oder Strict zu bringen.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="ccbc9-137">**Analyse und Verlauf der Konfigurations Drift** : in dieser Ansicht können Sie Richtlinienänderungen im Laufe der Zeit verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-137">**Configuration drift analysis and history** : This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="ccbc9-138">Registerkarte Einstellungen und Empfehlungen in der Konfigurationsanalyse</span><span class="sxs-lookup"><span data-stu-id="ccbc9-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="ccbc9-139">Standardmäßig wird die Registerkarte im Vergleich zum Standard Schutzprofil geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="ccbc9-140">Sie können zum Vergleich des strengen Schutz Profils wechseln, indem Sie auf **strenge Empfehlungen anzeigen** klicken.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="ccbc9-141">Um zurück zu wechseln, wählen Sie **Standard Empfehlungen anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-141">To switch back, select **View Standard recommendations**.</span></span>

![Ansicht "Einstellungen und Empfehlungen" in der Konfigurationsanalyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="ccbc9-143">Standardmäßig enthält die Spalte **Richtliniengruppen/Einstellungsname** eine reduzierte Ansicht der verschiedenen Typen von Sicherheitsrichtlinien und der Anzahl von Einstellungen, die verbessert werden müssen (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="ccbc9-144">Die Typen von Richtlinien lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-144">The types of policies are:</span></span>

- <span data-ttu-id="ccbc9-145">**Anti-Spam**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-145">**Anti-spam**</span></span>
- <span data-ttu-id="ccbc9-146">**Anti-Phishing**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-146">**Anti-phishing**</span></span>
- <span data-ttu-id="ccbc9-147">**Anti-Malware**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-147">**Anti-malware**</span></span>
- <span data-ttu-id="ccbc9-148">**ATP-sichere Anlagen** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)</span><span class="sxs-lookup"><span data-stu-id="ccbc9-148">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="ccbc9-149">**ATP-sichere Links** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)</span><span class="sxs-lookup"><span data-stu-id="ccbc9-149">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="ccbc9-150">In der Standardansicht wird alles reduziert.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="ccbc9-151">Neben den einzelnen Richtlinien gibt es eine Zusammenfassung der Vergleichsergebnisse aus ihren Richtlinien (die Sie ändern können) und die Einstellungen in den entsprechenden Richtlinien für die Standard mäßigen oder strengen Schutzprofile (die Sie nicht ändern können).</span><span class="sxs-lookup"><span data-stu-id="ccbc9-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="ccbc9-152">Die folgenden Informationen für das Schutzprofil, mit dem Sie verglichen werden, werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="ccbc9-153">**Grün** : alle Einstellungen in allen vorhandenen Richtlinien sind mindestens so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-153">**Green** : All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="ccbc9-154">**Amber** : eine kleine Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-154">**Amber** : A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="ccbc9-155">**Rot** : eine beträchtliche Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-155">**Red** : A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="ccbc9-156">Dabei kann es sich um einige Einstellungen in vielen Richtlinien oder um viele Einstellungen in einer Richtlinie handeln.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="ccbc9-157">Für günstige Vergleiche wird der Text angezeigt: **alle Einstellungen folgen** den \<**Standard** or **Strict**\> **Empfehlungen**.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="ccbc9-158">Andernfalls wird die Anzahl der empfohlenen Einstellungen angezeigt, die geändert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="ccbc9-159">Wenn Sie den **Namen der Richtliniengruppe/Einstellung** erweitern, werden alle Richtlinien und die zugehörigen Einstellungen in jeder spezifischen Richtlinie, die Aufmerksamkeit erfordern, aufgedeckt.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-159">If you expand **Policy group/setting name** , all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="ccbc9-160">Sie können auch einen bestimmten Richtlinientyp erweitern (beispielsweise **Anti-Spam** ), um nur die Einstellungen in diesen Richtlinientypen anzuzeigen, die Ihre Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-160">Or, you can expand a specific type of policy (for example, **Anti-spam** ) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="ccbc9-161">Wenn der Vergleich keine Empfehlungen für Verbesserungen (grün) hat, zeigt das Erweitern der Richtlinie nichts.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="ccbc9-162">Wenn es eine Reihe von Verbesserungsempfehlungen gibt (Amber oder rot), werden die Einstellungen, die Aufmerksamkeit erfordern, aufgedeckt, und entsprechende Informationen werden in den folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="ccbc9-163">Der Name der Einstellung, die Ihre Aufmerksamkeit erfordert.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="ccbc9-164">Im vorherigen Screenshot ist dies beispielsweise der **Schwellenwert für Massen-e-Mails** in einer Anti-Spam-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="ccbc9-165">**Richtlinie** : der Name der betroffenen Richtlinie, die die Einstellung enthält.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-165">**Policy** : The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="ccbc9-166">**Angewendet auf** : die Anzahl der Benutzer, auf die die betroffenen Richtlinien angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-166">**Applied to** : The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="ccbc9-167">**Aktuelle Konfiguration** : der aktuelle Wert der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-167">**Current configuration** : The current value of the setting.</span></span>

- <span data-ttu-id="ccbc9-168">**Zuletzt geändert** : das Datum, an dem die Richtlinie zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-168">**Last modified** : The date that the policy was last modified.</span></span>

- <span data-ttu-id="ccbc9-169">**Empfehlungen** : der Wert der Einstellung im Standard mäßigen oder strengen Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-169">**Recommendations** : The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="ccbc9-170">Klicken Sie auf über **nehmen** , um den Wert der Einstellung in Ihrer Richtlinie so zu ändern, dass er dem empfohlenen Wert im Schutzprofil entspricht.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="ccbc9-171">Wenn die Änderung erfolgreich war, wird die Meldung angezeigt: **Empfehlungen wurden erfolgreich angenommen**.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="ccbc9-172">Klicken Sie auf **Aktualisieren** , um die reduzierte Anzahl von Empfehlungen und das Entfernen der spezifischen Einstellung/Richtlinienzeile aus den Ergebnissen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="ccbc9-173">Konfigurations Drift Analyse und Registerkarte Verlauf in der Konfigurationsanalyse</span><span class="sxs-lookup"><span data-stu-id="ccbc9-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="ccbc9-174">Auf dieser Registerkarte können Sie die Änderungen nachverfolgen, die Sie an Ihren benutzerdefinierten Sicherheitsrichtlinien vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="ccbc9-175">Standardmäßig werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="ccbc9-176">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-176">**Last modified**</span></span>
- <span data-ttu-id="ccbc9-177">**Geändert von**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-177">**Modified by**</span></span>
- <span data-ttu-id="ccbc9-178">**Einstellungs Name**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-178">**Setting Name**</span></span>
- <span data-ttu-id="ccbc9-179">**Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-179">**Policy**</span></span>
- <span data-ttu-id="ccbc9-180">**Type**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-180">**Type**</span></span>

<span data-ttu-id="ccbc9-181">Klicken Sie auf **Filter** , um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="ccbc9-182">Im eingeblendeten **Filter** -Flyout können Sie aus den folgenden Filtern auswählen:</span><span class="sxs-lookup"><span data-stu-id="ccbc9-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="ccbc9-183">**Startzeit** und **Endzeit** (Datum)</span><span class="sxs-lookup"><span data-stu-id="ccbc9-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="ccbc9-184">**Standard Schutz** oder **strenger Schutz**</span><span class="sxs-lookup"><span data-stu-id="ccbc9-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="ccbc9-185">Klicken Sie auf **exportieren** , um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="ccbc9-185">To export the results to a .csv file, click **Export**.</span></span>

![Konfigurations Drift Analyse und Verlaufsansicht in der Konfigurationsanalyse](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
