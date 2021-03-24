---
title: Erhöhte Microsoft 365-Sicherheit für Ihre Microsoft 365 for Enterprise-Testumgebung
f1.keywords:
- NOCSH
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
description: Verwenden Sie dieses Testumgebungshandbuch, um zusätzliche Microsoft 365-Sicherheitseinstellungen für Ihre Microsoft 365 for Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 186452396af4227a94a7f6cd0fa0109e9d6a7e17
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051270"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5cb04-103">Erhöhte Microsoft 365-Sicherheit für Ihre Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="5cb04-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5cb04-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="5cb04-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5cb04-105">Mit den Anweisungen in diesem Artikel konfigurieren Sie zusätzliche Microsoft 365-Einstellungen, um die Sicherheit in Ihrer Microsoft 365 for Enterprise-Testumgebung zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="5cb04-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5cb04-107">Klicken Sie [hier](../downloads/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5cb04-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5cb04-108">Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="5cb04-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5cb04-109">Wenn Sie die erhöhte Sicherheit von Microsoft 365 nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="5cb04-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5cb04-110">Wenn Sie erhöhte Microsoft 365-Sicherheit in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5cb04-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5cb04-111">Das Testen erhöhter Microsoft 365-Sicherheit erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet umfasst, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="5cb04-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5cb04-112">Es wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="5cb04-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="5cb04-113">Phase 2: Konfigurieren erhöhter Microsoft 365-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5cb04-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="5cb04-114">In dieser Phase aktivieren Sie erhöhte Microsoft 365-Sicherheit für Ihre Microsoft 365 for Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="5cb04-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="5cb04-115">Weitere Details und Einstellungen finden Sie unter [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="5cb04-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="5cb04-116">Konfigurieren von SharePoint Online zum Blockieren von Apps, die keine moderne Authentifizierung unterstützen</span><span class="sxs-lookup"><span data-stu-id="5cb04-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="5cb04-117">Apps, die die moderne Authentifizierung nicht unterstützen, können keine Identitäts- und Gerätezugriffskonfigurationen auf sie angewendet werden. [Dies](../security/defender-365-security/microsoft-365-policies-configurations.md) ist ein wichtiges Element zum Sichern Ihres Microsoft 365-Abonnements und seiner digitalen Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="5cb04-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="5cb04-118">Wechseln Sie zum Microsoft 365 Admin Center ( ) und melden Sie sich mit Ihrem globalen Administratorkonto bei Ihrem [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365-Testumgebungsabonnement an.</span><span class="sxs-lookup"><span data-stu-id="5cb04-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="5cb04-119">Wenn Sie die einfache Microsoft 365-Testumgebung verwenden, melden Sie sich von Ihrem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="5cb04-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="5cb04-120">Wenn Sie die simulierte Microsoft 365-Testumgebung [](https://portal.azure.com) des Unternehmens verwenden, verwenden Sie das Azure-Portal, um eine Verbindung mit dem virtuellen CLIENT1-Computer herzustellen, und melden Sie sich dann über CLIENT1 an.</span><span class="sxs-lookup"><span data-stu-id="5cb04-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="5cb04-121">Klicken Sie auf der neuen **Registerkarte Microsoft 365 Admin Center** unter Admin **Center** im linken Navigationsbereich auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="5cb04-122">Klicken Sie auf der neuen **Registerkarte SharePoint Admin Center** auf Richtlinien > **Zugriffssteuerung**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="5cb04-123">Klicken Sie auf Apps, die die moderne **Authentifizierung nicht unterstützen,** wählen Sie **Zugriff blockieren** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="5cb04-124">Aktivieren von Defender für Office 365 für SharePoint, OneDrive for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5cb04-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="5cb04-125">Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.</span><span class="sxs-lookup"><span data-stu-id="5cb04-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="5cb04-126">Wechseln Sie zum [Security & Compliance Center,](https://protection.office.com) und melden Sie sich mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="5cb04-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="5cb04-127">Klicken Sie im linken Navigationsbereich unter **Bedrohungsverwaltung** auf **Richtlinie,** und klicken Sie dann auf **Sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="5cb04-128">Unter **Dateien in SharePoint, OneDrive und Microsoft Teams schützen**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="5cb04-129">Wählen **Sie ATP für SharePoint, OneDrive** und Microsoft Teams aktivieren aus.</span><span class="sxs-lookup"><span data-stu-id="5cb04-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="5cb04-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="5cb04-131">Aktivieren von Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="5cb04-131">Enable anti-malware</span></span>

<span data-ttu-id="5cb04-132">Malware ist Schadsoftware, die aus Viren und Spyware besteht.</span><span class="sxs-lookup"><span data-stu-id="5cb04-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="5cb04-133">Viren infizieren Programme und Daten und breiten sich auf dem ganzen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="5cb04-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="5cb04-134">Als Spyware wird Schadsoftware bezeichnet, die persönliche Informationen, wie etwa Anmelde- und persönliche Daten, auf Ihrem Computer erfasst und an den Urheber der Schadsoftware zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="5cb04-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="5cb04-135">Microsoft 365 verfügt über integrierte Schadsoftware- und Spamfilterfunktionen, die ein- und ausgehende Nachrichten vor Schadsoftware schützen und Sie vor Spam schützen.</span><span class="sxs-lookup"><span data-stu-id="5cb04-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="5cb04-136">Weitere Informationen finden Sie unter [Antispamschutz & Schutz vor Schadsoftware](../security/defender-365-security/anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="5cb04-136">For more information, see [Anti-spam & anti-malware protection](../security/defender-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="5cb04-137">So stellen Sie sicher, dass die Schadsoftwareverarbeitung für Dateien mit gängigen Anlagendateitypen ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="5cb04-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="5cb04-138">Klicken Sie auf die Schaltfläche Zurück in Ihrem Browser, um zur Seite **Richtlinie zurück** zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="5cb04-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="5cb04-139">Klicken Sie **auf An malware**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="5cb04-140">Doppelklicken Sie auf die Richtlinie mit dem Namen **Standard**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="5cb04-141">Klicken Sie im Fenster Richtlinie für **Schadsoftware** auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="5cb04-142">Wählen **Sie unter Filter Allgemeine Anlagentypen** die Option **Ein** aus, und klicken Sie dann auf **Speichern.**</span><span class="sxs-lookup"><span data-stu-id="5cb04-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="5cb04-143">Phase 3: Untersuchen des Sicherheitsdashboards</span><span class="sxs-lookup"><span data-stu-id="5cb04-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="5cb04-144">Die Bedrohungsverwaltung in Microsoft 365 kann Ihnen helfen, den Zugriff mobiler Geräte auf die Daten Ihrer Organisation zu steuern und zu verwalten, Ihre Organisation vor Datenverlust zu schützen und eingehende und ausgehende Nachrichten vor Schadsoftware und Spam zu schützen.</span><span class="sxs-lookup"><span data-stu-id="5cb04-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="5cb04-145">Sie verwenden auch die Bedrohungsverwaltung, um die Reputation Ihrer Domäne zu schützen und zu bestimmen, ob Absender Konten aus Ihrer Domäne böswillig spoofieren.</span><span class="sxs-lookup"><span data-stu-id="5cb04-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="5cb04-146">So sehen Sie das Sicherheitsdashboard:</span><span class="sxs-lookup"><span data-stu-id="5cb04-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="5cb04-147">Wechseln Sie bei Bedarf zum [Security & Compliance Center,](https://protection.office.com) und melden Sie sich mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="5cb04-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="5cb04-148">Klicken Sie im linken Navigationsbereich unter **Bedrohungsverwaltung** auf **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="5cb04-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="5cb04-149">Werfen Sie einen genauen Blick auf alle Karten auf dem Dashboard, um sich mit den bereitgestellten Informationen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="5cb04-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="5cb04-150">Weitere Informationen finden Sie unter [Security Dashboard](../security/defender-365-security/security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="5cb04-150">For more information, see [Security Dashboard](../security/defender-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="5cb04-151">Phase 4: Überprüfen der Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="5cb04-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="5cb04-152">Microsoft Secure Score zeigt Ihre Sicherheitslage als Zahl an, die Ihre aktuelle Stufe relativ zu den Features angibt, die in Ihrem Abonnement verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5cb04-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="5cb04-153">Außerdem erhalten Sie eine Liste der Verbesserungsmaßnahmen, die Sie zur Verbesserung Ihrer Bewertung ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="5cb04-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="5cb04-154">Erstellen Sie eine neue Registerkarte in Ihrem Browser, wechseln Sie zum [Microsoft 365 Security Center,](https://security.microsoft.com/)und klicken Sie dann auf **Punktzahl sichern.**</span><span class="sxs-lookup"><span data-stu-id="5cb04-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="5cb04-155">Notieren Sie **sich**  auf der Registerkarte Übersicht Ihre aktuelle Secure Score und wie sie mit dem globalen Durchschnitt und Abonnements mit einer ähnlichen Anzahl von Lizenzen verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="5cb04-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="5cb04-156">Lesen Sie **auf der** Registerkarte Verbesserungsaktionen die Liste der Aktionen durch, die Sie zum Erhöhen Ihrer Bewertung ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="5cb04-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="5cb04-157">Weitere Informationen finden Sie unter [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="5cb04-157">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5cb04-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5cb04-158">Next steps</span></span>

<span data-ttu-id="5cb04-159">Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#information-protection) Funktionen zum Schutz von Informationen in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="5cb04-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cb04-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cb04-160">See also</span></span>

[<span data-ttu-id="5cb04-161">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5cb04-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5cb04-162">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5cb04-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5cb04-163">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5cb04-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)