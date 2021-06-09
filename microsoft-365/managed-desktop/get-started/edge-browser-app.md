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
# <a name="new-microsoft-edge-app"></a>Neue Microsoft Edge-App

Der neue [Microsoft Edge Browser](https://www.microsoft.com/edge) bietet erstklassige Leistung mit mehr Datenschutz, mehr Produktivität und mehr Nutzen beim Browsen. Microsoft Managed Desktop bietet eine öffentliche Vorschau der Bereitstellung des neuen Edgebrowsers in Ihrer Umgebung.

## <a name="initial-deployment"></a>Erstbereitstellung

Um Ihre Microsoft Managed Desktop Geräte zum neuen Microsoft Edge Browser zu migrieren, melden Sie über das Microsoft Managed Desktop Portal ein IT-Supportticket an. Wir stellen den Edge Stable-Kanal für die Testgruppe bereit, wenn Sie das Ticket einreichen, und stellen ihn dann alle 24 Stunden in jeder nachfolgenden Bereitstellungsgruppe bereit. Wenn Sie die Bereitstellung anhalten möchten, geben Sie ein weiteres Ticket ein, in dem Operations zur Aufbewahrung aufgefordert wird.

Der [Betakanal](/deployedge/microsoft-edge-channels#beta-channel) steht auch auf Anfrage zur repräsentativen Validierung innerhalb Ihrer Organisation zur Verfügung. Microsoft Managed Desktop stellt die Anwendung nach Bedarf in den Test- und Erstgruppen bereit, sodass alle diese Benutzer zusätzlich zum Stable Channel über den Betakanal verfügen. Für alle anderen Benutzer, die Zugriff auf den Betakanal benötigen, fügen Sie sie der Gruppe **"Modern Workplace - Edge Beta-Benutzer"** hinzu und lassen Sie sie über die Unternehmensportal

## <a name="updates-to-microsoft-edge"></a>Updates für Microsoft Edge

Microsoft Managed Desktop stellt den [Stable-Kanal](/deployedge/microsoft-edge-channels#stable-channel) von Microsoft Edge bereit, der etwa alle sechs Wochen automatisch aktualisiert wird. Updates für den Stable-Kanal werden [schrittweise](/deployedge/microsoft-edge-update-progressive-rollout) von der Microsoft Edge Produktgruppe eingeführt, um die beste Benutzererfahrung für Kunden sicherzustellen. 

Der [Betakanal](/deployedge/microsoft-edge-channels#beta-channel) wird für Geräte in der Test- und der ersten Gruppe zur repräsentativen Überprüfung innerhalb der Organisation bereitgestellt. Dieser Kanal wird vollständig unterstützt und etwa alle sechs Wochen automatisch mit neuen Features aktualisiert.

Um sicherzustellen, dass Microsoft Edge Updates ordnungsgemäß aktualisiert, ändern Sie nicht die Microsoft Edge [Updaterichtlinien.](/deployedge/microsoft-edge-update-policies)



## <a name="settings-managed-by-microsoft-managed-desktop"></a>von Microsoft Managed Desktop verwaltete Einstellungen

Microsoft Managed Desktop hat einen Standardsatz von Richtlinien für Microsoft Edge zum Sichern des Browsers erstellt. Die Standardbrowsereinstellungen sind wie folgt:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge Erweiterungen

Die Sicherheitsgrundwerte für Microsoft Edge auf Microsoft Managed Desktop Geräten legen zwei Richtlinien fest, um alle Chrome-Erweiterungen und sicheren Benutzer zu deaktivieren. Informationen zum Aktivieren und Bereitstellen von Erweiterungen in Ihrer Umgebung finden Sie unter Einstellungen Sie verwalten. 

#### <a name="extension-installation-blocklist"></a>Erweiterungsinstallationsblockliste
**Standardwert:** Alle

Microsoft Managed Desktop legt diese Richtlinie fest, um zu verhindern, dass Chrome-Erweiterungen auf verwalteten Endpunkten installiert werden. Es gibt bekannte Risiken im Zusammenhang mit dem Chromium Erweiterungsmodell, einschließlich Schutz vor Datenverlust, Datenschutz und andere Risiken, die Geräte beeinträchtigen können. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Zulassen systemeigener Messaginghosts auf Benutzerebene (ohne Administratorberechtigungen installiert)

**Standardwert:** Deaktiviert

Durch Deaktivieren dieser Richtlinie verwenden Microsoft Edge nur systemeigene Messaginghosts, die auf Systemebene installiert sind. Systemeigene Messaginghosts sind Teil von Chrome-Erweiterungen, die es dem Browser ermöglichen, mit anderen Teilen des Endpunkts des Benutzers zu interagieren, wodurch eine Vielzahl von Sicherheitsbedenken entsteht.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Minimale TLS-Version

**Standardwert:** Mindestens tls 1.2 unterstützt

Wenn Sie das weniger sichere TLS 1.1 verwenden möchten, können Sie eine Entsprechendeanforderung senden.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Ermöglicht Benutzern das Fortfahren von der SSL-Warnseite

**Standardwert:** Deaktiviert

Es wird davon abgeraten, diese Einstellung zu aktivieren, da benutzer websites mit TSL-Fehlern besuchen können.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Konfigurieren von Windows Defender SmartScreen

**Standardwert:** Aktiviert

Standardmäßig aktiviert, um Benutzer zu schützen.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen-Aufforderungen für Websites

**Standardwert:** Aktiviert

Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da dies es Benutzern ermöglichen würde, Warnungen zu ignorieren und weiterhin potenziell schädliche Websites zu verwenden.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Verhindern der Umgehung von Windows Defender SmartScreen-Warnungen zu Downloads

**Standardwert:** Aktiviert

Es wird nicht empfohlen, diese Einstellung zu deaktivieren, da dadurch Benutzer Warnungen ignorieren und nicht überprüfte Downloads abschließen können.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standardeinstellung für Adobe Flash

**Standardwert:** Deaktiviert

Aufgrund der damit verbundenen Sicherheitsrisiken wird die Verwendung von Flash nicht empfohlen. Wenn Sie weiterhin Prozesse haben, die von Flash abhängig sind, legen Sie die **[PluginsAllowedForUrls-Richtlinie](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** fest, um Flash für Websites zu aktivieren, die es benötigen. Wenn Sie keine Liste zulässiger Websites zur Verwendung von Flash verwalten können, senden Sie eine Änderungsanforderung, um den Wert in **"Klick-und-Los" zu** ändern, sodass Benutzer auswählen können, wann Flash ausgeführt werden soll.

### <a name="password-manager"></a>Kennwort-Manager

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Aktivieren des Speicherns von Kennwörtern im Kennwort-Manager

**Standardwert:** Deaktiviert

Der Kennwort-Manager ist standardmäßig deaktiviert. Wenn Sie diese Funktion aktiviert haben, senden Sie eine Supportanfrage, und unsere Servicetechniker können die Einstellung in Ihrer Umgebung aktivieren. 

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer-Modus in Microsoft Edge
Der IE-Modus auf Microsoft Edge erleichtert die Verwendung aller Websites, die Ihre Organisation benötigt, in einem einzigen Browser. Es verwendet das integrierte Chromium-Modul für Websites, die mit dem Chromium Renderingmodul kompatibel sind, und das Trident MSHTML-Modul aus Internet Explorer 11 (IE11) für Websites, die nicht von IE-Funktionen abhängig sind oder davon abhängig sind. [Weitere Informationen](/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop aktiviert standardmäßig den Internet Explorer-Modus für Ihre Geräte 

#### <a name="internet-explorer-mode-integration"></a>Integration des Internet Explorer-Modus
**Standardwert:** Internet Explorer-Modus

Standardmäßig ist für Geräte die Verwendung des Internet Explorer-Modus festgelegt, Sie können jedoch festlegen, dass Websites stattdessen in einem eigenständigen Internet Explorer 11-Fenster geöffnet werden. Um dieses Verhalten zu ändern, stellen Sie eine Supportanfrage.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Hinzufügen von Websites zur Websiteliste für den Enterprise modus
Damit Websites im Internet Explorer-Modus geöffnet werden können, müssen Sie sie in die [websiteliste Enterprise](/DeployEdge/edge-ie-mode-sitelist)einschließen. Die Verwaltung und Bereitstellung der Enterprise Websiteliste liegt in Ihrer Verantwortung. Ausführliche Informationen finden Sie unter [Konfigurieren der Richtlinie "Konfigurieren Enterprise Mode Site List"](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Weitere Einstellungen

#### <a name="enable-site-isolation-for-every-site"></a>Aktivieren der Websiteisolation für jeden Standort

**Standardwert:** Aktiviert

Wenn diese Richtlinie aktiviert ist, können Benutzer das Standardverhalten, in dem jede Website in einem eigenen Prozess ausgeführt wird, nicht deaktivieren.

#### <a name="supported-authentication-schemes"></a>Unterstützte Authentifizierungsschemas

**Standardwert:** NTLM, Aushandeln

Microsoft Managed Desktop unterstützt keine Standard- oder Digestauthentifizierungsschemas.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Automatisches Importieren der Daten und Einstellungen eines anderen Browsers bei der ersten Ausführung

**Standardwert:** Automatisches Importieren aller unterstützten Datentypen und Einstellungen aus dem Standardbrowser 

Wenn diese Richtlinie angewendet wird, überspringt die Erste Ausführungserfahrung den Importabschnitt, wodurch die Benutzerinteraktion minimiert wird. Die Browserdaten aus älteren Versionen von Microsoft Edge werden unabhängig von dieser Einstellung bei der ersten Ausführung immer im Hintergrund migriert. 


## <a name="settings-you-manage"></a>Einstellungen Sie verwalten

Sie können alle Microsoft Edge Einstellungen bereitstellen, die zuvor nicht beschrieben wurden, indem Sie das Profil "Administrative Vorlagen" in Microsoft Intune verwenden. Ausführliche Informationen finden Sie unter [Konfigurieren Microsoft Edge Richtlinieneinstellungen mit Microsoft Intune.](/deployedge/configure-edge-with-intune) Wenn Sie eine Richtlinie auswerten möchten, die derzeit nicht in der Microsoft Edge Administrative Vorlagen in Intune enthalten ist, können Sie benutzerdefinierte Einstellungen für Windows 10 Geräte in Intune verwenden.

### <a name="enabling-specific-chrome-extensions"></a>Aktivieren bestimmter Chrome-Erweiterungen

Die administrative Vorlage bietet eine Einstellung zum Bereitstellen bestimmter Chrome-Erweiterungen mit Microsoft Intune. Sie finden sie unter **Computerkonfiguration > Microsoft Edge > Erweiterungen > Zulassen, dass bestimmte Erweiterungen installiert werden.**

### <a name="install-extensions-silently"></a>Automatisches Installieren von Erweiterungen

Sie können die administrative Vorlage auch verwenden, um Microsoft Edge zum Installieren von Erweiterungen festzulegen, ohne den Benutzer zu benachrichtigen. Sie finden es unter **Computerkonfiguration > Microsoft Edge > Erweiterungen > Steuern, welche Erweiterungen im Hintergrund installiert werden.**

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge Aktualisieren von Richtlinien
Um sicherzustellen, dass Microsoft Edge Updates ordnungsgemäß aktualisiert, ändern Sie nicht die Microsoft Edge [Updaterichtlinien.](/deployedge/microsoft-edge-update-policies)

### <a name="other-common-enterprise-policies"></a>Andere allgemeine Unternehmensrichtlinien

Microsoft Edge bietet viele andere Richtlinien. Dies sind einige der gängigsten:
 
- [Konfigurieren von Websites im Enterprise-Websitelisten- und IE-Modus](/deployedge/edge-ie-mode-sitelist)
- [Konfigurieren der Einstellungen für Start-Up, Startseite und neue Registerkartenseite](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Konfigurieren der Surf-Spieleinstellung](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Konfigurieren von Proxyservereinstellungen](/deployedge/microsoft-edge-policies#proxy-server)
