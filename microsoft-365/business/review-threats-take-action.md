---
title: Überprüfen erkannter Bedrohungen und ergreifen von Aktionen
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Hier erfahren Sie, wie Sie von Microsoft Defender Antivirus auf Ihren Windows 10-Geräten erkannte Bedrohungen überprüfen und verwalten können.
ms.openlocfilehash: 41465cb81850415a7b490b6af7f0ec66c724ca68
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588517"
---
# <a name="review-detected-threats-and-take-action"></a>Überprüfen erkannter Bedrohungen und ergreifen von Aktionen

Sobald eine bösartige Datei oder Software erkannt wird, blockiert Microsoft Defender Antivirus diese und verhindert die Ausführung. Und wenn der Cloud-geschützte Schutz aktiviert ist, werden dem Antivirus-und Antischadsoftware-Modul neu erkannte Bedrohungen hinzugefügt, damit auch Ihre anderen Geräte und Benutzer geschützt sind.

Microsoft Defender Antivirus erkennt und schützt vor den folgenden Arten von Bedrohungen:

- Viren, Schadsoftware und webbasierte Bedrohungen auf Geräten
- Phishing-Versuche
- Datendiebstahl Versuche

Als IT-Experte/Administrator können Sie Informationen zu Bedrohungserkennungen auf [Windows 10-Geräten anzeigen,](/mem/intune/enrollment/device-enrollment) die in InTune im Microsoft 365 Admin Center registriert sind. Es werden Zusammenfassungsinformationen angezeigt, beispielsweise:

- Wie viele Geräte benötigen Virenschutz
- Anzahl der Geräte, die nicht mit Sicherheitsrichtlinien übereinstimmen
- Wie viele Bedrohungen derzeit aktiv, gemildert oder behoben werden

Sie haben mehrere Möglichkeiten, um bestimmte Informationen zu Bedrohungserkennungen und-Geräten anzuzeigen:

