---
title: Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust) (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 'Microsoft 365 Endpunkt-DLP erweitert die Überwachung von Dateiaktivitäten sowie schützende Maßnahmen für diese Dateien auf Endpunkte. Die Dateien werden in den Microsoft 365 Compliance-Lösungen angezeigt. '
ms.openlocfilehash: 5dfe8fae1e000b97d7c2a17d3d7582fd1b24934e
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199983"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a>Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust) (Vorschau)

Sie können Microsoft 365-DLP (Data Loss Prevention, Verhinderung von Datenverlust) verwenden, um die Aktionen zu überwachen, die an Elementen ausgeführt werden, die Sie als vertraulich eingestuft haben, und um die unbeabsichtigte Freigabe dieser Elemente zu verhindern. Weitere Informationen zu DLP finden Sie unter [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md).

**Verhinderung von Datenverlust am Endpunkt** (Endpunkt-DLP) erweitert die Aktivitätsüberwachung und die Schutzfunktionen von DLP auf sensible Elemente auf Windows 10-Geräten. Sobald Geräte in die Geräteverwaltung eingebunden wurden, werden die Informationen zu den Aktionen, die Benutzer mit und an vertraulichen Elementen ausführen, im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt, und Sie können Schutzmaßnahmen für diese Elemente über [DLP-Richtlinien](create-test-tune-dlp-policy.md) erzwingen.

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Endpunktaktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können

Mit Microsoft Endpunkt-DLP können Sie die folgenden Aktivitätstypen überwachen und verwalten, die von Benutzern mit und an vertraulichen Elementen auf Windows 10-Geräten ausgeführt werden. Hierzu zählen Folgende:


|Aktivität am Element |überwachbar/einschränkbar  |
|---------|---------|
|erstellt    | überwachbar      |
|umbenannt    |  überwachbar       |
|auf Wechselmedium kopiert oder erstellt     |     überwachbar und einschränkbar|
|in Netzwerkfreigabe kopiert, z. B. \\my-server\fileshare   |     überwachbar und einschränkbar    |
|gedruckt |    überwachbar und einschränkbar       |
|über Chromium Edge in die Cloud kopiert    |   überwachbar und einschränkbar        |
|Zugriff über nicht zulässige Apps und Browser    |  überwachbar und einschränkbar       |

## <a name="whats-different-in-endpoint-dlp"></a>Was ist bei Endpunkt-DLP anders?

Es gibt ein paar zusätzliche Konzepte, die Sie kennen sollten, bevor Sie sich mit Endpunkt-DLP befassen.

### <a name="enabling-device-management"></a>Aktivieren der Geräteverwaltung

Bei der Geräteverwaltung handelt es sich um die Funktionalität, die das Erfassen von Telemetriedaten von Geräten ermöglicht und sie in Microsoft 365-Compliance-Lösungen wie Endpunkt-DLP und [Insider-Risikomanagement](insider-risk-management.md) überträgt. Sie müssen alle Geräte, die Sie als Speicherorte in DLP-Richtlinien verwenden möchten, einbinden.

![Aktivieren der Geräteverwaltung](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

Onboarding und Offboarding werden über Skripts verarbeitet, die Sie über das Center zur Geräteverwaltung herunterladen können. Im Center sind benutzerdefinierte Skripts für jede der folgenden Bereitstellungsmethoden verfügbar:

- lokales Skript (bis zu 10 Computer)
- Gruppenrichtlinie
- System Center Konfigurationsmanager (Version 1610 oder höher)
- Verwaltung mobiler Geräte/Microsoft Intune
- VDI-Onboarding-Skripts für nicht persistente Computer

![Seite für das Geräte-Onboarding](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Wenden Sie für das Geräte-Onboarding die unter [Erste Schritte mit Microsoft 365 Endpunkt-DLP-](endpoint-dlp-getting-started.md) beschriebene Vorgehensweise an.

Wenn das Geräte-Onboarding über [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/) erfolgt ist, werden diese Geräte automatisch in der Liste der Geräte angezeigt.

![Liste der verwalteten Geräte](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Anzeigen von Endpunkt-DLP-Daten

 Endpunkt-DLP überwacht Aktivitäten basierend auf dem MIME-Typ, sodass sie auch dann erfasst werden, wenn die Dateierweiterung geändert wurde. In der öffentlichen Vorschau wird Folgendes überwacht:

- Word-Dateien
- PowerPoint-Dateien
- Excel-Dateien
- PDF-Dateien
- CSV-Dateien
- TSV-Dateien
- c-Dateien
- Klassendateien
- CPP-Dateien
- CS-Dateien
- H-Dateien
- Java-Dateien

> [!NOTE]
> TXT- und Quellcodedateien werden standardmäßig nicht überwacht. DLP wertet sie anhand der angewendeten Richtlinien aus, anschließend werden Benutzeraktionen entsprechend überwacht oder blockiert.

Nach dem Onboarding eines Geräts werden Informationen zu überwachten Aktivitäten an den Aktivitäten-Explorer gesendet, noch bevor Sie DLP-Richtlinien konfigurieren und bereitstellen, die Geräte als Speicherort verwenden.

![Endpunkt-DLP-Ereignisse im Aktivitäten-Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

Endpunkt-DLP erfasst umfassende Informationen zu überwachten Aktivitäten.

Wenn eine Datei beispielsweise auf einen USB-Wechseldatenträger kopiert wird, werden die folgenden Attribute in den Aktivitätsdetails angezeigt:

- Aktivitätstyp
- Client-IP
- Zieldateipfad
- Ereignis-Zeitstempel
- Dateiname
- Benutzer
- Dateierweiterung
- Dateigröße
- Typ vertraulicher Information (sofern zutreffend)
- SHA1-Wert
- SHA256-Wert
- Vorheriger Dateiname
- Speicherort
- übergeordnetes Element
- Dateipfad
- Art des Quellspeicherorts
- Plattform
- Gerätename
- Art des Zielspeicherorts
- Anwendung, über die die Kopie erstellt wurde
- MDATP-Geräte-ID (sofern zutreffend)
- Hersteller des Wechselmediums
- Modell des Wechselmediums
- Seriennummer des Wechselmediums

![Attribute der Aktivität "nach USB kopieren"](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>Nächste Schritte

Jetzt, da Sie die Basics zu Endpunkt-DLP kennen, sind die nächsten Schritte folgende:

1) [Erste Schritte mit Microsoft Endpunkt-DLP (Vorschau)](endpoint-dlp-getting-started.md)
2) [Nutzung von Microsoft Endpunkt-DLP (Vorschau)](endpoint-dlp-using.md)

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit Microsoft Endpunkt-DLP (Vorschau)](endpoint-dlp-getting-started.md)
- [Nutzung von Microsoft Endpunkt-DLP (Vorschau)](endpoint-dlp-using.md)
- [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)
- [Insider-Risikomanagement](insider-risk-management.md)