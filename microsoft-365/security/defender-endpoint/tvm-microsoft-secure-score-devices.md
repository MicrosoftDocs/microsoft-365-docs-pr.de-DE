---
title: Microsoft-Sicherheitsbewertung für Geräte
description: Ihre Bewertung für Geräte zeigt den gemeinsamen Sicherheitskonfigurationsstatus Ihrer Geräte über Anwendung, Betriebssystem, Netzwerk, Konten und Sicherheitskontrollen hinweg.
keywords: Microsoft-Sicherheitsbewertung für Geräte, Microsoft Defender für Endpunkt Microsoft-Sicherheitsbewertung für Geräte, Sicherheitsbewertung, Konfigurationsbewertung, Bedrohungs- und Sicherheitsrisikomanagement, Sicherheitskontrollen, Verbesserungsmöglichkeiten, Sicherheitskonfigurationsbewertung im Laufe der Zeit, Sicherheitsstatus, Baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13307d3205818d41e7b2219b4e3a4ed6e9f2d5bb
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454774"
---
# <a name="microsoft-secure-score-for-devices"></a>Microsoft-Sicherheitsbewertung für Geräte

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohungs- und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> Die Konfigurationsbewertung ist jetzt Teil Bedrohungs- und Sicherheitsrisikomanagement als Microsoft-Sicherheitsbewertung für Geräte.

Ihre Bewertung für Geräte ist im [Bedrohungs- und Sicherheitsrisikomanagement-Dashboard](tvm-dashboard-insights.md) des Microsoft 365 Defender-Portals sichtbar. Eine höhere Microsoft-Sicherheitsbewertung für Geräte bedeutet, dass Ihre Endpunkte stabiler vor Angriffen auf Cybersicherheitsbedrohungen sind. Es spiegelt den gemeinsamen Sicherheitskonfigurationsstatus Ihrer Geräte in den folgenden Kategorien wider:

- Anwendung
- Betriebssystem
- Netzwerk
- Konten
- Sicherheitskontrollen

Wählen Sie eine Kategorie aus, um zur Seite [**"Sicherheitsempfehlungen"**](tvm-security-recommendation.md) zu wechseln und die entsprechenden Empfehlungen anzuzeigen.

## <a name="turn-on-the-microsoft-secure-score-connector"></a>Aktivieren des Microsoft Secure Score-Connectors

Leiten Sie Microsoft Defender für Endpunkt-Signale weiter, sodass Die Microsoft-Sicherheitsbewertung einen Einblick in den Sicherheitsstatus des Geräts erhält. Weitergeleitete Daten werden am selben Speicherort wie Ihre Microsoft-Sicherheitsbewertungsdaten gespeichert und verarbeitet.

Es kann bis zu ein paar Stunden dauern, bis Änderungen im Dashboard angezeigt werden.

1. Wechseln Sie im Navigationsbereich zu **Einstellungen** Allgemeine erweiterte  >    >    >  **Endpunktfeatures** 

2. Scrollen Sie nach unten zur **Microsoft-Sicherheitsbewertung,** und setzen Sie die Einstellung auf **"Ein".**

3. Wählen Sie **"Einstellungen speichern" aus.**

## <a name="how-it-works"></a>So funktioniert's

>[!NOTE]
> Die Microsoft-Sicherheitsbewertung für Geräte unterstützt derzeit Konfigurationen, die über Gruppenrichtlinien festgelegt wurden. Aufgrund der aktuellen teilweisen Intune-Unterstützung werden Konfigurationen, die möglicherweise über Intune festgelegt wurden, als falsch konfiguriert angezeigt. Wenden Sie sich an Ihren IT-Administrator, um den tatsächlichen Konfigurationsstatus für den Fall zu überprüfen, dass Ihre Organisation Intune für die sichere Konfigurationsverwaltung verwendet.

Die Daten in der Microsoft-Karte "Sicherheitsbewertung für Geräte" sind das Produkt eines laufenden Prozesses zur Ermittlung von Sicherheitsrisiken. Es wird mit Konfigurationsermittlungsbewertungen aggregiert, die fortlaufend:

- Vergleichen sie gesammelte Konfigurationen mit den erfassten Benchmarks, um falsch konfigurierte Ressourcen zu ermitteln.
- Zuordnen von Konfigurationen zu Sicherheitsrisiken, die behoben oder teilweise behoben werden können (Risikominderung)
- Sammeln und Verwalten von Konfigurationsbenchmarks für bewährte Methoden (Anbieter, Sicherheitsfeeds, interne Forschungsteams)
- Erfassen und Überwachen von Änderungen des Konfigurationsstatus der Sicherheitssteuerung aus allen Ressourcen

## <a name="improve-your-security-configuration"></a>Verbessern der Sicherheitskonfiguration

Verbessern Sie Ihre Sicherheitskonfiguration, indem Sie Probleme aus der Liste der Sicherheitsempfehlungen beheben. Dadurch wird Ihre Microsoft-Sicherheitsbewertung für Geräte verbessert, und Ihre Organisation wird stabiler gegen Cybersicherheitsbedrohungen und Sicherheitsrisiken.

1. Wählen Sie auf der Karte "Microsoft-Sicherheitsbewertung für Geräte" im Bedrohungs- und Sicherheitsrisikomanagement-Dashboard eine der Kategorien aus. Sie werden die Liste der Empfehlungen im Zusammenhang mit dieser Kategorie anzeigen. Sie gelangen dann zur Seite [**"Sicherheitsempfehlungen".**](tvm-security-recommendation.md) Wenn Sie alle Sicherheitsempfehlungen anzeigen möchten, löschen Sie das Suchfeld, sobald Sie zur Seite "Sicherheitsempfehlungen" gelangen.

2. Wählen Sie ein Element in der Liste aus. Das Flyout-Panel wird mit Details im Zusammenhang mit der Empfehlung geöffnet. Wählen Sie **Korrekturoptionen** aus.

   :::image type="content" alt-text="Sicherheitskontrollen im Zusammenhang mit Sicherheitsempfehlungen." source="images/security-controls.png":::

3. Lesen Sie die Beschreibung, um den Kontext des Problems und die nächsten Aktionen zu verstehen. Wählen Sie ein Fälligkeitsdatum aus, fügen Sie Notizen hinzu, und wählen Sie **"Alle Korrekturaktivitätsdaten in CSV exportieren"** aus, damit Sie sie zur Nachverfolgung an eine E-Mail anfügen können.

4. **Anforderung senden**. Es wird eine Bestätigungsmeldung angezeigt, dass die Korrekturaufgabe erstellt wurde.

   :::image type="content" alt-text="Bestätigung der Erstellung von Korrekturaufgaben." source="images/remediation-task-created.png":::

5. Speichern Sie Ihre CSV-Datei.

   :::image type="content" alt-text="Speichern Sie die CSV-Datei." source="images/tvm_save_csv_file.png":::

6. Senden Sie eine Nachverfolgungs-E-Mail an Ihren IT-Administrator, und lassen Sie zu, dass die Zeit, die Sie für die Korrektur zugewiesen haben, im System verteilt wird.

7. Überprüfen Sie die **Microsoft-Karte "Sicherheitsbewertung für Geräte"** erneut auf dem Dashboard. Die Anzahl der Empfehlungen für Sicherheitskontrollen nimmt ab. Wenn Sie **Sicherheitssteuerelemente** auswählen, um zur Seite **"Sicherheitsempfehlungen"** zurückzukehren, wird das element, das Sie adressiert haben, dort nicht mehr aufgeführt. Ihre Microsoft-Sicherheitsbewertung für Geräte sollte erhöht werden.

>[!IMPORTANT]
>Laden Sie die folgenden obligatorischen Sicherheitsupdates herunter, und stellen Sie sie in Ihrem Netzwerk bereit, um die Erkennungsraten ihrer Schwachstellen zu erhöhen:
>- 19H1-Kunden | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
>- RS5-Kunden | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
>- RS4-Kunden | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
>- RS3-Kunden | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
>So laden Sie die Sicherheitsupdates herunter:
>1. Wechseln Sie zum [Microsoft Update-Katalog.](https://www.catalog.update.microsoft.com/home.aspx)
>2. Geben Sie die KB-Nummer des Sicherheitsupdates ein, die Sie herunterladen müssen, und klicken Sie dann auf **"Suchen".**  

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Bedrohungen und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Gefährdungsscore](tvm-exposure-score.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)
