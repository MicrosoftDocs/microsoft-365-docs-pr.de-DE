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
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840349"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

## <a name="initial-deployment"></a>Erstbereitstellung

Microsoft Managed Desktop stellt sicher, dass Microsoft 365 Apps for Enterprise (64-Bit) als Teil des Images auf allen [Programmgeräten installiert wird.](../service-description/device-list.md) Alle der folgenden Anwendungen sollten auf dem Gerät vorhanden sein, wenn es zugestellt wird:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Zugriff
- Skype for Business
- OneNote

Dieser Ansatz minimiert die Auswirkungen auf das Netzwerk und stellt sicher, dass Benutzer produktiv sein können, sobald sie ihr Gerät erhalten. Anschließend stellen wir weitere Richtlinien für verwaltete Geräte zum Einrichten der Anwendungen für die Verwendung zur Verfügung.

> [!NOTE]
> Microsoft Teams wird separat von Microsoft 365 Apps for Enterprise bereitgestellt und ist nicht im Basisimage enthalten. 

### <a name="available-deployment-to-users"></a>Verfügbare Bereitstellung für Benutzer

Wenn ein Benutzer aus irgendeinem Grund nicht über Microsoft 365-Apps auf seinem Gerät verfügt, können Sie ein Paket verwenden, um das Gerät in den erwarteten Zustand zurückzukehren. Fügen Sie den Benutzer der **Gruppe "Modern Workplace-Office-Office365_Install"** hinzu, und die Apps werden ihnen im Unternehmensportal zur Verfügung stehen.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for Enterprise (32-Bit)

Microsoft Managed Desktop unterstützt die Bereitstellung der 32-Bit-Version von M365 Apps for Enterprise nicht.

## <a name="updates-to-microsoft-365-apps"></a>Updates für Microsoft 365-Apps

Microsoft 365-Apps werden im monatlichen Unternehmenskanal [aktualisiert.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) Diese Vorgehensweise bietet Ihren Benutzern jeden Monat neue Office-Features, aber sie erhalten nur ein Update pro Monat nach einem vorhersagbaren Veröffentlichungszeitplan. Updates werden am zweiten Dienstag des Monats veröffentlicht. Diese Updates können Feature-, Sicherheits- und Qualitätsupdates enthalten. Diese Updates erfolgen automatisch und werden direkt aus dem Office CDN für diesen bestimmten Kanal gezogen.

Microsoft Managed Desktop staffelt jede Version, um potenzielle Probleme in Ihrer Umgebung zu identifizieren. Wir schließen das Rollout 28 Tage nach der Veröffentlichung der Microsoft 365-App-Produktgruppe ab. Microsoft Managed Desktop plant Aktualisierungsversionen für verschiedene Gruppen, um wie folgt Zeit für Validierung und Tests zu lassen: 

- Test: Null Tage
- First: zero days
- Schnell: 7 Tage
- Breit: 21 Tage

Microsoft Managed Desktop legt einen Stichtag von sieben [Tagen für Updates für](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) Geräte fest. Sobald das Update verfügbar ist, muss es innerhalb von sieben Tagen installiert werden. Benutzer [werden](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) benachrichtigt, dass Updates an mehreren Stellen erforderlich sind: in der Anwendung, in der Taskleiste 12 Stunden vor Ablauf des Stichtag, und sie erhalten eine 15-minütige Warnung vor dem Stichtag. Alle Microsoft 365-Apps müssen geschlossen werden, damit das Update abgeschlossen ist.

### <a name="pausing-or-rolling-back-an-update"></a>Anhalten oder Rollback eines Updates

Wenn Sie das Microsoft 365-App-Update aus irgendeinem [](../working-with-managed-desktop/admin-support.md) Grund anhalten oder ein Rollback dafür starten müssen, senden Sie eine Administratorsupportanfrage über das Microsoft Managed Desktop-Portal.

Während einer Veröffentlichung überwacht Microsoft Managed Desktop die Fehlerraten aller Microsoft 365-Apps. Wenn wir einen erheblichen Qualitätsunterschied zwischen der neuen Version und ihrem Vorgänger erkennen, wenden wir uns möglicherweise über das Microsoft Managed Desktop Admin Portal an Sie. Je nach Schweregrad fragen wir Sie entweder, ob Sie die Veröffentlichung anhalten oder Sie darüber informieren möchten, dass wir Maßnahmen ergriffen haben, um ein Problem zu beheben. 

