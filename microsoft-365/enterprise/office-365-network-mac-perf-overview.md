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
ms.openlocfilehash: 4f88b3ad5bf8f0c32059a26348a651a6024ad544
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245768"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a>Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)

Das Microsoft 365 Admin Center enthält nun aggregierte Netzwerkkonnektivitätsmetriken, die von Ihrem Microsoft 365-Mandanten erfasst wurden und nur von administrativen Benutzern in Ihrem Mandanten angezeigt werden können.

> [!div class="mx-imgBorder"]
> ![Testtool für Netzwerkkonnektivität](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**Netzwerkbewertungen** und **Netzwerkeinblicke** werden im Microsoft 365 Admin Center unter **Integritätsbewertung | Netzwerkkonnektivität**.

> [!div class="mx-imgBorder"]
> ![Seite "Netzwerkleistung"](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>Die Netzwerkkonnektivität im Admin Center unterstützt Mandanten in WW Commercial und Deutschland, aber nicht GCC Moderate, GCC High, DoD oder China.

Wenn Sie zum ersten Mal zur Netzwerkleistungsseite navigieren, müssen Sie Ihre Standorte konfigurieren, um die Karte der globalen Netzwerkleistung, eine Netzwerkbewertung, die auf den gesamten Mandanten begrenzt ist, den Prozentsatz Ihrer Remotebenutzer im Vergleich zu vor Ort sowie eine Liste der aktuellen Probleme anzuzeigen, um Maßnahmen zu ergreifen und/oder weitere Untersuchungen zu unternehmen. Im Übersichtsbereich können Sie einen Drilldown erstellen, um bestimmte Netzwerkleistungsmetriken und -probleme nach Standort anzuzeigen. Weitere Informationen finden Sie unter [Übersicht über die Netzwerkleistung im Microsoft 365 Admin Center](#network-connectivity-overview-in-the-microsoft-365-admin-center).

Möglicherweise werden Sie aufgefordert, im Namen Ihrer Organisation an der öffentlichen Vorschau für dieses Feature teil zu nehmen. Die Annahme erfolgt in der Regel sofort, danach wird die Seite "Netzwerkkonnektivität" angezeigt.

Um auf die Seite "Netzwerkkonnektivität" zu zugreifen, müssen Sie ein Administrator für die Organisation innerhalb Microsoft 365. Die Administratorrolle "Berichtsleser" hat Lesezugriff auf diese Informationen. Zum Konfigurieren von Speicherorten und anderen Elementen der Netzwerkkonnektivität muss ein Administrator Teil einer Serveradministratorrolle sein, z. B. der Administratorrolle Dienstunterstützung.

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Voraussetzungen für die Schätzung der Netzwerkkonnektivität

Aktivieren Sie die Einstellung standortanmelden, um automatisch Daten von Geräten mithilfe von Windows Location Services zu sammeln, wechseln Sie zu Ihrer Liste Standorte, um Standortdaten hinzuzufügen oder hochzuladen, oder führen Sie den Microsoft 365-Netzwerkverbindungstest von Ihren Bürostandorten aus aus. Während die Netzwerkkonnektivität in der gesamten Organisation ausgewertet werden kann, müssen für bestimmte Bürostandorte Verbesserungen des Netzwerkentwurfs vorgenommen werden. Netzwerkverbindungsinformationen werden für jeden Bürostandort bereitgestellt, sobald diese Standorte bestimmt werden können. Es gibt drei Optionen zum Abrufen von Netzwerkbewertungen von Ihren Bürostandorten:

### <a name="1-enable-windows-location-services"></a>1. Aktivieren Windows Standortdienste

Für diese Option müssen an jedem Bürostandort mindestens zwei Computer ausgeführt werden, die die Voraussetzungen unterstützen. OneDrive für Windows muss auf jedem Computer auf dem neuesten Stand sein und installiert sein. Weitere Informationen zu OneDrive Versionen finden Sie in den [OneDrive Versionshinweisen.](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0) Netzwerkmessungen sollen in naher Zukunft zu anderen Office 365 Clientanwendungen hinzugefügt werden.

Windows Der Standortdienst muss auf den Computern zugestimmt werden. Sie können dies testen, indem Sie die **Karten** ausführen und sich selbst suchen. Sie kann auf einem einzelnen Computer mit Einstellungen | **Datenschutz | Speicherort,** an dem die Einstellung _Apps den Zugriff auf Ihren_ Standort erlauben aktiviert sein muss. Windows Die Zustimmung von Location Services kann auf PCs mithilfe von MDM oder Gruppenrichtlinien mit der Einstellung _LetAppsAccessLocation bereitgestellt werden._

Sie müssen mit dieser Methode keine Standorte im Admin Center hinzufügen, da diese automatisch bei der Stadtauflösung identifiziert werden. Mehrere Bürostandorte innerhalb derselben Stadt werden nicht angezeigt, wenn sie Windows verwenden. Standortinformationen werden auf die nächsten 300 Meter um 300 Meter gerundet, sodass nicht auf genauere Standortinformationen zugegriffen wird.

Die Computer sollten über Wi-Fi netzwerk statt über ein Ethernetkabel verfügen. Computer mit einem Ethernetkabel verfügen nicht über genaue Standortinformationen.

Messbeispiele und Bürostandorte sollten 24 Stunden nach Erfüllen dieser Voraussetzungen angezeigt werden.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Hinzufügen von Speicherorten und Bereitstellen von LAN-Subnetzinformationen

Für diese Option sind weder Windows Standortdienste noch Wi-Fi erforderlich. Ihre OneDrive für Windows muss auf dem neuesten Stand sein und auf mindestens einem Computer am Standort installiert sein.

Sie müssen auch Speicherorte auf der Seite Speicherorte **hinzufügen** oder aus einer CSV-Datei importieren. Die hinzugefügten Speicherorte müssen Ihre Office -LAN-Subnetzinformationen enthalten.

Mit dieser Option können Sie mehrere Büros innerhalb einer Stadt definieren.

Alle Testmessungen von Clientcomputern umfassen die LAN-Subnetzinformationen, die mit den eingegebenen Details zum Bürostandort korreliert sind. Messbeispiele und Bürostandorte sollten 24 Stunden nach Erfüllen dieser Voraussetzungen angezeigt werden.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Manuelles Erfassen von Testberichten mit Microsoft 365 Netzwerkverbindungstesttool

Für diese Option müssen Sie eine Person an jedem Standort identifizieren. Bitten Sie sie, zu [Microsoft 365 Netzwerkverbindungstests](https://connectivity.office.com) auf einem computer Windows, auf dem sie über Administratorberechtigungen verfügen. Auf der Website müssen sie sich bei ihrem Office 365 für dieselbe Organisation anmelden, die Sie die Ergebnisse sehen möchten. Anschließend sollten sie auf **Test ausführen klicken.** Während des Tests gibt es eine heruntergeladene Konnektivitätstest-EXE. Sie müssen dies öffnen und ausführen. Sobald die Tests abgeschlossen sind, wird das Testergebnis in das Admin Center hochgeladen.

Testberichte sind mit einem Speicherort verknüpft, wenn sie mit LAN-Subnetzinformationen hinzugefügt wurden, andernfalls werden sie nur am Ortsstandort angezeigt.

Messbeispiele und Bürostandorte sollten 2 bis 3 Minuten nach Abschluss eines Testberichts angezeigt werden. Weitere Informationen finden Sie [unter Microsoft 365 Netzwerkverbindungstest (Vorschau).](office-365-network-mac-perf-onboarding-tool.md)

## <a name="how-do-i-use-this-information"></a>Wie verwende ich diese Informationen?

**Netzwerkeinblicke,** deren zugehörige Leistungsempfehlungen und Netzwerkbewertungen sollen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen. Jeder Einblick enthält Details zu den Leistungsmerkmalen für ein bestimmtes häufiges Netzwerkproblem für jeden geografischen Standort, an dem Benutzer auf Ihren Mandanten zugreifen. **Leistungsempfehlungen** für jeden Netzwerkeinblick bieten spezifische Änderungen an der Netzwerkarchitektur, die Sie vornehmen können, um die Benutzerfreundlichkeit im Zusammenhang mit Microsoft 365 zu verbessern. Die Netzwerkbewertung zeigt, wie sich die Netzwerkkonnektivität auf die Benutzerfreundlichkeit aus wirkt und ermöglicht einen Vergleich verschiedener Netzwerkverbindungen mit Benutzerstandorten.

**Netzwerkbewertungen** verwerten ein Aggregat aus vielen Netzwerkleistungsmetriken in einer Momentaufnahme der Integrität Ihres Unternehmensnetzwerks, dargestellt durch einen Punktwert zwischen 0 und 100. Netzwerkbewertungen sind sowohl auf den gesamten Mandanten als auch auf jeden geografischen Standort begrenzt, von dem aus Benutzer eine Verbindung mit Ihrem Mandanten herstellen. Dies bietet Microsoft 365-Administratoren eine einfache Möglichkeit, sofort eine Gestalt des Netzwerkzustands des Unternehmens zu erfassen und schnell einen detaillierten Bericht für jeden globalen Bürostandort zu erstellen.

Komplexe Unternehmen mit mehreren Bürostandorten und nicht trivialen Netzwerkperimeterarchitekturen können von diesen Informationen profitieren, entweder während ihres anfänglichen Onboardings zu Microsoft 365 oder um probleme mit der Netzwerkleistung zu beheben, die bei der Nutzungssteigerung festgestellt wurden. Dies ist in der Regel nicht erforderlich für kleine Unternehmen, die Microsoft 365 verwenden, oder für Unternehmen, die bereits über einfache und direkte Netzwerkkonnektivität verfügen. Unternehmen mit mehr als 500 Benutzern und mehreren Bürostandorten werden voraussichtlich am meisten davon profitieren.

>[!IMPORTANT]
>Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die im Featurevorschauprogramm registriert wurden.

## <a name="enterprise-network-connectivity-challenges"></a>Enterprise Herausforderungen bei der Netzwerkkonnektivität

> [!div class="mx-imgBorder"]
> ![Kundennetzwerk in die Cloud](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Viele Unternehmen verfügen über Netzwerkperimeterkonfigurationen, die im Laufe der Zeit gewachsen sind und in erster Linie für den Zugriff auf die Internetwebsite von Mitarbeitern ausgelegt sind, bei denen die meisten Websites im Voraus nicht bekannt sind und nicht vertrauenswürdig sind. Der vorherrschende und notwendige Fokus liegt auf der Vermeidung von Schadsoftware und Phishingangriffen von diesen unbekannten Websites. Diese Netzwerkkonfigurationsstrategie kann zwar aus Sicherheitsgründen hilfreich sein, aber zu einer Beeinträchtigung Microsoft 365 Benutzerleistung und Benutzerfreundlichkeit führen.

## <a name="how-we-can-solve-these-challenges"></a>Wie wir diese Herausforderungen lösen können

Unternehmen können die allgemeine Benutzerfreundlichkeit verbessern [](./microsoft-365-network-connectivity-principles.md) und ihre Umgebung schützen, indem sie Office 365 Konnektivitätsprinzipien und mithilfe des Microsoft 365 Admin Center-Netzwerkkonnektivitätsfeatures folgen. In den meisten Fällen hat das Folgen dieser allgemeinen Prinzipien erhebliche positive Auswirkungen auf die Wartezeit der Endbenutzer, die Dienstzuverlässigkeit und die Gesamtleistung Microsoft 365.

Microsoft wird manchmal aufgefordert, Probleme mit der Netzwerkleistung mit Microsoft 365 großunternehmenskunden zu untersuchen, und diese haben häufig eine Hauptursache im Zusammenhang mit der Netzwerkperimeterinfrastruktur des Kunden. Wenn eine häufige Ursache eines Kundennetzwerkperimeterproblems gefunden wird, versuchen wir, einfache Testmessungen zu identifizieren, die es identifizieren. Ein Test mit einem Messschwellenwert, der ein bestimmtes Problem identifiziert, ist wertvoll, da wir dieselbe Messung an jedem Beliebigen Ort testen, bestimmen können, ob diese Hauptursache vorhanden ist, und sie als Netzwerkinblick mit dem Administrator teilen können.

Einige Netzwerkeinblicke deuten lediglich auf ein Problem hin, das weiter untersucht werden muss. Eine Netzwerkuntersuchung, bei der wir über genügend Tests verfügen, um eine bestimmte Korrekturaktion zur Behebung der Hauptursache zu zeigen, wird als empfohlene Aktion **aufgeführt.** Diese Empfehlungen, die auf Livemetriken basieren, die Werte anzeigen, die außerhalb eines vordefinierten Schwellenwerts liegen, sind viel wertvoller als allgemeine Empfehlungen zu bewährten Verfahren, da sie spezifisch für Ihre Umgebung sind und die tatsächliche Verbesserung zeigen, sobald die empfohlenen Änderungen vorgenommen wurden.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Übersicht über die Netzwerkkonnektivität im Microsoft 365 Admin Center

Microsoft verfügt über vorhandene Netzwerkmessungen von Office Desktop- und Webclients, die den Betrieb von Microsoft 365. Diese Messungen werden nun verwendet, um Einblicke in den Entwurf  der Netzwerkarchitektur und eine Netzwerkbewertung zu erhalten, die auf der Seite Netzwerkkonnektivität im Microsoft 365 angezeigt werden.

Standardmäßig identifizieren ungefähre Standortinformationen, die den Netzwerkmessungen zugeordnet sind, die Stadt, in der sich Clientgeräte befinden. Die Netzwerkbewertung an jedem Standort wird mit Farbe angezeigt, und die relative Anzahl der Benutzer an jedem Standort wird durch die Größe des Kreises dargestellt.

> [!div class="mx-imgBorder"]
> ![Übersichtskarte für Netzwerkeinblicke](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

Auf der Übersichtsseite wird auch die Netzwerkbewertung für den Kunden als gewichteter Durchschnitt für alle Bürostandorte angezeigt.

> [!div class="mx-imgBorder"]
> ![Netzwerkbewertung](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Sie können eine Tabellenansicht der Speicherorte anzeigen, an denen sie auf der Registerkarte Speicherorte gefiltert, sortiert und bearbeitet **werden** können. Standorte mit bestimmten Empfehlungen können auch eine geschätzte potenzielle Latenzverbesserung enthalten. Dies wird berechnet, indem die mediane Wartezeit der Benutzer Ihrer Organisation am Standort und die mediane Latenz für alle Organisationen in derselben Stadt subtrahiert werden.

> [!div class="mx-imgBorder"]
> ![Speicherorte für Netzwerkeinblicke](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="remote-worker-assessment-and-user-connection-metrics"></a>Remotearbeitsbewertung und Benutzerverbindungsmetriken

Wir klassifizieren Netzwerkdatenverkehrsprotokolle als Remote- oder Benutzer vor Ort und zeigen deren Prozentsätze im Abschnitt Benutzerverbindungsmetriken im Übersichtsbereich an. Für Städte, in denen Sie Remotebenutzer haben, finden Sie beim Öffnen der Seite dieses Standorts die Standortbewertung für ein bestimmtes Remotenetzwerk. Die Liste der Standorte enthält sowohl Bürostandorte als auch Remotearbeitsorte, die gefiltert und sortiert werden können. Wir stellen die Bewertungsbewertung für Remotemitarbeiter mit Punktaufschlüsselung für Exchange, SharePoint und Teams.

Einblicke in das Netzwerk von Privatbenutzern werden auf Stadtebene aggregiert und gemeldet und sind auf Städte mit mindestens 5 Remotemitarbeitern beschränkt. Wir identifizieren nicht einzelne Mitarbeiter, die von zu Hause aus arbeiten.

Speicherorte werden automatisch als "onsite" oder "remote" klassifiziert. Sie haben jedoch die Möglichkeit, alle Ihre vor Ort abziehende IP-Adressen manuell ein eingeben, um eine 100 %-Klassifizierung sicherzustellen. Wenn Sie sich für diese Route entscheiden, müssen Sie das Kontrollkästchen Alle vor Ort abgehende **IP-Adressen** manuell eingeben im Flyout Locations Einstellungen aktivieren, nachdem Sie alle Ihre ausziehende IP-Adressen hinzugefügt haben. Wenn dies geschieht, werden alle Netzwerkdatenverkehrsprotokolle von ip-Ausgangsadressen, die Sie als "vor Ort" gekennzeichnet haben, immer als Büros klassifiziert, und jede andere abziehende IP-Adresse wird als Remote klassifiziert.

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Zusammenfassung und Einblicke in die Leistung eines bestimmten Office-Standortnetzwerks

Wenn Sie einen Bürostandort auswählen, wird eine standortspezifische Zusammenfassungsseite geöffnet, auf der Details des Netzwerkresses angezeigt werden, der anhand von Messungen für den jeweiligen Bürostandort identifiziert wurde.

> [!div class="mx-imgBorder"]
> ![Details zu Netzwerkeinblicken nach Standort](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Eine Karte des Umkreisnetzwerks für Die Benutzer Ihrer Organisation am Standort wird mit einigen oder allen dieser Elemente angezeigt:

- **Office -** Der Bürostandort für die Seite, auf der Sie sich befinden
- **Netzwerkperimeter** : Der Speicherort der Quell-IP-Adresse für Verbindungen vom Bürostandort. Dies hängt von der Genauigkeit von Geo-IP-Standortdatenbanken ab.
- **Exchange optimale** Service-Eingangstür – Eine der empfohlenen Exchange, mit der Benutzer an diesem Bürostandort eine Verbindung herstellen sollten
- **Exchange unteroptimale Eingangstür** – Eine Exchange, mit der Benutzer verbunden sind, wird jedoch nicht empfohlen
- **SharePoint optimale Fronttür** für den Dienst – Eine der empfohlenen SharePoint, mit der Benutzer an diesem Bürostandort eine Verbindung herstellen sollten
- **SharePoint suboptimale** Dienst-Eingangstür – Eine SharePoint-Service-Eingangstür, mit der Benutzer verbunden sind, wird jedoch nicht empfohlen.
- **DNS-rekursiver Resolverserver** : Der Speicherort aus einer geo-IP-Datenbank des erkannten rekursiven DNS-Resolvers, der für Exchange Online verwendet wird (sofern verfügbar)
- **Ihr Proxyserver** – Der Speicherort aus einer geo-IP-Datenbank des erkannten Proxyservers (sofern verfügbar) 

Die Zusammenfassungsseite des Standorts zeigt außerdem die Netzwerkbewertung des Standorts, den Netzwerkbewertungsverlauf, einen Vergleich der Standortbewertung mit anderen Kunden in derselben Stadt sowie eine Liste spezifischer Einblicke und Empfehlungen, die Sie zur Verbesserung der Netzwerkleistung und Zuverlässigkeit unternehmen können.

Vergleiche zwischen Kunden in derselben Stadt basieren auf der Erwartung, dass alle Kunden gleichen Zugriff auf Netzwerkdienstanbieter, Telekommunikationsinfrastruktur und in der Nähe von Microsoft-Netzwerkpunkten haben.

Ortsnamen können angepasst werden, wenn ein neuer Speicherort hinzugefügt oder ein vorhandener Speicherort im Standortf flyout bearbeitet wird. Dies bietet Ihnen die Flexibilität, Ihre Standortnamen jederzeit anzupassen. Darüber hinaus wird beim Hinzufügen von LAN-Subnetzen direkt im Standortf flyout eine Dropdownliste mit soft-abgestimmten LAN-Subnetzen angezeigt, aus denen Sie auswählen können. Leitungsnamen für bestimmte Office-Ausgangs-IP-Adressen können ebenfalls hinzugefügt und bearbeitet werden.

Auf der Registerkarte Details auf der Seite Bürostandort werden die spezifischen Messergebnisse angezeigt, die verwendet wurden, um Einblicke, Empfehlungen und die Netzwerkbewertung zu erhalten. Dies wird bereitgestellt, damit Netzwerktechniker die Empfehlungen überprüfen und alle Einschränkungen oder Besonderheiten in ihrer Umgebung überprüfen können. Außerdem finden Sie die geschätzte Anzahl von Benutzern für die gesammelten Beispiele an diesem Bürostandort sowie die Remotemitarbeiter in dieser Stadt.

> [!div class="mx-imgBorder"]
> ![Standortspezifische Details](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)


## <a name="sharing-network-assessment-data-with-microsoft"></a>Freigeben von Netzwerkbewertungsdaten für Microsoft

Standardmäßig werden die Netzwerkbewertungen für Ihre Organisation und die Netzwerkeinblicke für Microsoft-Mitarbeiter freigegeben. Dies umfasst keine personenbezogenen Daten von Ihren Mitarbeitern, sondern nur die spezifischen Netzwerkbewertungsmetriken und Netzwerkeinblicke, die im Admin Center für Ihre Bürostandorte angezeigt werden. Sie enthält auch keine Namen ihrer Bürostandorte oder Straßenadressen, daher müssen Sie ihnen die Stadt und die Support-ID des Büros mitteilen, das Sie besprechen möchten. Wenn dies deaktiviert ist, können die Microsoft-Techniker, mit der Sie Ihre Netzwerkkonnektivität besprechen, keine dieser Informationen anzeigen. Wenn Sie diese Einstellung aktivieren, werden nur die zukünftigen Daten verwendet, die am Tag nach der Aktivierung beginnen.

## <a name="csv-import-for-lan-subnet-office-locations"></a>CSV-Import für STANDORTE von LAN-Subnetzbüros

Für die Identifikation von LAN-Subnetzbüros müssen Sie jeden Standort im Voraus hinzufügen. Anstatt einzelne Bürostandorte auf der **Registerkarte** Speicherorte zu hinzufügen, können Sie sie aus einer CSV-Datei importieren. Sie können diese Daten möglicherweise von anderen Orten abrufen, die Sie gespeichert haben, z. B. das Anrufqualitätsdashboard oder Active Directory-Websites und -Dienste.

In der CSV-Datei wird ein ermittelter Ort in der Spalte userEntered als leer angezeigt, und ein manuell hinzugefügter Bürostandort wird als 1 angezeigt.

1. Klicken Sie im _Hauptfenster_ Konnektivität Microsoft 365 auf die Registerkarte **Speicherorte.**

1. Klicken Sie **auf die** Schaltfläche Importieren direkt über der Liste der Speicherorte. Das **Flyout "Office-Speicherorte** importieren" wird angezeigt.

   > [!div class="mx-imgBorder"]
   > ![CSV-Importnachricht](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Klicken Sie auf den Link Aktuelle Bürostandorte **herunterladen (.csv),** um die Liste der aktuellen Speicherorte in eine CSV-Datei zu exportieren und sie auf ihrer lokalen Festplatte zu speichern. Dadurch erhalten Sie eine ordnungsgemäß formatierte CSV mit Spaltenüberschriften, denen Sie Speicherorte hinzufügen können. Sie können die vorhandenen exportierten Speicherorte so be lassen, wie sie sind. Sie werden beim Importieren der aktualisierten CSV nicht dupliziert. Wenn Sie die Adresse eines vorhandenen Speicherorts ändern möchten, wird sie beim Importieren der CSV aktualisiert. Die Adresse einer erkannten Stadt kann nicht geändert werden.

1. Öffnen Sie die CSV, und fügen Sie Ihre Speicherorte hinzu, indem Sie die folgenden Felder in einer neuen Zeile für jeden Speicherort ausfüllen, den Sie hinzufügen möchten. Lassen Sie alle anderen Felder leer. Werte, die Sie in andere Felder eingeben, werden ignoriert.

   1. **userEntered** (erforderlich): Muss 1 sein, damit ein neuer LAN-Subnetz-Office-Standort hinzugefügt wird
   1. **Name** (erforderlich): Der Name des Bürostandorts
   1. **Adresse** (erforderlich): Die physische Adresse des Büros
   1. **Latitude** (optional): Aufgefüllt aus Bing Karten nach der Adresse, wenn leer
   1. **Längengrad** (optional): Aufgefüllt aus Bing Karten nach der Adresse, wenn leer
   1. **Egress IP-Adressbereiche 1 bis 5** (optional): Geben Sie für jeden Bereich den Leitungsnamen gefolgt von einer leer getrennten Liste gültiger IPv4- oder IPv6-CIDR-Adressen ein. Diese Werte werden verwendet, um mehrere Bürostandorte zu unterscheiden, an denen Sie dieselben LAN-Subnetz-IP-Adressen verwenden. Egress ALLE IP-Adressbereiche müssen die Netzwerkgröße /24 aufweisen, und /24 ist nicht in der Eingabe enthalten.
   1. **LanIps** (erforderlich): Listet die an diesem Standort verwendeten LAN-Subnetzbereiche auf. LAN-Subnetz-IDs müssen über eine CIDR-Netzwerkgröße verfügen, wobei die Netzwerkgröße zwischen /8 und /29 liegen kann. Mehrere LAN-Subnetzbereiche können durch ein Komma oder ein Semikolon getrennt werden.
   
1. Wenn Sie Ihre Bürostandorte hinzugefügt und  die Datei gespeichert  haben, klicken Sie auf die Schaltfläche Durchsuchen neben dem Hochladen abgeschlossenen Feld, und wählen Sie die gespeicherte CSV-Datei aus.

1. Die Datei wird automatisch überprüft. Wenn Überprüfungsfehler auftreten, wird die Fehlermeldung angezeigt: Es gibt einige Fehler _in der Importdatei. Überprüfen Sie die Fehler, korrigieren Sie die Importdatei, und versuchen Sie es dann erneut._ Klicken Sie auf den **Link Fehlerdetails öffnen** für eine Liste bestimmter Feldüberprüfungsfehler.

   > [!div class="mx-imgBorder"]
   > ![Fehlermeldung zum CSV-Import](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Wenn die Datei keine Fehler enthält, wird die Meldung angezeigt: _Der Bericht ist bereit. X-Speicherorte zum Hinzufügen und zu aktualisierende x-Speicherorte gefunden._ Klicken Sie auf **die Schaltfläche Importieren,** um die CSV hochzuladen.

   > [!div class="mx-imgBorder"]
   > ![CSV-importbereite Nachricht](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="what-is-a-microsoft-365-service-front-door"></a>Was ist eine Microsoft 365-Service-Eingangstür?

Die Microsoft 365 ist ein Einstiegspunkt im globalen Netzwerk von Microsoft, in dem Office und Dienste ihre Netzwerkverbindung beenden. Für eine optimale Netzwerkverbindung mit Microsoft 365 wird empfohlen, dass Die Netzwerkverbindung in der nächsten Microsoft 365 beendet wird.

>[!NOTE]
>Microsoft 365-Front-Door-Dienst hat keine direkte Beziehung zum Azure Front Door Service-Produkt, das im Azure Marketplace verfügbar ist.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Was ist ein optimaler Microsoft 365-Front-Door-Service?

Eine optimale Microsoft 365 ist eine, die ihrem Netzwerkeingang am nächsten ist, in der Regel in Ihrer Stadt oder Ihrer U-Bahn. Verwenden Sie [Microsoft 365 -Konnektivitätstesttool (Vorschau),](office-365-network-mac-perf-onboarding-tool.md) um den Standort Ihrer in-Use-Microsoft 365-Service-Eingangstür und der optimalen Service-Eingangstür zu bestimmen. Wenn das Tool bestimmt, dass Ihre in-Use-Fronttür optimal ist, verbinden Sie sich optimal mit dem globalen Netzwerk von Microsoft.

### <a name="what-is-an-internet-egress-location"></a>Was ist ein Internet-Ausgangsspeicherort?

Der Internetaustrittsspeicherort ist der Ort, an dem Ihr Netzwerkdatenverkehr Ihr Unternehmensnetzwerk verlässt und eine Verbindung mit dem Internet herstellt. Dies wird auch als Standort identifiziert, an dem Sie über ein Nat-Gerät (Network Address Translation) verfügen und in der Regel eine Verbindung mit einem Internetdienstanbieter (Internet Service Provider, ISP) herstellen. Wenn ein langer Abstand zwischen Ihrem Standort und Ihrem Internet-Ausgangsspeicherort angezeigt wird, kann dies auf einen erheblichen WAN-Backhaul hinweisen.

### <a name="what-license-is-needed-for-this-capability"></a>Welche Lizenz ist für diese Funktion erforderlich?

Sie benötigen eine Lizenz, die Zugriff auf das Microsoft 365 bietet.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 Netzwerkeinblicke (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365 Konnektivitätstesttool (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
