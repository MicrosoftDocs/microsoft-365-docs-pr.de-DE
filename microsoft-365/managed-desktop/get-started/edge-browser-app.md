---
title: Das neue Microsoft Edge
description: Erläutert, wie der neue Edgebrowser bereitgestellt und aktualisiert wird
keywords: Browser, Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841339"
---
# <a name="new-microsoft-edge-app"></a>Neue Microsoft Edge-App

Der neue [Microsoft Edge Browser](https://www.microsoft.com/edge) bietet erstklassige Leistung mit mehr Datenschutz, mehr Produktivität und mehrwertigem Browsen. Microsoft Managed Desktop bietet eine öffentliche Vorschau der Bereitstellung des neuen Edgebrowsers in Ihrer Umgebung.

## <a name="initial-deployment"></a>Erstbereitstellung

Um Ihre Microsoft Managed Desktop-Geräte zum neuen Microsoft Edge-Browser zu migrieren, müssen Sie ein IT-Supportticket über das Microsoft Managed Desktop Portal eingeben. Wir stellen den Edge -Stable-Kanal bei der Datei des Tickets für die Testgruppe und dann alle 24 Stunden in jeder nachfolgenden Bereitstellungsgruppe zur Bereitstellung zur Testgruppe. Um die Bereitstellung anzuhalten, führen Sie ein weiteres Ticket aus, und bitten Sie operations, es zu halten.

Der [Betakanal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) ist auch auf Anforderung einer repräsentativen Überprüfung in Ihrer Organisation verfügbar. Microsoft Managed Desktop stellt die Anwendung nach Bedarf für die Test- und erste Gruppen zur Verfügung, sodass alle diese Benutzer zusätzlich zum stabilen Kanal über den Betakanal verfügen. Für alle anderen Benutzer, die Zugriff auf den Betakanal benötigen, fügen Sie sie der Gruppe **"Modern Workplace - Edge Beta Users"** hinzu und lassen Sie sie über das Unternehmensportal installieren.

## <a name="updates-to-microsoft-edge"></a>Updates für Microsoft Edge

Microsoft Managed Desktop stellt den [Stabilen](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) Kanal von Microsoft Edge zur Bereitstellung, der etwa alle sechs Wochen automatisch aktualisiert wird. Updates für den Kanal [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) Stable werden schrittweise von der Microsoft Edge-Produktgruppe veröffentlicht, um die bestmögliche Benutzererfahrung für Kunden zu gewährleisten. 

Der [Betakanal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) wird für Geräte in der Test- und der Ersten Gruppe zur repräsentativen Überprüfung innerhalb der Organisation bereitgestellt. Dieser Kanal wird vollständig unterstützt und etwa alle sechs Wochen automatisch mit neuen Features aktualisiert.

Um sicherzustellen, dass Microsoft Edge ordnungsgemäß aktualisiert wird, ändern Sie die Updaterichtlinien von Microsoft Edge [nicht.](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verwaltete Einstellungen

Microsoft Managed Desktop hat einen Standardsatz von Richtlinien für Microsoft Edge zum Sichern des Browsers erstellt. Die Standardbrowsereinstellungen sind wie folgt:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge-Erweiterungen

Die Sicherheitsbasislinie für Microsoft Edge auf Microsoft Managed Desktop-Geräten legt zwei Richtlinien fest, um alle Chrome-Erweiterungen und sicheren Benutzer zu deaktivieren. Informationen zum Aktivieren und Bereitstellen von Erweiterungen in Ihrer Umgebung finden Sie unter "Verwaltete Einstellungen". 

#### <a name="extension-installation-blocklist"></a>Erweiterungsinstallationsblockierungsliste
**Standardwert:** Alle

Microsoft Managed Desktop legt diese Richtlinie fest, um zu verhindern, dass Chrome-Erweiterungen auf verwalteten Endpunkten installiert werden. Es gibt bekannte Risiken im Zusammenhang mit dem Chromium-Erweiterungsmodell, einschließlich Schutz vor Datenverlust, Datenschutz und andere Risiken, durch die Geräte gefährdet werden können. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Zulassen systemeigener Messaginghosts auf Benutzerebene (ohne Administratorberechtigungen installiert)

**Standardwert:** Deaktiviert

Durch Deaktivieren dieser Richtlinie verwendet Microsoft Edge nur systemeigene Messaginghosts, die auf Systemebene installiert sind. Systemeigene Messaginghosts sind Teil von Chrome-Erweiterungen, die es dem Browser ermöglichen, mit anderen Teilen des Endpunkts des Benutzers zu interagieren, wodurch eine Vielzahl von Sicherheitsbedenken verbunden ist.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Mindestversion von TLS

**Standardwert:** Mindestens TLS 1.2 unterstützt

Wenn Sie das weniger sichere TLS 1.1 verwenden möchten, können Sie dazu eine Anforderung senden.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Ermöglicht Benutzern das Fortsetzen der SSL-Warnungsseite.

**Standardwert:** Deaktiviert

Es wird nicht empfohlen, diese Einstellung zu aktivieren, da Sie Benutzern das Besuchen von Websites mit TSL-Fehlern ermöglicht.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Konfigurieren Windows Defender SmartScreen

**Standardwert:** Aktiviert

Standardmäßig aktiviert, um Benutzer zu schützen.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender von SmartScreen-Eingabeaufforderungen für Websites

**Standardwert:** Aktiviert

Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da Benutzer Warnungen ignorieren und weiterhin potenziell schädliche Websites verwenden können.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Verhindern der Umgehung von Windows Defender von SmartScreen-Warnungen zu Downloads

**Standardwert:** Aktiviert

Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da Benutzer Warnungen ignorieren und nicht überprüfte Downloads ausführen können.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standardeinstellung für Adobe Flash

**Standardwert:** Deaktiviert

Die Verwendung von Flash wird aufgrund der damit verbundenen Sicherheitsrisiken nicht empfohlen. Wenn Sie noch Prozesse haben, die von Flash abhängen, legen Sie die **[Richtlinie PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** fest, um Flash für Websites zu aktivieren, die es benötigen. Wenn Sie keine Liste zulässiger Websites für die Verwendung von Flash verwalten können, senden Sie eine Änderungsanforderung, um den Wert in "Klick-und-Wiedergabe" zu ändern, wodurch Benutzer auswählen können, wann Flash ausgeführt werden soll.

### <a name="password-manager"></a>Kennwort-Manager

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Aktivieren des Speicherns von Kennwörtern im Kennwort-Manager

**Standardwert:** Deaktiviert

Es wird nicht empfohlen, Benutzern das Speichern von Kennwörtern auf ihrem Gerät zu erlauben.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer-Modus in Microsoft Edge
Der IE-Modus auf Microsoft Edge erleichtert die Verwendung aller Websites, die Ihre Organisation benötigt, in einem einzigen Browser. Es verwendet das integrierte Chromium-Modul für Websites, die mit dem Chromium-Renderingmodul kompatibel sind, und das Trident-MSHTML-Modul aus Internet Explorer 11 (IE11) für Websites, die nicht von der Funktionalität von IE abhängig sind oder von dieser abhängig sind. [Weitere Informationen] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop aktiviert standardmäßig den Internet Explorer-Modus für Ihre Geräte. 

#### <a name="internet-explorer-mode-integration"></a>Integration des Internet Explorer-Modus
**Standardwert:** Internet Explorer-Modus

Standardmäßig ist für Geräte die Verwendung des Internet Explorer-Modus festgelegt, Sie können jedoch festlegen, dass websites stattdessen in einem eigenständigen Internet Explorer 11-Fenster geöffnet werden. Um dieses Verhalten zu ändern, senden Sie eine Supportanfrage.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Hinzufügen von Websites zur Websiteliste für den Unternehmensmodus
Damit Websites im Internet Explorer-Modus geöffnet werden können, müssen Sie sie in die Liste der [Unternehmenswebsites aufgenommen haben.](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist) Die Verwaltung und Bereitstellung der Enterprise Site-Liste liegt in Ihrer Verantwortung. Weitere Informationen finden Sie unter ["Konfigurieren mithilfe der Richtlinie "Enterprise Mode Site List konfigurieren"](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Weitere Einstellungen

#### <a name="enable-site-isolation-for-every-site"></a>Aktivieren der Websiteisolation für jede Website

**Standardwert:** Aktiviert

Wenn diese Richtlinie aktiviert ist, können Benutzer das Standardverhalten, bei dem jede Website in einem eigenen Prozess ausgeführt wird, nicht abmelden.

#### <a name="supported-authentication-schemes"></a>Unterstützte Authentifizierungsschemas

**Standardwert:** NTLM, Aushandeln

Microsoft Managed Desktop unterstützt keine Standard- oder Digestauthentifizierungsschemas.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Automatisches Importieren der Daten und Einstellungen eines anderen Browsers bei der ersten Ausführung

**Standardwert:** Automatisches Importieren aller unterstützten Datentypen und Einstellungen aus dem Standardbrowser 

Wenn diese Richtlinie angewendet wird, überspringt die Erste Ausführung den Importabschnitt, wodurch die Benutzerinteraktion minimiert wird. Die Browserdaten aus älteren Versionen von Microsoft Edge werden unabhängig von dieser Einstellung bei der ersten Ausführung immer automatisch migriert. 


## <a name="settings-you-manage"></a>Von Ihnen verwaltete Einstellungen

Sie können alle Microsoft Edge-Einstellungen bereitstellen, die zuvor nicht beschrieben wurden, indem Sie das Profil "Administrative Vorlagen" in Microsoft Intune verwenden. Weitere Informationen finden Sie unter ["Konfigurieren von Microsoft Edge-Richtlinieneinstellungen mit Microsoft Intune".](https://docs.microsoft.com/deployedge/configure-edge-with-intune) Wenn Sie eine Richtlinie auswerten möchten, die derzeit nicht in den administrativen Vorlagen von Microsoft Edge in Intune enthalten ist, können Sie benutzerdefinierte Einstellungen für Windows 10-Geräte in Intune verwenden.

### <a name="enabling-specific-chrome-extensions"></a>Aktivieren bestimmter Chrome-Erweiterungen

Die administrative Vorlage bietet eine Einstellung zum Bereitstellen bestimmter Chrome-Erweiterungen mit Microsoft Intune. Sie finden ihn unter **"Computerkonfiguration" > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.

### <a name="install-extensions-silently"></a>Automatisches Installieren von Erweiterungen

Sie können die administrative Vorlage auch verwenden, um Microsoft Edge so zu definieren, dass Erweiterungen installiert werden, ohne den Benutzer zu warnen. Sie finden sie unter **"Computerkonfiguration" > Microsoft Edge > Extensions > Steuern,** welche Erweiterungen im Hintergrund installiert werden.

### <a name="microsoft-edge-update-policies"></a>Updaterichtlinien für Microsoft Edge
Um sicherzustellen, dass Microsoft Edge ordnungsgemäß aktualisiert wird, ändern Sie die Updaterichtlinien von Microsoft Edge [nicht.](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)

### <a name="other-common-enterprise-policies"></a>Andere allgemeine Unternehmensrichtlinien

Microsoft Edge bietet viele weitere Richtlinien. Dies sind einige der häufigeren:
 
- [Konfigurieren von Websites in der Enterprise Site List und im IE-Modus](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Konfigurieren von Einstellungen für Start, Homepage und neue Registerkartenseite](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Konfigurieren der Einstellung für das Surfspiel](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Konfigurieren von Proxyservereinstellungen](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

