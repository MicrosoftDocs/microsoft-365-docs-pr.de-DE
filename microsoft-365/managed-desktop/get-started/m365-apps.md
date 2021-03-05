---
title: Microsoft 365 Apps for Enterprise
description: So stellen Sie Microsoft 365-Apps zur Verfügung, wie sie aktualisiert werden und wie Einstellungen verwaltet werden
keywords: Änderungsverlauf
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 26e62d6e59f1f90e35d9e18e6eed917a66876645
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453921"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

## <a name="initial-deployment"></a>Erstbereitstellung

Microsoft Managed Desktop stellt sicher, dass Microsoft 365 Apps for Enterprise (64-Bit) als Teil des Images auf allen [Programmgeräten installiert ist.](../service-description/device-list.md) Alle folgenden Anwendungen sollten auf dem Gerät vorhanden sein, wenn es zugestellt wird:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Zugriff
- Skype for Business
- OneNote

Dieser Ansatz minimiert die Netzwerkbelastung und stellt sicher, dass Benutzer produktiv sein können, sobald sie ihr Gerät empfangen. Anschließend stellen wir weitere Richtlinien für verwaltete Geräte zum Einrichten der Anwendungen zur Verwendung zur Verfügung.

> [!NOTE]
> Microsoft Teams wird separat von Microsoft 365 Apps for Enterprise bereitgestellt und ist nicht im Basisimage enthalten. 

### <a name="available-deployment-to-users"></a>Verfügbare Bereitstellung für Benutzer

Wenn ein Benutzer aus irgendeinem Grund nicht über Microsoft 365-Apps auf seinem Gerät verfügt, können Sie ein Paket verwenden, um das Gerät in den erwarteten Zustand zurückzukehren. Fügen Sie den Benutzer der **Gruppe Modern Workplace-Office-Office365_Install** hinzu, und die Apps stehen ihnen im Unternehmensportal zur Verfügung.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for Enterprise (32-Bit)

Microsoft Managed Desktop unterstützt die Bereitstellung der 32-Bit-Version von M365 Apps for Enterprise nicht.

## <a name="updates-to-microsoft-365-apps"></a>Updates für Microsoft 365-Apps

Microsoft 365-Apps werden auf dem monatlichen Unternehmenskanal [aktualisiert.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) Diese Vorgehensweise stellt Ihren Benutzern jeden Monat neue Office-Features zur Verfügung, sie erhalten jedoch nur ein Update pro Monat in einem vorhersagbaren Veröffentlichungszeitplan. Updates werden am zweiten Dienstag des Monats veröffentlicht. Diese Updates können Feature-, Sicherheits- und Qualitätsupdates enthalten. Diese Updates erfolgen automatisch und werden direkt aus dem Office CDN für diesen bestimmten Kanal gezogen.

Microsoft Managed Desktop staffelt jede Version, um potenzielle Probleme in Ihrer Umgebung zu identifizieren. Wir schließen den Rollout 28 Tage nach der Veröffentlichung der Microsoft 365 App-Produktgruppe ab. Microsoft Managed Desktop plant Aktualisierungsversionen für verschiedene Gruppen, um Zeit für Überprüfungen und Tests wie folgt zu lassen: 

- Test: null Tage
- First: zero days
- Schnell: 3 Tage
- Broad: 7 Tage

Microsoft Managed Desktop legt einen Updatetermin von sieben [Tagen für](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) Geräte fest. Sobald das Update verfügbar ist, muss es innerhalb von sieben Tagen installiert werden. Benutzer [werden](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) benachrichtigt, dass Updates an mehreren Stellen erforderlich sind: der Anwendung, in der Systemleiste 12 Stunden vor dem Stichtag, und sie erhalten eine 15-minütige Warnung vor dem Stichtag. Alle Microsoft 365-Apps müssen geschlossen werden, damit das Update abgeschlossen ist.

### <a name="pausing-or-rolling-back-an-update"></a>Anhalten oder Rollback eines Updates

Wenn Sie das Microsoft 365-App-Update aus irgendeinem [](../working-with-managed-desktop/admin-support.md) Grund anhalten oder zurückrollen müssen, senden Sie eine Administratorunterstützungsanforderung über das Microsoft Managed Desktop-Portal.

