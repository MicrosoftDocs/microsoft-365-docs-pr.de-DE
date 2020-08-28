---
title: Microsoft 365 Apps for Enterprise
description: Bereitstellen von Microsoft 365-apps, deren Aktualisierung und die Verwaltung von Einstellungen
keywords: Änderungsverlauf
ms.prod: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: b3843da0d35d78486ed22af6d057930ee4ad5bc9
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2020
ms.locfileid: "47295263"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

## <a name="initial-deployment"></a>Erstbereitstellung

Microsoft Managed Desktop stellt sicher, dass Microsoft 365-Apps für Enterprise (64-Bit) als Teil des Abbilds auf allen [Programm Geräten](../service-description/device-list.md)installiert werden. Bei der Zustellung sollten alle folgenden Anwendungen auf dem Gerät vorhanden sein:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Zugriff
- Skype for Business
- OneNote

Dieser Ansatz minimiert die Auswirkungen auf das Netzwerk und stellt sicher, dass Benutzer produktiv sein können, sobald Sie Ihr Gerät empfangen. Anschließend stellen wir zusätzliche Richtlinien für verwaltete Geräte bereit, um die Anwendungen für die Verwendung einzurichten.

> [!NOTE]
> Microsoft Teams wird separat von Microsoft 365 apps for Enterprise bereitgestellt und ist nicht im Basisabbild enthalten. 

### <a name="available-deployment-to-users"></a>Verfügbare Bereitstellung für Benutzer

Wenn ein Benutzer aus irgendeinem Grund nicht über Microsoft 365-apps auf dem Gerät verfügt, können Sie ein Paket verwenden, um das Gerät in den erwarteten Zustand zurückzukehren. Fügen Sie den Benutzer der **modernen Arbeitsumgebung-Office-Office365_Install-** Gruppe hinzu, und die apps werden Ihnen im Unternehmens Portal zur Verfügung stehen.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365-Apps für Unternehmen (32-Bit)

Microsoft Managed Desktop unterstützt die Bereitstellung der 32-Bit-Version von M365 apps for Enterprise nicht.

## <a name="updates-to-microsoft-365-apps"></a>Updates für Microsoft 365-apps

Microsoft 365-apps werden im [monatlichen Enterprise-Kanal](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)auf "Aktualisieren" festgelegt. Diese Vorgehensweise bietet ihren Benutzern jeden Monat neue Office-Funktionen, aber Sie erhalten nur ein Update pro Monat für einen vorhersagbaren Veröffentlichungszeitplan. Updates werden am zweiten Dienstag im Monat veröffentlicht; Diese Updates können Features, Sicherheits-und Qualitäts Updates umfassen. Diese Updates werden automatisch durchgeführt und direkt aus dem Office CDN für den jeweiligen Kanal abgerufen.

Microsoft Managed Desktop staffelt jede Version, um potenzielle Probleme in Ihrer Umgebung zu identifizieren. Wir führen den Rollout 28 Tage nach der Veröffentlichung von der Microsoft 365 App-Produktgruppe aus. Microsoft Managed Desktop plant Update Releases für verschiedene Gruppen, um Zeit für Überprüfungen und Tests wie folgt zu gewähren: 

- Test: 0 Tage
- Zuerst: 0 Tage
- Fast: 7 Tage
- Allgemein: 21 Tage

Microsoft Managed Desktop legt eine siebentägige [Update Frist](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) für Geräte fest. Sobald das Update verfügbar ist, muss es innerhalb von sieben Tagen installiert werden. Benutzer werden [benachrichtigt](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) , dass Aktualisierungen an mehreren Standorten erforderlich sind: in der Anwendung, in der Taskleiste 12 Stunden vor dem Stichtag, und Sie erhalten eine 15-minütige Warnung vor dem Stichtag. Alle Microsoft 365-apps müssen geschlossen sein, damit das Update abgeschlossen werden kann.

### <a name="pausing-or-rolling-back-an-update"></a>Anhalten oder Rollback eines Updates

Wenn Sie das Microsoft 365-App-Update aus irgendeinem Grund anhalten oder ein Rollback ausführen müssen, melden Sie sich über das Microsoft Managed Desktop Portal über eine [Administrator Unterstützungsanforderung](../working-with-managed-desktop/admin-support.md) .

