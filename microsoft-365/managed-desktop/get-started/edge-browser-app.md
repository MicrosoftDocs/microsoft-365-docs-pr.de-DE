---
title: Neuer Microsoft Edge
description: ''
keywords: Browser, Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d11fd8f29e3232472f9457ba1fc288a5084429e9
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936137"
---
# <a name="new-microsoft-edge-app"></a>Neue Microsoft Edge-App

Der neue [Microsoft Edge-Browser](https://www.microsoft.com/edge) bietet erstklassige Leistung mit mehr Datenschutz, mehr Produktivität und mehr Wert beim Durchsuchen. Microsoft Managed Desktop bietet eine öffentliche Vorschau der Bereitstellung des neuen Edge-Browsers in Ihrer Umgebung.

## <a name="initial-deployment"></a>Erstbereitstellung

Um Ihre verwalteten Desktop Geräte von Microsoft auf den neuen Microsoft Edge-Browser zu migrieren, müssen Sie ein IT-Support Ticket über das Microsoft Managed Desktop Portal einreichen. Wenn Sie das Ticket archivieren, stellen wir den Edge stable-Kanal für die Test Gruppe bereit und stellen ihn dann alle 24 Stunden in jeder nachfolgenden Bereitstellungsgruppe bereit. Um die Bereitstellung anzuhalten, müssen Sie ein weiteres Ticket anfordern, in dem Vorgänge angehalten werden.

## <a name="updates-to-microsoft-edge"></a>Updates für Microsoft Edge

Microsoft Managed Desktop stellt den [stabilen Kanal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) von Microsoft Edge bereit, der etwa alle sechs Wochen automatisch aktualisiert wird. Updates auf dem stabilen Kanal werden [schrittweise](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) von der Microsoft Edge-Produktgruppe ausgeführt, um die beste Benutzerfreundlichkeit sicherzustellen. Der Microsoft Edge Beta-Kanal ist derzeit nicht verfügbar.

Um sicherzustellen, dass Microsoft Edge ordnungsgemäß aktualisiert wird, sollten Sie die Microsoft-Edge- [Update-Richtlinien](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)nicht ändern.

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verwaltete Einstellungen

Microsoft Managed Desktop hat eine Reihe von Standardrichtlinien für Microsoft Edge erstellt, um den Browser zu schützen. Die standardmäßigen Browsereinstellungen lauten wie folgt:

### <a name="microsoft-edge-extensions"></a>Microsoft-Edge-Erweiterungen

Die Sicherheitsbasis für Microsoft Edge auf Microsoft Managed Desktop-Geräten legt zwei Richtlinien fest, um alle Chrome-Erweiterungen und sicheren Endbenutzer zu deaktivieren. Informationen zum Aktivieren und Bereitstellen von Erweiterungen in Ihrer Umgebung finden Sie unter Einstellungen, die Sie verwalten. 

#### <a name="extension-installation-blocklist"></a>Erweiterungs Installations Blockliste
**Standardwert:** Alle

Microsoft Managed Desktop legt diese Richtlinie fest, um zu verhindern, dass Chrome-Erweiterungen auf verwalteten Endpunkten installiert werden. Es gibt bekannte risksassociated mit dem Chromium-Erweiterungsmodell, einschließlich Datenverlust Schutz, Datenschutz und anderen Risiken, die Geräte gefährden können. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Zulassen von systemeigenen Messaginghosts auf Benutzerebene (installiert ohne Administratorberechtigungen)

**Standardwert:** Deaktiviert

Durch Deaktivieren dieser Richtlinie verwendet Microsoft Edge nur systemeigene Messaginghosts, die auf Systemebene installiert sind. Systemeigene Messaginghosts sind ein Teil von Chrome-Erweiterungen, mit denen der Browser mit anderen Teilen des Endpunkts des Benutzers interagieren kann, wodurch eine Vielzahl von Sicherheitsaspekten entsteht.  

### <a name="secure-sockets-layer-ssl"></a>Secure Sockets Layer (SSL)

#### <a name="minimum-ssl-version"></a>Minimale SSL-Version

**Standardwert:** Mindestens TLS 1,2 unterstützt

Wenn Sie die unsicherste TLS 1,1 verwenden möchten, können Sie dies anfordern.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Ermöglicht Benutzern das Fortfahren auf der Seite SSL-Warnung

**Standardwert:** Deaktiviert

Es wird nicht empfohlen, diese Einstellung zu aktivieren, da Benutzer Websites mit SSL-Fehlern besuchen können.

### <a name="microsoft-defender-smart-screen"></a>Smart Screen von Microsoft Defender

#### <a name="configure-microsoft-defender-smartscreen"></a>Konfigurieren von Microsoft Defender SmartScreen

**Standardwert:** Aktiviert

Standardmäßig aktiviert, um den Schutz von Endbenutzern zu erleichtern.

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a>Microsoft Defender-SmartScreen-Eingabeaufforderungen für Websites

**Standardwert:** Aktiviert

Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da Benutzer Warnungen ignorieren und weiterhin potenziell schädliche Websites verwenden können.

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>Verhindern der Umgehung von Microsoft Defender-SmartScreen-Warnungen bei Downloads

**Standardwert:** Aktiviert

Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da Benutzer Warnungen ignorieren und nicht überprüfte Downloads durchführen können.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standardeinstellung für Adobe Flash

**Standardwert:** Deaktiviert

Es wird nicht empfohlen, Flash aufgrund der zugeordneten Sicherheitsrisiken zu verwenden. Wenn Sie weiterhin über Prozesse verfügen, die von Flash abhängen, legen Sie die **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** -Richtlinie so fest, dass Flash für Websites aktiviert wird, die diese benötigen. Wenn die Liste der Websites, für die Flash verwendet werden kann, nicht verwaltet werden kann, müssen Sie eine Änderungsanforderung zum Ändern des Werts in **"Click to Play"** ändern, mit dem Benutzer auswählen können, wann Flash ausgeführt werden soll.

### <a name="password-manager"></a>Kennwort-Manager

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Speichern von Kennwörtern im Password Manager aktivieren

**Standardwert:** Deaktiviert

Es wird nicht empfohlen, dass Benutzer Kennwörter auf Ihrem Gerät speichern können.

### <a name="other-settings"></a>Weitere Einstellungen

#### <a name="enable-site-isolation-for-every-site"></a>Aktivieren der Website Isolierung für jeden Standort

**Standardwert:** Aktiviert

Wenn diese Richtlinie aktiviert ist, können Benutzer nicht das Standardverhalten ablehnen, bei dem jede Website in einem eigenen Prozess ausgeführt wird.

#### <a name="supported-authentication-schemes"></a>Unterstützte Authentifizierungsschemas

**Standardwert:** NTLM, aushandeln

Microsoft Managed Desktop unterstützt keine Standard-oder Digest-Authentifizierungsschemas.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Automatisches Importieren der Daten und Einstellungen eines anderen Browsers bei der ersten Ausführung

**Standardwert:** Automatisches Importieren aller unterstützten Datentypen und Einstellungen aus dem Standardbrowser 

Wenn diese Richtlinie angewendet wird, überspringt die erste Ausführungsumgebung den Import Abschnitt, wodurch die Benutzerinteraktion minimiert wird. Die Browserdaten aus älteren Versionen von Microsoft Edge werden unabhängig von dieser Einstellung immer automatisch bei der ersten Ausführung migriert. 


## <a name="settings-you-manage"></a>Einstellungen, die Sie verwalten

Sie können alle Microsft-edgeeinstellungen bereitstellen, die zuvor nicht mithilfe des Profils für administrative Vorlagen in Microsoft InTune beschrieben wurden. Ausführliche Informationen finden Sie unter [configure Microsoft Edge Policy Settings with Microsoft InTune](https://docs.microsoft.com/deployedge/configure-edge-with-intune). Wenn Sie eine Richtlinie auswerten möchten, die derzeit nicht in den Microsoft Edge Administrative Templates in InTune enthalten ist, können Sie benutzerdefinierte Einstellungen für Windows 10-Geräte in InTune verwenden.

### <a name="enabling-specific-chrome-extensions"></a>Aktivieren bestimmter Chrome-Erweiterungen

Die administrative Vorlage bietet eine Einstellung zum Bereitstellen bestimmter Chrome-Erweiterungen mit Microsoft InTune. Sie finden Sie unter **Computer Konfiguration > Microsoft Edge > Extensions > für die Installation bestimmter Erweiterungen zugelassen sind**.

### <a name="install-extensions-silently"></a>Automatische Installation von Erweiterungen

Sie können auch die administrative Vorlage verwenden, um Microsoft Edge so festzulegen, dass Erweiterungen installiert werden, ohne dass der Benutzer benachrichtigt wird. Sie finden Sie unter **Computer Konfiguration > Microsoft Edge > Extensions > steuern, welche Erweiterungen automatisch installiert werden**.

### <a name="other-common-enterprise-policies"></a>Andere allgemeine Unternehmensrichtlinien

Microsoft Edge bietet eine Vielzahl zusätzlicher Richtlinien. Dies sind einige der häufigsten:
 
- [Konfigurieren von Websites in der Liste "Enterprise-Website" und im IE-Modus](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Konfigurieren der Einstellungen für Start, Startseite und neue Registerkartenseiten](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Konfigurieren der Surf Spieleinstellung](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Konfigurieren von Proxyservereinstellungen](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