Während einer Version überwacht Microsoft Managed Desktop die Fehlerraten aller Microsoft 365-Apps. Wenn wir einen erheblichen Qualitätsunterschied zwischen der neuen Version und dem Vorgänger beachten, können wir sie über das Microsoft Managed Desktop Admin-Portal kontaktieren. Je nach Schweregrad fragen wir Sie entweder, ob Sie die Veröffentlichung anhalten möchten, oder informieren Sie, dass wir Maßnahmen ergriffen haben, um ein Problem zu beheben. 

### <a name="delivery-optimization"></a>Übermittlungsoptimierung

Die Übermittlungsoptimierung ist eine Peer-zu-Peer-Verteilungstechnologie, die unter Windows 10 verfügbar ist. Sie ermöglicht Es Geräten, Inhalte, z. B. Updates, zu teilen, die die Geräte über das Internet von Microsoft heruntergeladen haben. Die Verwendung kann dazu beitragen, die Netzwerkbandbreite zu reduzieren, da ein Gerät Teile des Updates von einem anderen Gerät im lokalen Netzwerk erhalten kann, anstatt das Update vollständig von Microsoft herunterladen zu müssen.

[Die Übermittlungsoptimierung](https://docs.microsoft.com/deployoffice/delivery-optimization) ist standardmäßig auf Geräten mit den Editionen Windows 10 Enterprise oder Windows 10 Education aktiviert. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verwaltete Einstellungen

Microsoft verwaltet einige Einstellungen als Teil des Diensts. Microsoft Managed Desktop verwaltet keine Office Security-Basislinie, Aber Sie können diese selbst festlegen, indem Sie den Anweisungen im Abschnitt Einstellungen folgen, [die Sie verwalten.](#settings-you-manage)

### <a name="update-settings"></a>Einstellungen aktualisieren

Microsoft Managed Desktop verwaltet alle [Updateeinstellungen](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) für verwaltete Geräte, und Sie sollten diese Einstellungen ändern.

### <a name="set-updates-to-occur-automatically"></a>Festlegen der automatischen Durchführung von Updates

**Standardwert :** Aktiviert

Diese Richtlinie ist so konfiguriert, dass alle Office-Geräte aus der Cloud auf dem neuesten Stand gehalten werden können. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Festlegen eines Stichtermins, wenn Updates angewendet werden müssen

**Standardwert:** 7 Tage

Die **UpdateDeadline-Richtlinie** wird verwendet, um den Kulanzzeitraum zu konfigurieren, den Benutzer haben, bevor ein Update auf dem Gerät erzwungen wird. Diese Stichtagrichtlinie löst außerdem Benachrichtigungen [an](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) den Benutzer aus, um sie über die auf ihrem Gerät erforderlichen Änderungen zu informieren.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Zurückdingen von Updates auf einem Gerät für einen Bestimmten Zeitraum

Diese Richtlinie ist für jede Updateverwaltungsgerätegruppe unterschiedlich konfiguriert und ist für Microsoft Managed Desktop erforderlich, um seine Updateziele zu erfüllen:  

- Test: null Tage
- First: zero days
- Fast 7 Tage
- Broad: 21 Tage

### <a name="update-notifications-settings"></a>Aktualisieren von Benachrichtigungseinstellungen

**Standardwert:** False

Die Einstellung "Updatebenachrichtigungen ausblenden" ist auf Microsoft Managed Desktop-Geräten auf [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) **False** festgelegt, um benutzern die beste Updateerfahrung zu bieten, indem Sie sie benachrichtigen, wenn Updates erforderlich sind.

### <a name="specify-a-location-to-look-for-updates"></a>Angeben eines Orts für die Suche nach Updates

**Standardwert:** Monatlicher Unternehmenskanal

Eine Kombination der **UpdatePath-** und **UpdateChannel-Richtlinien** wird bei Bedarf verwendet, um den Updatezeitplan zu erreichen. Diese Richtlinien sind so festgelegt, dass alle Office-Geräte Updates direkt vom CDN für den monatlichen Unternehmenskanal erhalten.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Angeben der Zielversion von Microsoft 365-Apps

Die Zielversionsrichtlinie wird manchmal von Microsoft Managed Desktop zum Rollback oder Anheften einer bestimmten Version von Office verwendet. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ausblenden der Option zum Aktivieren oder Deaktivieren automatischer Office-Updates

**Standardwert :** Aktiviert

Diese Einstellung ist erforderlich, damit Microsoft Managed Desktop seine Updateziele für Microsoft 365-Anwendungen erfüllen kann. 

### <a name="first-run-settings"></a>Einstellungen für die erste Ausführung 

Es gibt mehrere Einstellungen, die sich auf das Verhalten beim ersten Ausführen von Office auswirken.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Akzeptieren der Lizenzbedingungen im Namen des Endbenutzers

**Standardwert :** Deaktiviert

Wenn ein Benutzer eine Microsoft 365-App zum ersten Mal öffnet, wird er aufgefordert, die Lizenzbedingungen zu akzeptieren. Wenn Sie die Lizenzbedingungen im Namen Ihrer Benutzer akzeptieren möchten, stellen Sie eine Dienstanforderung beim Microsoft Managed Desktop Operations-Team, in dem Sie die Aktivierung dieser Einstellung anfordern. 

### <a name="suppress-outlook-mobile-check-box"></a>Kontrollkästchen Mobiles Outlook unterdrücken

**Standardwert :** Deaktiviert

Wenn ein Benutzer Outlook zum ersten Mal öffnet, wird er zur Installation von Outlook Mobile aufgefordert. Wenn Das Kontrollkästchen für Die Benutzer nicht angezeigt werden soll, senden Sie eine Dienstanforderung beim Microsoft Managed Desktop Operations-Team, um diese Einstellung für Ihre Geräte zu aktivieren. 

## <a name="other-settings"></a>Weitere Einstellungen

Es gibt weitere Microsoft 365-App-Einstellungen, die Microsoft Managed Desktop optional in Ihrem Namen konfigurieren kann. 

### <a name="disable-personal-onedrive"></a>Deaktivieren von Persönlichem OneDrive

**Standardwert :** Deaktiviert

Einige Organisationen machen sich Sorgen darüber, dass Benutzer auf ihren Geräten Zugriff auf Unternehmens- und persönliche Dateien haben. Sie können eine Dienstanforderung beim Microsoft Managed Desktop Operations-Team anfordern, dass diese Einstellung aktiviert ist. 

## <a name="settings-you-manage"></a>Von Ihnen verwaltete Einstellungen

Es gibt viele andere Richtlinien, die Microsoft Managed Desktop noch nicht als Teil unseres Diensts festgelegt hat. Sie können diese Richtlinien mithilfe von Microsoft Intune konfigurieren, das den [Office Cloud Policy Service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) verwendet. Führen Sie zum Festlegen dieser Richtlinien die folgenden Schritte aus:

1.  Melden Sie sich beim Microsoft Endpoint Manager Admin Center an.
2.  Auswählen **von Apps > Richtlinien für Office-Apps > Erstellen**
3.  Gehen Sie **auf der Seite** Richtlinienkonfiguration erstellen wie folgt vor:
    - Geben Sie einen Namen ein.
    - Geben Sie eine Beschreibung an (optional).
    - Wählen **Sie** in Zuordnungen aus, ob diese Richtlinie für alle Benutzer von Microsoft 365 Apps for Enterprise oder nur für Benutzer gilt, die anonym über Office für das Web auf Dokumente zugreifen.
    - Wählen Sie die AAD-basierte Sicherheitsgruppe aus, die der Richtlinienkonfiguration zugewiesen ist. Jede Richtlinienkonfiguration kann nur einer Gruppe zugewiesen werden, und jeder Gruppe kann nur eine Richtlinienkonfiguration zugewiesen werden.
    - Konfigurieren Sie die Richtlinieneinstellungen, die in die Richtlinienkonfiguration einbezogen werden sollen. Sie können nach dem Namen der Richtlinieneinstellung suchen, um die Richtlinieneinstellung zu finden, die Sie konfigurieren möchten. Sie können auch nach der Anwendung, nach einer empfohlenen Sicherheitsbasislinie und nach der Konfiguration der Richtlinie filtern. Die Plattformspalte gibt an, ob die Richtlinie auf Microsoft 365 Apps for Enterprise für Windows-Geräte, Office für das Web oder alle angewendet wird.
4.  Nachdem Sie Ihre Auswahl getroffen haben, wählen Sie **Erstellen aus.**

> [!NOTE]
> Office-Konfigurationsrichtlinien unterstützen nur die benutzerbasierte Bereitstellung