Während einer Version überwacht Microsoft Managed Desktop die Fehlerraten aller Microsoft 365-apps. Wenn wir einen signifikanten Qualitätsunterschied zwischen der neuen Version und Ihrem Vorgänger feststellen, können wir Sie über das Verwaltungsportal von Microsoft Managed Desktop kontaktieren. Je nach Schweregrad werden wir entweder Fragen, ob Sie die Veröffentlichung anhalten möchten oder Ihnen mitteilen, dass wir Maßnahmen ergriffen haben, um ein Problem zu beheben. 

### <a name="delivery-optimization"></a>Zustellungsoptimierung

Die Zustellungsoptimierung ist eine Peer-to-Peer-Verteilungstechnologie, die in Windows 10 verfügbar ist. Geräte können Inhalte wie Updates freigeben, die die Geräte über das Internet von Microsoft heruntergeladen haben. Dies kann dazu beitragen, dass die Netzwerkbandbreite verringert wird, da ein Gerät Teile des Updates von einem anderen Gerät in seinem lokalen Netzwerk erhalten kann, anstatt das Update vollständig von Microsoft herunterladen zu müssen.

Die [Zustellungsoptimierung](https://docs.microsoft.com/deployoffice/delivery-optimization) ist auf Geräten mit Windows 10 Enterprise-oder Windows 10 Education-Editionen standardmäßig aktiviert. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verwaltete Einstellungen

Microsoft verwaltet einige Einstellungen als Teil des Diensts. Microsoft Managed Desktop verwaltet keine Office-Sicherheitsbasislinie, aber Sie können sich selbst festlegen, indem Sie den Anweisungen im Abschnitt [Verwalten von Einstellungen](#settings-you-manage) folgen.

### <a name="update-settings"></a>Einstellungen aktualisieren

Microsoft Managed Desktop behält alle [Updateeinstellungen](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) für verwaltete Geräte bei, und Sie sollten diese Einstellungen ändern.

### <a name="set-updates-to-occur-automatically"></a>Festlegen der automatischen Durchführung von Updates

**Standardwert**: aktiviert

Diese Richtlinie wird konfiguriert, um sicherzustellen, dass alle Office-Geräte in der Cloud auf dem neuesten Stand gehalten werden können. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Festlegen eines Stichtags, wenn Updates angewendet werden müssen

**Standardwert**: 7 Tage

Die **UpdateDeadline** -Richtlinie wird verwendet, um die Kulanzzeit zu konfigurieren, die Benutzer vor dem Erzwingen einer Aktualisierung auf dem Gerät haben. Diese Frist Richtlinie löst auch [Benachrichtigungen](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) an den Benutzer aus, um Sie über die auf dem Gerät erforderlichen Änderungen zu informieren.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Aufschieben von Updates auf einem Gerät für einen bestimmten Zeitraum

Diese Richtlinie wird für jede Update Verwaltungsgeräte Gruppe unterschiedlich konfiguriert und ist für Microsoft Managed Desktop erforderlich, um die Update Ziele zu erfüllen:  

- Test: 0 Tage
- Zuerst: 0 Tage
- Fast 7 Tage
- Allgemein: 21 Tage

### <a name="update-notifications-settings"></a>Aktualisieren von Benachrichtigungseinstellungen

**Standardwert**: false

Die Einstellung "Update Benachrichtigungen ausblenden" ist auf Microsoft Managed Desktop-Geräten auf " **false** " festgelegt, um Benutzern das beste Update zur Verfügung zu stellen, indem Sie [benachrichtigt](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) werden, wenn Updates erforderlich sind.

### <a name="specify-a-location-to-look-for-updates"></a>Angeben eines Orts für die Suche nach Updates

**Standardwert**: monatlicher Enterprise-Kanal

Eine Kombination der **UpdatePath** -und **UpdateChannel** -Richtlinien wird nach Bedarf verwendet, um den Updatezeitplan zu erreichen. Diese Richtlinien werden festgelegt, um sicherzustellen, dass alle Office-Geräte Updates direkt aus dem CDN für den monatlichen Enterprise-Kanal erhalten.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Angeben der Ziel Version von Microsoft 365-apps

Die Ziel Versionsrichtlinie wird manchmal von Microsoft Managed Desktop verwendet, um eine bestimmte Version von Office zurückzusetzen oder zu fixieren. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ausblenden der Option zum Aktivieren oder Deaktivieren von automatischen Office-Updates

**Standardwert**: aktiviert

Diese Einstellung ist für Microsoft Managed Desktop erforderlich, um die Update Ziele für Microsoft 365-Anwendungen zu erfüllen. 

### <a name="first-run-settings"></a>Einstellungen für die erste Ausführung 

Es gibt verschiedene Einstellungen, die sich auf das Verhalten auswirken, wenn Office erstmalig ausgeführt wird.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Akzeptieren der Lizenzbedingungen im Namen des Endbenutzers

**Standardwert**: deaktiviert

Wenn ein Benutzer eine Microsoft 365-App zum ersten Mal öffnet, werden diese aufgefordert, die Lizenzbedingungen zu akzeptieren. Wenn Sie die Lizenzbedingungen im Namen Ihrer Benutzer akzeptieren möchten, müssen Sie eine Dienstanforderung beim Microsoft Managed Desktop Operations-Team einreichen, in der Sie gefragt werden, ob diese Einstellung aktiviert werden soll. 

### <a name="suppress-outlook-mobile-check-box"></a>Outlook Mobile-Kontrollkästchen unterdrücken

**Standardwert**: deaktiviert

Wenn ein Benutzer Outlook zum ersten Mal öffnet, werden diese aufgefordert, Outlook Mobile zu installieren. Wenn Sie den Benutzern das Kontrollkästchen nicht anzeigen möchten, müssen Sie im Microsoft Managed Desktop Operations-Team eine Dienstanforderung einreichen, in der Sie gefragt werden, ob diese Einstellung für Ihre Geräte aktiviert werden soll. 

## <a name="other-settings"></a>Weitere Einstellungen

Es gibt andere Microsoft 365-App-Einstellungen, die von Microsoft Managed Desktop optional in Ihrem Auftrag konfiguriert werden können. 

### <a name="disable-personal-onedrive"></a>Deaktivieren der persönlichen OneDrive

**Standardwert**: deaktiviert

Einige Organisationen befassen sich damit, dass Benutzer auf Ihren Geräten Zugriff auf geschäftliche und persönliche Dateien haben. Sie können eine Dienstanforderung mit dem Microsoft Managed Desktop Operations-Team einreichen, in dem Sie gefragt werden, ob diese Einstellung aktiviert werden soll. 

## <a name="settings-you-manage"></a>Einstellungen, die Sie verwalten

Es gibt viele andere Richtlinien, die von Microsoft Managed Desktop noch nicht als Bestandteil unseres Diensts festgelegt wurden. Sie können diese mithilfe von Microsoft InTune konfigurieren, das den [Office-Cloud-Richtlinien](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Dienst verwendet. Gehen Sie dazu wie folgt vor:

1.  Melden Sie sich beim Microsoft Endpoint Manager Admin Center an.
2.  Auswählen **von apps > Richtlinien für Office-Apps > erstellen**
3.  Führen Sie auf der Seite **Richtlinienkonfiguration erstellen** die folgenden Aktionen aus:
    - Geben Sie einen Namen ein.
    - Geben Sie eine Beschreibung an (optional).
    - Wählen Sie unter **Zuweisungen**aus, ob diese Richtlinie für alle Benutzer von Microsoft 365 apps for Enterprise gilt oder nur für Benutzer, die anonym mit Office für das Internet auf Dokumente zugreifen.
    - Wählen Sie die Aad-basierte Sicherheitsgruppe aus, die der Richtlinienkonfiguration zugewiesen ist. Jede Richtlinienkonfiguration kann nur einer Gruppe zugewiesen werden, und jeder Gruppe kann nur eine Richtlinienkonfiguration zugewiesen werden.
    - Konfigurieren Sie die Richtlinieneinstellungen, die in die Richtlinienkonfiguration eingeschlossen werden sollen. Sie können nach dem Namen der Richtlinieneinstellung suchen, um die Richtlinieneinstellung zu finden, die Sie konfigurieren möchten. Sie können auch nach der Anwendung filtern, ob die Richtlinie eine empfohlene Sicherheitsbasis ist und ob die Richtlinie konfiguriert wurde. Die Spalte Platform gibt an, ob die Richtlinie auf Microsoft 365-Apps für Enterprise für Windows-Geräte, Office für das Internet oder alle angewendet wird.
4.  Nachdem Sie Ihre Auswahl getroffen haben, wählen Sie **Erstellen**aus.

> [!NOTE]
> Office-Konfigurationsrichtlinien unterstützen nur die benutzerbasierte Bereitstellung
