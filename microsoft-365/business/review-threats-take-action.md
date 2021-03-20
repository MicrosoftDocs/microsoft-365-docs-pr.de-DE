---
title: Untersuchen erkannter Bedrohungen und Ergreifen von Maßnahmen
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
description: Erfahren Sie, wie Sie bedrohungen überprüfen und verwalten, die von Microsoft Defender Antivirus auf Ihren Windows 10-Geräten erkannt wurden.
ms.openlocfilehash: 15e99fb75e4a3ac1af842ca7d0b900e02cbc6bd4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912786"
---
# <a name="review-detected-threats-and-take-action"></a>Untersuchen erkannter Bedrohungen und Ergreifen von Maßnahmen

Sobald eine schädliche Datei oder Software erkannt wird, blockiert Microsoft Defender Antivirus sie und verhindert, dass sie ausgeführt wird. Und wenn der in der Cloud zugestellte Schutz aktiviert ist, werden dem Antivirus- und Antischantischungsmodul neu erkannte Bedrohungen hinzugefügt, sodass auch Ihre anderen Geräte und Benutzer geschützt sind.

Microsoft Defender Antivirus erkennt und schützt vor den folgenden Arten von Bedrohungen:

- Viren, Schadsoftware und webbasierte Bedrohungen auf Geräten
- Phishingversuche
- Datendiebstahlversuche

Als IT-Profi/Administrator können Sie Informationen zu Bedrohungserkennungen auf [Windows 10-Geräten](/mem/intune/enrollment/device-enrollment) anzeigen, die in Intune im Microsoft 365 Admin Center registriert sind. Es werden Zusammenfassungsinformationen angezeigt, z. B.:

- Wie viele Geräte Antivirusschutz benötigen
- Wie viele Geräte nicht mit Sicherheitsrichtlinien kompatibel sind
- Wie viele Bedrohungen derzeit aktiv, gemildert oder gelöst sind

Sie haben mehrere Optionen, um bestimmte Informationen zu Bedrohungserkennungen und -geräten anzuzeigen:

