---
title: Das neue Microsoft Edge
description: Erläutert, wie der neue Edgebrowser bereitgestellt und aktualisiert wird.
keywords: Browser, Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822250"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="579b6-104">Neue Microsoft Edge-App</span><span class="sxs-lookup"><span data-stu-id="579b6-104">New Microsoft Edge app</span></span>

<span data-ttu-id="579b6-105">Der neue [Microsoft Edge Browser](https://www.microsoft.com/edge) bietet erstklassige Leistung mit mehr Datenschutz, mehr Produktivität und mehr Nutzen beim Browsen.</span><span class="sxs-lookup"><span data-stu-id="579b6-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="579b6-106">Microsoft Managed Desktop bietet eine öffentliche Vorschau der Bereitstellung des neuen Edgebrowsers in Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="579b6-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="579b6-107">Erstbereitstellung</span><span class="sxs-lookup"><span data-stu-id="579b6-107">Initial deployment</span></span>

<span data-ttu-id="579b6-108">Um Ihre Microsoft Managed Desktop Geräte zum neuen Microsoft Edge Browser zu migrieren, melden Sie über das Microsoft Managed Desktop Portal ein IT-Supportticket an.</span><span class="sxs-lookup"><span data-stu-id="579b6-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="579b6-109">Wir stellen den Edge Stable-Kanal für die Testgruppe bereit, wenn Sie das Ticket einreichen, und stellen ihn dann alle 24 Stunden in jeder nachfolgenden Bereitstellungsgruppe bereit.</span><span class="sxs-lookup"><span data-stu-id="579b6-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="579b6-110">Wenn Sie die Bereitstellung anhalten möchten, geben Sie ein weiteres Ticket ein, in dem Operations zur Aufbewahrung aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="579b6-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="579b6-111">Der [Betakanal](/deployedge/microsoft-edge-channels#beta-channel) steht auch auf Anfrage zur repräsentativen Validierung innerhalb Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="579b6-111">The [Beta Channel](/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="579b6-112">Microsoft Managed Desktop stellt die Anwendung nach Bedarf in den Test- und Erstgruppen bereit, sodass alle diese Benutzer zusätzlich zum Stable Channel über den Betakanal verfügen.</span><span class="sxs-lookup"><span data-stu-id="579b6-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="579b6-113">Für alle anderen Benutzer, die Zugriff auf den Betakanal benötigen, fügen Sie sie der Gruppe **"Modern Workplace - Edge Beta-Benutzer"** hinzu und lassen Sie sie über die Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="579b6-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="579b6-114">Updates für Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="579b6-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="579b6-115">Microsoft Managed Desktop stellt den [Stable-Kanal](/deployedge/microsoft-edge-channels#stable-channel) von Microsoft Edge bereit, der etwa alle sechs Wochen automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="579b6-115">Microsoft Managed Desktop deploys the [Stable channel](/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="579b6-116">Updates für den Stable-Kanal werden [schrittweise](/deployedge/microsoft-edge-update-progressive-rollout) von der Microsoft Edge Produktgruppe eingeführt, um die beste Benutzererfahrung für Kunden sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="579b6-116">Updates on the Stable channel are rolled out [progressively](/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="579b6-117">Der [Betakanal](/deployedge/microsoft-edge-channels#beta-channel) wird für Geräte in der Test- und der ersten Gruppe zur repräsentativen Überprüfung innerhalb der Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="579b6-117">The [Beta Channel](/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="579b6-118">Dieser Kanal wird vollständig unterstützt und etwa alle sechs Wochen automatisch mit neuen Features aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="579b6-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="579b6-119">Um sicherzustellen, dass Microsoft Edge Updates ordnungsgemäß aktualisiert, ändern Sie nicht die Microsoft Edge [Updaterichtlinien.](/deployedge/microsoft-edge-update-policies)</span><span class="sxs-lookup"><span data-stu-id="579b6-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="579b6-120">von Microsoft Managed Desktop verwaltete Einstellungen</span><span class="sxs-lookup"><span data-stu-id="579b6-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="579b6-121">Microsoft Managed Desktop hat einen Standardsatz von Richtlinien für Microsoft Edge zum Sichern des Browsers erstellt.</span><span class="sxs-lookup"><span data-stu-id="579b6-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="579b6-122">Die Standardbrowsereinstellungen sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="579b6-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="579b6-123">Microsoft Edge Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="579b6-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="579b6-124">Die Sicherheitsgrundwerte für Microsoft Edge auf Microsoft Managed Desktop Geräten legen zwei Richtlinien fest, um alle Chrome-Erweiterungen und sicheren Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="579b6-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="579b6-125">Informationen zum Aktivieren und Bereitstellen von Erweiterungen in Ihrer Umgebung finden Sie unter Einstellungen Sie verwalten.</span><span class="sxs-lookup"><span data-stu-id="579b6-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="579b6-126">Erweiterungsinstallationsblockliste</span><span class="sxs-lookup"><span data-stu-id="579b6-126">Extension installation blocklist</span></span>
<span data-ttu-id="579b6-127">**Standardwert:** Alle</span><span class="sxs-lookup"><span data-stu-id="579b6-127">**Default value:** All</span></span>

<span data-ttu-id="579b6-128">Microsoft Managed Desktop legt diese Richtlinie fest, um zu verhindern, dass Chrome-Erweiterungen auf verwalteten Endpunkten installiert werden.</span><span class="sxs-lookup"><span data-stu-id="579b6-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="579b6-129">Es gibt bekannte Risiken im Zusammenhang mit dem Chromium Erweiterungsmodell, einschließlich Schutz vor Datenverlust, Datenschutz und andere Risiken, die Geräte beeinträchtigen können.</span><span class="sxs-lookup"><span data-stu-id="579b6-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="579b6-130">Zulassen systemeigener Messaginghosts auf Benutzerebene (ohne Administratorberechtigungen installiert)</span><span class="sxs-lookup"><span data-stu-id="579b6-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="579b6-131">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="579b6-131">**Default value:** Disabled</span></span>

<span data-ttu-id="579b6-132">Durch Deaktivieren dieser Richtlinie verwenden Microsoft Edge nur systemeigene Messaginghosts, die auf Systemebene installiert sind.</span><span class="sxs-lookup"><span data-stu-id="579b6-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="579b6-133">Systemeigene Messaginghosts sind Teil von Chrome-Erweiterungen, die es dem Browser ermöglichen, mit anderen Teilen des Endpunkts des Benutzers zu interagieren, wodurch eine Vielzahl von Sicherheitsbedenken entsteht.</span><span class="sxs-lookup"><span data-stu-id="579b6-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="579b6-134">Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="579b6-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="579b6-135">Minimale TLS-Version</span><span class="sxs-lookup"><span data-stu-id="579b6-135">Minimum TLS version</span></span>

<span data-ttu-id="579b6-136">**Standardwert:** Mindestens tls 1.2 unterstützt</span><span class="sxs-lookup"><span data-stu-id="579b6-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="579b6-137">Wenn Sie das weniger sichere TLS 1.1 verwenden möchten, können Sie eine Entsprechendeanforderung senden.</span><span class="sxs-lookup"><span data-stu-id="579b6-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="579b6-138">Ermöglicht Benutzern das Fortfahren von der SSL-Warnseite</span><span class="sxs-lookup"><span data-stu-id="579b6-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="579b6-139">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="579b6-139">**Default value:** Disabled</span></span>

<span data-ttu-id="579b6-140">Es wird davon abgeraten, diese Einstellung zu aktivieren, da benutzer websites mit TSL-Fehlern besuchen können.</span><span class="sxs-lookup"><span data-stu-id="579b6-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="579b6-141">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="579b6-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="579b6-142">Konfigurieren von Windows Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="579b6-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="579b6-143">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="579b6-143">**Default value:** Enabled</span></span>

<span data-ttu-id="579b6-144">Standardmäßig aktiviert, um Benutzer zu schützen.</span><span class="sxs-lookup"><span data-stu-id="579b6-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="579b6-145">Windows Defender SmartScreen-Aufforderungen für Websites</span><span class="sxs-lookup"><span data-stu-id="579b6-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="579b6-146">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="579b6-146">**Default value:** Enabled</span></span>

<span data-ttu-id="579b6-147">Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da dies es Benutzern ermöglichen würde, Warnungen zu ignorieren und weiterhin potenziell schädliche Websites zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="579b6-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="579b6-148">Verhindern der Umgehung von Windows Defender SmartScreen-Warnungen zu Downloads</span><span class="sxs-lookup"><span data-stu-id="579b6-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="579b6-149">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="579b6-149">**Default value:** Enabled</span></span>

<span data-ttu-id="579b6-150">Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da dadurch Benutzer Warnungen ignorieren und nicht überprüfte Downloads abschließen können.</span><span class="sxs-lookup"><span data-stu-id="579b6-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="579b6-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="579b6-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="579b6-152">Standardeinstellung für Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="579b6-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="579b6-153">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="579b6-153">**Default value:** Disabled</span></span>

<span data-ttu-id="579b6-154">Aufgrund der damit verbundenen Sicherheitsrisiken wird die Verwendung von Flash nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="579b6-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="579b6-155">Wenn Sie weiterhin Prozesse haben, die von Flash abhängig sind, legen Sie die **[PluginsAllowedForUrls-Richtlinie](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** fest, um Flash für Websites zu aktivieren, die es benötigen.</span><span class="sxs-lookup"><span data-stu-id="579b6-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="579b6-156">Wenn Sie keine Liste zulässiger Websites zur Verwendung von Flash verwalten können, senden Sie eine Änderungsanforderung, um den Wert in **"Klick-und-Los" zu** ändern, sodass Benutzer auswählen können, wann Flash ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="579b6-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="579b6-157">Kennwort-Manager</span><span class="sxs-lookup"><span data-stu-id="579b6-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="579b6-158">Aktivieren des Speicherns von Kennwörtern im Kennwort-Manager</span><span class="sxs-lookup"><span data-stu-id="579b6-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="579b6-159">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="579b6-159">**Default value:** Disabled</span></span>

<span data-ttu-id="579b6-160">Der Kennwort-Manager ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="579b6-160">The password manager is disabled by default.</span></span> <span data-ttu-id="579b6-161">Wenn Sie diese Funktion aktiviert haben, senden Sie eine Supportanfrage, und unsere Servicetechniker können die Einstellung in Ihrer Umgebung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="579b6-161">If you's like this feature enabled, file a support request and our service engineers can enable the setting in your environment.</span></span> 

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="579b6-162">Internet Explorer-Modus in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="579b6-162">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="579b6-163">Der IE-Modus auf Microsoft Edge erleichtert die Verwendung aller Websites, die Ihre Organisation benötigt, in einem einzigen Browser.</span><span class="sxs-lookup"><span data-stu-id="579b6-163">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="579b6-164">Es verwendet das integrierte Chromium-Modul für Websites, die mit dem Chromium Renderingmodul kompatibel sind, und das Trident MSHTML-Modul aus Internet Explorer 11 (IE11) für Websites, die nicht von IE-Funktionen abhängig sind oder davon abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="579b6-164">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> [<span data-ttu-id="579b6-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="579b6-165">Learn more</span></span>](/DeployEdge/edge-ie-mode) 

<span data-ttu-id="579b6-166">Microsoft Managed Desktop aktiviert standardmäßig den Internet Explorer-Modus für Ihre Geräte</span><span class="sxs-lookup"><span data-stu-id="579b6-166">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="579b6-167">Integration des Internet Explorer-Modus</span><span class="sxs-lookup"><span data-stu-id="579b6-167">Internet Explorer mode integration</span></span>
<span data-ttu-id="579b6-168">**Standardwert:** Internet Explorer-Modus</span><span class="sxs-lookup"><span data-stu-id="579b6-168">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="579b6-169">Standardmäßig ist für Geräte die Verwendung des Internet Explorer-Modus festgelegt, Sie können jedoch festlegen, dass Websites stattdessen in einem eigenständigen Internet Explorer 11-Fenster geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="579b6-169">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="579b6-170">Um dieses Verhalten zu ändern, stellen Sie eine Supportanfrage.</span><span class="sxs-lookup"><span data-stu-id="579b6-170">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="579b6-171">Hinzufügen von Websites zur Websiteliste für den Enterprise modus</span><span class="sxs-lookup"><span data-stu-id="579b6-171">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="579b6-172">Damit Websites im Internet Explorer-Modus geöffnet werden können, müssen Sie sie in die [websiteliste Enterprise](/DeployEdge/edge-ie-mode-sitelist)einschließen.</span><span class="sxs-lookup"><span data-stu-id="579b6-172">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="579b6-173">Die Verwaltung und Bereitstellung der Enterprise Websiteliste liegt in Ihrer Verantwortung.</span><span class="sxs-lookup"><span data-stu-id="579b6-173">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="579b6-174">Ausführliche Informationen finden Sie unter [Konfigurieren der Richtlinie "Konfigurieren Enterprise Mode Site List"](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="579b6-174">For details, see [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="579b6-175">Weitere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="579b6-175">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="579b6-176">Aktivieren der Websiteisolation für jeden Standort</span><span class="sxs-lookup"><span data-stu-id="579b6-176">Enable site isolation for every site</span></span>

<span data-ttu-id="579b6-177">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="579b6-177">**Default value:** Enabled</span></span>

<span data-ttu-id="579b6-178">Wenn diese Richtlinie aktiviert ist, können Benutzer das Standardverhalten, in dem jede Website in einem eigenen Prozess ausgeführt wird, nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="579b6-178">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="579b6-179">Unterstützte Authentifizierungsschemas</span><span class="sxs-lookup"><span data-stu-id="579b6-179">Supported authentication schemes</span></span>

<span data-ttu-id="579b6-180">**Standardwert:** NTLM, Aushandeln</span><span class="sxs-lookup"><span data-stu-id="579b6-180">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="579b6-181">Microsoft Managed Desktop unterstützt keine Standard- oder Digestauthentifizierungsschemas.</span><span class="sxs-lookup"><span data-stu-id="579b6-181">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="579b6-182">Automatisches Importieren der Daten und Einstellungen eines anderen Browsers bei der ersten Ausführung</span><span class="sxs-lookup"><span data-stu-id="579b6-182">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="579b6-183">**Standardwert:** Automatisches Importieren aller unterstützten Datentypen und Einstellungen aus dem Standardbrowser</span><span class="sxs-lookup"><span data-stu-id="579b6-183">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="579b6-184">Wenn diese Richtlinie angewendet wird, überspringt die Erste Ausführungserfahrung den Importabschnitt, wodurch die Benutzerinteraktion minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="579b6-184">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="579b6-185">Die Browserdaten aus älteren Versionen von Microsoft Edge werden unabhängig von dieser Einstellung bei der ersten Ausführung immer im Hintergrund migriert.</span><span class="sxs-lookup"><span data-stu-id="579b6-185">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="579b6-186">Einstellungen Sie verwalten</span><span class="sxs-lookup"><span data-stu-id="579b6-186">Settings you manage</span></span>

<span data-ttu-id="579b6-187">Sie können alle Microsoft Edge Einstellungen bereitstellen, die zuvor nicht beschrieben wurden, indem Sie das Profil "Administrative Vorlagen" in Microsoft Intune verwenden.</span><span class="sxs-lookup"><span data-stu-id="579b6-187">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="579b6-188">Ausführliche Informationen finden Sie unter [Konfigurieren Microsoft Edge Richtlinieneinstellungen mit Microsoft Intune.](/deployedge/configure-edge-with-intune)</span><span class="sxs-lookup"><span data-stu-id="579b6-188">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="579b6-189">Wenn Sie eine Richtlinie auswerten möchten, die derzeit nicht in der Microsoft Edge Administrative Vorlagen in Intune enthalten ist, können Sie benutzerdefinierte Einstellungen für Windows 10 Geräte in Intune verwenden.</span><span class="sxs-lookup"><span data-stu-id="579b6-189">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="579b6-190">Aktivieren bestimmter Chrome-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="579b6-190">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="579b6-191">Die administrative Vorlage bietet eine Einstellung zum Bereitstellen bestimmter Chrome-Erweiterungen mit Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="579b6-191">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="579b6-192">Sie finden sie unter **Computerkonfiguration > Microsoft Edge > Erweiterungen > Zulassen, dass bestimmte Erweiterungen installiert werden.**</span><span class="sxs-lookup"><span data-stu-id="579b6-192">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="579b6-193">Automatisches Installieren von Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="579b6-193">Install extensions silently</span></span>

<span data-ttu-id="579b6-194">Sie können die administrative Vorlage auch verwenden, um Microsoft Edge zum Installieren von Erweiterungen festzulegen, ohne den Benutzer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="579b6-194">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="579b6-195">Sie finden es unter **Computerkonfiguration > Microsoft Edge > Erweiterungen > Steuern, welche Erweiterungen im Hintergrund installiert werden.**</span><span class="sxs-lookup"><span data-stu-id="579b6-195">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="579b6-196">Microsoft Edge Aktualisieren von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="579b6-196">Microsoft Edge update policies</span></span>
<span data-ttu-id="579b6-197">Um sicherzustellen, dass Microsoft Edge Updates ordnungsgemäß aktualisiert, ändern Sie nicht die Microsoft Edge [Updaterichtlinien.](/deployedge/microsoft-edge-update-policies)</span><span class="sxs-lookup"><span data-stu-id="579b6-197">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="579b6-198">Andere allgemeine Unternehmensrichtlinien</span><span class="sxs-lookup"><span data-stu-id="579b6-198">Other common enterprise policies</span></span>

<span data-ttu-id="579b6-199">Microsoft Edge bietet viele andere Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="579b6-199">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="579b6-200">Dies sind einige der gängigsten:</span><span class="sxs-lookup"><span data-stu-id="579b6-200">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="579b6-201">Konfigurieren von Websites im Enterprise-Websitelisten- und IE-Modus</span><span class="sxs-lookup"><span data-stu-id="579b6-201">Configure Sites on the Enterprise Site List and IE Mode</span></span>](/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="579b6-202">Konfigurieren der Einstellungen für Start-Up, Startseite und neue Registerkartenseite</span><span class="sxs-lookup"><span data-stu-id="579b6-202">Configure start-up, home page, and new tab page settings</span></span>](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="579b6-203">Konfigurieren der Surf-Spieleinstellung</span><span class="sxs-lookup"><span data-stu-id="579b6-203">Configure Surf game setting</span></span>](/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="579b6-204">Konfigurieren von Proxyservereinstellungen</span><span class="sxs-lookup"><span data-stu-id="579b6-204">Configure proxy server settings</span></span>](/deployedge/microsoft-edge-policies#proxy-server)
