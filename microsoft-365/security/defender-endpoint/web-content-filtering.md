---
title: Internet-Inhaltsfilterung
description: Verwenden Sie die Webinhaltsfilterung in Microsoft Defender für Endpunkt, um den Zugriff auf Websites basierend auf ihren Inhaltskategorien nachzuverfolgen und zu steuern.
keywords: Webschutz, Schutz vor Webbedrohungen, Webbrowsen, Überwachung, Berichte, Karten, Domänenliste, Sicherheit, Phishing, Schadsoftware, Exploit, Websites, Netzwerkschutz, Edge, Internet Explorer, Chrome, Firefox, Webbrowser
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c7b39b600af2fed130a0b78a590740a8bc063f50
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861695"
---
# <a name="web-content-filtering"></a>Internet-Inhaltsfilterung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Die Webinhaltsfilterung befindet sich derzeit in der öffentlichen Vorschau**<br>
> Diese Vorschauversion wird ohne Vereinbarung zum Servicelevel bereitgestellt und für Produktionsarbeitslasten nicht empfohlen. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen über eingeschränkte Funktionen.
> Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt-Vorschaufeatures.](preview.md)

> [!TIP]
> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Die Webinhaltsfilterung ist Teil der [Webschutzfunktionen](web-protection-overview.md) in Microsoft Defender für Endpunkt. Es ermöglicht Ihrer Organisation, den Zugriff auf Websites basierend auf ihren Inhaltskategorien nachzuverfolgen und zu regeln. Viele dieser Websites, obwohl sie nicht bösartig sind, können aufgrund von Compliance-Vorschriften, Bandbreitennutzung oder anderen Bedenken problematisch sein.

Konfigurieren Sie Richtlinien für Alle Gerätegruppen, um bestimmte Kategorien zu blockieren. Durch das Blockieren einer Kategorie wird verhindert, dass Benutzer innerhalb der angegebenen Gerätegruppen auf URLs zugreifen, die der Kategorie zugeordnet sind. Für jede Kategorie, die nicht blockiert ist, werden die URLs automatisch überwacht. Ihre Benutzer können ohne Unterbrechung auf die URLs zugreifen, und Sie erfassen Zugriffsstatistiken, um eine benutzerdefinierte Richtlinienentscheidung zu erstellen. Ihren Benutzern wird eine Blockierungsbenachrichtigung angezeigt, wenn ein Element auf der angezeigten Seite Aufrufe an eine blockierte Ressource durchführt.

Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Barre and Opera). Weitere Informationen zur Browserunterstützung finden Sie im Abschnitt "Voraussetzungen".

Zusammenfassung der Vorteile:

- Benutzern wird der Zugriff auf Websites in blockierten Kategorien verhindert, unabhängig davon, ob sie lokal oder abwesend surfen.
- Ihr Sicherheitsteam kann Richtlinien bequem für Benutzergruppen bereitstellen, die Gerätegruppen verwenden, die in [den rollenbasierten Zugriffssteuerungseinstellungen](/microsoft-365/security/defender-endpoint/rbac) von Microsoft Defender für Endpunkt definiert sind.
- Ihr Sicherheitsteam kann an demselben zentralen Ort auf Webberichte zugreifen, mit Sichtbarkeit der tatsächlichen Blöcke und der Webnutzung

## <a name="user-experience"></a>Verwendung durch den Benutzer

Die Blockierungsfunktion für von Drittanbietern unterstützte Browser wird durch Netzwerkschutz bereitgestellt, der eine Popupbenachrichtigung auf Systemebene bereitstellt, die den Benutzer über eine blockierte Verbindung benachrichtigt. Für eine benutzerfreundlichere, browserinterne Erfahrung sollten Sie Microsoft Edge verwenden.

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie dieses Feature ausprobieren, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

- Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security Add-On oder die eigenständige Microsoft Defender für Endpunkt-Lizenz. 
- Zugriff auf Microsoft Defender Security Center Portal ( https://securitycenter.windows.com) .
- Geräte mit Windows 10 Anniversary Update (Version 1607) oder höher mit dem neuesten MoCAMP-Update.
- Windows Defender SmartScreen und Netzwerkschutz aktiviert.


## <a name="data-handling"></a>Datenverarbeitung

Daten werden in der Region gespeichert, die als Teil Ihrer [Microsoft Defender für Endpunkt-Datenverarbeitungseinstellungen](data-storage-privacy.md)ausgewählt wurde. Ihre Daten verlassen das Rechenzentrum in dieser Region nicht. Darüber hinaus werden Ihre Daten nicht an Dritte, einschließlich unserer Datenanbieter, weitergegeben.

## <a name="turn-on-web-content-filtering"></a>Aktivieren der Webinhaltsfilterung

Wählen Sie im linken Navigationsmenü **Einstellungen**  >  **Allgemeine**  >  **erweiterte Features** aus. Scrollen Sie nach unten, bis der Eintrag für **die Webinhaltsfilterung** angezeigt wird. Setzen Sie die Umschaltfläche auf **"Ein",** und **speichern Sie die Einstellungen.**

### <a name="configure-web-content-filtering-policies"></a>Konfigurieren von Richtlinien für die Webinhaltsfilterung

Web content filtering policies specify which site categories are blocked on which device groups. Wechseln Sie zum Verwalten der Richtlinien zu **Einstellungen**  >    >  **Webinhaltsfilterung** für Regeln.

Verwenden Sie den Filter, um Nachschlagerichtlinien zu suchen, die bestimmte blockierte Kategorien enthalten oder auf bestimmte Gerätegruppen angewendet werden.

### <a name="create-a-policy"></a>Erstellen einer Richtlinie

So fügen Sie eine neue Richtlinie hinzu:

1. Wählen Sie auf der **Seite "Webinhaltsfilterung"** in **Einstellungen** die Option **"Richtlinie hinzufügen"** aus.

2. Geben Sie einen Namen an.

3. Wählen Sie die Kategorien aus, die blockiert werden sollen. Verwenden Sie das Symbol zum Erweitern, um die einzelnen übergeordneten Kategorien vollständig zu erweitern und bestimmte Webinhaltskategorien auszuwählen.

4. Geben Sie den Richtlinienbereich an. Wählen Sie die Gerätegruppen aus, um anzugeben, wo die Richtlinie angewendet werden soll. Nur Geräte in den ausgewählten Gerätegruppen werden am Zugriff auf Websites in den ausgewählten Kategorien gehindert.

5. Überprüfen Sie die Zusammenfassung, und speichern Sie die Richtlinie. Die Aktualisierung der Richtlinie kann bis zu 2 Stunden dauern, bis sie auf die ausgewählten Geräte angewendet wurde.

> [!NOTE]
> - Sie können eine Richtlinie bereitstellen, ohne eine Kategorie in einer Gerätegruppe auszuwählen. Mit dieser Aktion wird eine Nur-Überwachungsrichtlinie erstellt, die Ihnen dabei hilft, das Benutzerverhalten zu verstehen, bevor Sie eine Blockierungsrichtlinie erstellen.
> - Wenn Sie eine Richtlinie entfernen oder Gerätegruppen gleichzeitig ändern, kann dies zu einer Verzögerung bei der Richtlinienbereitstellung führen.
> - Das Blockieren der Kategorie "Nicht kategorisiert" kann zu unerwarteten und unerwünschten Ergebnissen führen.  

### <a name="allow-specific-websites"></a>Bestimmte Websites zulassen

Es ist möglich, die blockierte Kategorie in der Webinhaltsfilterung zu überschreiben, um eine einzelne Website zuzulassen, indem Sie eine benutzerdefinierte Indikatorrichtlinie erstellen. Die benutzerdefinierte Indikatorrichtlinie ersetzt die Webinhaltsfilterrichtlinie, wenn sie auf die betreffende Gerätegruppe angewendet wird.

1. Erstellen Sie einen benutzerdefinierten Indikator im Microsoft Defender Security Center, indem Sie zu **Einstellungen**  >  **Indicators**  >  **URL/Domain**  >  **Add Item wechseln.**

2. Geben Sie die Domäne der Website ein.

3. Legen Sie die Richtlinienaktion auf **"Zulassen"** fest.  

### <a name="reporting-inaccuracies"></a>Melden von Ungenauigkeiten

Wenn sie auf eine Domäne stoßen, die falsch kategorisiert wurde, können Sie Ungenauigkeiten direkt über die Berichtsseite der Webinhaltsfilterung an uns melden. Dieses Feature ist nur im neuen Microsoft 365 Security Center (security.microsoft.com) verfügbar.

Um eine Ungenauigkeit zu melden, navigieren Sie zu  >  Webinhaltsfilterungs-Detaildomänen für Den **Webschutz.**  >    >   Auf der Registerkarte "Domänen" unserer Webinhaltsfilter-Berichte werden neben jeder Domäne auslassungszeichen angezeigt. Zeigen Sie auf diese Auslassungszeichen, und wählen Sie **"Ungenauigkeit melden"** aus.

Ein Bereich wird geöffnet, in dem Sie die Priorität auswählen und zusätzliche Details wie die vorgeschlagene Kategorie für die erneute Kategorisierung hinzufügen können. Nachdem Sie das Formular ausgefüllt haben, wählen Sie **"Absenden"** aus. Unser Team überprüft die Anforderung innerhalb eines Geschäftstags. Erstellen Sie zum sofortigen Aufheben der Blockierung eine [benutzerdefinierte Zulassungsanzeige.](indicator-ip-domain.md)

## <a name="web-content-filtering-cards-and-details"></a>Karten und Details zum Filtern von Webinhalten

Wählen Sie   >  **"Berichtswebschutz"** aus, um Karten mit Informationen zur Webinhaltsfilterung und zum Schutz vor Webbedrohungen anzuzeigen. Die folgenden Karten enthalten zusammenfassende Informationen zur Webinhaltsfilterung.

### <a name="web-activity-by-category"></a>Webaktivität nach Kategorie

Diese Karte listet die übergeordneten Webinhaltskategorien mit der größten Erhöhung oder Verringerung der Anzahl der Zugriffsversuche auf. Grundlegendes zu tiefgreifenden Änderungen der Webaktivitätsmuster in Ihrer Organisation von den letzten 30 Tagen, 3 Monaten oder 6 Monaten. Wählen Sie einen Kategorienamen aus, um weitere Informationen anzuzeigen.

In den ersten 30 Tagen der Verwendung dieses Features verfügt Ihre Organisation möglicherweise nicht über genügend Daten, um diese Informationen anzuzeigen.

![Abbildung der Webaktivität nach Kategoriekarte](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Zusammenfassungskarte für die Webinhaltsfilterung

Diese Karte zeigt die Verteilung blockierter Zugriffsversuche in den verschiedenen übergeordneten Webinhaltskategorien an. Wählen Sie einen der farbigen Balken aus, um weitere Informationen zu einer bestimmten übergeordneten Webkategorie anzuzeigen.

![Abbildung der Zusammenfassungskarte für die Webinhaltsfilterung](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Zusammenfassungskarte für Webaktivität

Diese Karte zeigt die Gesamtzahl der Anforderungen für Webinhalte in allen URLs an.

![Abbildung der Zusammenfassungskarte für Webaktivität](images/web-activity-summary.png)

### <a name="view-card-details"></a>Anzeigen von Kartendetails

Sie können auf die **Berichtsdetails** für jede Karte zugreifen, indem Sie eine Tabellenzeile oder eine farbige Leiste aus dem Diagramm auf der Karte auswählen. Die Berichtsdetailseite für jede Karte enthält umfangreiche statistische Daten zu Webinhaltskategorien, Websitedomänen und Gerätegruppen.

![Abbildung der Webschutzberichtsdetails](images/web-protection-report-details.png)

- **Webkategorien:** Listet die Webinhaltskategorien auf, für die in Ihrer Organisation Zugriffsversuche ausgeführt wurden. Wählen Sie eine bestimmte Kategorie aus, um ein Zusammenfassungs-Flyout zu öffnen.

- **Domänen:** Listet die Webdomänen auf, auf die in Ihrer Organisation zugegriffen oder blockiert wurde. Wählen Sie eine bestimmte Domäne aus, um detaillierte Informationen zu dieser Domäne anzuzeigen.

- **Gerätegruppen:** Listet alle Gerätegruppen auf, die Webaktivitäten in Ihrer Organisation generiert haben

Verwenden Sie den Zeitbereichsfilter oben links auf der Seite, um einen Zeitraum auszuwählen. Sie können auch die Informationen filtern oder die Spalten anpassen. Wählen Sie eine Zeile aus, um einen Flyoutbereich mit noch mehr Informationen zum ausgewählten Element zu öffnen.

## <a name="errors-and-issues"></a>Fehler und Probleme

### <a name="limitations-and-known-issues-in-this-preview"></a>Einschränkungen und bekannte Probleme in dieser Vorschau

- Nur Microsoft Edge wird unterstützt, wenn die Betriebssystemkonfiguration Ihres Geräts server (**cmd**  >  **Systeminfo**  >  **OS Configuration**) ist. Der Netzwerkschutz wird nur im Inspect-Modus auf Servergeräten unterstützt, der für die Sicherung des Datenverkehrs über unterstützte Browser von Drittanbietern verantwortlich ist.

- Nicht zugewiesene Geräte verfügen über falsche Daten, die im Bericht angezeigt werden. Im Pivot **"Berichtsdetails**  >  **Gerätegruppen"** wird möglicherweise eine Zeile mit einem leeren Feld "Gerätegruppe" angezeigt. Diese Gruppe enthält Ihre nicht zugewiesenen Geräte, bevor sie in die angegebene Gruppe aufgenommen werden. Der Bericht für diese Zeile enthält möglicherweise keine genaue Anzahl von Geräten oder Zugriffsanzahlen.

- Web content filtering reports are currently limited to showing the top 5000 records. Der Domänenbericht zeigt beispielsweise nur maximal 5000 Domänen für eine bestimmte Filterabfrage an, sofern zutreffend. 



- [Übersicht über Internetschutz](web-protection-overview.md)
- [Internet-Bedrohungsschutz](web-threat-protection.md)
- [Überwachen der Websicherheit](web-protection-monitoring.md)
- [Reagieren auf Internetbedrohungen](web-protection-response.md)
- [Anforderungen für den Netzwerkschutz](web-content-filtering.md)