- Die **Seite Aktive Geräte** im Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365 Admin Center</a>. Weitere Informationen finden Sie unter [Verwalten von Bedrohungserkennungen auf der Seite Aktive](#manage-threat-detections-on-the-active-devices-page) Geräte in diesem Artikel.
- Die **Seite Aktive Bedrohungen** im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>. Weitere Informationen finden Sie unter [Verwalten von Bedrohungserkennungen auf der Seite Aktive](#manage-threat-detections-on-the-active-threats-page) Bedrohungen in diesem Artikel.
- Die **Seite Antivirus** im Microsoft Endpoint <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Manager</a>. Weitere [Informationen finden Sie unter Manage threat detections in Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) in diesem Artikel.

Weitere Informationen finden Sie [unter Bedrohungen, die von Microsoft Defender Antivirus erkannt werden.](threats-detected-defender-av.md)

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Verwalten von Bedrohungserkennungen auf der **Seite Aktive** Geräte

Das folgende Verfahren gilt für Kunden mit Microsoft 365 Business Premium.

1. Wechseln Sie zum Microsoft 365 Admin Center <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> unter, und melden Sie sich an.

2. Wählen Sie auf der Navigationsseite **Geräte**  >  **Aktive Geräte aus.** Es wird eine Liste der aktiven Geräte und Details angezeigt, z. B. Schutzstatus, Antivirusschutzstatus (AV) und anzahl der erkannten aktiven Bedrohungen.

3. Wählen Sie ein Gerät aus, um weitere Details zu diesem Gerät und den verfügbaren Aktionen anzuzeigen. Ein Flyout wird mit Empfehlungen und verfügbaren Aktionen geöffnet, z. B. **Updaterichtlinie,** **Antivirus** **aktualisieren,** Schnellscan **ausführen,** vollständige Überprüfung ausführen und vieles mehr.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Verwalten von Bedrohungserkennungen auf der **Seite Aktive Bedrohungen**

Das folgende Verfahren gilt für Kunden mit Microsoft 365 Business Premium. [Windows 10-Geräte müssen gesichert und](./secure-win-10-pcs.md) in [Intune registriert sein.](/mem/intune/enrollment/windows-enrollment-methods)

> [!NOTE]
> Die **Seite "Microsoft Defender Antivirus-Karte"** und "Aktive Bedrohungen" wird in Phasen ausgeführt, sodass Sie möglicherweise keinen sofortigen Zugriff darauf haben. 

1. Wechseln Sie zum Microsoft 365 Admin Center <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> unter, und melden Sie sich an.

2. Wählen Sie **auf der Microsoft Defender Antivirus-Karte** aktive **Bedrohungen anzeigen aus.** (Alternativ wählen Sie im Navigationsbereich Die Option **Integrität aus.**  >  **Bedrohungen & Antivirus**.)

3. Wählen Sie **auf der** Seite Aktive Bedrohungen eine erkannte Bedrohung aus, um mehr darüber zu erfahren. Ein Flyout wird mit Details zu dieser Bedrohung geöffnet, einschließlich der betroffenen Geräte.

4. Wählen Sie im Flyout ein Gerät zum Anzeigen verfügbarer Aktionen aus, z. B. **Updaterichtlinie,** **Antivirus** aktualisieren, **Schnellscan** ausführen und vieles mehr.

## <a name="actions-you-can-take"></a>Aktionen, die Sie ausführen können

Wenn Sie Details zu bestimmten Bedrohungen oder Geräten anzeigen, werden Empfehlungen und eine oder mehrere Aktionen angezeigt, die Sie ausführen können. In der folgenden Tabelle werden Aktionen beschrieben, die möglicherweise angezeigt werden.<br><br>

| Aktion | Beschreibung |
|--|--|
| Konfigurieren des Schutzes | Ihre Bedrohungsschutzrichtlinien müssen konfiguriert werden. Wählen Sie den Link aus, um zu Ihrer Richtlinienkonfigurationsseite zu wechseln.<br><br>Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Manage device security with endpoint security policies in Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Richtlinie aktualisieren | Ihre Antiviren- und Echtzeitschutzrichtlinien müssen aktualisiert oder konfiguriert werden. Wählen Sie den Link aus, um zur Seite richtlinienkonfiguration zu wechseln.<br><br>Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Manage device security with endpoint security policies in Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Schnellscan ausführen | Startet eine schnelle Antivirenscan auf dem Gerät und konzentriert sich auf häufige Speicherorte, an denen Schadsoftware registriert werden kann, z. B. Registrierungsschlüssel und bekannte Windows-Startordner. |
| Ausführen des vollständigen Scans | Startet eine vollständige Antivirenscan auf dem Gerät, wobei der Schwerpunkt auf allgemeinen Speicherorten liegt, an denen Schadsoftware registriert werden kann, einschließlich aller Dateien und Ordner auf dem Gerät. Die Ergebnisse werden an [Microsoft Endpoint Manager gesendet.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Aktualisieren von Antivirenprogrammen | Erfordert, dass das Gerät [Sicherheitsintelligenzupdates für](https://go.microsoft.com/fwlink/?linkid=2149926) Antivirus- und Antischalwareschutz erhalten muss. |
| Gerät neu starten | Erzwingt einen Neustart eines Windows 10-Geräts innerhalb von fünf Minuten.<br><br>**WICHTIG:** Der Gerätebesitzer oder -benutzer wird nicht automatisch über den Neustart benachrichtigt und kann nicht gespeicherte Arbeit verlieren. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Verwalten von Bedrohungserkennungen in Microsoft Endpoint Manager

Sie können Microsoft Endpoint Manager verwenden, um Bedrohungserkennungen zu verwalten. Windows 10-Geräte müssen [in Intune](/mem/intune/enrollment/windows-enrollment-methods) (Teil von Microsoft Endpoint Manager) registriert werden.

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> unter, und melden Sie sich an.

2. Wählen Sie im Navigationsbereich **Endpunktsicherheit aus.**

3. Wählen **Sie unter Verwalten** die Option Antivirus **aus.** Es werden mehrere Registerkarten angezeigt, z. B. **Zusammenfassung**, **Fehlerhafte Windows 10-Endpunkte** und **windows 10 erkannte Schadsoftware**.

4. Überprüfen Sie die Informationen auf den verfügbaren Registerkarten, und ergreifen Sie dann alle erforderlichen Aktionen.

Nehmen wir beispielsweise an, dass Geräte auf der **Registerkarte Windows 10 erkannte Schadsoftware aufgeführt** sind. Wenn Sie ein Gerät auswählen, sind bestimmte Aktionen verfügbar, z. B. **Neustart,** **Schnellscan,** **Vollständige** Überprüfung, **Synchronisierung** oder **Updatesignaturen.** Wählen Sie eine Aktion für dieses Gerät aus.

In der folgenden Tabelle werden die Aktionen beschrieben, die möglicherweise in Microsoft Endpoint Manager angezeigt werden.<br><br>

| Aktion | Beschreibung |
|--|--|
| Neustart | Erzwingt einen Neustart eines Windows 10-Geräts innerhalb von fünf Minuten.<br><br>**WICHTIG:** Der Gerätebesitzer oder -benutzer wird nicht automatisch über den Neustart benachrichtigt und kann nicht gespeicherte Arbeit verlieren. |
| Schnellscan | Startet eine schnelle Antivirenscan auf dem Gerät und konzentriert sich auf häufige Speicherorte, an denen Schadsoftware registriert werden kann, z. B. Registrierungsschlüssel und bekannte Windows-Startordner. Die Ergebnisse werden an [Microsoft Endpoint Manager gesendet.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Vollständiger Scan | Startet eine vollständige Antivirenscan auf dem Gerät, wobei der Schwerpunkt auf allgemeinen Speicherorten liegt, an denen Schadsoftware registriert werden kann, einschließlich aller Dateien und Ordner auf dem Gerät. Die Ergebnisse werden an [Microsoft Endpoint Manager gesendet.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Synchronisierung | Erfordert, dass ein Gerät mit Intune (Teil von Microsoft Endpoint Manager) einchecken muss. Wenn das Gerät eincheckt, empfängt das Gerät alle ausstehenden Aktionen oder Richtlinien, die dem Gerät zugewiesen sind. |
| Aktualisieren von Signaturen | Erfordert, dass das Gerät [Sicherheitsintelligenzupdates für](https://go.microsoft.com/fwlink/?linkid=2149926) Antivirus- und Antischalwareschutz erhalten muss. |

> [!TIP]
> Weitere Informationen finden Sie unter [Remoteaktionen für Geräte](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Übermitteln einer Datei für die Schadsoftwareanalyse

Wenn Sie eine Datei haben, von der Sie glauben, dass sie als Schadsoftware verpasst oder falsch klassifiziert wurde, können Sie diese Datei zur Schadsoftwareanalyse an Microsoft übermitteln. Benutzer und IT-Administratoren können eine Datei zur Analyse übermitteln. Besuchen [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) Sie .