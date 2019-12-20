---
title: Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um zusätzliche Microsoft 365-Sicherheitseinstellungen für Ihre Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 8e8e05f223faedd60ea53683b3531964b3220291
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801690"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4315f-103">Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="4315f-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4315f-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="4315f-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4315f-105">Mit den Anweisungen in diesem Artikel Konfigurieren Sie zusätzliche Einstellungen von Microsoft 365, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4315f-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4315f-107">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4315f-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4315f-108">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="4315f-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4315f-109">Wenn Sie die erhöhte Sicherheit von Microsoft 365 nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4315f-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4315f-110">Wenn Sie die erhöhte Sicherheit von Microsoft 365 in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4315f-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4315f-111">Für das Testen der erhöhten Sicherheit von Microsoft 365 ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS)-Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="4315f-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4315f-112">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="4315f-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="4315f-113">Phase 2: Konfigurieren der erhöhten Sicherheit von Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4315f-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="4315f-114">In dieser Phase aktivieren Sie die erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="4315f-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="4315f-115">Weitere Details und Einstellungen finden Sie unter [Konfigurieren des Office 365 Mandanten für erhöhte Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="4315f-115">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="4315f-116">Konfigurieren von SharePoint Online zum Blockieren von apps, die keine moderne Authentifizierung unterstützen</span><span class="sxs-lookup"><span data-stu-id="4315f-116">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="4315f-117">Für apps, die keine moderne Authentifizierung unterstützen, können keine [Identitäts-und Gerätezugriffs Konfigurationen](microsoft-365-policies-configurations.md) angewendet werden, was ein wichtiges Element für die Sicherung Ihres Microsoft 365-Abonnements und seiner digitalen Objekte ist.</span><span class="sxs-lookup"><span data-stu-id="4315f-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="4315f-118">Wechseln Sie zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)), und melden Sie sich bei Ihrem Microsoft 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="4315f-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="4315f-119">Wenn Sie die einfache Microsoft 365-Testumgebung verwenden, melden Sie sich von Ihrem lokalen Computer aus an.</span><span class="sxs-lookup"><span data-stu-id="4315f-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="4315f-120">Wenn Sie die simulierte Enterprise Microsoft 365-Testumgebung verwenden, verwenden Sie das [Azure-Portal](https://portal.azure.com) , um eine Verbindung mit dem virtuellen Computer Client1 herzustellen, und melden Sie sich dann von CLIENT1 aus an.</span><span class="sxs-lookup"><span data-stu-id="4315f-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="4315f-121">Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** unter **Admin Center** im linken Navigationsbereich auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4315f-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="4315f-122">Klicken Sie auf der neuen **SharePoint Admin Center** -Registerkarte auf **Zugriffssteuerung**.</span><span class="sxs-lookup"><span data-stu-id="4315f-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="4315f-123">Klicken Sie auf **apps, die die moderne Authentifizierung nicht unterstützen**, wählen Sie **Zugriff blockieren**aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4315f-123">Click **Apps that don’t support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="4315f-124">Aktivieren von Advanced Threat Protection für SharePoint, OneDrive für Unternehmen und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4315f-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="4315f-125">Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.</span><span class="sxs-lookup"><span data-stu-id="4315f-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="4315f-126">Wechseln Sie zum [Office 365 Security #a0 Compliance Center](https://protection.office.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="4315f-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="4315f-127">Klicken Sie im linken Navigationsbereich unter **Bedrohungs Verwaltung**auf **Richtlinie**, und klicken Sie dann auf **ATP-sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="4315f-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="4315f-128">Unter **Protect Files in SharePoint, OneDrive und Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="4315f-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="4315f-129">Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="4315f-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="4315f-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4315f-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="4315f-131">Anti-Malware aktivieren</span><span class="sxs-lookup"><span data-stu-id="4315f-131">Enable anti-malware</span></span>

<span data-ttu-id="4315f-132">Malware ist Schadsoftware, die aus Viren und Spyware besteht.</span><span class="sxs-lookup"><span data-stu-id="4315f-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="4315f-133">Viren infizieren Programme und Daten und breiten sich auf dem ganzen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="4315f-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="4315f-134">Als Spyware wird Schadsoftware bezeichnet, die persönliche Informationen, wie etwa Anmelde- und persönliche Daten, auf Ihrem Computer erfasst und an den Urheber der Schadsoftware zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="4315f-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="4315f-135">Microsoft 365 verfügt über integrierte Funktionen für Malware und Spamfilterung, mit denen eingehende und ausgehende Nachrichten vor bösartiger Software geschützt werden und Sie vor Spam schützen können.</span><span class="sxs-lookup"><span data-stu-id="4315f-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="4315f-136">Weitere Informationen finden Sie unter [Anti-Spam-#a0 Schutz vor Schadsoftware in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="4315f-136">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="4315f-137">Um sicherzustellen, dass die Antischadsoftware-Verarbeitung für Dateien mit gängigen Anlagendateitypen ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="4315f-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="4315f-138">Klicken Sie auf die Schaltfläche "zurück" in Ihrem Browser, um zur **Richtlinien** Seite zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="4315f-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="4315f-139">Klicken Sie auf **Anti-Malware**.</span><span class="sxs-lookup"><span data-stu-id="4315f-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="4315f-140">Doppelklicken Sie auf die Richtlinie mit dem Namen **default**.</span><span class="sxs-lookup"><span data-stu-id="4315f-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="4315f-141">Klicken Sie im Fenster **Anti-Malware-Richtlinie** auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="4315f-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="4315f-142">Wählen Sie unter **Allgemeine Anlagentypen Filter**die Option **ein**aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4315f-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="4315f-143">Phase 3: Überprüfen des Sicherheits Dashboards</span><span class="sxs-lookup"><span data-stu-id="4315f-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="4315f-144">Office 365 Threat Management kann Ihnen dabei helfen, den Zugriff auf die Daten Ihrer Organisation zu steuern und zu verwalten, Ihre Organisation vor Datenverlust zu schützen und eingehende und ausgehende Nachrichten vor bösartiger Software und Spam zu schützen.</span><span class="sxs-lookup"><span data-stu-id="4315f-144">Office 365 threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="4315f-145">Außerdem verwenden Sie Threat Management, um die Reputation Ihrer Domäne zu schützen und festzustellen, ob Absender böswillige Konten aus Ihrer Domäne Spoofing.</span><span class="sxs-lookup"><span data-stu-id="4315f-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="4315f-146">So zeigen Sie das Sicherheits Dashboard an:</span><span class="sxs-lookup"><span data-stu-id="4315f-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="4315f-147">Wechseln Sie bei Bedarf zum [Office 365 Security #a0 Compliance Center](https://protection.office.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="4315f-147">If needed, go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="4315f-148">Klicken Sie im linken Navigationsbereich unter **Bedrohungs Verwaltung**auf **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="4315f-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="4315f-149">Werfen Sie einen Blick auf alle Karten im Dashboard, um sich mit den bereitgestellten Informationen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="4315f-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="4315f-150">Weitere Informationen finden Sie unter [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span><span class="sxs-lookup"><span data-stu-id="4315f-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="4315f-151">Phase 4: Untersuchen von Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="4315f-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="4315f-152">Microsoft Secure Score zeigt Ihre Sicherheitsposition als Nummer an, die Ihre aktuelle Ebene relativ zu den in Ihrem Abonnement verfügbaren Features angibt.</span><span class="sxs-lookup"><span data-stu-id="4315f-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="4315f-153">Außerdem erhalten Sie eine Liste von Verbesserungs Aktionen, die Sie ausführen können, um Ihre Punktzahl zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4315f-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="4315f-154">Erstellen Sie eine neue Registerkarte in Ihrem Browser, und wechseln Sie zum [Microsoft 365-Sicherheitscenter](https://security.microsoft.com/), und klicken Sie dann auf **sichere Bewertung**.</span><span class="sxs-lookup"><span data-stu-id="4315f-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="4315f-155">Notieren Sie sich auf der Registerkarte **Übersicht** Ihre aktuelle sichere Bewertung und wie diese mit dem globalen Durchschnitt und Abonnements mit ähnlicher Anzahl von Lizenzen verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="4315f-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="4315f-156">Lesen Sie auf der Registerkarte **Verbesserungs Aktionen** die Liste der Aktionen durch, die Sie ausführen können, um Ihre Punktzahl zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4315f-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="4315f-157">Weitere Informationen finden Sie unter [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="4315f-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4315f-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4315f-158">Next steps</span></span>

<span data-ttu-id="4315f-159">Informationen und Links zum Konfigurieren dieser Einstellungen in der Produktion finden Sie im Schritt [configure more Security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) in der **Information Protection** -Phase.</span><span class="sxs-lookup"><span data-stu-id="4315f-159">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="4315f-160">Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="4315f-160">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4315f-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4315f-161">See also</span></span>

[<span data-ttu-id="4315f-162">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4315f-162">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4315f-163">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4315f-163">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4315f-164">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4315f-164">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