- Seite " **aktive Geräte** " im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>. Weitere Informationen finden Sie unter [Verwalten von Bedrohungserkennungen auf der Seite aktive Geräte](#manage-threat-detections-on-the-active-devices-page) in diesem Artikel.
- Die Seite " **aktive Bedrohungen** " im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>. Weitere Informationen finden Sie unter [Manage Threat Detections on the Active Threats Page](#manage-threat-detections-on-the-active-threats-page) in this article.
- Die **Antivirus** -Seite in <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Microsoft Endpoint Manager</a>. Weitere Informationen finden Sie unter [Verwalten von Bedrohungserkennungen in Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) in diesem Artikel.

Weitere Informationen finden Sie unter [Threats Detected by Microsoft Defender Antivirus](threats-detected-defender-av.md).

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Verwalten von Bedrohungserkennungen auf der Seite " **aktive Geräte** "

Das folgende Verfahren gilt für Kunden mit Microsoft 365 Business Premium.

1. Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> , und melden Sie sich an.

2. Wählen Sie auf der Navigationsseite **Geräte**  >  **aktive Geräte** aus. Es wird eine Liste der aktiven Geräte und Details angezeigt, beispielsweise Schutzstatus, Antivirenschutz (AV)-Schutzstatus und die Anzahl der erkannten aktiven Bedrohungen.

3. Wählen Sie ein Gerät aus, um weitere Details zu diesem Gerät und den verfügbaren Aktionen anzuzeigen. Ein Flyout wird mit Empfehlungen und verfügbaren Aktionen wie **Updaterichtlinie**, **Update Antivirus**, **Run Quick Scan**, **Run Full Scan** und mehr geöffnet.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Verwalten von Bedrohungserkennungen auf der Seite " **aktive Bedrohungen** "

Das folgende Verfahren gilt für Kunden mit Microsoft 365 Business Premium. [Windows 10-Geräte müssen gesichert](/microsoft-365/business/secure-win-10-pcs) und [in InTune registriert](/mem/intune/enrollment/windows-enrollment-methods)sein.

> [!NOTE]
> Auf der Seite **Microsoft Defender Antivirus** -Karte und **aktive Bedrohungen** wird in Phasen ein Rollback ausgeführt, sodass Sie möglicherweise keinen unmittelbaren Zugriff darauf haben.

1. Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> , und melden Sie sich an.

2. Wählen Sie auf der Antivirus-Karte von **Microsoft Defender** die Option **aktive Bedrohungen anzeigen** aus. (Wählen Sie alternativ im Navigationsbereich **Integrität**  >  aus. **Bedrohungen & Antivirus**.)

3. Wählen Sie auf der Seite **aktive Bedrohungen** eine erkannte Bedrohung aus, um mehr darüber zu erfahren. Ein Flyout mit Details zu dieser Bedrohung, einschließlich der betroffenen Geräte, wird geöffnet.

4. Wählen Sie im Flyout ein Gerät aus, um die verfügbaren Aktionen anzuzeigen, wie **Updaterichtlinie**, **Antivirus aktualisieren**, **Schnellscan ausführen** und vieles mehr.

## <a name="actions-you-can-take"></a>Aktionen, die Sie ausführen können

Wenn Sie Details zu bestimmten Bedrohungen oder Geräten anzeigen, sehen Sie Empfehlungen und eine oder mehrere Aktionen, die Sie ausführen können. In der folgenden Tabelle werden Aktionen beschrieben, die möglicherweise angezeigt werden.<br><br>

| Aktion | Beschreibung |
|--|--|
| Konfigurieren des Schutzes | Ihre Richtlinien für den Schutz von Bedrohungen müssen konfiguriert werden. Wählen Sie den Link aus, um zur Richtlinien Konfigurationsseite zu wechseln.<br><br>Benötigen Sie Hilfe? Weitere Informationen finden Sie unter [Manage Device Security with Endpoint Security Policies in Microsoft InTune](/mem/intune/protect/endpoint-security-policy). |
| Richtlinie aktualisieren | Ihre Antivirus-und Echtzeitschutzrichtlinien müssen aktualisiert oder konfiguriert werden. Wählen Sie den Link aus, um zur Seite Richtlinienkonfiguration zu wechseln.<br><br>Benötigen Sie Hilfe? Weitere Informationen finden Sie unter [Manage Device Security with Endpoint Security Policies in Microsoft InTune](/mem/intune/protect/endpoint-security-policy). |
| Ausführen des Schnellscans | Startet eine schnelle Antivirus-Überprüfung auf dem Gerät mit dem Schwerpunkt auf gemeinsame Orte, an denen Schadsoftware registriert werden kann, beispielsweise Registrierungsschlüssel und bekannte Windows-Startordner. |
| Vollständige Überprüfung ausführen | Startet eine vollständige Antivirus-Überprüfung auf dem Gerät mit Schwerpunkt auf gemeinsame Orte, an denen Schadsoftware registriert werden kann, und einschließlich aller Dateien und Ordner auf dem Gerät. Ergebnisse werden an [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)gesendet. |
| Antivirus aktualisieren | Erfordert, dass das Gerät [Sicherheits-Intelligence-Updates](https://go.microsoft.com/fwlink/?linkid=2149926) für Antivirus-und Antischadsoftware-Schutz erhält. |
| Gerät neu starten | Erzwingt, dass ein Windows 10-Gerät innerhalb von fünf Minuten neu gestartet wird.<br><br>**Wichtig:** Der Gerätebesitzer oder-Benutzer wird nicht automatisch über den Neustart informiert und kann nicht gespeicherte Arbeit verlieren. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Verwalten von Bedrohungserkennungen in Microsoft Endpoint Manager

Sie können den Microsoft Endpoint Manager zum Verwalten von Bedrohungserkennungen verwenden. Windows 10-Geräte müssen [in InTune registriert](/mem/intune/enrollment/windows-enrollment-methods) sein (Teil von Microsoft Endpoint Manager).

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> , und melden Sie sich an.

2. Wählen Sie im Navigationsbereich die Option **Endpunktsicherheit** aus.

3. Wählen Sie unter **Verwalten** die Option **Antivirus** aus. Es werden mehrere Registerkarten wie **Zusammenfassung**, fehlerhafte **Windows 10-Endpunkte** und **Windows 10 erkannte Schadsoftware** angezeigt.

4. Überprüfen Sie die Informationen auf den verfügbaren Registerkarten, und führen Sie dann alle erforderlichen Aktionen aus.

Nehmen wir beispielsweise an, dass die Geräte auf der Registerkarte **Windows 10 erkannte Malware** aufgeführt sind. Wenn Sie ein Gerät auswählen, stehen Ihnen bestimmte Aktionen zur Verfügung, wie **Neustart**, **schnelle Überprüfung**, **vollständige Überprüfung**, **Synchronisierung** oder **Update Signaturen**. Wählen Sie eine Aktion für dieses Gerät aus.

In der folgenden Tabelle werden die Aktionen beschrieben, die in Microsoft Endpoint Manager möglicherweise angezeigt werden.<br><br>

| Aktion | Beschreibung |
|--|--|
| Neustart | Erzwingt, dass ein Windows 10-Gerät innerhalb von fünf Minuten neu gestartet wird.<br><br>**Wichtig:** Der Gerätebesitzer oder-Benutzer wird nicht automatisch über den Neustart informiert und kann nicht gespeicherte Arbeit verlieren. |
| Schnellüberprüfung | Startet eine schnelle Antivirus-Überprüfung auf dem Gerät mit dem Schwerpunkt auf gemeinsame Orte, an denen Schadsoftware registriert werden kann, beispielsweise Registrierungsschlüssel und bekannte Windows-Startordner. Ergebnisse werden an [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)gesendet. |
| Vollständige Überprüfung | Startet eine vollständige Antivirus-Überprüfung auf dem Gerät mit Schwerpunkt auf gemeinsame Orte, an denen Schadsoftware registriert werden kann, und einschließlich aller Dateien und Ordner auf dem Gerät. Ergebnisse werden an [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)gesendet. |
| Synchronisierung | Erfordert ein Gerät zum Einchecken mit InTune (Teil von Microsoft Endpoint Manager). Wenn das Gerät eingecheckt wird, erhält das Gerät alle ausstehenden Aktionen oder Richtlinien, die dem Gerät zugewiesen sind. |
| Aktualisieren von Signaturen | Erfordert, dass das Gerät [Sicherheits-Intelligence-Updates](https://go.microsoft.com/fwlink/?linkid=2149926) für Antivirus-und Antischadsoftware-Schutz erhält. |

> [!TIP]
> Weitere Informationen finden Sie unter [Remote Aktionen für Geräte](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Vorgehensweise zum Übermitteln einer Datei für die Malware Analyse

Wenn Sie eine Datei haben, die ihrer Meinung nach falsch als Schadsoftware klassifiziert wurde, können Sie diese Datei zur Untersuchung von Schadsoftware an Microsoft übermitteln. Benutzer und IT-Administratoren können eine Datei zur Analyse übermitteln. Besuchen Sie [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .
