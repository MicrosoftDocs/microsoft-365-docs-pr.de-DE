---
title: Internet-Inhaltsfilterung
description: Verwenden Sie die Webinhaltsfilterung in Microsoft Defender for Endpoint, um den Zugriff auf Websites basierend auf ihren Inhaltskategorien nachverfolgt und zu regeln.
keywords: Webschutz, Schutz vor Webbedrohungen, Browsen im Web, Überwachung, Berichte, Karten, Domänenliste, Sicherheit, Phishing, Schadsoftware, Exploit, Websites, Netzwerkschutz, Edge, Internet Explorer, Chrome, Firefox, Webbrowser
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
ms.openlocfilehash: 47211e187d1f9f883745f008c6d94d04ee762e98
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302064"
---
# <a name="web-content-filtering"></a>Internet-Inhaltsfilterung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Webinhaltsfilterung befindet sich derzeit in der öffentlichen Vorschau**<br>
> Diese Vorschauversion wird ohne Vereinbarung zum Servicelevel bereitgestellt und wird für Produktionsworkloads nicht empfohlen. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.
> Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint Preview Features](preview.md).

> [!TIP]
> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Die Webinhaltsfilterung ist Teil der [Webschutzfunktionen](web-protection-overview.md) in Microsoft Defender for Endpoint. Sie ermöglicht Es Ihrer Organisation, den Zugriff auf Websites basierend auf ihren Inhaltskategorien nachverfolgt und zu regeln. Viele dieser Websites sind zwar nicht bösartig, können jedoch aufgrund von Compliancebestimmungen, Bandbreitennutzung oder anderen Bedenken problematisch sein.

Konfigurieren Sie Richtlinien für alle Gerätegruppen, um bestimmte Kategorien zu blockieren. Das Blockieren einer Kategorie verhindert, dass Benutzer innerhalb angegebener Gerätegruppen auf URLs zugreifen, die der Kategorie zugeordnet sind. Für jede Kategorie, die nicht blockiert ist, werden die URLs automatisch überwacht. Ihre Benutzer können ohne Unterbrechung auf die URLs zugreifen, und Sie sammeln Zugriffsstatistiken, um eine benutzerdefiniertere Richtlinienentscheidung zu erstellen. Ihren Benutzern wird eine Sperrbenachrichtigung angezeigt, wenn ein Element auf der angezeigten Seite Aufrufe einer blockierten Ressource vor sich hat.

Die Webinhaltsfilterung ist in den wichtigsten Webbrowsern mit Blöcken verfügbar, die von Windows Defender SmartScreen (Microsoft Edge) und Network Protection (Chrome, Firefox, Brave und Opera) ausgeführt werden. Weitere Informationen zur Browserunterstützung finden Sie im Abschnitt Voraussetzungen.

Zusammenfassung der Vorteile:

- Benutzer werden am Zugriff auf Websites in blockierten Kategorien gehindert, unabhängig davon, ob sie lokal oder fern surfen
- Ihr Sicherheitsteam kann Richtlinien mithilfe von Gerätegruppen, die in rollenbasierten Zugriffssteuerungseinstellungen von Microsoft Defender for Endpoint definiert sind, bequem für Benutzergruppen [bereitstellen.](/microsoft-365/security/defender-endpoint/rbac)
- Ihr Sicherheitsteam kann auf Webberichte am gleichen zentralen Speicherort zugreifen, mit Sichtbarkeit über tatsächliche Blöcke und Webnutzung

## <a name="user-experience"></a>Verwendung durch den Benutzer

Die Sperrerfahrung für von Drittanbietern unterstützte Browser wird von Network Protection bereitgestellt, das ein Popup auf Systemebene bietet, das den Benutzer über eine blockierte Verbindung informiert. Für eine benutzerfreundlichere, browserfreundlichere Benutzeroberfläche sollten Sie die Verwendung von Microsoft Edge.

## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie vor dem Ausprobieren dieses Features sicher, dass Die folgenden Anforderungen erfüllt sind:

- Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security oder die eigenständige Microsoft Defender for Endpoint-Lizenz. 
- Zugriff auf Microsoft Defender Security Center Portal ( https://securitycenter.windows.com) .
- Geräte mit Windows 10 Anniversary Update (Version 1607) oder höher mit dem neuesten MoCAMP-Update.

## <a name="data-handling"></a>Datenverarbeitung

Wir folgen der Region, die Sie als Teil Ihrer [Microsoft Defender for Endpoint-Datenverarbeitungseinstellungen verwendet haben.](data-storage-privacy.md) Ihre Daten verlassen das Rechenzentrum nicht in dieser Region. Darüber hinaus werden Ihre Daten nicht an Dritte, einschließlich unserer Datenanbieter, weitergegeben.

## <a name="turn-on-web-content-filtering"></a>Aktivieren der Webinhaltsfilterung

Wählen Sie im linken Navigationsmenü die **Option Einstellungen**  >  **Erweiterte Features**  >  **aus.** Scrollen Sie nach unten, bis der Eintrag für die **Webinhaltsfilterung angezeigt wird.** Wechseln Sie zum Umschalten zu **Ein** und **Speichern der Einstellungen**.

### <a name="configure-web-content-filtering-policies"></a>Konfigurieren von Webinhaltsfilterrichtlinien

Web content filtering policies specify which site categories are blocked on which device groups. Um die Richtlinien zu verwalten, wechseln Sie **zu Einstellungen**  >  **Rules**  >  **Web content filtering**.

Verwenden Sie den Filter, um Richtlinien zu finden, die bestimmte blockierte Kategorien enthalten oder auf bestimmte Gerätegruppen angewendet werden.

### <a name="create-a-policy"></a>Erstellen einer Richtlinie

So fügen Sie eine neue Richtlinie hinzu:

1. Wählen **Sie Richtlinie hinzufügen** auf der **Webinhaltsfilterseite** in **Einstellungen**.

2. Geben Sie einen Namen an.

3. Wählen Sie die zu blockierende Kategorie aus. Verwenden Sie das Erweiterungssymbol, um alle übergeordneten Kategorien vollständig zu erweitern und bestimmte Webinhaltskategorien auszuwählen.

4. Geben Sie den Richtlinienbereich an. Wählen Sie die Gerätegruppen aus, um anzugeben, wo die Richtlinie angewendet werden soll. Nur Geräte in den ausgewählten Gerätegruppen können nicht auf Websites in den ausgewählten Kategorien zugreifen.

5. Überprüfen Sie die Zusammenfassung, und speichern Sie die Richtlinie. Die Richtlinienaktualisierung kann bis zu 2 Stunden dauern, bis sie auf ihre ausgewählten Geräte angewendet wird.

> [!TIP]
> Sie können eine Richtlinie bereitstellen, ohne eine Kategorie in einer Gerätegruppe auswählen zu müssen. Mit dieser Aktion wird eine Nur-Überwachung-Richtlinie erstellt, damit Sie das Benutzerverhalten besser verstehen können, bevor Sie eine Sperrrichtlinie erstellen.

>[!NOTE]
>Wenn Sie gleichzeitig eine Richtlinie entfernen oder Gerätegruppen ändern, kann dies zu verzögerungen bei der Richtlinienbereitstellung führen.

>[!IMPORTANT]
>Das Blockieren der Kategorie "Uncategorized" kann zu unerwarteten und unerwünschten Ergebnissen führen.  

### <a name="allow-specific-websites"></a>Zulassen bestimmter Websites

Es ist möglich, die blockierte Kategorie in der Webinhaltsfilterung außer Kraft zu setzen, um eine einzelne Website durch Erstellen einer benutzerdefinierten Indikatorrichtlinie zu ermöglichen. Die benutzerdefinierte Indikatorrichtlinie ersetzt die Webinhaltsfilterrichtlinie, wenn sie auf die entsprechende Gerätegruppe angewendet wird.

1. Erstellen Sie einen benutzerdefinierten Indikator im Microsoft Defender Security Center, indem Sie **Einstellungen**  >    >  **Indikatoren-URL/Domänen-Add-Element**  >  **.**

2. Geben Sie die Domäne der Website ein.

3. Legen Sie die Richtlinienaktion auf **Zulassen .**  

### <a name="reporting-inaccuracies"></a>Melden von Ungenauigkeiten

Wenn Eine Domäne fälschlicherweise kategorisiert wurde, können Sie Ungenauigkeiten direkt über die Seite Web content filtering reports melden. Dieses Feature ist nur im neuen Microsoft 365 Security Center (security.microsoft.com) verfügbar.

Um eine Ungenauigkeit zu melden, navigieren Sie zu **Berichte**  >  **Webschutz Web** Content Filtering  >  **Details**  >  **Domains**. Auf der Registerkarte Domänen unserer Web Content Filtering-Berichte wird neben jeder Domäne ein Auslassungsauslassungsblatt angezeigt. Zeigen Sie auf diese Auslassungspunkte, und wählen **Sie Ungenauigkeit melden aus.**

Ein Bereich wird geöffnet, in dem Sie die Priorität auswählen und zusätzliche Details hinzufügen können, z. B. die vorgeschlagene Kategorie für die erneute Kategorisierung. Nachdem Sie das Formular abgeschlossen haben, wählen Sie **Absenden aus.** Unser Team überprüft die Anforderung innerhalb eines Arbeitstags. Erstellen Sie zum sofortigen Aufheben der Blockierung einen [benutzerdefinierten Zulässigen Indikator](indicator-ip-domain.md).

## <a name="web-content-filtering-cards-and-details"></a>Webinhaltsfilterkarten und -details

Wählen **Sie Berichte > Webschutz aus,** um Karten mit Informationen zur Filterung von Webinhalten und zum Schutz vor Webbedrohungen anzuzeigen. Die folgenden Karten enthalten Zusammenfassende Informationen zur Webinhaltsfilterung.

### <a name="web-activity-by-category"></a>Webaktivität nach Kategorie

Diese Karte listet die übergeordneten Webinhaltskategorien mit der größten Zunahme oder Verringerung der Anzahl der Zugriffsversuche auf. Verstehen Sie drastische Änderungen an Webaktivitätsmustern in Ihrer Organisation seit den letzten 30 Tagen, 3 Monaten oder 6 Monaten. Wählen Sie einen Kategorienamen aus, um weitere Informationen anzeigen zu können.

In den ersten 30 Tagen nach der Verwendung dieses Features verfügt Ihre Organisation möglicherweise nicht über genügend Daten, um diese Informationen anzeigen zu können.

![Abbildung der Webaktivität nach Kategoriekarte](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Zusammenfassungskarte für die Webinhaltsfilterung

Diese Karte zeigt die Verteilung blockierter Zugriffsversuche auf die verschiedenen übergeordneten Webinhaltskategorien an. Wählen Sie einen der farbigen Balken aus, um weitere Informationen zu einer bestimmten übergeordneten Webkategorie anzeigen zu können.

![Abbildung der Zusammenfassungskarte für die Webinhaltsfilterung](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Zusammenfassungskarte für Webaktivität

Diese Karte zeigt die Gesamtzahl der Anforderungen für Webinhalte in allen URLs an.

![Abbildung der Zusammenfassungskarte für Webaktivität](images/web-activity-summary.png)

### <a name="view-card-details"></a>Anzeigen von Kartendetails

Sie können auf die **Berichtsdetails** für jede Karte zugreifen, indem Sie im Diagramm auf der Karte eine Tabellenzeile oder einen farbigen Balken auswählen. Die Berichtsdetailsepage für jede Karte enthält umfangreiche statistische Daten zu Webinhaltskategorien, Websitedomänen und Gerätegruppen.

![Abbildung der Details des Webschutzberichts](images/web-protection-report-details.png)

- **Webkategorien:** Listet die Webinhaltskategorien auf, für die in Ihrer Organisation Zugriffsversuche versucht wurden. Wählen Sie eine bestimmte Kategorie aus, um ein Zusammenfassungsf flyout zu öffnen.

- **Domänen:** Listet die Webdomänen auf, auf die in Ihrer Organisation zugegriffen oder blockiert wurde. Wählen Sie eine bestimmte Domäne aus, um detaillierte Informationen zu dieser Domäne anzeigen zu können.

- **Gerätegruppen**: Listet alle Gerätegruppen auf, die Webaktivitäten in Ihrer Organisation generiert haben

Verwenden Sie den Zeitbereichsfilter oben links auf der Seite, um einen Zeitraum auszuwählen. Sie können die Informationen auch filtern oder die Spalten anpassen. Wählen Sie eine Zeile aus, um einen Flyoutbereich mit noch mehr Informationen zum ausgewählten Element zu öffnen.

## <a name="errors-and-issues"></a>Fehler und Probleme

### <a name="limitations-and-known-issues-in-this-preview"></a>Einschränkungen und bekannte Probleme in dieser Vorschau

- Nur Microsoft Edge wird unterstützt, wenn die Betriebssystemkonfiguration Ihres Geräts Server (**cmd**  >  **Systeminfo** OS Configuration )  >  **ist.** Network Protection wird nur im Inspect-Modus auf Servergeräten unterstützt, der für die Sicherung des Datenverkehrs über unterstützte Browser von Drittanbietern verantwortlich ist.

- Auf nicht zugewiesenen Geräten werden falsche Daten im Bericht angezeigt. Im **Pivot "Berichtdetails**  >  **Gerätegruppen"** wird möglicherweise eine Zeile mit einem leeren Feld Gerätegruppe angezeigt. Diese Gruppe enthält Ihre nicht zugewiesenen Geräte, bevor sie in Ihre angegebene Gruppe eingesenert werden. Der Bericht für diese Zeile enthält möglicherweise keine genaue Anzahl von Geräten oder Zugriffsanzahlen.

- Web content filtering reports are currently limited to showing the top 5000 records. Der Domänenbericht zeigt beispielsweise nur maximal 5000 Domänen für eine bestimmte Filterabfrage an, sofern zutreffend. 

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Internetschutz](web-protection-overview.md)
- [Internet-Bedrohungsschutz](web-threat-protection.md)
- [Überwachen der Websicherheit](web-protection-monitoring.md)
- [Reagieren auf Internetbedrohungen](web-protection-response.md)
