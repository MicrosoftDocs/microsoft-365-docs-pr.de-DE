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
ms.openlocfilehash: 976059e1469861ea28b2a94b84e373119935fb20
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145391"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a>Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)

Das Microsoft 365 Admin Center enthält jetzt aggregierte Metriken für die Netzwerkkonnektivität, die von Ihrem Microsoft 365-Mandanten erfasst wurden und nur von Verwaltungsbenutzern in Ihrem Mandanten angezeigt werden können.

> [!div class="mx-imgBorder"]
> ![Tool zum Testen der Netzwerkkonnektivität](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**Netzwerkbewertungen** und **Netzwerkeinblicke** werden im Microsoft 365 Admin Center unter **"Integritätsbewertung" | Konnektivität**.

> [!div class="mx-imgBorder"]
> ![Seite "Netzwerkleistung"](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>Das Testtool für die Netzwerkkonnektivität unterstützt Mandanten in WW Commercial und Deutschland, aber nicht GCC Moderate, GCC High, DoD oder China.

Wenn Sie zum ersten Mal zur Seite "Netzwerkleistung" navigieren, wird ein Übersichtsbereich mit einer Karte der globalen Netzwerkleistung, einer Netzwerkbewertung für den gesamten Mandanten und einer Liste aktueller Probleme angezeigt. Aus der Übersicht können Sie einen Drilldown erstellen, um bestimmte Metriken und Probleme der Netzwerkleistung nach Standort anzuzeigen. Weitere Informationen finden Sie im [Microsoft 365 Admin Center](#network-connectivity-overview-in-the-microsoft-365-admin-center)im Überblick über die Netzwerkleistung.

Möglicherweise werden Sie aufgefordert, im Namen Ihrer Organisation an der öffentlichen Vorschau für dieses Feature teil zu nehmen. Die Annahme ist in der Regel sofort erfolgt, und dann wird die Seite mit der Netzwerkverbindung angezeigt. 

Beim Navigieren zur Seite "Netzwerkkonnektivität" wird ein Übersichtsbereich mit einer Karte der globalen Netzwerkleistung, einer Netzwerkbewertung für den gesamten Mandanten und einer Liste aktueller Probleme angezeigt. Um auf diese Seite zugreifen zu können, müssen Sie ein Administrator für die Organisation in Microsoft 365 sein. Die Administratorrolle "Berichtsleseprogramm" hat Lesezugriff auf diese Informationen. Zum Konfigurieren von Standorten und anderen Elementen der Netzwerkkonnektivität muss ein Administrator Teil einer Serveradministratorrolle sein, z. B. der Administratorrolle "Dienstunterstützung". Aus der Übersicht können Sie einen Drilldown erstellen, um bestimmte Metriken und Probleme der Netzwerkleistung nach Standort anzuzeigen. Weitere Informationen finden Sie in [der Übersicht über die Netzwerkkonnektivität im Microsoft 365 Admin Center.](#network-connectivity-overview-in-the-microsoft-365-admin-center)

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Voraussetzungen für die Bewertung der Netzwerkkonnektivität

Um zu beginnen, aktivieren Sie Ihre Standort-Opt-In-Einstellung, um automatisch Daten von Geräten mit Windows Location Services zu sammeln, zu Ihrer Standortliste zu wechseln, um Standortdaten hinzuzufügen oder hochzuladen, oder führen Sie den Microsoft 365-Netzwerkverbindungstest von Ihren Bürostandorten aus aus. Während die Netzwerkkonnektivität organisationsweit ausgewertet werden kann, müssen für bestimmte Bürostandorte Verbesserungen am Netzwerkentwurf vorgenommen werden. Netzwerkverbindungsinformationen werden für jeden Bürostandort bereitgestellt, sobald diese Standorte ermittelt werden können. Es gibt drei Optionen zum Abrufen von Netzwerkbewertungen von Ihren Bürostandorten:

### <a name="1-enable-windows-location-services"></a>1. Aktivieren von Windows Location Services

Für diese Option müssen an jedem Bürostandort mindestens zwei Computer ausgeführt werden, die die Voraussetzungen unterstützen. OneDrive für **Windows, Version 19.232** oder höher, muss auf jedem Computer installiert sein. Weitere Informationen zu #A0 finden Sie in den [OneDrive-Versionshinweisen.](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0) Netzwerkmessungen sollen in naher Zukunft in anderen Office 365-Clientanwendungen hinzugefügt werden.

Der Windows Location Service muss auf den Computern zugestimmt werden. Sie können dies testen, indem **Sie** die Karten-App ausführen und sich selbst suchen. Sie kann auf einem einzelnen Computer mit der **Einstellungseinstellung aktiviert | Datenschutzrichtlinien | Speicherort,** an dem die Einstellung _"Apps den Zugriff auf Ihren Standort erlauben"_ aktiviert sein muss. Die Zustimmung von Windows Location Services kann auf PCs mithilfe von MDM oder Gruppenrichtlinien mit der Einstellung _LetAppsAccessLocation bereitgestellt werden._

Sie müssen mit dieser Methode keine Standorte im Admin Center hinzufügen, da sie automatisch in der Stadtauflösung identifiziert werden. Sie können nicht mehrere Bürostandorte innerhalb einer Stadt mithilfe von Windows Location Services anzeigen. Standortinformationen werden auch vor dem Hochladen auf die nächsten 300 Meter gerundet, damit auf genauere Standortinformationen nicht zugegriffen werden kann.

Die Computer sollten über Wi-Fi netzwerk statt über ein Ethernetkabel verfügen. Computer mit einem Ethernetkabel verfügen nicht über genaue Standortinformationen.

Messbeispiele und Bürostandorte sollten 24 Stunden nach Erfüllen dieser Voraussetzungen angezeigt werden.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Hinzufügen von Standorten und Bereitstellen von INFORMATIONEN zum LAN-Subnetz

Für diese Option sind weder Windows Location Services noch Wi-Fi erforderlich. OneDrive für Windows, Version **20.161** oder höher, muss auf jedem Computer am Standort installiert sein.

Sie müssen auch Speicherorte auf der Seite "Admin Center-Netzwerkkonnektivität" hinzufügen oder diese aus einer CSV-Datei importieren. Die hinzugefügten Standorte müssen Ihre Office-LAN-Subnetzinformationen enthalten.

Da Sie die Standorte hinzufügen, können Sie mehrere Büros innerhalb einer Stadt definieren.

Alle Testmessungen von Clientcomputern enthalten die LAN-Subnetzinformationen, die mit den eingegebenen Bürostandortdetails korreliert sind. Messbeispiele und Bürostandorte sollten 24 Stunden nach Erfüllen dieser Voraussetzungen angezeigt werden.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Manuelles Sammeln von Testberichten mit dem Microsoft 365-Netzwerkverbindungstesttool

Für diese Option müssen Sie eine Person an jedem Standort identifizieren. Bitten Sie sie, zum [Microsoft 365-Netzwerkverbindungstest](https://connectivity.office.com) auf einem Windows-Computer zu navigieren, auf dem sie über Administratorberechtigungen verfügen. Auf der Website müssen sie sich bei ihrem Office 365-Konto für dieselbe Organisation anmelden, in der Sie die Ergebnisse sehen möchten. Anschließend sollten sie auf **"Test ausführen" klicken.** Während des Tests gibt es eine heruntergeladene Verbindungstest-EXE. Sie müssen dies auch öffnen und ausführen. Sobald die Tests abgeschlossen sind, wird das Testergebnis in Office 365 hochgeladen.

Testberichte sind mit einem Standort verknüpft, wenn sie mit Informationen zum LAN-Subnetz hinzugefügt wurden, andernfalls werden sie nur am Standort der Stadt angezeigt.

Messbeispiele und Bürostandorte sollten 2-3 Minuten nach Abschluss eines Testberichts angezeigt werden. Weitere Informationen finden Sie unter [Microsoft 365-Netzwerkkonnektivitätstest (Vorschau).](office-365-network-mac-perf-onboarding-tool.md)

## <a name="how-do-i-use-this-information"></a>Wie verwende ich diese Informationen?

**Netzwerkeinblicke,** zugehörige Leistungsempfehlungen und Netzwerkbewertungen sollen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen. Jeder Einblick enthält Details zu den Leistungsmerkmalen für ein bestimmtes häufiges Problem für jeden geografischen Standort, an dem Benutzer auf Ihren Mandanten zugreifen. **Leistungsempfehlungen** für jeden Netzwerkeinblick bieten spezifische Änderungen an der Netzwerkarchitektur, die Sie vornehmen können, um die Benutzerfreundlichkeit im Zusammenhang mit der Microsoft 365-Netzwerkkonnektivität zu verbessern. Die Netzwerkbewertung zeigt, wie sich die Netzwerkkonnektivität auf die Benutzererfahrung aus wirkt, sodass verschiedene Netzwerkverbindungen für Benutzerstandorte verglichen werden können.

**Netzwerkbewertungen** enthalten ein Aggregat aus vielen Metriken zur Netzwerkleistung in einer Momentaufnahme des Unternehmensnetzwerkzustands, dargestellt durch einen Punktwert zwischen 0 und 100. Netzwerkbewertungen sind sowohl auf den gesamten Mandanten als auch auf jeden geografischen Standort, von dem aus Benutzer eine Verbindung mit Ihrem Mandanten herstellen, begrenzt, wodurch Microsoft 365-Administratoren eine einfache Möglichkeit erhalten, sofort einen Einblick in den Netzwerkzustand des Unternehmens zu erhalten und schnell einen detaillierten Bericht für jeden globalen Bürostandort zu erhalten.

Komplexe Unternehmen mit mehreren Bürostandorten und nicht triviale Netzwerkperimeterarchitekturen können von diesen Informationen entweder während des anfänglichen Onboardings in Microsoft 365 oder zur Behebung von Problemen mit der Netzwerkleistung profitieren, die bei der Zunahme der Nutzung erkannt wurden. Dies ist in der Regel nicht erforderlich für kleine Unternehmen, die Microsoft 365 verwenden, oder für Unternehmen, die bereits über einfache und direkte Netzwerkkonnektivität verfügen. Unternehmen mit mehr als 500 Benutzern und mehreren Bürostandorten werden voraussichtlich am meisten profitieren.

>[!IMPORTANT]
>Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die für das Featurevorschauprogramm registriert wurden.

## <a name="enterprise-network-connectivity-challenges"></a>Herausforderungen bei der Netzwerkkonnektivität in Unternehmen

> [!div class="mx-imgBorder"]
> ![Kundennetzwerk in cloudbasiertes Netzwerk](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Viele Unternehmen verfügen über Netzwerkperimeterkonfigurationen, die sich im Laufe der Zeit entwickelt haben und in erster Linie darauf ausgelegt sind, den Zugriff auf die Internetwebsite der Mitarbeiter zu unterstützen, bei denen die meisten Websites im Voraus nicht bekannt sind und nicht vertrauenswürdig sind. Der um- und notwendige Fokus liegt auf der Vermeidung von Schadsoftware und Angriffen durch diese unbekannten Websites. Diese Netzwerkkonfigurationsstrategie ist zwar aus Sicherheitsgründen hilfreich, kann jedoch zu einer Beeinträchtigung der Leistung und Benutzerfreundlichkeit von Microsoft 365 führen.

## <a name="how-we-can-solve-these-challenges"></a>Wie wir diese Herausforderungen lösen können

Unternehmen können die allgemeine Benutzerfreundlichkeit verbessern und ihre Umgebung schützen, indem sie die Prinzipien der [Office 365-Konnektivität](https://aka.ms/pnc) und das Microsoft 365 Admin Center-Netzwerkkonnektivitätsfeature verwenden. In den meisten Fällen hat das Folgen dieser allgemeinen Prinzipien erhebliche positive Auswirkungen auf die Wartezeit der Endbenutzer, die Dienstzuverlässigkeit und die Gesamtleistung von Microsoft 365.

Microsoft wird manchmal aufgefordert, Probleme mit der Netzwerkleistung mit Microsoft 365 für Große Unternehmenskunden zu untersuchen, und diese haben häufig eine Ursache im Zusammenhang mit der Netzwerkperimeterinfrastruktur der Kunden. Wenn eine häufige Ursache für ein Problem mit dem Netzwerkperimeter eines Kunden gefunden wird, versuchen wir, einfache Testmessungen zu identifizieren, die es identifizieren. Ein Test mit einem Messschwellenwert, der ein bestimmtes Problem identifiziert, ist nützlich, da wir dieselbe Messung an einem beliebigen Ort testen, bestimmen können, ob diese Ursache dort vorhanden ist, und sie als Netzwerkinblick für den Administrator freigeben können.

Einige Netzwerkeinblicke weisen lediglich auf ein Problem hin, das weiter untersucht werden muss. Ein Netzwerk einblick, bei dem wir genügend Tests haben, um eine bestimmte Korrekturaktion zur Behebung der Hauptursache zu zeigen, wird als empfohlene **Aktion aufgeführt.** Diese Empfehlungen, basierend auf Livemetriken, die Werte anzeigen, die einen vordefinierten Schwellenwert überschreiten, sind viel wertvoller als allgemeine Empfehlungen zu bewährten Vorgehensweisen, da sie für Ihre Umgebung spezifisch sind und die tatsächliche Verbesserung zeigen, sobald die empfohlenen Änderungen vorgenommen wurden.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Übersicht über die Netzwerkkonnektivität im Microsoft 365 Admin Center

Microsoft verfügt über vorhandene Netzwerkmessungen von mehreren Office-Desktop- und Webclients, die den Betrieb von Microsoft 365 unterstützen. Diese Messungen werden nun verwendet, um Einblicke in den Entwurf  der Netzwerkarchitektur und eine Netzwerkbewertung zu liefern, die auf der Seite "Netzwerkkonnektivität" im Microsoft 365 Admin Center angezeigt werden.

Standardmäßig geben die ungefähren Standortinformationen im Zusammenhang mit den Netzwerkmessungen die Stadt an, in der sich Clientgeräte befinden. Die Netzwerkbewertung an jedem Standort wird mit Farbe angezeigt, und die relative Anzahl von Benutzern an jedem Standort wird durch die Größe des Kreises dargestellt.

> [!div class="mx-imgBorder"]
> ![Übersichtskarte zu Netzwerkeinblicken](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

Auf der Übersichtsseite wird auch die Netzwerkbewertung für den Kunden als gewichteter Durchschnitt für alle Bürostandorte angezeigt.

> [!div class="mx-imgBorder"]
> ![Netzwerkbewertung](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Auf der Registerkarte "Speicherorte" können Sie eine Tabellenansicht der Speicherorte anzeigen, an denen sie gefiltert, sortiert und bearbeitet werden können. Standorte mit bestimmten Empfehlungen können auch eine geschätzte potenzielle Latenzverbesserung beinhalten. Dies wird berechnet, indem die Medianlatenz der Benutzer Ihrer Organisation am Standort und die mittlere Wartezeit für alle Organisationen in derselben Stadt subtrahiert werden.

> [!div class="mx-imgBorder"]
> ![Orte für Netzwerkeinblicke](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Spezifische Zusammenfassung und Einblicke in die Netzwerkleistung eines bestimmten Bürostandorts

Wenn Sie einen Bürostandort auswählen, wird eine standortspezifische Zusammenfassungsseite mit Details des Netzwerk-Ausgangs geöffnet, der anhand von Messungen für den jeweiligen Bürostandort identifiziert wurde.

> [!div class="mx-imgBorder"]
> ![Details zu Netzwerkeinblicken nach Standort](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Eine Karte des Umkreisnetzwerks für Die Benutzer Ihrer Organisation am Standort wird mit einigen oder allen dieser Elemente angezeigt:

- **Bürostandort** – Der Bürostandort für die Seite, auf der Sie sich befinden
- **Netzwerkumkreis** – Der Speicherort der Quell-IP-Adresse für Verbindungen vom Bürostandort. Dies hängt von der Genauigkeit der Geo-IP-Standortdatenbanken ab.
- **Optimale Front-Door des** Exchange-Diensts – eine der empfohlenen Front-Doors des Exchange-Diensts, mit der Benutzer an diesem Bürostandort eine Verbindung herstellen sollten
- **Unteroptimale Eingangstür von Exchange** – Eine Front-Door des Exchange-Diensts, mit der Benutzer verbunden sind, wird jedoch nicht empfohlen.
- **SharePoint optimaler Service -** Eine der empfohlenen Front-Doors des SharePoint-Diensts, mit dem Benutzer an diesem Bürostandort eine Verbindung herstellen sollten
- **SharePoint suboptimale Service-Front-Door** : Eine Front-Door des SharePoint-Diensts, mit der Benutzer verbunden sind, wird jedoch nicht empfohlen.
- **DNS recursive resolver server** – Der Standort aus einer Geo-IP-Datenbank des erkannten rekursiven DNS-Resolvers, der für Exchange Online verwendet wird (sofern verfügbar)
- **Ihr Proxyserver –** Der Standort aus einer Geo-IP-Datenbank des erkannten Proxyservers (sofern verfügbar) 

Auf der Seite mit der Zusammenfassung des Bürostandorts werden außerdem die Netzwerkbewertung des Standorts, der Netzwerkbewertungsverlauf, ein Vergleich der Bewertung dieses Standorts mit anderen Kunden in derselben Stadt sowie eine Liste bestimmter Einblicke und Empfehlungen angezeigt, die Sie zur Verbesserung der Netzwerkleistung und Zuverlässigkeit unternehmen können.

Vergleiche zwischen Kunden in derselben Stadt basieren auf der Erwartung, dass alle Kunden gleichen Zugriff auf Netzwerkdienstanbieter, Telekommunikationsinfrastruktur und in der Nähe von Microsoft-Netzwerkpunkten haben.

Auf der Registerkarte "Details" auf der Seite "Bürostandort" werden die spezifischen Messergebnisse angezeigt, die verwendet wurden, um Einblicke, Empfehlungen und die Netzwerkbewertung zu erhalten. Dies wird bereitgestellt, damit Netzwerktechniker die Empfehlungen überprüfen und einschränkungen oder Spezifisches in ihrer Umgebung eindingen können.

> [!div class="mx-imgBorder"]
> ![Standortspezifische Details](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="csv-import-for-lan-subnet-office-locations"></a>CSV-Import für Bürostandorte im LAN-Subnetz

Für die Identifizierung der LAN-Subnetz-Büros müssen Sie jeden Standort im Voraus hinzufügen. Anstatt einzelne Bürostandorte auf der **Registerkarte** "Speicherorte" hinzufügen, können Sie diese aus einer CSV-Datei importieren. Sie können diese Daten möglicherweise von anderen Orten abrufen, an denen Sie sie gespeichert haben, z. B. das Anrufqualitätsdashboard oder Active Directory-Standorte und -Dienste.

In der CSV-Datei wird ein ermittelter Ort in der Spalte "userEntered" als leer angezeigt, und ein manuell hinzugefügter Bürostandort wird als 1 angezeigt.

1. Klicken Sie im _Hauptfenster "Verbindung mit Microsoft 365"_ auf die Registerkarte **"Speicherorte".**

1. Klicken Sie direkt **über** der Standortliste auf die Schaltfläche "Importieren". Das **Flyout "Standorte importieren"** wird angezeigt.

   > [!div class="mx-imgBorder"]
   > ![CSV-Importnachricht](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Klicken Sie auf den Link zum Herunterladen der aktuellen Bürostandorte **(CSV),** um die aktuelle Speicherortliste in eine CSV-Datei zu exportieren und auf der lokalen Festplatte zu speichern. Dadurch erhalten Sie eine ordnungsgemäß formatierte CSV mit Spaltenüberschriften, der Sie Speicherorte hinzufügen können. Sie können die vorhandenen exportierten Speicherorte so be lassen, wie sie sind. Sie werden beim Importieren der aktualisierten CSV nicht dupliziert. Wenn Sie die Adresse eines vorhandenen Speicherorts ändern möchten, wird sie beim Importieren der CSV aktualisiert. Sie können die Adresse einer ermittelten Stadt nicht ändern.

1. Öffnen Sie die CSV, und fügen Sie Ihre Speicherorte hinzu, indem Sie die folgenden Felder in einer neuen Zeile für jeden Speicherort ausfüllen, den Sie hinzufügen möchten. Lassen Sie alle anderen Felder leer. Werte, die Sie in andere Felder eingeben, werden ignoriert.

   1. **userEntered** (erforderlich): Muss für einen neuen Standort eines LAN-Subnetzes 1 sein.
   1. **Adresse** (erforderlich): Die physische Adresse des Büros
   1. **Breitengrad** (optional): Ausgefüllt aus der Bing -Karten-Suche der Adresse, wenn leer
   1. **Längengrad** (optional): Aus Bing -Karten-Nachschlageplan der Adresse aufgefüllt, wenn leer
   1. **Austritts-IP-Adressbereiche 1 bis 5** (optional): Geben Sie für jeden Bereich den Leitungsnamen ein, gefolgt von einer Leerzeichen getrennten Liste gültiger IPv4- oder IPv6 CIDR-Adressen. Diese Werte werden verwendet, um mehrere Bürostandorte zu unterscheiden, an denen Sie dieselben LAN-Subnetz-IP-Adressen verwenden. Alle Ausgänge von IP-Adressbereichen müssen die Netzwerkgröße /24 aufweisen, und der /24-Bereich ist nicht in der Eingabe enthalten.
   1. **LanIps** (erforderlich): Listet die an diesem Standort verwendeten LAN-Subnetzbereiche auf. LAN-Subnetz-IDs müssen eine GRÖßE des CIDR-Netzwerks aufweisen, wobei die Netzwerkgröße zwischen /8 und /29 liegen kann. Mehrere LAN-Subnetzbereiche können durch ein Komma oder ein Semikolon getrennt werden.
   
1. Wenn Sie Ihre Bürostandorte hinzugefügt und  die Datei gespeichert  haben, klicken Sie auf die Schaltfläche "Durchsuchen" neben dem Feld "Fertig hochladen", und wählen Sie die gespeicherte CSV-Datei aus.

1. Die Datei wird automatisch überprüft. Wenn Überprüfungsfehler auftreten, wird die Fehlermeldung angezeigt, dass die Importdatei _einige Fehler enthält. Überprüfen Sie die Fehler, korrigieren Sie die Importdatei, und versuchen Sie es dann erneut._ Klicken Sie auf den **Link "Fehlerdetails öffnen",** um eine Liste mit bestimmten Feldüberprüfungsfehlern anzuzeigen.

   > [!div class="mx-imgBorder"]
   > ![Fehlermeldung für den CSV-Import](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Wenn die Datei keine Fehler enthält, wird die Meldung angezeigt, dass _der Bericht bereit ist. X-Speicherorte, die hinzugefügt werden müssen, und x zu aktualisierende Speicherorte gefunden._ Klicken Sie auf die **Schaltfläche "Importieren",** um die CSV hochzuladen.

   > [!div class="mx-imgBorder"]
   > ![Csv import ready message](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="what-is-a-microsoft-365-service-front-door"></a>Was ist eine Microsoft 365-Service-Eingangstür?

Die Microsoft 365-Dienst-Front-Door ist ein Einstiegspunkt im globalen Microsoft-Netzwerk, in dem die Netzwerkverbindung von Office-Clients und -Diensten beendet wird. Für eine optimale Netzwerkverbindung mit Microsoft 365 wird empfohlen, dass Ihre Netzwerkverbindung mit der nächstgelegenen Microsoft 365-Eingangstür beendet wird.

>[!NOTE]
>Microsoft 365-Service-Front-Door hat keine direkte Beziehung zum Azure Front Door Service-Produkt, das im Azure Marketplace verfügbar ist.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Was ist eine optimale Microsoft 365-Service-Front-Door?

Eine optimale Microsoft 365-Service-Front-Door ist eine, die Ihrem Netzwerkeingang am nächsten ist, in der Regel in Ihrer Stadt oder Ihrem Stadtbereich. Verwenden Sie [das Microsoft 365-Konnektivitätstesttool (Vorschau),](office-365-network-mac-perf-onboarding-tool.md) um den Standort Ihrer verwendeten Microsoft 365-Service-Front-Door und die optimale Service-Front-Door zu ermitteln. Wenn das Tool feststellt, dass Ihre einsatzf?nige Eingangstür optimal ist, können Sie sich optimal mit dem globalen Netzwerk von Microsoft verbinden.

### <a name="what-is-an-internet-egress-location"></a>Was ist ein Internet-Ausgangsspeicherort?

Der Internetausgangsstandort ist der Ort, an dem Ihr Netzwerkdatenverkehr Ihr Unternehmensnetzwerk verlässt und eine Verbindung mit dem Internet herstellt. Dies wird auch als Standort identifiziert, an dem Sie über ein Netzwerkadressenübersetzungsgerät (Network Address Translation, NAT) verfügen und in der Regel, an dem Sie eine Verbindung mit einem Internetdienstanbieter (Internet Service Provider, ISP) herstellen. Wenn ein langer Abstand zwischen Ihrem Standort und Ihrem Internetstandort angezeigt wird, kann dies auf eine erhebliche WAN-Backhaul hinweisen.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365-Netzwerkeinblicke (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365-Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365-Konnektivitätstesttool (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
