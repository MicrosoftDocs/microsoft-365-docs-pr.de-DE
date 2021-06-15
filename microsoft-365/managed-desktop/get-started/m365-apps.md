---
title: Microsoft 365 Apps for Enterprise
description: Bereitstellen von Microsoft 365 Apps, Aktualisieren und Verwalten von Einstellungen
keywords: Änderungsverlauf
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: c3928b5814332f2585adc613e1e84cbe5cc883a0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925611"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

## <a name="initial-deployment"></a>Erstbereitstellung

Microsoft Managed Desktop stellt sicher, dass Microsoft 365 Apps for Enterprise (64-Bit) als Teil des Images auf allen [Programmgeräten](../service-description/device-list.md)installiert werden. Alle folgenden Anwendungen sollten auf dem Gerät vorhanden sein, wenn es bereitgestellt wird:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype for Business
- OneNote

Dieser Ansatz minimiert die Auswirkungen auf das Netzwerk und stellt sicher, dass Benutzer produktiv sein können, sobald sie ihr Gerät erhalten. Anschließend stellen wir weitere Richtlinien auf verwalteten Geräten bereit, um die Anwendungen für die Verwendung einzurichten.

> [!NOTE]
> Microsoft Teams wird separat von Microsoft 365 Apps for Enterprise bereitgestellt und ist nicht im Basisimage enthalten. 

### <a name="available-deployment-to-users"></a>Verfügbare Bereitstellung für Benutzer

Wenn ein Benutzer aus irgendeinem Grund keine Microsoft 365 Apps auf seinem Gerät hat, können Sie ein Paket verwenden, um das Gerät in den erwarteten Zustand zurückzugeben. Fügen Sie den Benutzer der Gruppe **"Modern Workplace-Office-Office365_Install"** hinzu, und die Apps stehen ihnen im Unternehmensportal zur Verfügung.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for Enterprise (32-Bit)

Microsoft Managed Desktop unterstützt nicht die Bereitstellung der 32-Bit-Version von M365 Apps for Enterprise.

## <a name="updates-to-microsoft-365-apps"></a>Updates für Microsoft 365 Apps

Microsoft 365 Apps im [monatlichen Enterprise Kanal](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)aktualisiert werden. Diese Vorgehensweise bietet Ihren Benutzern jeden Monat neue Office Features, aber sie erhalten nur ein Update pro Monat nach einem vorhersagbaren Veröffentlichungszeitplan. Updates werden am zweiten Dienstag des Monats veröffentlicht. Diese Updates können Funktions-, Sicherheits- und Qualitätsupdates enthalten. Diese Updates erfolgen automatisch und werden direkt aus dem Office CDN für diesen bestimmten Kanal abgerufen.

Microsoft Managed Desktop staturiert jede Version, um potenzielle Probleme in Ihrer Umgebung zu identifizieren. Das Rollout wird 28 Tage nach der Veröffentlichung der Microsoft 365 App-Produktgruppe abgeschlossen. Microsoft Managed Desktop plant Updateversionen für verschiedene Gruppen, um Zeit für Überprüfungen und Tests wie folgt zu lassen: 

- Test: null Tage
- First: zero days
- Schnell: 3 Tage
- Allgemein: 7 Tage

Microsoft Managed Desktop legt einen [Stichtag](/deployoffice/configure-update-settings-microsoft-365-apps) für sieben Tage für Updates für Geräte fest. Sobald das Update verfügbar ist, muss es innerhalb von sieben Tagen installiert werden. Benutzer werden [benachrichtigt,](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) dass Updates an verschiedenen Stellen erforderlich sind: die Anwendung, 12 Stunden vor dem Stichtag in der Taskleiste des Systems, und sie erhalten eine 15-minütige Warnung vor dem Stichtag. Alle Microsoft 365 Apps müssen geschlossen werden, damit das Update abgeschlossen ist.

### <a name="pausing-or-rolling-back-an-update"></a>Anhalten oder Zurücksetzen eines Updates

Wenn Sie Microsoft 365 App-Update aus irgendeinem Grund anhalten oder zurücksetzen müssen, senden Sie eine [Administrator-Supportanfrage](../working-with-managed-desktop/admin-support.md) über das Microsoft Managed Desktop Portal.

