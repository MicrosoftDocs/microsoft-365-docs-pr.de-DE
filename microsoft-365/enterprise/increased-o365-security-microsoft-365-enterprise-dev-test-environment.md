---
title: Erhöhte Sicherheit von Office 365 für die Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie in diesem Test Lab Guide So aktivieren Sie zusätzliche Einstellungen von Office 365-Sicherheit Ihrer Umgebung für Microsoft 365 Enterprise.
ms.openlocfilehash: f46db95a3bd216bdd8f46230d623e8a7f36f7f85
ms.sourcegitcommit: 42e4d280b562304335efc93787c89992504c5823
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26538772"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4f5e8-103">Erhöhte Sicherheit von Office 365 für die Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="4f5e8-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4f5e8-104">Mit den Anweisungen in diesem Artikel konfigurieren Sie zusätzliche Einstellungen von Office 365 zum Erhöhen der Sicherheit in Ihrer testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4f5e8-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4f5e8-107">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4f5e8-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4f5e8-108">Wenn Sie auf einfache Weise mit den Mindestanforderungen erhöhte Sicherheit für Office 365 konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4f5e8-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4f5e8-109">Wenn Sie in einer simulierten Enterprise erhöhte Sicherheit für Office 365 konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4f5e8-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f5e8-p101">Erhöhte Sicherheit für Office 365 Testen erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="4f5e8-112">Phase 2: Konfigurieren von erhöhte Sicherheit für Office 365</span><span class="sxs-lookup"><span data-stu-id="4f5e8-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="4f5e8-p102">In dieser Phase können Sie erhöhte Sicherheit für Office 365 für Ihre Umgebung für Microsoft 365 Enterprise. Weitere Einzelheiten und Einstellungen finden Sie unter [Configure Ihre Office 365-Mandanten, um eine höhere Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="4f5e8-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="4f5e8-115">Konfigurieren von SharePoint Online, um apps zu blockieren, die moderne Authentifizierung nicht unterstützen</span><span class="sxs-lookup"><span data-stu-id="4f5e8-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="4f5e8-116">Apps, die moderne Authentifizierung nicht unterstützen können nicht angewendet werden, also ein wichtiges Element der Schützen Ihres Microsoft-365-Abonnements und seine digitaler Objekte [Identität und Gerät zugreifen Konfigurationen](microsoft-365-policies-configurations.md) haben.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="4f5e8-117">Wechseln Sie zu der Office-Portal ([https://office.com](https://office.com)) und melden Sie sich Test Office 365-Abonnement mit Ihrer globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="4f5e8-118">Wenn Sie die einfache Microsoft 365 Test-Umgebung verwenden, melden Sie sich von Ihrem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="4f5e8-119">Bei Verwendung die testumgebung simulierten Enterprise Microsoft 365 mithilfe von der [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer CLIENT1, und melden Sie sich von CLIENT1 aus.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="4f5e8-120">Klicken Sie auf der Registerkarte **Microsoft 365 Administrationscenter** auf **Admin**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="4f5e8-121">Klicken Sie auf der Registerkarte Neu **Microsoft 365 Administrationscenter** auf **Zentriert Admin > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="4f5e8-122">Klicken Sie auf der Registerkarte Neu **SharePoint Administrationscenter** **Steuerung des Zugriffs**auf.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="4f5e8-123">Klicken Sie unter **Apps, die moderne Authentifizierung nicht unterstützen**, auf **Blockieren > OK**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-123">Under **Apps that don’t support modern authentication**, click **Block > OK**.</span></span>


### <a name="enable-advanced-threat-protection-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4f5e8-124">Aktivieren Sie die erweiterte Threat Protection (ATP) für SharePoint, OneDrive und Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="4f5e8-124">Enable Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="4f5e8-p103">Office 365 erweiterte Threat Protection (ATP) ist ein Feature von Exchange Online Protection (EOP), mit deren behalten Schadsoftware aus Ihrer e-Mails. Mit ATP Sie Richtlinien erstellen, in der Exchange-Verwaltungskonsole (EAC) oder die Sicherheit und Compliance Center, die sicherstellen, dass Ihre Benutzer greifen Sie auf nur Links oder Anlagen in e-Mails, die als nicht bösartige identifiziert werden. Weitere Informationen finden Sie unter [erweiterte Schutz für sichere Anlagen und sichere Links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="4f5e8-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="4f5e8-128">Klicken Sie auf der Registerkarte **Microsoft 365 Administrationscenter** Ihres Browsers auf **Zentriert Admin > Sicherheit und Compliance**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="4f5e8-129">Klicken Sie auf der neuen Registerkarte **Sicherheit und Compliance** auf **Bedrohung Verwaltung > Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="4f5e8-130">Klicken Sie auf **ATP sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="4f5e8-131">Klicken Sie im **sicheren Anlagen** aktivieren Sie das Kontrollkästchen **auf ATP für SharePoint, OneDrive, und Microsoft-Teams**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="4f5e8-132">Anti-Malware aktivieren</span><span class="sxs-lookup"><span data-stu-id="4f5e8-132">Enable anti-malware</span></span>