### <a name="delivery-optimization"></a>Übermittlungsoptimierung

Die Übermittlungsoptimierung ist eine Peer-zu-Peer-Verteilungstechnologie, die in Windows 10 verfügbar ist. Sie ermöglicht Geräten das Freigeben von Inhalten, z. B. Updates, die die Geräte über das Internet von Microsoft heruntergeladen haben. Die Verwendung kann dazu beitragen, die Netzwerkbandbreite zu reduzieren, da ein Gerät Teile des Updates von einem anderen Gerät im lokalen Netzwerk erhalten kann, anstatt das Update vollständig von Microsoft herunterladen zu müssen.

[Die Übermittlungsoptimierung](https://docs.microsoft.com/deployoffice/delivery-optimization) ist auf Geräten mit der Windows 10 Enterprise- oder Windows 10 Education-Edition standardmäßig aktiviert. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verwaltete Einstellungen

Microsoft verwaltet einige Einstellungen als Teil des Diensts. Microsoft Managed Desktop verwaltet keine Office-Sicherheitsgrundwerte, Aber Sie können diese selbst festlegen, indem Sie die Anweisungen im Abschnitt "Einstellungen, die [Sie verwalten"](#settings-you-manage) verwenden.

### <a name="update-settings"></a>Einstellungen aktualisieren

Microsoft Managed Desktop verwaltet alle [Updateeinstellungen](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) für verwaltete Geräte, und Sie sollten diese Einstellungen ändern.

### <a name="set-updates-to-occur-automatically"></a>Festlegen der automatischen Durchführung von Updates

**Standardwert:** Aktiviert

Diese Richtlinie wird konfiguriert, um sicherzustellen, dass alle Office-Geräte aus der Cloud auf dem neuesten Stand gehalten werden können. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Festlegen eines Stichtags, an dem Updates angewendet werden müssen

**Standardwert:** 7 Tage

Die **Richtlinie "UpdateDeadline"** wird verwendet, um die Kulanzfrist zu konfigurieren, die Benutzer haben, bevor ein Update auf dem Gerät erzwungen wird. Diese Fristrichtlinie löst außerdem Benachrichtigungen [an](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) den Benutzer aus, um den Benutzer über die auf dem Gerät erforderlichen Änderungen zu informieren.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Zurückfristen von Updates auf einem Gerät für einen Bestimmten Zeitraum

Diese Richtlinie wird für jede Updateverwaltungsgerätegruppe unterschiedlich konfiguriert und ist für Microsoft Managed Desktop erforderlich, um die Updateziele zu erreichen:  

- Test: Null Tage
- First: zero days
- Fast 7 Tage
- Breit: 21 Tage

### <a name="update-notifications-settings"></a>Aktualisieren von Benachrichtigungseinstellungen

**Standardwert:** False

Die Einstellung "Updatebenachrichtigungen ausblenden" ist auf Microsoft Managed Desktop-Geräten auf [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) **"False"** festgelegt, um benutzern die beste Updateerfahrung zu bieten, indem sie benachrichtigt werden, wenn Updates erforderlich sind.

### <a name="specify-a-location-to-look-for-updates"></a>Angeben eines Orts für die Suche nach Updates

**Standardwert:** Monatlicher Unternehmenskanal

Bei Bedarf wird eine Kombination **der UpdatePath-** und **UpdateChannel-Richtlinien** verwendet, um den Updatezeitplan zu erreichen. Diese Richtlinien werden festgelegt, um sicherzustellen, dass alle Office-Geräte Updates direkt aus dem CDN für den monatlichen Unternehmenskanal erhalten.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Angeben der Zielversion von Microsoft 365-Apps

Die Zielversionsrichtlinie wird manchmal von Microsoft Managed Desktop verwendet, um ein Rollback oder Anheften einer bestimmten Version von Office zu erstellen. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ausblenden der Option zum Aktivieren oder Deaktivieren automatischer Updates für Office

**Standardwert:** Aktiviert

Diese Einstellung ist erforderlich, damit Microsoft Managed Desktop seine Updateziele für Microsoft 365-Anwendungen erfüllen kann. 

### <a name="first-run-settings"></a>Einstellungen für die erste Ausführung 

Es gibt mehrere Einstellungen, die sich auf das Verhalten beim ersten Ausführen von Office auswirken.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Akzeptieren Sie die Lizenzbedingungen im Namen des Endbenutzers.

**Standardwert:** Deaktiviert

Wenn ein Benutzer eine Microsoft 365-App zum ersten Mal öffnet, wird er aufgefordert, die Lizenzbedingungen zu akzeptieren. Wenn Sie die Lizenzbedingungen im Namen Ihrer Benutzer akzeptieren möchten, senden Sie eine Serviceanfrage beim Microsoft Managed Desktop Operations-Team, in der Sie aufgefordert werden, diese Einstellung zu aktivieren. 

### <a name="suppress-outlook-mobile-check-box"></a>Unterdrücken des mobilen Kontrollkästchens für Outlook

**Standardwert:** Deaktiviert

Wenn ein Benutzer Outlook zum ersten Mal öffnet, wird er aufgefordert, Outlook Mobile zu installieren. Wenn Sie nicht möchten, dass das Kontrollkästchen für Ihre Benutzer angezeigt wird, senden Sie eine Serviceanfrage beim Microsoft Managed Desktop Operations-Team, in der Sie aufgefordert werden, diese Einstellung für Ihre Geräte zu aktivieren. 

## <a name="other-settings"></a>Weitere Einstellungen

Es gibt weitere Microsoft 365-App-Einstellungen, die Microsoft Managed Desktop optional in Ihrem Auftrag konfigurieren kann. 

### <a name="disable-personal-onedrive"></a>Deaktivieren von Personal OneDrive

**Standardwert:** Deaktiviert

Einige Organisationen befürchten, dass Benutzer sowohl auf Unternehmens- als auch auf persönliche Dateien auf ihren Geräten zugreifen können. Sie können eine Serviceanfrage beim Microsoft Managed Desktop Operations-Team stellen, in der Sie aufgefordert werden, diese Einstellung zu aktivieren. 

## <a name="settings-you-manage"></a>Von Ihnen verwaltete Einstellungen

Es gibt viele andere Richtlinien, die Microsoft Managed Desktop noch nicht als Teil unseres Diensts festgelegt hat. Sie können diese Richtlinien mithilfe von Microsoft Intune konfigurieren, das den [Office-Cloud-Richtliniendienst](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) verwendet. Führen Sie zum Festlegen dieser Richtlinien die folgenden Schritte aus:

1.  Melden Sie sich beim Microsoft Endpoint Manager Admin Center an.
2.  Auswählen **von > von Apps für Office-Apps, die > werden**
3.  Gehen Sie **auf der Seite "Richtlinienkonfiguration** erstellen" wie folgt vor:
    - Geben Sie einen Namen ein.
    - Geben Sie eine Beschreibung an (optional).
    - Wählen **Sie** in Zuweisungen aus, ob diese Richtlinie für alle Benutzer von Microsoft 365 Apps for Enterprise oder nur für Benutzer gilt, die anonym über Office für das Web auf Dokumente zugreifen.
    - Wählen Sie die AAD-basierte Sicherheitsgruppe aus, die der Richtlinienkonfiguration zugewiesen ist. Jede Richtlinienkonfiguration kann nur einer Gruppe zugewiesen werden, und jeder Gruppe kann nur eine Richtlinienkonfiguration zugewiesen werden.
    - Konfigurieren Sie die Richtlinieneinstellungen, die in die Richtlinienkonfiguration aufgenommen werden sollen. Sie können nach dem Namen der Richtlinieneinstellung suchen, um die Richtlinieneinstellung zu finden, die Sie konfigurieren möchten. Sie können auch nach der Anwendung filtern, ob die Richtlinie eine empfohlene Sicherheitsbasis ist und ob die Richtlinie konfiguriert wurde. Die Plattformspalte gibt an, ob die Richtlinie auf Microsoft 365 Apps for Enterprise für Windows-Geräte, Office für das Web oder alle angewendet wird.
4.  Nachdem Sie Ihre Auswahl getroffen haben, wählen Sie **"Erstellen" aus.**

> [!NOTE]
> Office-Konfigurationsrichtlinien unterstützen nur die benutzerbasierte Bereitstellung