Während einer Veröffentlichung überwacht Microsoft Managed Desktop die Fehlerraten aller Microsoft 365 Apps. Wenn wir einen erheblichen Qualitätsunterschied zwischen der neuen Version und dem Vorgänger feststellen, können wir Sie über das Microsoft Managed Desktop Admin-Portal kontaktieren. Je nach Schweregrad werden wir entweder fragen, ob Sie die Version anhalten möchten, oder Sie darüber informieren, dass wir Maßnahmen zur Behebung eines Problems ergriffen haben. 

### <a name="delivery-optimization"></a>Übermittlungsoptimierung

Die Übermittlungsoptimierung ist eine Peer-to-Peer-Verteilungstechnologie, die in Windows 10 verfügbar ist. Damit können Geräte Inhalte, z. B. Updates, freigeben, die die Geräte über das Internet von Microsoft heruntergeladen haben. Die Verwendung kann dazu beitragen, die Netzwerkbandbreite zu reduzieren, da ein Gerät Teile des Updates von einem anderen Gerät im lokalen Netzwerk abrufen kann, anstatt das Update vollständig von Microsoft herunterladen zu müssen.

[Die Übermittlungsoptimierung](/deployoffice/delivery-optimization) ist standardmäßig auf Geräten aktiviert, auf denen die Windows 10 Enterprise- oder Windows 10 Education-Edition ausgeführt wird. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>von Microsoft Managed Desktop verwaltete Einstellungen