<span data-ttu-id="4f5e8-p104">Malware besteht Viren und Spyware. Viren infiziert andere Programme und Daten, und sie Ihren Computer Programme infiziert Nachrichtensymbol verteilt. Spyware bezieht sich auf Schadsoftware, die Ihre persönlichen Informationen, wie etwa-Anmeldung und persönliche Daten sammelt und sendet ihn wieder an den Autor Malware.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="4f5e8-p105">Office 365 verfügt über integrierte Malware- und spamfilterfunktionen, die eingehende und ausgehende Nachrichten vor Schadsoftware schützen und Schutz vor Spam. Weitere Informationen finden Sie unter [Anti-Spam & Anti-Malware Protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="4f5e8-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="4f5e8-138">So stellen Sie sicher, dass Anti-Malware Verarbeitung für Dateien mit gemeinsamen Anlagendateitypen ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="4f5e8-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="4f5e8-139">Klicken Sie auf die zurück-Schaltfläche in Ihrem Browser zu der Seite **Richtlinie** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="4f5e8-140">Klicken Sie auf **Anti-Malware**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="4f5e8-141">Doppelklicken Sie auf die Richtlinie mit dem Namen **Default**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="4f5e8-142">Klicken Sie auf **Einstellungen**, klicken Sie im Fenster **Antischadsoftware - Richtlinie** .</span><span class="sxs-lookup"><span data-stu-id="4f5e8-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="4f5e8-143">Klicken Sie unter **allgemeine Typen von Anhängen Filter**auf **auf > Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="4f5e8-144">Phase 3: Untersuchen Sie Sicherheits-Tools für Office 365 und Protokolle</span><span class="sxs-lookup"><span data-stu-id="4f5e8-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="4f5e8-145">In dieser Phase betrachten Sie integrierte Dienste, die über Sicherheitsereignisse informiert Sie und Ihre Sicherheitsstatus messen.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="4f5e8-146">Threat Management dashboard</span><span class="sxs-lookup"><span data-stu-id="4f5e8-146">Threat management dashboard</span></span>

<span data-ttu-id="4f5e8-p106">Office 365 Threat Management hilft Ihnen steuern und Verwalten von mobilen Gerätezugriff auf die Daten des Unternehmen, Ihre Organisation vor Datenverlust schützen und Schutz von eingehenden und ausgehenden Nachrichten vor Schadsoftware und Spam. Sie können auch Bedrohung, dass Management zum Schutz Ihrer Domäne und um zu bestimmen, ob Absender in böswilliger Absicht spoofing sind oder nicht von Ihrer Domäne Konten verwenden. Weitere Informationen finden Sie unter [Threat Management in Office 365-Sicherheit & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="4f5e8-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="4f5e8-150">Verwenden Sie folgende Schritte aus, um das Office 365 Threat Management Dashboard anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="4f5e8-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="4f5e8-151">Klicken Sie auf der Registerkarte **Microsoft 365 Administrationscenter** Ihres Browsers auf **Zentriert Admin > Sicherheit und Compliance**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="4f5e8-152">Klicken Sie auf der neuen Registerkarte **Sicherheit und Compliance** auf **Bedrohung Verwaltung > Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="4f5e8-153">Beachten Sie auf der neuen Registerkarte **Dashboard** in Ihrem Browser die Malwaretrends, Erkenntnisse und anderen Abschnitten des Dashboards.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="4f5e8-154">Dashboard für Office 365-Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4f5e8-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="4f5e8-p107">Office 365 Cloud App-Sicherheit, früher bekannt als Office 365 Advanced Security Management können Sie Richtlinien erstellen, die für überwachen und informieren Sie verdächtige Aktivitäten in Ihrem Office 365-Abonnement, damit Sie überprüfen können, und möglich leiten Remediation-Aktion. Weitere Informationen finden Sie unter [Overview of Office 365 Cloud App-Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="4f5e8-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="4f5e8-157">Klicken Sie auf der Registerkarte **Microsoft 365 Administrationscenter** Ihres Browsers auf **Zentriert Admin > Sicherheit und Compliance**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="4f5e8-158">Klicken Sie auf der neuen Registerkarte **Sicherheit und Compliance** auf **Warnungen > erweiterte Benachrichtigungen verwalten > Gehe zu Office 365-Cloud-App-Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="4f5e8-159">Beachten Sie auf der Registerkarte Neu **Cloud App-Sicherheit** Dashboard-Ansicht und die Liste der Standard-Richtlinien, die überwacht werden, die für verschiedene Aktivitäten in Ihrem Office 365-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="4f5e8-160">Klicken Sie auf das Dashboard-Symbol, um eine Zusammenfassung der Cloud App-Sicherheit Aktivitäten angezeigt, die überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="4f5e8-161">Klicken Sie auf **Überprüfen** (das Symbol Brille) und dann auf **Aktivitätsprotokolls** , um die Liste der zuletzt verwendete Anmeldungen und andere Aktivitäten finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="4f5e8-162">Sichere Score</span><span class="sxs-lookup"><span data-stu-id="4f5e8-162">Secure Score</span></span>

1. <span data-ttu-id="4f5e8-163">Erstellen Sie eine neue Registerkarte in Ihrem Browser, und wechseln Sie zur **securescore.office.com**.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="4f5e8-164">Beachten Sie auf der **Registerkarte Dashboard**Ihr aktuelles Ergebnis Secure und die Liste der Aktionen in der Warteschlange, um Ihr Ergebnis zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="4f5e8-165">Finden Sie im Schritt [konfigurieren eine höhere Sicherheit für Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) in der Phase **Information Protection** Informationen und Links zum Konfigurieren dieser Einstellungen in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="4f5e8-166">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4f5e8-166">Next step</span></span>

<span data-ttu-id="4f5e8-167">Hier finden Sie zusätzliche [Informationen Protection](m365-enterprise-test-lab-guides.md#information-protection) Features und Funktionen in Ihrer testumgebung.</span><span class="sxs-lookup"><span data-stu-id="4f5e8-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f5e8-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f5e8-168">See also</span></span>

[<span data-ttu-id="4f5e8-169">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4f5e8-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4f5e8-170">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4f5e8-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4f5e8-171">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4f5e8-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

