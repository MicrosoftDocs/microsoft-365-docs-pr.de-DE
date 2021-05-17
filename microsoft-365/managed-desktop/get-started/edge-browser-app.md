---
title: Das neue Microsoft Edge
description: Erläutert, wie der neue Edgebrowser bereitgestellt und aktualisiert wird
keywords: browser, Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 033826a7f82278f6e36b422284a1076cba57d584
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921978"
---
# <a name="new-microsoft-edge-app"></a>Neue Microsoft Edge-App

Der neue [Microsoft Edge bietet](https://www.microsoft.com/edge) erstklassige Leistung mit mehr Datenschutz, mehr Produktivität und mehr Wert beim Browsen. Microsoft Managed Desktop bietet eine öffentliche Vorschau der Bereitstellung des neuen Edgebrowsers in Ihrer Umgebung.

## <a name="initial-deployment"></a>Erstbereitstellung

Um Ihre Microsoft Managed Desktop zum neuen Microsoft Edge zu migrieren, müssen Sie ein IT-Supportticket über das Microsoft Managed Desktop erstellen. Wir stellen den Edge stable-Kanal bei der Testgruppe zur Datei des Tickets und anschließend alle 24 Stunden in jeder nachfolgenden Bereitstellungsgruppe. Um die Bereitstellung anzuhalten, führen Sie ein weiteres Ticket aus, in dem Operations zum Anhalten aufgefordert wird.

Der [Betakanal](/deployedge/microsoft-edge-channels#beta-channel) ist auch auf Anfrage für eine repräsentative Überprüfung in Ihrer Organisation verfügbar. Microsoft Managed Desktop stellt die Anwendung nach Bedarf für die Test- und erste Gruppen zur Verfügung, sodass alle diese Benutzer zusätzlich zum Stable Channel über den Betakanal verfügen. Für alle anderen Benutzer, die Zugriff auf den Betakanal benötigen, fügen Sie sie der Gruppe **Modern Workplace - Edge Beta Users** hinzu, und lassen Sie sie von der Unternehmensportal

## <a name="updates-to-microsoft-edge"></a>Updates für Microsoft Edge

Microsoft Managed Desktop stellt den [Stable-Kanal](/deployedge/microsoft-edge-channels#stable-channel) von Microsoft Edge, der etwa alle sechs Wochen automatisch aktualisiert wird. Updates auf dem Stable-Kanal werden schrittweise von der Microsoft Edge produktgruppe veröffentlicht, um eine optimale Benutzererfahrung für Kunden zu gewährleisten. [](/deployedge/microsoft-edge-update-progressive-rollout) 

Der [Betakanal](/deployedge/microsoft-edge-channels#beta-channel) wird auf Geräten in den Gruppen Test und First zur repräsentativen Überprüfung innerhalb der Organisation bereitgestellt. Dieser Kanal wird vollständig unterstützt und mit neuen Features etwa alle sechs Wochen automatisch aktualisiert.

Um sicherzustellen, dass Microsoft Edge aktualisiert werden, ändern Sie nicht die Microsoft Edge [Updaterichtlinien](/deployedge/microsoft-edge-update-policies).



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Einstellungen verwaltet von Microsoft Managed Desktop

Microsoft Managed Desktop hat einen Standardsatz von Richtlinien für Microsoft Edge zum Sichern des Browsers erstellt. Die Standardbrowsereinstellungen sind wie folgt:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge-Erweiterungen

Die Sicherheitsgrundlinie für Microsoft Edge auf Microsoft Managed Desktop legt zwei Richtlinien fest, um alle Chrome-Erweiterungen zu deaktivieren und Benutzer zu schützen. Informationen zum Aktivieren und Bereitstellen von Erweiterungen in Ihrer Umgebung finden Sie unter Einstellungen sie verwalten. 

#### <a name="extension-installation-blocklist"></a>Blockliste der Erweiterungsinstallation
**Standardwert:** All

Microsoft Managed Desktop legt diese Richtlinie fest, um zu verhindern, dass Chrome-Erweiterungen auf verwalteten Endpunkten installiert werden. Es gibt bekannte Risiken im Zusammenhang mit Chromium Erweiterungsmodell, einschließlich Schutz vor Datenverlust, Datenschutz und andere Risiken, die Geräte in Gefahr führen können. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Zulassen systemeigener Messaginghosts auf Benutzerebene (ohne Administratorberechtigungen installiert)

**Standardwert:** Deaktiviert

Wenn Sie diese Richtlinie deaktivieren, Microsoft Edge nur systemeigene Messaginghosts verwendet, die auf Systemebene installiert sind. Native Messaginghosts sind Teil von Chrome-Erweiterungen, die es dem Browser ermöglichen, mit anderen Teilen des Endpunkts des Benutzers zu interagieren, was eine Vielzahl von Sicherheitsbedenken schafft.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Minimale TLS-Version

**Standardwert:** Mindestens TLS 1.2 unterstützt

Wenn Sie das weniger sichere TLS 1.1 verwenden möchten, können Sie eine Anforderung dazu senden.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Ermöglicht Benutzern das Fortfahren von der SSL-Warnungsseite

**Standardwert:** Deaktiviert

Es wird nicht empfohlen, diese Einstellung zu aktivieren, da sie Benutzern das Besuchen von Websites mit TSL-Fehlern ermöglicht.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Konfigurieren Windows Defender SmartScreen

**Standardwert:** Aktiviert

Standardmäßig aktiviert, um Benutzer zu schützen.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen-Eingabeaufforderungen für Websites

**Standardwert:** Aktiviert

Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da benutzer Warnungen ignorieren und weiterhin potenziell schädliche Websites verwenden können.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Verhindern der Umgehung Windows Defender Von SmartScreen-Warnungen zu Downloads

**Standardwert:** Aktiviert

Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da benutzer Warnungen ignorieren und nicht überprüfte Downloads abschließen können.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standardeinstellung für Adobe Flash

**Standardwert:** Deaktiviert

Die Verwendung von Flash wird aufgrund der damit verbundenen Sicherheitsrisiken nicht empfohlen. Wenn Sie noch prozesse haben, die von Flash abhängen, legen Sie die **[Richtlinie PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** so fest, dass Flash für Websites aktiviert wird, die es benötigen. Wenn Sie keine liste der zulässigen Websites für die Verwendung von Flash verwalten können, senden Sie eine Änderungsanforderung, um den Wert in Klick auf **Wiedergabe** zu ändern, wodurch Benutzer auswählen können, wann Flash ausgeführt werden soll.

### <a name="password-manager"></a>Kennwort-Manager

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Aktivieren des Speicherns von Kennwörtern im Kennwort-Manager

**Standardwert:** Deaktiviert

Es wird nicht empfohlen, Benutzern das Speichern von Kennwörtern auf ihrem Gerät zu erlauben.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer-Modus in Microsoft Edge
Der IE-Microsoft Edge erleichtert die Verwendung aller Websites, die Ihre Organisation in einem einzigen Browser benötigt. Es verwendet das integrierte Chromium-Modul für Websites, die mit dem Chromium-Renderingmodul kompatibel sind, und es verwendet das Trident-MSHTML-Modul von Internet Explorer 11 (IE11) für Websites, die nicht von der IE-Funktionalität abhängig sind oder abhängigkeiten. [Weitere Informationen] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop aktiviert standardmäßig den Internet Explorer-Modus für Ihre Geräte 

#### <a name="internet-explorer-mode-integration"></a>Integration des Internet Explorer-Modus
**Standardwert:** Internet Explorer-Modus

Standardmäßig ist für Geräte die Verwendung des Internet Explorer-Modus festgelegt, Sie können jedoch festlegen, dass websites stattdessen in einem eigenständigen Internet Explorer 11-Fenster geöffnet werden. Um dieses Verhalten zu ändern, senden Sie eine Supportanfrage.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Hinzufügen von Websites zur liste Enterprise Moduswebsite
Damit Websites im Internet Explorer-Modus geöffnet werden können, müssen Sie sie in die Liste [Enterprise Website hinzufügen.](/DeployEdge/edge-ie-mode-sitelist) Die Verwaltung und Bereitstellung Enterprise Websiteliste liegt in Ihrer Verantwortung. Weitere Informationen finden Sie unter [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Weitere Einstellungen

#### <a name="enable-site-isolation-for-every-site"></a>Aktivieren der Websiteisolation für jede Website

**Standardwert:** Aktiviert

Wenn diese Richtlinie aktiviert ist, können Benutzer das Standardverhalten, bei dem jede Website in einem eigenen Prozess ausgeführt wird, nicht abmelden.

#### <a name="supported-authentication-schemes"></a>Unterstützte Authentifizierungsschemas

**Standardwert:** NTLM, Negotiate

Microsoft Managed Desktop unterstützt keine Standard- oder Digestauthentifizierungsschemas.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Automatisches Importieren der Daten und Einstellungen eines anderen Browsers bei der ersten Ausführung

**Standardwert:** Automatisches Importieren aller unterstützten Datentypen und Einstellungen aus dem Standardbrowser 

Wenn diese Richtlinie angewendet wird, überspringt die First Run Experience den Importabschnitt, wodurch die Benutzerinteraktion minimiert wird. Die Browserdaten aus älteren Versionen von Microsoft Edge werden unabhängig von dieser Einstellung bei der ersten Ausführung immer automatisch migriert. 


## <a name="settings-you-manage"></a>Einstellungen, die Sie verwalten

Sie können alle einstellungen Microsoft Edge, die zuvor nicht beschrieben wurden, mithilfe des Profils administrative Vorlagen in Microsoft Intune. Weitere Informationen finden Sie unter [Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune). Wenn Sie eine Richtlinie auswerten möchten, die derzeit nicht in den Microsoft Edge Administrative Vorlagen in Intune enthalten ist, können Sie benutzerdefinierte Einstellungen für Windows 10 in Intune verwenden.

### <a name="enabling-specific-chrome-extensions"></a>Aktivieren bestimmter Chrome-Erweiterungen

Die Administrative Vorlage bietet eine Einstellung zum Bereitstellen bestimmter Chrome-Erweiterungen mit Microsoft Intune. Informationen dazu finden Sie unter **Computerkonfiguration > Microsoft Edge > Erweiterungen > Zulassen** der Installation bestimmter Erweiterungen .

### <a name="install-extensions-silently"></a>Automatisches Installieren von Erweiterungen

Sie können auch mithilfe der Administrativen Vorlage festlegen, Microsoft Edge Erweiterungen zu installieren, ohne den Benutzer zu warnen. Sie finden sie unter **Computerkonfiguration > Microsoft Edge > Erweiterungen > Steuern,** welche Erweiterungen im Hintergrund installiert werden.

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge Updaterichtlinien
Um sicherzustellen, dass Microsoft Edge aktualisiert werden, ändern Sie nicht die Microsoft Edge [Updaterichtlinien](/deployedge/microsoft-edge-update-policies).

### <a name="other-common-enterprise-policies"></a>Andere allgemeine Unternehmensrichtlinien

Microsoft Edge bietet viele andere Richtlinien. Dies sind einige der gängigen:
 
- [Konfigurieren von Websites in Enterprise Websiteliste und im IE-Modus](/deployedge/edge-ie-mode-sitelist)
- [Konfigurieren von Einstellungen für Start-, Homepage- und neue Registerkartenseiten](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Konfigurieren der Einstellung für Surfspiele](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Konfigurieren von Proxyservereinstellungen](/deployedge/microsoft-edge-policies#proxy-server)