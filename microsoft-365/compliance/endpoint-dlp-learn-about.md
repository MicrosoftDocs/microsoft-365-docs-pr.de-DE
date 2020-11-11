---
title: Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 Endpunkt-DLP erweitert die Überwachung von Dateiaktivitäten und Schutzmaßnahmen für diese Dateien auf Endpunkte. Dateien werden in den Microsoft 365 Compliance-Lösungen sichtbar gemacht. '
ms.openlocfilehash: 966e201acb8038d85f0d06c0800c9845fd79097e
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984929"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)

Sie können Microsoft 365 Data Loss Prevention (DLP) verwenden, um Ihre Maßnahmen für vertrauliche Objekte zu überwachen und um die unbeabsichtigte gemeinsame Nutzung dieser Objekte zu verhindern. Mehr Informationen zu DLP finden Sie unter [Überblick über DLP](data-loss-prevention-policies.md).

**Verhinderung von Datenverlust** (Endpunkt-DLP) erweitert die Aktivitätsüberwachungs- und Schutzfunktionen von DLP auf vertrauliche Objekte, die sich auf Windows 10-Geräten befinden. Sobald die Geräte in die Microsoft 365 Compliance-Lösungen integriert sind, werden die Informationen darüber, was Benutzer mit vertraulichen Objekten tun, im [Aktivitäts-Explorer](data-classification-activity-explorer.md) sichtbar. Sie können Schutzmaßnahmen für diese Objekte über [DLP-Richtlinien](create-test-tune-dlp-policy.md) durchsetzen.

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Endpunktaktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können

Mit Microsoft Endpunkt-DLP können Sie folgende Arten von Aktivitäten prüfen und verwalten, die Benutzer auf Windows 10-Geräten ausführen. Dazu gehören:


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

### <a name="enabling-device-management"></a>Geräteverwaltung aktivieren

Bei der Geräteverwaltung handelt es sich um die Funktionalität, die das Erfassen von Telemetriedaten von Geräten ermöglicht und sie in Microsoft 365 Compliance-Lösungen wie Endpunkt-DLP und [Insider-Risikomanagement](insider-risk-management.md) überträgt. Sie müssen alle Geräte, die Sie als Speicherorte in DLP-Richtlinien verwenden möchten, einbinden.

> [!div class="mx-imgBorder"]
> ![Geräteverwaltung aktivieren](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

Onboarding und Offboarding werden über Skripte abgewickelt, die Sie vom Geräteverwaltungszentrum herunterladen. Das Zentrum verfügt über benutzerdefinierte Skripte für jede dieser Bereitstellungsmethoden:

- lokales Skript (bis zu 10 Computer)
- Gruppenrichtlinie
- System Center Konfigurationsmanager (Version 1610 oder höher)
- Verwaltung mobiler Geräte/Microsoft Intune
- VDI-Onboarding-Skripts für nicht persistente Computer

> [!div class="mx-imgBorder"]
> ![Seite für das Onboarding eines Geräts](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Wenden Sie für das Onboarding eines Geräts die unter [Erste Schritte mit Microsoft 365 Endpunkt-DLP](endpoint-dlp-getting-started.md) beschriebene Vorgehensweise an.

Wenn das Onboarding eines Geräts über [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/) erfolgt ist, werden diese Geräte automatisch in der Liste der Geräte angezeigt.

> [!div class="mx-imgBorder"]
> ![Liste der verwalteten Geräte](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Endpunkt-DLP-Daten anzeigen

 Endpunkt-DLP Endpunkt-DLP überwacht Aktivitäten auf der Grundlage des MIME-Typs, so dass Aktivitäten auch dann erfasst werden, wenn die Dateierweiterung geändert wird. In der öffentlichen Vorschau folgende Dateien überwacht:

- Word-Dateien
- PowerPoint-Dateien
- Excel-Dateien
- PDF-Dateien
- CSV-Dateien
- TSV-Dateien
- TXT-Dateien
- RTF-Dateien
- C-Dateien
- CLASS-Dateien
- CPP-Dateien
- CS-Dateien
- H-Dateien
- JAVA-Dateien

> [!NOTE]
> Endpunkt-DLP bewertet Dateien der oben genannten Dateitypen anhand der DLP-Richtlinie und wendet die entsprechenden Schutzmaßnahmen an. Alle Dateien, die mit einer DLP-Richtlinie übereinstimmen, werden auf alle unterstützten Aktionen geprüft, auch wenn sie nicht gesperrt sind. Zusätzlich werden alle auf Word-, PowerPoint-, Excel-, PDF- und CSV-Dateien ausgeführte Dateiaktivitäten standardmäßig geprüft, unabhängig davon, ob eine DLP-Richtlinie vorhanden ist oder mit diesen Dateien übereinstimmt.

Nach dem Onboarding eines Geräts werden Informationen zu überwachten Aktivitäten an den Aktivitäten-Explorer gesendet, noch bevor Sie DLP-Richtlinien konfigurieren und bereitstellen, die Geräte als Speicherort verwenden.

> [!div class="mx-imgBorder"]
> ![Endpunkt-DLP-Ereignisse im Aktivitäten-Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

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
- Microsoft Defender für Endpunkt-Geräte-ID (sofern zutreffend)
- Hersteller des Wechselmediums
- Modell des Wechselmediums
- Seriennummer des Wechselmediums

> [!div class="mx-imgBorder"]
> ![Attribute der Aktivität auf USB kopieren](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

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
- [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/)
- [Insider-Risikomanagement](insider-risk-management.md)
