---
title: Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie dieses Test Labor Handbuch, um zusätzliche Microsoft 365-Sicherheitseinstellungen für Ihre Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 54e05122dcbe5d4e24f092536897f2a8ad449e05
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283655"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6d372-103">Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="6d372-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6d372-104">Mit den Anweisungen in diesem Artikel Konfigurieren Sie zusätzliche Microsoft 365-Einstellungen, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6d372-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6d372-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6d372-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6d372-107">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="6d372-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6d372-108">Wenn Sie nur erhöhte Sicherheit von Microsoft 365 auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6d372-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6d372-109">Wenn Sie die erhöhte Sicherheit von Microsoft 365 in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6d372-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d372-110">Das Testen der erhöhten Sicherheit von Microsoft 365 erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="6d372-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6d372-111">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="6d372-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="6d372-112">Phase 2: Konfigurieren der erhöhten Sicherheit von Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d372-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="6d372-113">In dieser Phase aktivieren Sie erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="6d372-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="6d372-114">Weitere Informationen und Einstellungen finden Sie unter [Konfigurieren Ihres Office 365-Mandanten für mehr Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="6d372-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="6d372-115">Konfigurieren von SharePoint Online zum Blockieren von apps, die keine moderne Authentifizierung unterstützen</span><span class="sxs-lookup"><span data-stu-id="6d372-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="6d372-116">Apps, die die moderne Authentifizierung nicht unterstützen, können keine [Identitäts-und Gerätezugriffs Konfigurationen](microsoft-365-policies-configurations.md) verwenden, was ein wichtiger Bestandteil der Sicherung ihres Microsoft 365-Abonnements und der digitalen Objekte ist.</span><span class="sxs-lookup"><span data-stu-id="6d372-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="6d372-117">Wechseln Sie zum Office-Portal[https://office.com](https://office.com)(), und melden Sie sich bei ihrem Office 365-Testabonnement mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="6d372-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="6d372-118">Wenn Sie die einfache Microsoft 365-Testumgebung verwenden, melden Sie sich auf dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="6d372-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="6d372-119">Wenn Sie die simulierte Enterprise-Testumgebung von Microsoft 365 verwenden, stellen Sie mithilfe des [Azure](https://portal.azure.com) -Portals eine Verbindung mit dem virtuellen Computer Client1 her, und melden Sie sich dann bei CLIENT1 an.</span><span class="sxs-lookup"><span data-stu-id="6d372-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="6d372-120">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **Admin**.</span><span class="sxs-lookup"><span data-stu-id="6d372-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="6d372-121">Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** auf **Admin Center > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6d372-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="6d372-122">Klicken Sie auf der neuen Registerkarte **SharePoint Admin Center** auf **Zugriffssteuerung**.</span><span class="sxs-lookup"><span data-stu-id="6d372-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="6d372-123">Klicken Sie unter **apps, die die moderne Authentifizierung nicht unterstützen**auf **blockieren**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d372-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="6d372-124">Aktivieren von Advanced Threat Protection für SharePoint, OneDrive for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d372-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="6d372-125">Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.</span><span class="sxs-lookup"><span data-stu-id="6d372-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="6d372-126">Wechseln Sie zum [Office 365 Security _AMP_ Compliance Center](https://protection.office.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="6d372-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="6d372-127">Wählen Sie im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie > sichere Anlagen**aus.</span><span class="sxs-lookup"><span data-stu-id="6d372-127">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="6d372-128">Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6d372-128">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="6d372-129">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6d372-129">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="6d372-130">Aktivieren von Antischadsoftware</span><span class="sxs-lookup"><span data-stu-id="6d372-130">Enable anti-malware</span></span>

<span data-ttu-id="6d372-131">Malware ist Schadsoftware, die aus Viren und Spyware besteht.</span><span class="sxs-lookup"><span data-stu-id="6d372-131">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="6d372-132">Viren infizieren Programme und Daten und breiten sich auf dem ganzen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="6d372-132">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="6d372-133">Als Spyware wird Schadsoftware bezeichnet, die persönliche Informationen, wie etwa Anmelde- und persönliche Daten, auf Ihrem Computer erfasst und an den Urheber der Schadsoftware zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="6d372-133">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="6d372-134">Office 365 verfügt über integrierte Funktionen zur Filterung von Schadsoftware und Spam, die eingehende und ausgehende Nachrichten vor Schadsoftware schützen und Sie vor Spam schützen.</span><span class="sxs-lookup"><span data-stu-id="6d372-134">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="6d372-135">Weitere Informationen finden Sie unter [Antispam-&-Schutz vor Schadsoftware in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="6d372-135">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="6d372-136">So stellen Sie sicher, dass die Antischadsoftware-Verarbeitung für Dateien mit gängigen Dateitypen von Anlagen ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="6d372-136">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="6d372-137">Klicken Sie auf die Schaltfläche "zurück" in Ihrem Browser, um zur **Richtlinien** Seite zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="6d372-137">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="6d372-138">Klicken \*\*\*\* Sie auf Antischadsoftware.</span><span class="sxs-lookup"><span data-stu-id="6d372-138">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="6d372-139">Doppelklicken Sie auf die Richtlinie mit dem Namen **default**.</span><span class="sxs-lookup"><span data-stu-id="6d372-139">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="6d372-140">Klicken Sie im Fenster Antischadsoftware **-Richtlinie** auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="6d372-140">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="6d372-141">Klicken Sie unter **Allgemeine Anlagentypen Filter** **auf > speichern**.</span><span class="sxs-lookup"><span data-stu-id="6d372-141">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="6d372-142">Phase 3: Untersuchen von Office 365-Sicherheitstools und-Protokollen</span><span class="sxs-lookup"><span data-stu-id="6d372-142">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="6d372-143">In dieser Phase sehen Sie sich die integrierten Dienste an, die Sie über Sicherheitsereignisse informieren und ihre allgemeine Sicherheitsposition messen.</span><span class="sxs-lookup"><span data-stu-id="6d372-143">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="6d372-144">Risikomanagement-Dashboard</span><span class="sxs-lookup"><span data-stu-id="6d372-144">Threat management dashboard</span></span>

<span data-ttu-id="6d372-145">Mithilfe von Office 365 Threat Management können Sie den Zugriff mobiler Geräte auf die Daten Ihrer Organisation steuern und verwalten, Ihre Organisation vor Datenverlust schützen und eingehende und ausgehende Nachrichten vor Schadsoftware und Spam schützen.</span><span class="sxs-lookup"><span data-stu-id="6d372-145">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="6d372-146">Sie verwenden auch die Bedrohungs Verwaltung, um die Reputation Ihrer Domäne zu schützen und zu ermitteln, ob Absender in böswilliger Absicht Konten aus Ihrer Domäne spoofen.</span><span class="sxs-lookup"><span data-stu-id="6d372-146">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="6d372-147">Weitere Informationen finden Sie unter [Threat Management im Microsoft 365 Security Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="6d372-147">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>


### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="6d372-148">Office 365 Cloud App-Sicherheits Dashboard</span><span class="sxs-lookup"><span data-stu-id="6d372-148">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="6d372-149">Office 365 Cloud App Security, bisher bekannt als Office 365 Advanced Security Management, ermöglicht Ihnen das Erstellen von Richtlinien, mit denen Sie verdächtige Aktivitäten in Ihrem Office 365-Abonnement überwachen und darüber informieren können, damit Sie untersuchen und mögliche Korrekturaktion.</span><span class="sxs-lookup"><span data-stu-id="6d372-149">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action.</span></span> <span data-ttu-id="6d372-150">Weitere Informationen finden Sie unter [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="6d372-150">For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="6d372-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6d372-151">Next steps</span></span>

<span data-ttu-id="6d372-152">Weitere Informationen und Links zum Konfigurieren dieser Einstellungen in der Produktionsumgebung finden Sie unter [Konfigurieren von mehr Sicherheit für Microsoft 365](infoprotect-configure-increased-security-office-365.md) Schritt in der **Informationsschutz** Phase.</span><span class="sxs-lookup"><span data-stu-id="6d372-152">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="6d372-153">Erkunden Sie zusätzliche Features und Funktionen zum [Schutz von Informationen](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="6d372-153">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d372-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d372-154">See also</span></span>

[<span data-ttu-id="6d372-155">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d372-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6d372-156">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d372-156">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6d372-157">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d372-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

