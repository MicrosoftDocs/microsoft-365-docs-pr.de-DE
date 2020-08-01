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
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie mithilfe der Konfigurationsanalyse Sicherheitsrichtlinien suchen und beheben, die Einstellungen enthalten, die den Standard mäßigen Sicherheitsrichtlinien für Schutz und strenge Schutz unterliegen.
ms.openlocfilehash: 259d498646ecf893a57a608a37e3b771083716cc
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533970"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="a53b3-103">Konfigurationsanalyse für Schutzrichtlinien in EoP und Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a53b3-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="a53b3-104">Die in diesem Thema beschriebenen Funktionen befinden sich in der Vorschau, sind nicht in allen Organisationen verfügbar und können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a53b3-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="a53b3-105">Configuration Analyzer im Security & Compliance Center bietet einen zentralen Standort, um Sicherheitsrichtlinien zu finden und zu beheben, die Einstellungen enthalten, die unter den Standard mäßigen Schutz-und strengen Schutzprofil Einstellungen in [vordefinierten Sicherheitsrichtlinien](preset-security-policies.md)liegen.</span><span class="sxs-lookup"><span data-stu-id="a53b3-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="a53b3-106">Die folgenden Richtlinientypen werden vom Configuration Analyzer analysiert:</span><span class="sxs-lookup"><span data-stu-id="a53b3-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="a53b3-107">**Exchange Online Protection (EoP)-Richtlinien**: Dies umfasst Microsoft 365-Organisationen mit Exchange Online Postfächern und eigenständigen EoP-Organisationen ohne Exchange Online Postfächern:</span><span class="sxs-lookup"><span data-stu-id="a53b3-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="a53b3-108">[Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a53b3-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="a53b3-109">[Anti-Malware-Richtlinien](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a53b3-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="a53b3-110">[EoP-Anti-Phishing-Richtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="a53b3-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="a53b3-111">**Office 365 Advanced Threat Protection (ATP)-Richtlinien**: Dies umfasst Organisationen mit Microsoft 365 E5 oder Office 365 ATP-Add-on-Abonnements:</span><span class="sxs-lookup"><span data-stu-id="a53b3-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="a53b3-112">Anti-Phishing-Richtlinien für ATP, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="a53b3-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="a53b3-113">Dieselben [spoofeinstellungen](set-up-anti-phishing-policies.md#spoof-settings) , die in den EoP-Richtlinien zum Schutz vor Phishing verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a53b3-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="a53b3-114">Einstellungen für Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="a53b3-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="a53b3-115">Erweiterte Phishing-Schwellenwerte</span><span class="sxs-lookup"><span data-stu-id="a53b3-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="a53b3-116">[Richtlinien für sichere Links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="a53b3-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="a53b3-117">[Richtlinien für sichere Anlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="a53b3-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="a53b3-118">Die **Standard mäßigen** und **strengen** Richtlinien Einstellungswerte, die als Baselines verwendet werden, werden in den [empfohlenen Einstellungen für EoP und Office 365 ATP-Sicherheit](recommended-settings-for-eop-and-office365-atp.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a53b3-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a53b3-119">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a53b3-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a53b3-120">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a53b3-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a53b3-121">Wenn Sie direkt zur Seite **Configuration Analyzer** wechseln möchten, verwenden Sie <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="a53b3-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="a53b3-122">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a53b3-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a53b3-123">Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="a53b3-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="a53b3-124">Sie müssen Mitglied einer der folgenden Rollengruppen sein, um die Konfigurationsanalyse verwenden **und** Updates für Sicherheitsrichtlinien vornehmen zu können:</span><span class="sxs-lookup"><span data-stu-id="a53b3-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="a53b3-125">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a53b3-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="a53b3-126">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="a53b3-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="a53b3-127">Für den schreibgeschützten Zugriff auf die Konfigurationsanalyse müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="a53b3-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="a53b3-128">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a53b3-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="a53b3-129">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="a53b3-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="a53b3-130">Verwenden des Configuration Analyzer im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a53b3-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="a53b3-131">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Configuration Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="a53b3-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Configuration Analyzer-Widget auf der Seite "Threat Management- \> Richtlinie"](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="a53b3-133">Die Konfigurationsanalyse verfügt über zwei Hauptregisterkarten:</span><span class="sxs-lookup"><span data-stu-id="a53b3-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="a53b3-134">**Einstellungen und Empfehlungen**: Sie wählen Standard oder Strict aus und vergleichen diese Einstellungen mit Ihren vorhandenen Sicherheitsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="a53b3-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="a53b3-135">In den Ergebnissen können Sie die Werte Ihrer Einstellungen anpassen, um Sie auf die gleiche Stufe wie Standard oder Strict zu bringen.</span><span class="sxs-lookup"><span data-stu-id="a53b3-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="a53b3-136">**Analyse und Verlauf der Konfigurations Drift**: in dieser Ansicht können Sie die Änderungen, die Sie an Ihren Richtlinien vorgenommen haben, basierend auf den Ergebnissen der Konfigurationsanalyse über einen Zeitraum nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a53b3-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="a53b3-137">Registerkarte Einstellungen und Empfehlungen in der Konfigurationsanalyse</span><span class="sxs-lookup"><span data-stu-id="a53b3-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="a53b3-138">Standardmäßig wird die Registerkarte im Vergleich zum Standard Schutzprofil geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a53b3-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="a53b3-139">Sie können zum Vergleich des strengen Schutz Profils wechseln, indem Sie auf **strenge Empfehlungen anzeigen**klicken.</span><span class="sxs-lookup"><span data-stu-id="a53b3-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="a53b3-140">Um zurück zu wechseln, wählen Sie **Standard Empfehlungen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="a53b3-140">To switch back, select **View Standard recommendations**.</span></span>

![Ansicht "Einstellungen und Empfehlungen" in der Konfigurationsanalyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="a53b3-142">Standardmäßig enthält die Spalte **Richtliniengruppen/Einstellungsname** eine reduzierte Ansicht der verschiedenen Typen von Sicherheitsrichtlinien und die Anzahl der Einstellungen in diesen Richtlinien, die verbessert werden müssen (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="a53b3-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="a53b3-143">Die Typen von Richtlinien lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a53b3-143">The types of policies are:</span></span>

- <span data-ttu-id="a53b3-144">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="a53b3-144">**Anti-spam**</span></span>
- <span data-ttu-id="a53b3-145">**Anti-Phishing**</span><span class="sxs-lookup"><span data-stu-id="a53b3-145">**Anti-phishing**</span></span>
- <span data-ttu-id="a53b3-146">**Anti-Malware**</span><span class="sxs-lookup"><span data-stu-id="a53b3-146">**Anti-malware**</span></span>
- <span data-ttu-id="a53b3-147">**ATP-sichere Anlagen** (wenn Ihr Abonnement ATP umfasst)</span><span class="sxs-lookup"><span data-stu-id="a53b3-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="a53b3-148">**ATP-sichere Links** (wenn Ihr Abonnement ATP umfasst)</span><span class="sxs-lookup"><span data-stu-id="a53b3-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="a53b3-149">In der Standardansicht wird alles reduziert.</span><span class="sxs-lookup"><span data-stu-id="a53b3-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="a53b3-150">Neben den einzelnen Richtlinien wird eine Zusammenfassung der Vergleichsergebnisse aus ihren Richtlinien (die Sie ändern können) und die Einstellungen in den entsprechenden Richtlinien für die Standard mäßigen oder strengen Schutzprofile angezeigt, die Sie nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="a53b3-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="a53b3-151">Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a53b3-151">You'll see the following information:</span></span>

- <span data-ttu-id="a53b3-152">**Grün**: alle Einstellungen in allen vorhandenen Richtlinien sind mindestens so sicher wie das Schutzprofil, mit dem Sie verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="a53b3-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="a53b3-153">**Amber**: eine kleine Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil, mit dem Sie verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="a53b3-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="a53b3-154">**Rot**: eine beträchtliche Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil, mit dem Sie verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="a53b3-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="a53b3-155">Dabei kann es sich um einige Einstellungen in vielen Richtlinien oder um viele Einstellungen in einer Richtlinie handeln.</span><span class="sxs-lookup"><span data-stu-id="a53b3-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="a53b3-156">Für günstige Vergleiche wird der Text angezeigt: **alle Einstellungen folgen** den \<**Standard** or **Strict**\> **Empfehlungen**.</span><span class="sxs-lookup"><span data-stu-id="a53b3-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="a53b3-157">Andernfalls wird die Anzahl der empfohlenen Einstellungen angezeigt, die geändert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="a53b3-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="a53b3-158">Wenn Sie den **Namen der Richtliniengruppe/Einstellung**erweitern, werden alle Richtlinien und die zugehörigen Einstellungen in jeder spezifischen Richtlinie, die Aufmerksamkeit erfordern, aufgedeckt.</span><span class="sxs-lookup"><span data-stu-id="a53b3-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="a53b3-159">Sie können auch einen bestimmten Richtlinientyp erweitern (beispielsweise **Anti-Spam**), um nur die Einstellungen in diesen Richtlinientypen anzuzeigen, die Ihre Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="a53b3-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="a53b3-160">Wenn der Vergleich keine Empfehlungen für Verbesserungen (grün) hat, zeigt das Erweitern der Richtlinie nichts.</span><span class="sxs-lookup"><span data-stu-id="a53b3-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="a53b3-161">Wenn es eine Reihe von Verbesserungsempfehlungen gibt (Amber oder rot), werden die Einstellungen, die Aufmerksamkeit erfordern, aufgedeckt, und entsprechende Informationen werden in den folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a53b3-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="a53b3-162">Der Name der Einstellung, die Ihre Aufmerksamkeit erfordert.</span><span class="sxs-lookup"><span data-stu-id="a53b3-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="a53b3-163">Im vorherigen Screenshot ist dies beispielsweise der **Schwellenwert für Massen-e-Mails** in einer Anti-Spam-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a53b3-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="a53b3-164">**Richtlinie**: der Name der betroffenen Richtlinie, die die Einstellung enthält.</span><span class="sxs-lookup"><span data-stu-id="a53b3-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="a53b3-165">**Angewendet auf**: die Anzahl der Benutzer, auf die die betroffenen Richtlinien angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a53b3-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="a53b3-166">**Aktuelle Konfiguration**: der aktuelle Wert der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="a53b3-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="a53b3-167">**Zuletzt geändert**: das Datum, an dem die Richtlinie zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="a53b3-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="a53b3-168">**Empfehlungen**: der Wert der Einstellung im Standard mäßigen oder strengen Schutzprofil.</span><span class="sxs-lookup"><span data-stu-id="a53b3-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="a53b3-169">Klicken Sie auf über **nehmen**, um den Wert der Einstellung in Ihrer Richtlinie so zu ändern, dass er dem empfohlenen Wert im Schutzprofil entspricht.</span><span class="sxs-lookup"><span data-stu-id="a53b3-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="a53b3-170">Wenn die Änderung erfolgreich war, wird die Meldung angezeigt: **Empfehlungen wurden erfolgreich angenommen**.</span><span class="sxs-lookup"><span data-stu-id="a53b3-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="a53b3-171">Klicken Sie auf **Aktualisieren** , um die reduzierte Anzahl von Empfehlungen und das Entfernen der spezifischen Einstellung/Richtlinienzeile aus den Ergebnissen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a53b3-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="a53b3-172">Konfigurations Drift Analyse und Registerkarte Verlauf in der Konfigurationsanalyse</span><span class="sxs-lookup"><span data-stu-id="a53b3-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="a53b3-173">Auf dieser Registerkarte können Sie die Änderungen nachverfolgen, die Sie basierend auf den Informationen im Security Analyzer an Ihren benutzerdefinierten Sicherheitsrichtlinien vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="a53b3-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="a53b3-174">Standardmäßig werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a53b3-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="a53b3-175">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="a53b3-175">**Last modified**</span></span>
- <span data-ttu-id="a53b3-176">**Geändert von**</span><span class="sxs-lookup"><span data-stu-id="a53b3-176">**Modified by**</span></span>
- <span data-ttu-id="a53b3-177">**Einstellungs Name**</span><span class="sxs-lookup"><span data-stu-id="a53b3-177">**Setting Name**</span></span>
- <span data-ttu-id="a53b3-178">**Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="a53b3-178">**Policy**</span></span>
- <span data-ttu-id="a53b3-179">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a53b3-179">**Type**</span></span>

<span data-ttu-id="a53b3-180">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="a53b3-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a53b3-181">Im eingeblendeten **Filter** -Flyout können Sie aus den folgenden Filtern auswählen:</span><span class="sxs-lookup"><span data-stu-id="a53b3-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="a53b3-182">**Startzeit** und **Endzeit** (Datum)</span><span class="sxs-lookup"><span data-stu-id="a53b3-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="a53b3-183">**Standard Schutz** oder **strenger Schutz**</span><span class="sxs-lookup"><span data-stu-id="a53b3-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="a53b3-184">Klicken Sie auf **exportieren**, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="a53b3-184">To export the results to a .csv file, click **Export**.</span></span>

![Konfigurations Drift Analyse und Verlaufsansicht in der Konfigurationsanalyse](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
