---
title: Neuer Microsoft Edge
description: ''
keywords: Browser, Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f4bc5f85b21148c5a923ca1fc18879a193191c4b
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094786"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="af18c-103">Neue Microsoft Edge-App</span><span class="sxs-lookup"><span data-stu-id="af18c-103">New Microsoft Edge app</span></span>

<span data-ttu-id="af18c-104">Der neue [Microsoft Edge-Browser](https://www.microsoft.com/edge) bietet erstklassige Leistung mit mehr Datenschutz, mehr Produktivität und mehr Wert beim Durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="af18c-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="af18c-105">Microsoft Managed Desktop bietet eine öffentliche Vorschau der Bereitstellung des neuen Edge-Browsers in Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="af18c-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="af18c-106">Erstbereitstellung</span><span class="sxs-lookup"><span data-stu-id="af18c-106">Initial deployment</span></span>

<span data-ttu-id="af18c-107">Um Ihre verwalteten Desktop Geräte von Microsoft auf den neuen Microsoft Edge-Browser zu migrieren, müssen Sie ein IT-Support Ticket über das Microsoft Managed Desktop Portal einreichen.</span><span class="sxs-lookup"><span data-stu-id="af18c-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="af18c-108">Wenn Sie das Ticket archivieren, stellen wir den Edge stable-Kanal für die Test Gruppe bereit und stellen ihn dann alle 24 Stunden in jeder nachfolgenden Bereitstellungsgruppe bereit.</span><span class="sxs-lookup"><span data-stu-id="af18c-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="af18c-109">Um die Bereitstellung anzuhalten, müssen Sie ein weiteres Ticket anfordern, in dem Vorgänge angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="af18c-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="af18c-110">Updates für Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="af18c-110">Updates to Microsoft Edge</span></span>

<span data-ttu-id="af18c-111">Microsoft Managed Desktop stellt den [stabilen Kanal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) von Microsoft Edge bereit, der etwa alle sechs Wochen automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="af18c-111">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="af18c-112">Updates auf dem stabilen Kanal werden [schrittweise](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) von der Microsoft Edge-Produktgruppe ausgeführt, um die beste Benutzerfreundlichkeit sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="af18c-112">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> <span data-ttu-id="af18c-113">Der Microsoft Edge Beta-Kanal ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="af18c-113">The Microsoft Edge Beta channel is not currently available.</span></span>

<span data-ttu-id="af18c-114">Um sicherzustellen, dass Microsoft Edge ordnungsgemäß aktualisiert wird, sollten Sie die Microsoft-Edge- [Update-Richtlinien](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="af18c-114">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="af18c-115">Von Microsoft Managed Desktop verwaltete Einstellungen</span><span class="sxs-lookup"><span data-stu-id="af18c-115">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="af18c-116">Microsoft Managed Desktop hat eine Reihe von Standardrichtlinien für Microsoft Edge erstellt, um den Browser zu schützen.</span><span class="sxs-lookup"><span data-stu-id="af18c-116">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="af18c-117">Die standardmäßigen Browsereinstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="af18c-117">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="af18c-118">Microsoft-Edge-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="af18c-118">Microsoft Edge extensions</span></span>

<span data-ttu-id="af18c-119">Die Sicherheitsbasis für Microsoft Edge auf Microsoft Managed Desktop-Geräten legt zwei Richtlinien fest, um alle Chrome-Erweiterungen und sicheren Endbenutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="af18c-119">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="af18c-120">Informationen zum Aktivieren und Bereitstellen von Erweiterungen in Ihrer Umgebung finden Sie unter Einstellungen, die Sie verwalten.</span><span class="sxs-lookup"><span data-stu-id="af18c-120">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="af18c-121">Erweiterungs Installations Blockliste</span><span class="sxs-lookup"><span data-stu-id="af18c-121">Extension installation blocklist</span></span>
<span data-ttu-id="af18c-122">**Standardwert:** Alle</span><span class="sxs-lookup"><span data-stu-id="af18c-122">**Default value:** All</span></span>

<span data-ttu-id="af18c-123">Microsoft Managed Desktop legt diese Richtlinie fest, um zu verhindern, dass Chrome-Erweiterungen auf verwalteten Endpunkten installiert werden.</span><span class="sxs-lookup"><span data-stu-id="af18c-123">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="af18c-124">Es gibt bekannte risksassociated mit dem Chromium-Erweiterungsmodell, einschließlich Datenverlust Schutz, Datenschutz und anderen Risiken, die Geräte gefährden können.</span><span class="sxs-lookup"><span data-stu-id="af18c-124">There are known risksassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="af18c-125">Zulassen von systemeigenen Messaginghosts auf Benutzerebene (installiert ohne Administratorberechtigungen)</span><span class="sxs-lookup"><span data-stu-id="af18c-125">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="af18c-126">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="af18c-126">**Default value:** Disabled</span></span>

<span data-ttu-id="af18c-127">Durch Deaktivieren dieser Richtlinie verwendet Microsoft Edge nur systemeigene Messaginghosts, die auf Systemebene installiert sind.</span><span class="sxs-lookup"><span data-stu-id="af18c-127">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="af18c-128">Systemeigene Messaginghosts sind ein Teil von Chrome-Erweiterungen, mit denen der Browser mit anderen Teilen des Endpunkts des Benutzers interagieren kann, wodurch eine Vielzahl von Sicherheitsaspekten entsteht.</span><span class="sxs-lookup"><span data-stu-id="af18c-128">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="af18c-129">Secure Sockets Layer (SSL)</span><span class="sxs-lookup"><span data-stu-id="af18c-129">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="af18c-130">Minimale SSL-Version</span><span class="sxs-lookup"><span data-stu-id="af18c-130">Minimum SSL version</span></span>

<span data-ttu-id="af18c-131">**Standardwert:** Mindestens TLS 1,2 unterstützt</span><span class="sxs-lookup"><span data-stu-id="af18c-131">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="af18c-132">Wenn Sie die unsicherste TLS 1,1 verwenden möchten, können Sie dies anfordern.</span><span class="sxs-lookup"><span data-stu-id="af18c-132">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="af18c-133">Ermöglicht Benutzern das Fortfahren auf der Seite SSL-Warnung</span><span class="sxs-lookup"><span data-stu-id="af18c-133">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="af18c-134">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="af18c-134">**Default value:** Disabled</span></span>

<span data-ttu-id="af18c-135">Es wird nicht empfohlen, diese Einstellung zu aktivieren, da Benutzer Websites mit SSL-Fehlern besuchen können.</span><span class="sxs-lookup"><span data-stu-id="af18c-135">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smart-screen"></a><span data-ttu-id="af18c-136">Smart Screen von Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="af18c-136">Microsoft Defender Smart Screen</span></span>

#### <a name="configure-microsoft-defender-smartscreen"></a><span data-ttu-id="af18c-137">Konfigurieren von Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="af18c-137">Configure Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="af18c-138">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="af18c-138">**Default value:** Enabled</span></span>

<span data-ttu-id="af18c-139">Standardmäßig aktiviert, um den Schutz von Endbenutzern zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="af18c-139">Enabled by default to help protect end users.</span></span>

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="af18c-140">Microsoft Defender-SmartScreen-Eingabeaufforderungen für Websites</span><span class="sxs-lookup"><span data-stu-id="af18c-140">Microsoft Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="af18c-141">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="af18c-141">**Default value:** Enabled</span></span>

<span data-ttu-id="af18c-142">Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da Benutzer Warnungen ignorieren und weiterhin potenziell schädliche Websites verwenden können.</span><span class="sxs-lookup"><span data-stu-id="af18c-142">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="af18c-143">Verhindern der Umgehung von Microsoft Defender-SmartScreen-Warnungen bei Downloads</span><span class="sxs-lookup"><span data-stu-id="af18c-143">Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="af18c-144">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="af18c-144">**Default value:** Enabled</span></span>

<span data-ttu-id="af18c-145">Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da Benutzer Warnungen ignorieren und nicht überprüfte Downloads durchführen können.</span><span class="sxs-lookup"><span data-stu-id="af18c-145">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="af18c-146">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="af18c-146">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="af18c-147">Standardeinstellung für Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="af18c-147">Default Adobe Flash setting</span></span>

<span data-ttu-id="af18c-148">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="af18c-148">**Default value:** Disabled</span></span>

<span data-ttu-id="af18c-149">Es wird nicht empfohlen, Flash aufgrund der zugeordneten Sicherheitsrisiken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="af18c-149">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="af18c-150">Wenn Sie weiterhin über Prozesse verfügen, die von Flash abhängen, legen Sie die **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** -Richtlinie so fest, dass Flash für Websites aktiviert wird, die diese benötigen.</span><span class="sxs-lookup"><span data-stu-id="af18c-150">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="af18c-151">Wenn Sie eine zulässige Liste von Websites für die Verwendung von Flash nicht verwalten können, müssen Sie eine Änderungsanforderung zum Ändern des Werts in **"Click to Play"** ändern, mit dem Benutzer auswählen können, wann Flash ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="af18c-151">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="af18c-152">Kennwort-Manager</span><span class="sxs-lookup"><span data-stu-id="af18c-152">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="af18c-153">Speichern von Kennwörtern im Password Manager aktivieren</span><span class="sxs-lookup"><span data-stu-id="af18c-153">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="af18c-154">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="af18c-154">**Default value:** Disabled</span></span>

<span data-ttu-id="af18c-155">Es wird nicht empfohlen, dass Benutzer Kennwörter auf Ihrem Gerät speichern können.</span><span class="sxs-lookup"><span data-stu-id="af18c-155">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="other-settings"></a><span data-ttu-id="af18c-156">Weitere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="af18c-156">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="af18c-157">Aktivieren der Website Isolierung für jeden Standort</span><span class="sxs-lookup"><span data-stu-id="af18c-157">Enable site isolation for every site</span></span>

<span data-ttu-id="af18c-158">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="af18c-158">**Default value:** Enabled</span></span>

<span data-ttu-id="af18c-159">Wenn diese Richtlinie aktiviert ist, können Benutzer nicht das Standardverhalten ablehnen, bei dem jede Website in einem eigenen Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="af18c-159">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="af18c-160">Unterstützte Authentifizierungsschemas</span><span class="sxs-lookup"><span data-stu-id="af18c-160">Supported authentication schemes</span></span>

<span data-ttu-id="af18c-161">**Standardwert:** NTLM, aushandeln</span><span class="sxs-lookup"><span data-stu-id="af18c-161">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="af18c-162">Microsoft Managed Desktop unterstützt keine Standard-oder Digest-Authentifizierungsschemas.</span><span class="sxs-lookup"><span data-stu-id="af18c-162">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="af18c-163">Automatisches Importieren der Daten und Einstellungen eines anderen Browsers bei der ersten Ausführung</span><span class="sxs-lookup"><span data-stu-id="af18c-163">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="af18c-164">**Standardwert:** Automatisches Importieren aller unterstützten Datentypen und Einstellungen aus dem Standardbrowser</span><span class="sxs-lookup"><span data-stu-id="af18c-164">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="af18c-165">Wenn diese Richtlinie angewendet wird, überspringt die erste Ausführungsumgebung den Import Abschnitt, wodurch die Benutzerinteraktion minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="af18c-165">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="af18c-166">Die Browserdaten aus älteren Versionen von Microsoft Edge werden unabhängig von dieser Einstellung immer automatisch bei der ersten Ausführung migriert.</span><span class="sxs-lookup"><span data-stu-id="af18c-166">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="af18c-167">Einstellungen, die Sie verwalten</span><span class="sxs-lookup"><span data-stu-id="af18c-167">Settings you manage</span></span>

<span data-ttu-id="af18c-168">Sie können alle Microsft-edgeeinstellungen bereitstellen, die zuvor nicht mithilfe des Profils für administrative Vorlagen in Microsoft InTune beschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="af18c-168">You can deploy any Microsft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="af18c-169">Ausführliche Informationen finden Sie unter [configure Microsoft Edge Policy Settings with Microsoft InTune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="af18c-169">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="af18c-170">Wenn Sie eine Richtlinie auswerten möchten, die derzeit nicht in den Microsoft Edge Administrative Templates in InTune enthalten ist, können Sie benutzerdefinierte Einstellungen für Windows 10-Geräte in InTune verwenden.</span><span class="sxs-lookup"><span data-stu-id="af18c-170">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="af18c-171">Aktivieren bestimmter Chrome-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="af18c-171">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="af18c-172">Die administrative Vorlage bietet eine Einstellung zum Bereitstellen bestimmter Chrome-Erweiterungen mit Microsoft InTune.</span><span class="sxs-lookup"><span data-stu-id="af18c-172">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="af18c-173">Sie finden Sie unter **Computer Konfiguration > Microsoft Edge > Extensions > für die Installation bestimmter Erweiterungen zugelassen sind**.</span><span class="sxs-lookup"><span data-stu-id="af18c-173">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="af18c-174">Automatische Installation von Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="af18c-174">Install extensions silently</span></span>

<span data-ttu-id="af18c-175">Sie können auch die administrative Vorlage verwenden, um Microsoft Edge so festzulegen, dass Erweiterungen installiert werden, ohne dass der Benutzer benachrichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="af18c-175">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="af18c-176">Sie finden Sie unter **Computer Konfiguration > Microsoft Edge > Extensions > steuern, welche Erweiterungen automatisch installiert werden**.</span><span class="sxs-lookup"><span data-stu-id="af18c-176">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="af18c-177">Andere allgemeine Unternehmensrichtlinien</span><span class="sxs-lookup"><span data-stu-id="af18c-177">Other common enterprise policies</span></span>

<span data-ttu-id="af18c-178">Microsoft Edge bietet eine Vielzahl zusätzlicher Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="af18c-178">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="af18c-179">Dies sind einige der häufigsten:</span><span class="sxs-lookup"><span data-stu-id="af18c-179">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="af18c-180">Konfigurieren von Websites in der Liste "Enterprise-Website" und im IE-Modus</span><span class="sxs-lookup"><span data-stu-id="af18c-180">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="af18c-181">Konfigurieren der Einstellungen für Start, Startseite und neue Registerkartenseiten</span><span class="sxs-lookup"><span data-stu-id="af18c-181">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="af18c-182">Konfigurieren der Surf Spieleinstellung</span><span class="sxs-lookup"><span data-stu-id="af18c-182">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="af18c-183">Konfigurieren von Proxyservereinstellungen</span><span class="sxs-lookup"><span data-stu-id="af18c-183">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

