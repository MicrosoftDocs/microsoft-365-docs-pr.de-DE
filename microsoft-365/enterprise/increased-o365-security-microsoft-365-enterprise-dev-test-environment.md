---
title: Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um zusätzliche Microsoft 365-Sicherheitseinstellungen für Ihre Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 3173796167a0a9fb59e23ee2dc6eebf5000ed3d7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672691"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="aff24-103">Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="aff24-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="aff24-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="aff24-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="aff24-105">Mit den Anweisungen in diesem Artikel Konfigurieren Sie zusätzliche Einstellungen von Microsoft 365, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="aff24-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="aff24-107">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aff24-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="aff24-108">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="aff24-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="aff24-109">Wenn Sie die erhöhte Sicherheit von Microsoft 365 nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="aff24-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="aff24-110">Wenn Sie die erhöhte Sicherheit von Microsoft 365 in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="aff24-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="aff24-111">Für das Testen der erhöhten Sicherheit von Microsoft 365 ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="aff24-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="aff24-112">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="aff24-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="aff24-113">Phase 2: Konfigurieren der erhöhten Sicherheit von Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aff24-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="aff24-114">In dieser Phase aktivieren Sie die erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="aff24-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="aff24-115">Weitere Details und Einstellungen finden Sie unter [Konfigurieren des Office 365 Mandanten für erhöhte Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="aff24-115">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="aff24-116">Konfigurieren von SharePoint Online zum Blockieren von apps, die keine moderne Authentifizierung unterstützen</span><span class="sxs-lookup"><span data-stu-id="aff24-116">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="aff24-117">Für apps, die keine moderne Authentifizierung unterstützen, können keine [Identitäts-und Gerätezugriffs Konfigurationen](microsoft-365-policies-configurations.md) angewendet werden, was ein wichtiges Element für die Sicherung Ihres Microsoft 365-Abonnements und seiner digitalen Objekte ist.</span><span class="sxs-lookup"><span data-stu-id="aff24-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="aff24-118">Wechseln Sie zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)), und melden Sie sich bei Ihrem Office 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="aff24-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="aff24-119">Wenn Sie die einfache Microsoft 365-Testumgebung verwenden, melden Sie sich von Ihrem lokalen Computer aus an.</span><span class="sxs-lookup"><span data-stu-id="aff24-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="aff24-120">Wenn Sie die simulierte Enterprise Microsoft 365-Testumgebung verwenden, verwenden Sie das [Azure-Portal](https://portal.azure.com) , um eine Verbindung mit dem virtuellen Computer Client1 herzustellen, und melden Sie sich dann von CLIENT1 aus an.</span><span class="sxs-lookup"><span data-stu-id="aff24-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="aff24-121">Klicken Sie auf der neuen Registerkarte " **Microsoft 365 Admin Center** " auf admin Centers **#a0 SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="aff24-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
3. <span data-ttu-id="aff24-122">Klicken Sie auf der neuen **SharePoint Admin Center** -Registerkarte auf **Zugriffssteuerung**.</span><span class="sxs-lookup"><span data-stu-id="aff24-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="aff24-123">Klicken Sie unter **apps, die die moderne Authentifizierung nicht unterstützen**auf **blockieren**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="aff24-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="aff24-124">Aktivieren von Advanced Threat Protection für SharePoint, OneDrive für Unternehmen und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aff24-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="aff24-125">Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.</span><span class="sxs-lookup"><span data-stu-id="aff24-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="aff24-126">Wechseln Sie zum [Office 365 Security #a0 Compliance Center](https://protection.office.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="aff24-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="aff24-127">Wählen Sie im linken Navigationsbereich unter **Threat Management**die Option **Richtlinie #a0 sichere Anlagen**aus.</span><span class="sxs-lookup"><span data-stu-id="aff24-127">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="aff24-128">Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="aff24-128">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="aff24-129">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="aff24-129">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="aff24-130">Anti-Malware aktivieren</span><span class="sxs-lookup"><span data-stu-id="aff24-130">Enable anti-malware</span></span>

<span data-ttu-id="aff24-131">Malware ist Schadsoftware, die aus Viren und Spyware besteht.</span><span class="sxs-lookup"><span data-stu-id="aff24-131">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="aff24-132">Viren infizieren Programme und Daten und breiten sich auf dem ganzen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="aff24-132">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="aff24-133">Als Spyware wird Schadsoftware bezeichnet, die persönliche Informationen, wie etwa Anmelde- und persönliche Daten, auf Ihrem Computer erfasst und an den Urheber der Schadsoftware zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="aff24-133">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="aff24-134">Office 365 verfügt über integrierte Funktionen für Malware und Spamfilterung, mit denen eingehende und ausgehende Nachrichten vor bösartiger Software geschützt werden und Sie vor Spam schützen können.</span><span class="sxs-lookup"><span data-stu-id="aff24-134">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="aff24-135">Weitere Informationen finden Sie unter [Anti-Spam-#a0 Schutz vor Schadsoftware in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="aff24-135">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="aff24-136">Um sicherzustellen, dass die Antischadsoftware-Verarbeitung für Dateien mit gängigen Anlagendateitypen ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="aff24-136">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="aff24-137">Klicken Sie auf die Schaltfläche "zurück" in Ihrem Browser, um zur **Richtlinien** Seite zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="aff24-137">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="aff24-138">Klicken Sie auf **Anti-Malware**.</span><span class="sxs-lookup"><span data-stu-id="aff24-138">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="aff24-139">Doppelklicken Sie auf die Richtlinie mit dem Namen **default**.</span><span class="sxs-lookup"><span data-stu-id="aff24-139">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="aff24-140">Klicken Sie im Fenster **Anti-Malware-Richtlinie** auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="aff24-140">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="aff24-141">Klicken Sie unter **Allgemeine Filter für Anlagentypen** **auf #a0 speichern**.</span><span class="sxs-lookup"><span data-stu-id="aff24-141">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-the-threat-management-dashboard"></a><span data-ttu-id="aff24-142">Phase 3: Untersuchen des Threat Management-Dashboards</span><span class="sxs-lookup"><span data-stu-id="aff24-142">Phase 3: Examine the threat management dashboard</span></span>

<span data-ttu-id="aff24-143">Office 365 Threat Management kann Ihnen dabei helfen, den Zugriff auf die Daten Ihrer Organisation zu steuern und zu verwalten, Ihre Organisation vor Datenverlust zu schützen und eingehende und ausgehende Nachrichten vor bösartiger Software und Spam zu schützen.</span><span class="sxs-lookup"><span data-stu-id="aff24-143">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="aff24-144">Außerdem verwenden Sie Threat Management, um die Reputation Ihrer Domäne zu schützen und festzustellen, ob Absender böswillige Konten aus Ihrer Domäne Spoofing.</span><span class="sxs-lookup"><span data-stu-id="aff24-144">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="aff24-145">Weitere Informationen finden Sie unter [Threat Management im Microsoft 365 Security Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="aff24-145">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="aff24-146">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="aff24-146">Next steps</span></span>

<span data-ttu-id="aff24-147">Informationen und Links zum Konfigurieren dieser Einstellungen in der Produktion finden Sie im Schritt [configure more Security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) in der **Information Protection** -Phase.</span><span class="sxs-lookup"><span data-stu-id="aff24-147">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="aff24-148">Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="aff24-148">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="aff24-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aff24-149">See also</span></span>

[<span data-ttu-id="aff24-150">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aff24-150">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="aff24-151">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aff24-151">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="aff24-152">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aff24-152">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

