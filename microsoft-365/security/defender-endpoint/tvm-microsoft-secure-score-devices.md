---
title: Microsoft-Sicherheitsbewertung für Geräte
description: Ihre Bewertung für Geräte zeigt den gemeinsamen Sicherheitskonfigurationsstatus Ihrer Geräte über Anwendungs-, Betriebssystem-, Netzwerk-, Konten- und Sicherheitssteuerelemente hinweg an.
keywords: Microsoft Secure Score for Devices, Microsoft Defender for Endpoint Microsoft Secure Score for Devices, Secure Score, Configuration Score, Bedrohungs- und Sicherheitsrisikomanagement, security controls, improvement opportunities, security configuration score over time, security posture, baseline
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
ms.openlocfilehash: f2c799d477c400482c16b09b4d8a5cdc01106dfa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934081"
---
# <a name="microsoft-secure-score-for-devices"></a>Microsoft-Sicherheitsbewertung für Geräte

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> Die Konfigurationsnote ist nun Teil Bedrohungs- und Sicherheitsrisikomanagement Microsoft Secure Score für Geräte.

Ihre Bewertung für Geräte ist im Bedrohungs- und Sicherheitsrisikomanagement [des](tvm-dashboard-insights.md) Microsoft Defender Security Center. Eine höhere Microsoft Secure Score für Geräte bedeutet, dass Ihre Endpunkte widerstandsfähiger gegen Cybersicherheitsangriffe sind. Dies spiegelt den Konfigurationsstatus für die gemeinsame Sicherheit Ihrer Geräte in den folgenden Kategorien wider:

- Anwendung
- Betriebssystem
- Netzwerk
- Konten
- Sicherheitssteuerelemente

Wählen Sie eine Kategorie aus, um zur Seite [**Sicherheitsempfehlungen zu**](tvm-security-recommendation.md) wechseln, und zeigen Sie die entsprechenden Empfehlungen an.

## <a name="turn-on-the-microsoft-secure-score-connector"></a>Aktivieren des Microsoft Secure Score-Connectors

Weiterleiten von Microsoft Defender for Endpoint-Signalen, was Microsoft Secure Score Sichtbarkeit in der Gerätesicherheitshaltung bietet. Weitergeleitete Daten werden am gleichen Speicherort wie Ihre Microsoft Secure Score-Daten gespeichert und verarbeitet.

Es kann bis zu ein paar Stunden dauern, bis Änderungen im Dashboard angezeigt werden.

1. Wechseln Sie im Navigationsbereich zu **Einstellungen**  >  **Erweiterte Features** 

2. Scrollen Sie nach unten **zu Microsoft Secure Score,** und schalten Sie die Einstellung auf **Ein um.**

3. Wählen **Sie Einstellungen speichern aus.**

## <a name="how-it-works"></a>Funktionsweise

>[!NOTE]
> Microsoft Secure Score für Geräte unterstützt derzeit Konfigurationen, die über Gruppenrichtlinien festgelegt werden. Aufgrund der aktuellen teilweisen Intune-Unterstützung werden Konfigurationen, die möglicherweise über Intune festgelegt wurden, möglicherweise als falsch konfiguriert angezeigt. Wenden Sie sich an Ihren IT-Administrator, um den tatsächlichen Konfigurationsstatus zu überprüfen, falls Ihre Organisation Intune für die sichere Konfigurationsverwaltung verwendet.

Die Daten auf der Microsoft Secure Score for Devices-Karte sind das Produkt einer sorgfältigen und fortlaufenden Ermittlung von Sicherheitslücken. Es wird mit Konfigurationsermittlungsbewertungen aggregiert, die kontinuierlich:

- Vergleichen erfasster Konfigurationen mit den gesammelten Benchmarks zum Ermitteln falsch konfigurierter Ressourcen
- Zuordnung von Konfigurationen zu Sicherheitsrisiken, die behoben oder teilweise behoben werden können (Risikominderung)
- Sammeln und Verwalten bewährter Konfigurations benchmarks (Anbieter, Sicherheitsfeeds, interne Forschungsteams)
- Erfassen und Überwachen von Änderungen des Konfigurationsstatus der Sicherheitssteuerung aus allen Ressourcen

## <a name="improve-your-security-configuration"></a>Verbessern Der Sicherheitskonfiguration

Verbessern Sie Ihre Sicherheitskonfiguration, indem Sie Probleme aus der Liste der Sicherheitsempfehlungen beheben. Dabei verbessert sich Ihre Microsoft Secure Score for Devices, und Ihre Organisation wird widerstandsfähiger gegen Cybersicherheitsbedrohungen und Sicherheitsrisiken.

1. Wählen Sie auf der Microsoft Secure Score for Devices-Karte im Bedrohungs- und Sicherheitsrisikomanagement eine der Kategorien aus. Sie sehen die Liste der Empfehlungen im Zusammenhang mit dieser Kategorie. Sie gelangen zur Seite [**Sicherheitsempfehlungen.**](tvm-security-recommendation.md) Wenn Sie alle Sicherheitsempfehlungen anzeigen möchten, löschen Sie das Suchfeld, sobald Sie zur Seite Sicherheitsempfehlungen gelangen.

2. Wählen Sie ein Element in der Liste aus. Das Flyoutpanel wird mit Details zur Empfehlung geöffnet. Wählen **Sie Korrekturoptionen aus.**

   ![Sicherheitskontrollen im Zusammenhang mit Sicherheitsempfehlungen](images/tvm_security_controls.png)

3. Lesen Sie die Beschreibung, um den Kontext des Problems und die nächsten Schritte zu verstehen. Wählen Sie ein Fälligkeitsdatum aus, fügen Sie Notizen hinzu, und wählen Sie Alle Berichtsberichtsaktivitätsdaten in **CSV** exportieren aus, damit Sie sie an eine E-Mail für die Nachbereinigung anfügen können.

4. **Senden der Anforderung**. Es wird eine Bestätigungsmeldung angezeigt, dass die Problembehebungsaufgabe erstellt wurde.
   ![Bestätigung der Erstellung von Korrekturaufgabe](images/tvm_remediation_task_created.png)

5. Speichern Sie Ihre CSV-Datei.
   ![Speichern der CSV-Datei](images/tvm_save_csv_file.png)

6. Senden Sie eine Follow-up-E-Mail an Ihren IT-Administrator, und lassen Sie die Zeit zu, die Sie für die Behebung zur Vermehrung im System zugewiesen haben.

7. Überprüfen Sie **die Microsoft Secure Score for Devices-Karte** erneut auf dem Dashboard. Die Anzahl der Empfehlungen für Sicherheitskontrollen nimmt ab. Wenn Sie **Sicherheitssteuerelemente auswählen,** um zur Seite Sicherheitsempfehlungen zurück zu wechseln, wird das von Ihnen adressierte Element dort nicht mehr aufgeführt.  Ihre Microsoft Secure Score für Geräte sollte erhöht werden.

>[!IMPORTANT]
>Laden Sie die folgenden obligatorischen Sicherheitsupdates herunter, und stellen Sie sie in Ihrem Netzwerk bereit, um die Erkennungsraten für Sicherheitsrisiken zu erhöhen:
>- 19H1-Kunden | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
>- RS5-Kunden | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
>- RS4-Kunden | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
>- RS3-Kunden | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
>So laden Sie die Sicherheitsupdates herunter:
>1. Wechseln Sie zu [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).
>2. Wählen Sie die KB-Nummer des Sicherheitsupdates ein, die Sie herunterladen müssen, und klicken Sie dann auf **Suchen**.  

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Gefährdungsscore](tvm-exposure-score.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)