Microsoft verwaltet einige Einstellungen als Teil des Diensts. Microsoft Managed Desktop verwaltet keine Office Sicherheitsgrundwerte, Aber Sie können eine selbst festlegen, indem Sie die Anweisungen im [Abschnitt Einstellungen Verwalten](#settings-you-manage) befolgen.

### <a name="update-settings"></a>Einstellungen aktualisieren

Microsoft Managed Desktop verwaltet alle [Updateeinstellungen](/deployoffice/configure-update-settings-microsoft-365-apps) für verwaltete Geräte, und Sie sollten diese Einstellungen ändern.

### <a name="set-updates-to-occur-automatically"></a>Festlegen der automatischen Durchführung von Updates

**Standardwert:** Aktiviert

Diese Richtlinie wird konfiguriert, um sicherzustellen, dass alle Office Geräte aus der Cloud auf dem neuesten Stand gehalten werden können. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Festlegen eines Stichtags für die Anwendung von Updates

**Standardwert:** 7 Tage

Die **UpdateDeadline-Richtlinie** wird verwendet, um die Karenzzeit zu konfigurieren, über die Benutzer verfügen, bevor ein Update auf dem Gerät erzwungen wird. Diese Stichtagsrichtlinie löst auch [Benachrichtigungen](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) an den Benutzer aus, um sie über die auf dem Gerät erforderlichen Änderungen zu informieren.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Zurückstellen von Updates auf einem Gerät für einen Bestimmten Zeitraum

Diese Richtlinie ist für jede Updateverwaltungsgerätegruppe unterschiedlich konfiguriert und für Microsoft Managed Desktop erforderlich, um ihre Updateziele zu erreichen:  

- Test: null Tage
- First: zero days
- Schnell 7 Tage
- Allgemein: 21 Tage

### <a name="update-notifications-settings"></a>Aktualisieren von Benachrichtigungseinstellungen

**Standardwert:** False

Die Einstellung "Updatebenachrichtigungen ausblenden" ist auf Microsoft Managed Desktop Geräten auf **"False"** festgelegt, um benutzern die bestmögliche Updateerfahrung zu bieten, indem sie [benachrichtigt](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) werden, wenn Updates erforderlich sind.

### <a name="specify-a-location-to-look-for-updates"></a>Angeben eines Orts für die Suche nach Updates

**Standardwert:** Monatlicher Enterprise-Kanal

Eine Kombination der **UpdatePath-** und **UpdateChannel-Richtlinien** wird nach Bedarf verwendet, um den Updatezeitplan zu erreichen. Diese Richtlinien werden festgelegt, um sicherzustellen, dass alle Office Geräte Updates direkt vom CDN für den monatlichen Enterprise Kanal erhalten.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Angeben der Zielversion von Microsoft 365 Apps

Die Zielversionsrichtlinie wird manchmal von Microsoft Managed Desktop zum Zurücksetzen oder Anheften einer bestimmten Version von Office verwendet. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ausblenden der Option zum Aktivieren oder Deaktivieren Office automatischen Updates

**Standardwert:** Aktiviert

Diese Einstellung ist erforderlich, damit Microsoft Managed Desktop die Updateziele für Microsoft 365-Anwendungen erreichen können. 

### <a name="first-run-settings"></a>Einstellungen für die erstausführung 

Es gibt mehrere Einstellungen, die sich auf das Verhalten auswirken, wenn Office zum ersten Mal ausgeführt wird.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Akzeptieren der Lizenzbedingungen im Namen des Endbenutzers

**Standardwert:** Deaktiviert

Wenn ein Benutzer ein Microsoft 365 App zum ersten Mal öffnet, wird er aufgefordert, die Lizenzbedingungen zu akzeptieren. Wenn Sie die Lizenzbedingungen im Namen Ihrer Benutzer akzeptieren möchten, senden Sie eine Serviceanfrage beim Microsoft Managed Desktop Operations-Team, in dem Sie die Aktivierung dieser Einstellung anfordern. 

### <a name="suppress-outlook-mobile-check-box"></a>Kontrollkästchen "Outlook Mobile unterdrücken"

**Standardwert:** Deaktiviert

Wenn ein Benutzer Outlook zum ersten Mal geöffnet wird, wird er aufgefordert, Outlook Mobile zu installieren. Wenn Sie nicht möchten, dass Ihren Benutzern dieses Kontrollkästchen angezeigt wird, senden Sie eine Serviceanfrage an das Microsoft Managed Desktop Operations-Team, in dem sie aufgefordert werden, diese Einstellung für Ihre Geräte zu aktivieren. 

## <a name="other-settings"></a>Weitere Einstellungen

Es gibt weitere Microsoft 365 App-Einstellungen, die Microsoft Managed Desktop optional in Ihrem Auftrag konfigurieren können. 

### <a name="disable-personal-onedrive"></a>Persönliche OneDrive deaktivieren

**Standardwert:** Deaktiviert

Einige Organisationen sind darüber besorgt, dass Benutzer Zugriff auf unternehmenseigene und persönliche Dateien auf ihren Geräten haben. Sie können eine Serviceanfrage beim Microsoft Managed Desktop Operations-Team einreichen und diese Einstellung aktivieren. 

## <a name="settings-you-manage"></a>Einstellungen, die Sie verwalten

Es gibt viele andere Richtlinien, die Microsoft Managed Desktop noch nicht als Teil unseres Diensts festgelegt wurde. Sie können diese Richtlinien mithilfe von Microsoft Intune konfigurieren, die den [Office Cloudrichtliniendienst](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) verwendet. Gehen Sie folgendermaßen vor, um diese Richtlinien festzulegen:

1.  Melden Sie sich beim Microsoft Endpoint Manager Admin Center an.
2.  Auswählen von **Apps > Richtlinien für Office Apps > Erstellen**
3.  Führen Sie auf der Seite **"Richtlinienkonfiguration erstellen"** die folgenden Schritte aus:
    - Geben Sie einen Namen ein.
    - Geben Sie eine Beschreibung an (optional).
    - Wählen Sie in **Aufgaben** aus, ob diese Richtlinie für alle Benutzer von Microsoft 365 Apps for Enterprise oder nur für Benutzer gilt, die anonym über Office für das Web auf Dokumente zugreifen.
    - Wählen Sie die AAD-basierte Sicherheitsgruppe aus, die der Richtlinienkonfiguration zugewiesen ist. Jede Richtlinienkonfiguration kann nur einer Gruppe zugewiesen werden, und jeder Gruppe kann nur eine Richtlinienkonfiguration zugewiesen werden.
    - Konfigurieren Sie die Richtlinieneinstellungen, die in der Richtlinienkonfiguration enthalten sein sollen. Sie können nach dem Namen der Richtlinieneinstellung suchen, um die Richtlinieneinstellung zu finden, die Sie konfigurieren möchten. Sie können auch nach der Anwendung filtern, ob es sich bei der Richtlinie um eine empfohlene Sicherheitsbaseline handelt und ob die Richtlinie konfiguriert wurde. Die Plattformspalte gibt an, ob die Richtlinie auf Microsoft 365 Apps for Enterprise für Windows Geräte, Office für das Web oder alle angewendet wird.
4.  Nachdem Sie Ihre Auswahl getroffen haben, wählen Sie **Erstellen** aus.

> [!NOTE]
> Office Konfigurationsrichtlinien unterstützen nur die benutzerbasierte Bereitstellung