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
description: 'Microsoft 365 Endpunkt-DLP erweitert die Überwachung von Dateiaktivitäten sowie schützende Maßnahmen für diese Dateien auf Endpunkte. Die Dateien werden in den Microsoft 365 Compliance-Lösungen angezeigt. '
ms.openlocfilehash: d5394499b5514e6e0a49f958a62e70cde61ebf44
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279309"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)

Sie können Microsoft 365-DLP (Data Loss Prevention, Verhinderung von Datenverlust) verwenden, um die Aktionen zu überwachen, die an Elementen ausgeführt werden, die Sie als vertraulich eingestuft haben, und um die unbeabsichtigte Freigabe dieser Elemente zu verhindern. Weitere Informationen zu DLP finden Sie unter [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md).

**Verhinderung von Datenverlust am Endpunkt** (Endpunkt-DLP) erweitert die Aktivitätsüberwachung und die Schutzfunktionen von DLP auf sensible Elemente auf Windows 10-Geräten. Sobald Geräte in den Microsoft 365 Compliance-Lösungen eingebunden wurden, werden die Informationen zu den Aktionen, die Benutzer mit und an vertraulichen Elementen ausführen, im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt, und Sie können Schutzmaßnahmen für diese Elemente über [DLP-Richtlinien](create-test-tune-dlp-policy.md) erzwingen.

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Endpunktaktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können

Mit Microsoft Endpunkt-DLP können Sie die folgenden Aktivitätstypen überwachen und verwalten, die von Benutzern mit und an vertraulichen Elementen auf Windows 10-Geräten ausgeführt werden. 

|Aktivität |Beschreibung  | überwachbar/einschränkbar|
|---------|---------|---------|
|In einen Clouddienst hochladen oder über nicht zugelassene Browser zugreifen    | Erkennt, wenn ein Benutzer versucht, ein Element in eine eingeschränkte Dienstdomäne hochzuladen oder über einen Browser auf ein Element zuzugreifen.  Wird ein Browser verwendet, der im DLP als nicht zugelassener Browser aufgeführt ist, wird die Uploadaktivität blockiert, und der Benutzer wird umgeleitet, um Edge Chromium zu verwenden. Edge Chromium kann dann, basierend auf der DLP-Richtlinienkonfiguration, entweder den Upload erlauben oder blockieren oder auf das Element zugreifen.         |überwachbar und einschränkbar|
|In andere App kopieren    |Erkennt, wenn ein Benutzer versucht, Informationen aus einem geschützten Element zu kopieren und in eine andere App, einen Prozess oder ein Element einzufügen. Das Kopieren und Einfügen von Informationen innerhalb derselben App, desselben Prozesses oder desselben Elements wird von dieser Aktivität nicht erkannt.         | überwachbar und einschränkbar|
|Auf USB-Wechseldatenträger kopieren |Erkennt, wenn ein Benutzer versucht, ein Element oder Informationen auf einen Wechseldatenträger oder ein USB-Gerät zu kopieren.         | überwachbar und einschränkbar|
|Auf eine Netzwerkfreigabe kopieren    |Erkennt, wenn ein Benutzer versucht, ein Element auf eine Netzwerkfreigabe oder ein zugeordnetes Netzlaufwerk zu kopieren.         |überwachbar und einschränkbar|
|Dokument drucken    |Erkennt, wenn ein Benutzer versucht, ein geschütztes Element auf einem lokalen oder Netzwerkdrucker zu drucken.| überwachbar und einschränkbar         |
|Element erstellen|Erkennt, wenn ein Benutzer ein Element erstellt.| überwachbar|
|Element umbenennen|Erkennt, wenn ein Benutzer ein Element umbenennt.| überwachbar|

 ## <a name="monitored-files"></a>Überwachte Dateien

Endpunkt-DLP unterstützt die Überwachung dieser Dateitypen:

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
 
Standardmäßig überwacht Endpunkt-DLP die Aktivitäten für diese Dateitypen, auch wenn keine Richtlinienübereinstimmung vorliegt. Wenn Sie nur Daten aus Richtlinienübereinstimmungen überwachen möchten, können Sie **Dateiaktivität für Geräte immer überwachen** in den globalen Endpunkt-DLP-Einstellungen deaktivieren. Unabhängig davon werden Aktivitäten für sämtliche Word-, PowerPoint-, Excel-, PDF- und CSV-Dateien immer überwacht.

Verhinderung von Datenverlust am Endpunkt (Endpunkt-DLP) überwacht Aktivitäten basierend auf dem MIME-Typ, sodass sie auch dann erfasst werden, wenn die Dateierweiterung geändert wurde. 

## <a name="whats-different-in-endpoint-dlp"></a>Was ist bei Endpunkt-DLP anders?

Es gibt ein paar zusätzliche Konzepte, die Sie kennen sollten, bevor Sie sich mit Endpunkt-DLP befassen.

### <a name="enabling-device-management"></a>Aktivieren der Geräteverwaltung

Bei der Geräteverwaltung handelt es sich um die Funktionalität, die das Erfassen von Telemetriedaten von Geräten ermöglicht und sie in Microsoft 365-Compliance-Lösungen wie Endpunkt-DLP und [Insider-Risikomanagement](insider-risk-management.md) überträgt. Sie müssen alle Geräte, die Sie als Speicherorte in DLP-Richtlinien verwenden möchten, einbinden.

> [!div class="mx-imgBorder"]
> ![Aktivieren der Geräteverwaltung](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

Onboarding und Offboarding werden über Skripts verarbeitet, die Sie über das Center zur Geräteverwaltung herunterladen können. Im Center sind benutzerdefinierte Skripts für jede der folgenden Bereitstellungsmethoden verfügbar:

- lokales Skript (bis zu 10 Computer)
- Gruppenrichtlinie
- System Center Konfigurationsmanager (Version 1610 oder höher)
- Verwaltung mobiler Geräte/Microsoft Intune
- VDI-Onboarding-Skripts für nicht persistente Computer

> [!div class="mx-imgBorder"]
> ![Seite für das Onboarding eines Geräts](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Wenden Sie für das Geräte-Onboarding die unter [Erste Schritte mit Microsoft 365 Endpunkt-DLP-](endpoint-dlp-getting-started.md) beschriebene Vorgehensweise an.

Wenn das Onboarding eines Geräts über [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/) erfolgt ist, werden diese Geräte automatisch in der Liste der Geräte angezeigt.

> [!div class="mx-imgBorder"]
> ![Liste der verwalteten Geräte](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Anzeigen von Endpunkt-DLP-Daten



Sie können Benachrichtigungen anzeigen, die mit auf Endpunktgeräten durchgesetzten DLP-Richtlinien verbunden sind, indem Sie zum [Verwaltungsdasboard „DLP-Benachrichtigungen“](dlp-configure-view-alerts-policies.md) wechseln.

![Warninformationen](../media/Alert-info-1.png)

Sie können ebenfalls Details des zugehörigen Ereignisses mit umfangreichen Metadaten im gleichen Dashboard anzeigen.

![Ereignisinformationen](../media/Event-info-1.png)

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

1) [Erste Schritte mit Microsoft Endpunkt-DLP ](endpoint-dlp-getting-started.md)
2) [Nutzung von Microsoft Endpunkt-DLP ](endpoint-dlp-using.md)

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit Microsoft Endpunkt-DLP](endpoint-dlp-getting-started.md)
- [Nutzung von Microsoft Endpunkt-DLP ](endpoint-dlp-using.md)
- [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/)
- [Insider-Risikomanagement](insider-risk-management.md)
