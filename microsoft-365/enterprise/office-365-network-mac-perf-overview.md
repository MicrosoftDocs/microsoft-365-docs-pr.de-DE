---
title: Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
description: Übersicht über die Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)
ms.openlocfilehash: 159edf6f95910625c3f924d02c8307d681164df7
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454241"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a>Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)

Das Microsoft 365 Admin Center enthält nun aggregierte Metriken für die Netzwerkkonnektivität, die von Ihrem Microsoft 365-Mandanten erfasst wurden und nur von administrativen Benutzern in Ihrem Mandanten angezeigt werden können.

> [!div class="mx-imgBorder"]
> ![Testtool für Netzwerkkonnektivität](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**Netzwerkbewertungen** und **Netzwerkeinblicke** werden im Microsoft 365 Admin Center unter **Integritätsbewertung | Konnektivität**.

> [!div class="mx-imgBorder"]
> ![Seite "Netzwerkleistung"](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>Das Testtool für netzwerkkonnektivität unterstützt Mandanten in WW Commercial und Deutschland, aber nicht GCC Moderate, GCC High, DoD oder China.

Wenn Sie zum ersten Mal zur Seite "Netzwerkleistung" navigieren, wird ein Übersichtsbereich mit einer Karte der globalen Netzwerkleistung, einer Netzwerkbewertung auf den gesamten Mandanten und einer Liste der aktuellen Probleme angezeigt. In der Übersicht können Sie einen Drilldown erstellen, um bestimmte Metriken und Probleme der Netzwerkleistung nach Standort anzuzeigen. Weitere Informationen finden Sie unter [Übersicht über die Netzwerkleistung im Microsoft 365 Admin Center](#network-connectivity-overview-in-the-microsoft-365-admin-center).

Möglicherweise werden Sie aufgefordert, im Namen Ihrer Organisation an der öffentlichen Vorschau für dieses Feature teil zu nehmen. Die Annahme ist in der Regel sofort erfolgt, und dann wird die Seite mit der Netzwerkverbindung angezeigt. 

Bei der Navigation zur Seite "Netzwerkkonnektivität" wird ein Übersichtsbereich mit einer Karte der globalen Netzwerkleistung, einer Auf den gesamten Mandanten umfassenden Netzwerkbewertung und einer Liste der aktuellen Probleme angezeigt. Für den Zugriff auf diese Seite müssen Sie ein Administrator für die Organisation in Microsoft 365 sein. Die Administratorrolle "Berichtsleser" hat Lesezugriff auf diese Informationen. Zum Konfigurieren von Speicherorten und anderen Elementen der Netzwerkkonnektivität muss ein Administrator Teil einer Serveradministratorrolle sein, z. B. der Administratorrolle Dienstunterstützung. In der Übersicht können Sie einen Drilldown erstellen, um bestimmte Metriken und Probleme der Netzwerkleistung nach Standort anzuzeigen. Weitere Informationen finden Sie unter [Übersicht über die Netzwerkkonnektivität im Microsoft 365 Admin Center](#network-connectivity-overview-in-the-microsoft-365-admin-center).

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Voraussetzungen für die Schätzung der Netzwerkkonnektivität

Aktivieren Sie die Einstellung standortanmelden, um automatisch Daten von Geräten mithilfe von Windows Location Services zu sammeln, zur Liste Standorte zu wechseln, um Standortdaten hinzuzufügen oder hochzuladen, oder führen Sie den Microsoft 365-Netzwerkkonnektivitätstest an Ihren Bürostandorten aus. Während die Netzwerkkonnektivität in der gesamten Organisation ausgewertet werden kann, müssen für bestimmte Bürostandorte Verbesserungen des Netzwerkentwurfs vorgenommen werden. Netzwerkverbindungsinformationen werden für jeden Bürostandort bereitgestellt, sobald diese Standorte bestimmt werden können. Es gibt drei Optionen zum Abrufen von Netzwerkbewertungen von Ihren Bürostandorten:

### <a name="1-enable-windows-location-services"></a>1. Aktivieren von Windows Location Services

Für diese Option müssen an jedem Bürostandort mindestens zwei Computer ausgeführt werden, die die Voraussetzungen unterstützen. OneDrive für #A0 muss auf jedem Computer auf dem neuesten Stand sein und installiert sein. Weitere Informationen zu #A0 finden Sie in den [OneDrive-Versionshinweisen](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0). Netzwerkmessungen sollen in naher Zukunft in anderen Office 365-Clientanwendungen hinzugefügt werden.

Windows Location Service muss auf den Computern zugestimmt werden. Sie können dies testen, indem Sie die **Karten-App** ausführen und sich selbst suchen. Sie kann auf einem einzelnen Computer mit Einstellungen aktiviert **| Datenschutz | Speicherort,** an dem die Einstellung _Apps den Zugriff auf Ihren_ Standort erlauben aktiviert sein muss. Die Zustimmung von Windows Location Services kann auf PCs mithilfe von MDM oder Gruppenrichtlinien mit der Einstellung _LetAppsAccessLocation bereitgestellt werden._

Sie müssen mit dieser Methode keine Standorte im Admin Center hinzufügen, da diese automatisch bei der Stadtauflösung identifiziert werden. Sie können nicht mehrere Bürostandorte in einer Stadt mithilfe von Windows Location Services anzeigen. Standortinformationen werden auch auf die nächsten 300 Meter um 300 Meter gerundet, bevor sie hochgeladen werden, damit auf genauere Standortinformationen nicht zugegriffen werden kann.

Die Computer sollten über Wi-Fi netzwerk statt über ein Ethernetkabel verfügen. Computer mit einem Ethernetkabel verfügen nicht über genaue Standortinformationen.

Messbeispiele und Bürostandorte sollten 24 Stunden nach Erfüllen dieser Voraussetzungen angezeigt werden.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Hinzufügen von Speicherorten und Bereitstellen von LAN-Subnetzinformationen

Für diese Option sind weder Windows Location Services noch Wi-Fi erforderlich. Ihre OneDrive für #A0 muss auf dem neuesten Stand sein und auf jedem Computer am Standort installiert sein.

Sie müssen auch Speicherorte auf der Admin Center-Netzwerkverbindungsseite hinzufügen oder diese aus einer CSV-Datei importieren. Die hinzugefügten Speicherorte müssen Ihre Office -LAN-Subnetzinformationen enthalten.

Da Sie die Standorte hinzufügen, können mehrere Büros innerhalb einer Stadt definiert sein.

Alle Testmessungen von Clientcomputern umfassen die LAN-Subnetzinformationen, die mit den eingegebenen Details zum Bürostandort korreliert sind. Messbeispiele und Bürostandorte sollten 24 Stunden nach Erfüllen dieser Voraussetzungen angezeigt werden.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Manuelles Sammeln von Testberichten mit dem Microsoft 365-Netzwerkverbindungstesttool

Für diese Option müssen Sie eine Person an jedem Standort identifizieren. Bitten Sie sie, zum [Microsoft 365-Netzwerkverbindungstest](https://connectivity.office.com) auf einem Windows-Computer zu navigieren, auf dem sie über Administratorberechtigungen verfügen. Auf der Website müssen sie sich bei ihrem Office 365-Konto für dieselbe Organisation anmelden, für die Sie die Ergebnisse sehen möchten. Anschließend sollten sie auf **Test ausführen klicken.** Während des Tests gibt es eine heruntergeladene Konnektivitätstest-EXE. Sie müssen dies auch öffnen und ausführen. Sobald die Tests abgeschlossen sind, wird das Testergebnis in Office 365 hochgeladen.

Testberichte sind mit einem Speicherort verknüpft, wenn sie mit LAN-Subnetzinformationen hinzugefügt wurden, andernfalls werden sie nur am Ortsstandort angezeigt.

Messbeispiele und Bürostandorte sollten 2 bis 3 Minuten nach Abschluss eines Testberichts angezeigt werden. Weitere Informationen finden Sie unter [Microsoft 365 Network Connectivity Test (Preview)](office-365-network-mac-perf-onboarding-tool.md).

## <a name="how-do-i-use-this-information"></a>Wie verwende ich diese Informationen?

**Netzwerkeinblicke,** deren zugehörige Leistungsempfehlungen und Netzwerkbewertungen sollen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen. Jeder Einblick enthält Details zu den Leistungsmerkmalen für ein bestimmtes häufiges Problem für jeden geografischen Standort, an dem Benutzer auf Ihren Mandanten zugreifen. **Leistungsempfehlungen** für jede Netzwerkeinblick bieten spezifische Änderungen an der Netzwerkarchitektur, die Sie vornehmen können, um die Benutzerfreundlichkeit im Zusammenhang mit der Microsoft 365-Netzwerkkonnektivität zu verbessern. Die Netzwerkbewertung zeigt, wie sich die Netzwerkkonnektivität auf die Benutzerfreundlichkeit aus wirkt und ermöglicht einen Vergleich verschiedener Netzwerkverbindungen mit Benutzerstandorten.

**Netzwerkbewertungen** verwerten ein Aggregat aus vielen Netzwerkleistungsmetriken in einer Momentaufnahme der Integrität Ihres Unternehmensnetzwerks, dargestellt durch einen Punktwert zwischen 0 und 100. Netzwerkbewertungen sind sowohl auf den gesamten Mandanten als auch auf jeden geografischen Standort begrenzt, von dem aus Benutzer eine Verbindung mit Ihrem Mandanten herstellen, und bieten Microsoft 365-Administratoren eine einfache Möglichkeit, sofort eine Gestalt des Netzwerkzustands des Unternehmens zu erfassen und schnell einen detaillierten Bericht für jeden globalen Bürostandort zu erstellen.

Komplexe Unternehmen mit mehreren Bürostandorten und nicht trivialen Netzwerkperimeterarchitekturen können von diesen Informationen profitieren, entweder während des anfänglichen Onboardings bei Microsoft 365 oder um probleme mit der Netzwerkleistung zu beheben, die bei der Nutzungssteigerung festgestellt wurden. Dies ist in der Regel nicht erforderlich für kleine Unternehmen, die Microsoft 365 verwenden, oder für Unternehmen, die bereits über einfache und direkte Netzwerkkonnektivität verfügen. Unternehmen mit mehr als 500 Benutzern und mehreren Bürostandorten werden voraussichtlich am meisten davon profitieren.

>[!IMPORTANT]
>Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die im Featurevorschauprogramm registriert wurden.

## <a name="enterprise-network-connectivity-challenges"></a>Herausforderungen bei der Netzwerkkonnektivität in Unternehmen

> [!div class="mx-imgBorder"]
> ![Kundennetzwerk in die Cloud](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Viele Unternehmen verfügen über Netzwerkperimeterkonfigurationen, die im Laufe der Zeit gewachsen sind und in erster Linie für den Zugriff auf die Internetwebsite von Mitarbeitern ausgelegt sind, bei denen die meisten Websites im Voraus nicht bekannt sind und nicht vertrauenswürdig sind. Der vorherrschende und notwendige Fokus liegt auf der Vermeidung von Schadsoftware und Angelangriffen von diesen unbekannten Websites. Diese Netzwerkkonfigurationsstrategie kann zwar aus Sicherheitsgründen hilfreich sein, aber zu einer Beeinträchtigung der Leistung und Benutzerfreundlichkeit von Microsoft 365 führen.

## <a name="how-we-can-solve-these-challenges"></a>Wie wir diese Herausforderungen lösen können

Unternehmen können die allgemeine Benutzerfreundlichkeit verbessern und ihre Umgebung schützen, indem sie [die Office 365-Konnektivitätsprinzipien](https://aka.ms/pnc) und das Netzwerkkonnektivitätsfeature für Microsoft 365 Admin Center verwenden. In den meisten Fällen hat das Folgen dieser allgemeinen Prinzipien erhebliche positive Auswirkungen auf die Wartezeit der Endbenutzer, die Dienstzuverlässigkeit und die Gesamtleistung von Microsoft 365.

Microsoft wird manchmal aufgefordert, Probleme mit der Netzwerkleistung mit Microsoft 365 für große Unternehmenskunden zu untersuchen, und diese haben häufig eine Ursache im Zusammenhang mit der Netzwerkperimeterinfrastruktur der Kunden. Wenn eine häufige Ursache eines Kundennetzwerkperimeterproblems gefunden wird, versuchen wir, einfache Testmessungen zu identifizieren, die es identifizieren. Ein Test mit einem Messschwellenwert, der ein bestimmtes Problem identifiziert, ist wertvoll, da wir dieselbe Messung an jedem Beliebigen Ort testen, bestimmen können, ob diese Hauptursache vorhanden ist, und sie als Netzwerkinblick mit dem Administrator teilen können.

Einige Netzwerkeinblicke deuten lediglich auf ein Problem hin, das weiter untersucht werden muss. Eine Netzwerkuntersuchung, bei der wir über genügend Tests verfügen, um eine bestimmte Korrekturaktion zur Behebung der Hauptursache zu zeigen, wird als empfohlene Aktion **aufgeführt.** Diese Empfehlungen, die auf Livemetriken basieren, die Werte anzeigen, die außerhalb eines vordefinierten Schwellenwerts liegen, sind viel wertvoller als allgemeine Empfehlungen zu bewährten Verfahren, da sie spezifisch für Ihre Umgebung sind und die tatsächliche Verbesserung zeigen, sobald die empfohlenen Änderungen vorgenommen wurden.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Übersicht über die Netzwerkkonnektivität im Microsoft 365 Admin Center

Microsoft verfügt über vorhandene Netzwerkmessungen von mehreren Office-Desktop- und Webclients, die den Betrieb von Microsoft 365 unterstützen. Diese Messungen werden nun verwendet, um Einblicke in den Entwurf  der Netzwerkarchitektur und eine Netzwerkbewertung zu erhalten, die auf der Seite Netzwerkkonnektivität im Microsoft 365 Admin Center angezeigt werden.

Standardmäßig identifizieren ungefähre Standortinformationen, die den Netzwerkmessungen zugeordnet sind, die Stadt, in der sich Clientgeräte befinden. Die Netzwerkbewertung an jedem Standort wird mit Farbe angezeigt, und die relative Anzahl der Benutzer an jedem Standort wird durch die Größe des Kreises dargestellt.

> [!div class="mx-imgBorder"]
> ![Übersichtskarte für Netzwerkeinblicke](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

Auf der Übersichtsseite wird auch die Netzwerkbewertung für den Kunden als gewichteter Durchschnitt für alle Bürostandorte angezeigt.

> [!div class="mx-imgBorder"]
> ![Netzwerkbewertung](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Sie können eine Tabellenansicht der Speicherorte anzeigen, an denen sie auf der Registerkarte Speicherorte gefiltert, sortiert und bearbeitet werden können. Standorte mit bestimmten Empfehlungen können auch eine geschätzte potenzielle Latenzverbesserung enthalten. Dies wird berechnet, indem die mediane Wartezeit der Benutzer Ihrer Organisation am Standort und die mediane Latenz für alle Organisationen in derselben Stadt subtrahiert werden.

> [!div class="mx-imgBorder"]
> ![Speicherorte für Netzwerkeinblicke](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Zusammenfassung und Einblicke in die Leistung eines bestimmten Office-Standortnetzwerks

Wenn Sie einen Bürostandort auswählen, wird eine standortspezifische Zusammenfassungsseite geöffnet, auf der Details des Netzwerkresses angezeigt werden, der anhand von Messungen für den jeweiligen Bürostandort identifiziert wurde.

> [!div class="mx-imgBorder"]
> ![Details zu Netzwerkeinblicken nach Standort](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Eine Karte des Umkreisnetzwerks für Die Benutzer Ihrer Organisation am Standort wird mit einigen oder allen dieser Elemente angezeigt:

- **Office-Standort** – Der Bürostandort für die Seite, auf der Sie sich befinden
- **Netzwerkperimeter** : Der Speicherort der Quell-IP-Adresse für Verbindungen vom Bürostandort. Dies hängt von der Genauigkeit von Geo-IP-Standortdatenbanken ab.
- **Optimale Exchange-Dienst-Eingangstür** – Eine der empfohlenen Fronttüren des Exchange-Diensts, mit der Benutzer an diesem Bürostandort eine Verbindung herstellen sollten
- **Suboptimale Exchange-Eingangstür** – Eine Fronttür des Exchange-Diensts, mit der Benutzer verbunden sind, wird jedoch nicht empfohlen
- **Optimale SharePoint-Dienst-Eingangstür** – Eine der empfohlenen Fronttüren des SharePoint-Diensts, mit der Benutzer an diesem Bürostandort eine Verbindung herstellen sollten
- **Suboptimale SharePoint-Dienst-Eingangstür** – Eine Fronttür des SharePoint-Diensts, mit der Benutzer verbunden sind, wird jedoch nicht empfohlen.
- **DNS-rekursiver Resolverserver** : Der Speicherort aus einer Geo-IP-Datenbank des erkannten rekursiven DNS-Resolvers, der für Exchange Online verwendet wird (sofern verfügbar)
- **Ihr Proxyserver** – Der Speicherort aus einer geo-IP-Datenbank des erkannten Proxyservers (sofern verfügbar) 

Die Zusammenfassungsseite des Standorts zeigt außerdem die Netzwerkbewertung des Standorts, den Netzwerkbewertungsverlauf, einen Vergleich der Standortbewertung mit anderen Kunden in derselben Stadt sowie eine Liste spezifischer Einblicke und Empfehlungen, die Sie zur Verbesserung der Netzwerkleistung und Zuverlässigkeit unternehmen können.

Vergleiche zwischen Kunden in derselben Stadt basieren auf der Erwartung, dass alle Kunden gleichen Zugriff auf Netzwerkdienstanbieter, Telekommunikationsinfrastruktur und in der Nähe von Microsoft-Netzwerkpunkten haben.

Auf der Registerkarte Details auf der Seite Bürostandort werden die spezifischen Messergebnisse angezeigt, die verwendet wurden, um Einblicke, Empfehlungen und die Netzwerkbewertung zu erhalten. Dies wird bereitgestellt, damit Netzwerktechniker die Empfehlungen überprüfen und alle Einschränkungen oder Besonderheiten in ihrer Umgebung überprüfen können.

> [!div class="mx-imgBorder"]
> ![Standortspezifische Details](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="csv-import-for-lan-subnet-office-locations"></a>CSV-Import für STANDORTE von LAN-Subnetzbüros

Für die Identifikation von LAN-Subnetzbüros müssen Sie jeden Standort im Voraus hinzufügen. Anstatt einzelne Bürostandorte auf der **Registerkarte** Speicherorte zu hinzufügen, können Sie sie aus einer CSV-Datei importieren. Sie können diese Daten möglicherweise von anderen Orten abrufen, die Sie gespeichert haben, z. B. das Anrufqualitätsdashboard oder Active Directory-Websites und -Dienste.

In der CSV-Datei wird ein gefundener Ort in der Spalte userEntered als leer angezeigt, und ein manuell hinzugefügter Bürostandort wird als 1 angezeigt.

1. Klicken Sie im _Hauptfenster Konnektivität mit Microsoft 365_ auf die Registerkarte **Speicherorte.**

1. Klicken Sie **auf die** Schaltfläche Importieren direkt über der Liste der Speicherorte. Das **Flyout "Office-Speicherorte** importieren" wird angezeigt.

   > [!div class="mx-imgBorder"]
   > ![CSV-Importnachricht](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Klicken Sie auf den Link Aktuelle **Bürostandorte herunterladen (CSV),** um die Liste der aktuellen Speicherorte in eine CSV-Datei zu exportieren und sie auf ihrer lokalen Festplatte zu speichern. Dadurch erhalten Sie eine ordnungsgemäß formatierte CSV mit Spaltenüberschriften, denen Sie Speicherorte hinzufügen können. Sie können die vorhandenen exportierten Speicherorte so be lassen, wie sie sind. Sie werden beim Importieren der aktualisierten CSV nicht dupliziert. Wenn Sie die Adresse eines vorhandenen Speicherorts ändern möchten, wird sie beim Importieren der CSV aktualisiert. Die Adresse einer erkannten Stadt kann nicht geändert werden.

1. Öffnen Sie die CSV, und fügen Sie Ihre Speicherorte hinzu, indem Sie die folgenden Felder in einer neuen Zeile für jeden Speicherort ausfüllen, den Sie hinzufügen möchten. Lassen Sie alle anderen Felder leer. Werte, die Sie in andere Felder eingeben, werden ignoriert.

   1. **userEntered** (erforderlich): Muss 1 für einen neuen Office-Standort des LAN-Subnetzes sein
   1. **Adresse** (erforderlich): Die physische Adresse des Büros
   1. **Latitude** (optional): Aufgefüllt aus Bing-Karten-Suche der Adresse, wenn leer
   1. **Längengrad** (optional): Aus Bing aufgefüllte Karten-Suche der Adresse, wenn leer
   1. **Egress-IP-Adressbereiche 1-5** (optional): Geben Sie für jeden Bereich den Leitungsnamen ein, gefolgt von einer leer getrennten Liste gültiger IPv4- oder IPv6-CIDR-Adressen. Diese Werte werden verwendet, um mehrere Bürostandorte zu unterscheiden, an denen Sie dieselben LAN-Subnetz-IP-Adressen verwenden. Alle Egress-IP-Adressbereiche müssen die Netzwerkgröße /24 aufweisen, und der /24-Bereich ist nicht in der Eingabe enthalten.
   1. **LanIps** (erforderlich): Listet die an diesem Standort verwendeten LAN-Subnetzbereiche auf. LAN-Subnetz-IDs müssen über eine CIDR-Netzwerkgröße verfügen, wobei die Netzwerkgröße zwischen /8 und /29 liegen kann. Mehrere LAN-Subnetzbereiche können durch ein Komma oder ein Semikolon getrennt werden.
   
1. Wenn Sie Ihre Bürostandorte hinzugefügt und die Datei gespeichert haben, klicken Sie auf die Schaltfläche **Durchsuchen** neben dem **Feld Abgeschlossen** hochladen, und wählen Sie die gespeicherte CSV-Datei aus.

1. Die Datei wird automatisch überprüft. Wenn Überprüfungsfehler auftreten, wird die Fehlermeldung Angezeigt: Es gibt einige Fehler _in der Importdatei. Überprüfen Sie die Fehler, korrigieren Sie die Importdatei, und versuchen Sie es dann erneut._ Klicken Sie auf den **Link Fehlerdetails öffnen** für eine Liste bestimmter Feldüberprüfungsfehler.

   > [!div class="mx-imgBorder"]
   > ![Fehlermeldung zum CSV-Import](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Wenn die Datei keine Fehler enthält, wird die Meldung _Der Bericht ist bereit angezeigt. X-Speicherorte zum Hinzufügen und zu aktualisierende x-Speicherorte gefunden._ Klicken Sie auf **die Schaltfläche Importieren,** um die CSV hochzuladen.

   > [!div class="mx-imgBorder"]
   > ![CSV-importbereite Nachricht](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="what-is-a-microsoft-365-service-front-door"></a>Was ist eine Microsoft 365-Dienst-Eingangstür?

Die Microsoft 365-Dienst-Eingangstür ist ein Einstiegspunkt im globalen Netzwerk von Microsoft, in dem Office-Clients und -Dienste ihre Netzwerkverbindung beenden. Für eine optimale Netzwerkverbindung mit Microsoft 365 wird empfohlen, dass Ihre Netzwerkverbindung mit der nächsten Microsoft 365-Eingangstür beendet wird.

>[!NOTE]
>Die Microsoft 365-Dienst-Eingangstür hat keine direkte Beziehung zum Azure Front Door Service-Produkt, das im Azure Marketplace verfügbar ist.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Was ist eine optimale Microsoft 365-Service-Eingangstür?

Eine optimale Microsoft 365-Service-Eingangstür ist eine, die Ihrem Netzwerkeingang am nächsten ist, im Allgemeinen in Ihrer Stadt oder Ihrer U-Bahn-Region. Verwenden Sie [das Microsoft 365-Konnektivitätstesttool (Vorschau),](office-365-network-mac-perf-onboarding-tool.md) um den Standort Ihrer verwendeten Microsoft 365-Dienst-Eingangstür und die optimale Service-Eingangstür zu bestimmen. Wenn das Tool bestimmt, dass Ihre in-Use-Fronttür optimal ist, verbinden Sie sich optimal mit dem globalen Netzwerk von Microsoft.

### <a name="what-is-an-internet-egress-location"></a>Was ist ein Internet-Ausgangsspeicherort?

Der Internetaustrittsspeicherort ist der Ort, an dem Ihr Netzwerkdatenverkehr Ihr Unternehmensnetzwerk verlässt und eine Verbindung mit dem Internet herstellt. Dies wird auch als Standort identifiziert, an dem Sie über ein Nat-Gerät (Network Address Translation) verfügen und in der Regel eine Verbindung mit einem Internetdienstanbieter (Internet Service Provider, ISP) herstellen. Wenn sie einen langen Abstand zwischen Ihrem Standort und Ihrem Internet-Ausgangsstandort sehen, kann dies auf einen erheblichen WAN-Backhaul hinweisen.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 Network Insights (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365-Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365 Connectivity Test Tool (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
