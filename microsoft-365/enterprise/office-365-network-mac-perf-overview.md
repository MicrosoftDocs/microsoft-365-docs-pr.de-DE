---
title: Netzwerkkonnektivität im Microsoft 365 Admin Center
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
description: Übersicht über die Netzwerkkonnektivität im Microsoft 365 Admin Center
ms.openlocfilehash: 8ad589ede747975ca9dcd3c81e661a2147fc1b88
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53277001"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center"></a>Netzwerkkonnektivität im Microsoft 365 Admin Center

Das Microsoft 365 Admin Center enthält jetzt aggregierte Netzwerkkonnektivitätsmetriken, die von Ihrem Microsoft 365 Mandanten erfasst werden und nur von Administrativen Benutzern in Ihrem Mandanten angezeigt werden können.

> [!div class="mx-imgBorder"]
> ![Testtool für Netzwerkkonnektivität](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**Netzwerkbewertungen** und **Netzwerkerkenntnisse** werden im Microsoft 365 Admin Center unter **"Integrität" | Netzwerkkonnektivität**.

> [!div class="mx-imgBorder"]
> ![Seite "Netzwerkleistung"](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>Die Netzwerkkonnektivität im Admin Center unterstützt Mandanten in WW Commercial und Deutschland, aber nicht GCC Moderate, GCC High, DoD oder China.

Wenn Sie zum ersten Mal zur Netzwerkleistungsseite navigieren, müssen Sie Ihre Standorte konfigurieren, um die Karte der globalen Netzwerkleistung, eine Netzwerkbewertung für den gesamten Mandanten, den Prozentsatz der Benutzer, die remote arbeiten, und eine Liste der aktuellen Probleme anzuzeigen, um Maßnahmen zu ergreifen und/oder weiter zu recherchieren. Im Übersichtsbereich können Sie einen Drilldown ausführen, um bestimmte Netzwerkleistungsmetriken und Probleme nach Standort anzuzeigen. Weitere Informationen finden Sie [unter Netzwerkleistungsübersicht im Microsoft 365 Admin Center.](#network-connectivity-overview-in-the-microsoft-365-admin-center)

Möglicherweise werden Sie aufgefordert, der öffentlichen Vorschau für dieses Feature im Namen Ihrer Organisation beizutreten. Die Akzeptanz erfolgt in der Regel sofort, danach wird die Seite "Netzwerkkonnektivität" angezeigt.

Um auf die Netzwerkkonnektivitätsseite zuzugreifen, müssen Sie ein Administrator für die Organisation innerhalb Microsoft 365 sein. Die Administrative Rolle "Leser des Berichts" hat Lesezugriff auf diese Informationen. Zum Konfigurieren von Standorten und anderen Elementen der Netzwerkkonnektivität muss ein Administrator Teil einer Serveradministratorrolle sein, z. B. der Administratorrolle "Dienstsupport".

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Voraussetzungen für die Bewertung der Netzwerkkonnektivität

Um zu beginnen, aktivieren Sie die Einstellung für die Standort-Anmeldung, um daten automatisch von Geräten mithilfe Windows Standortdienste zu sammeln, wechseln Sie zu Ihrer Standortliste, um Standortdaten hinzuzufügen oder hochzuladen, oder führen Sie den Microsoft 365 Netzwerkverbindungstest von Ihren Bürostandorten aus aus. Wenn die Netzwerkkonnektivität organisationsweit ausgewertet werden kann, müssen für bestimmte Bürostandorte Verbesserungen am Netzwerkentwurf vorgenommen werden. Informationen zur Netzwerkkonnektivität werden für jeden Bürostandort bereitgestellt, sobald diese Standorte ermittelt werden können. Es gibt drei Optionen zum Abrufen von Netzwerkbewertungen von Ihren Bürostandorten:

### <a name="1-enable-windows-location-services"></a>1. Aktivieren Windows Standortdienste

Für diese Option müssen mindestens zwei Computer an jedem Bürostandort ausgeführt werden, die die Voraussetzungen unterstützen. OneDrive für Windows Version muss auf dem neuesten Stand sein und auf jedem Computer installiert sein. Weitere Informationen zu OneDrive Versionen finden Sie in den [OneDrive Versionshinweisen.](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0) Netzwerkmessungen sollen in naher Zukunft anderen Office 365-Clientanwendungen hinzugefügt werden.

Windows Der Standortdienst muss auf den Computern zustimmen. Sie können dies testen, indem Sie die **Karten-App** ausführen und sich selbst suchen. Sie kann auf einem einzelnen Computer mit **Einstellungen | Datenschutz | Standort,** an dem die Einstellung _"Apps den Zugriff auf Ihren Standort erlauben"_ aktiviert sein muss. Windows Die Standortdienstzustimmung kann mithilfe von MDM oder Gruppenrichtlinien mit der Einstellung _LetAppsAccessLocation_ auf PCs bereitgestellt werden.

Sie müssen keine Standorte im Admin Center mit dieser Methode hinzufügen, da sie bei der Auflösung der Stadt automatisch identifiziert werden. Mehrere Bürostandorte innerhalb derselben Stadt werden bei Verwendung Windows Standortdienste nicht angezeigt. Standortinformationen werden auf die nächsten 300 m x 300 Meter gerundet, sodass kein genauerer Zugriff auf Standortinformationen erfolgt.

Die Computer sollten über Wi-Fi Netzwerk anstelle eines Ethernet-Kabels verfügen. Computer mit einem Ethernet-Kabel verfügen nicht über genaue Standortinformationen.

Messbeispiele und Bürostandorte sollten 24 Stunden nach Erfüllung dieser Voraussetzungen angezeigt werden.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Hinzufügen von Standorten und Bereitstellen von LAN-Subnetzinformationen

Für diese Option sind weder Windows Ortungsdienste noch Wi-Fi erforderlich. Ihre OneDrive für Windows Version muss auf dem neuesten Stand sein und auf mindestens einem Computer am Speicherort installiert sein.

Sie müssen außerdem Speicherorte auf der **Seite "Speicherorte"** hinzufügen oder aus einer CSV-Datei importieren. Die hinzugefügten Standorte müssen Ihre Office LAN-Subnetzinformationen enthalten.

Mit dieser Option können Sie mehrere Büros in einer Stadt definieren lassen.

Alle Testmessungen von Clientcomputern enthalten die LAN-Subnetzinformationen, die mit den von Ihnen eingegebenen Office-Standortdetails korreliert werden. Messbeispiele und Bürostandorte sollten 24 Stunden nach Erfüllung dieser Voraussetzungen angezeigt werden.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Manuelles Sammeln von Testberichten mit dem Microsoft 365 Netzwerkverbindungstesttool

Für diese Option müssen Sie eine Person an jedem Standort identifizieren. Bitten Sie sie, zu [Microsoft 365 Netzwerkverbindungstest](https://connectivity.office.com) auf einem Windows Computer zu navigieren, auf dem sie über Administratorberechtigungen verfügen. Auf der Website müssen sie sich bei ihrem Office 365 Konto für dieselbe Organisation anmelden, in der die Ergebnisse angezeigt werden sollen. Anschließend sollten sie auf **"Test ausführen"** klicken. Während des Tests wird eine EXE-Datei für den Verbindungstest heruntergeladen. Sie müssen dies öffnen und ausführen. Nach Abschluss der Tests wird das Testergebnis in das Admin Center hochgeladen.

Testberichte sind mit einem Standort verknüpft, wenn sie mit LAN-Subnetzinformationen hinzugefügt wurden, andernfalls werden sie nur am Ort angezeigt.

Messbeispiele und Bürostandorte sollten 2 bis 3 Minuten nach Abschluss eines Testberichts angezeigt werden. Weitere Informationen finden Sie unter [Microsoft 365 Netzwerkverbindungstest.](office-365-network-mac-perf-onboarding-tool.md)

> [!NOTE]
> Wenn Sie Ihre Bürostandorte Microsoft 365 Netzwerkkonnektivität im Microsoft 365 Admin Center hinzufügen, können Sie entweder IPv4- oder IPv6-Adressen für Ihre LAN-Subnetze angeben. Egress IP-Adressen müssen IPv4 verwenden.

## <a name="how-do-i-use-this-information"></a>Wie verwende ich diese Informationen?

**Netzwerkerkenntnisse,** zugehörige Leistungsempfehlungen und Netzwerkbewertungen sollen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen. Jeder Einblick enthält Details zu den Leistungsmerkmalen für ein bestimmtes häufiges Netzwerkproblem für jeden geografischen Standort, an dem Benutzer auf Ihren Mandanten zugreifen. **Performance recommendations** for each network insight offer specific network architecture design changes you can make to improve user experience related to Microsoft 365 network connectivity. Die Netzwerkbewertung zeigt, wie sich die Netzwerkkonnektivität auf die Benutzererfahrung auswirkt, sodass unterschiedliche Netzwerkverbindungen am Standort unterschiedlicher Benutzer verglichen werden können.

**Bei Netzwerkbewertungen** wird ein Aggregat aus vielen Netzwerkleistungsmetriken in eine Momentaufnahme Ihres Unternehmensnetzwerkstatus umgewandelt, dargestellt durch einen Punktwert zwischen 0 und 100. Netzwerkbewertungen sind sowohl auf den gesamten Mandanten als auch für jeden geografischen Standort beschränkt, von dem aus Benutzer eine Verbindung mit Ihrem Mandanten herstellen, sodass Microsoft 365 Administratoren eine einfache Möglichkeit haben, sofort einen Überblick über die Netzwerkintegrität des Unternehmens zu erhalten und schnell einen detaillierten Bericht für jeden globalen Bürostandort zu finden.

Komplexe Unternehmen mit mehreren Bürostandorten und nicht trivialen Netzwerkperimeterarchitekturen können von diesen Informationen entweder während ihres anfänglichen Onboardings in Microsoft 365 oder zur Behebung von Netzwerkleistungsproblemen profitieren, die mit dem Nutzungsplus erkannt wurden. Dies ist in der Regel nicht für kleine Unternehmen erforderlich, die Microsoft 365 verwenden, oder für Unternehmen, die bereits über einfache und direkte Netzwerkkonnektivität verfügen. Unternehmen mit mehr als 500 Benutzern und mehreren Bürostandorten werden am meisten profitieren.

>[!IMPORTANT]
>Netzwerkerkenntnisse, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365 Mandanten verfügbar, die im Featurevorschauprogramm registriert wurden.

## <a name="enterprise-network-connectivity-challenges"></a>Enterprise Herausforderungen bei der Netzwerkkonnektivität

> [!div class="mx-imgBorder"]
> ![Kundennetzwerk zur Cloud](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Viele Unternehmen verfügen über Netzwerkperimeterkonfigurationen, die sich im Laufe der Zeit weiterentwickelt haben und in erster Linie darauf ausgelegt sind, den Zugriff auf die Internetwebsite von Mitarbeitern zu ermöglichen, bei denen die meisten Websites im Voraus nicht bekannt sind und nicht vertrauenswürdig sind. Der schwerpunkt liegt auf der Vermeidung von Schadsoftware und Phishingangriffen von diesen unbekannten Websites. Diese Netzwerkkonfigurationsstrategie ist zwar für Sicherheitszwecke hilfreich, kann aber zu einer Beeinträchtigung der Microsoft 365 Benutzerleistung und Benutzerfreundlichkeit führen.

## <a name="how-we-can-solve-these-challenges"></a>Wie wir diese Herausforderungen lösen können

Unternehmen können die allgemeine Benutzererfahrung verbessern und ihre Umgebung schützen, indem [sie Office 365 Verbindungsprinzipien](./microsoft-365-network-connectivity-principles.md) folgen und das Feature Microsoft 365 Admin Center-Netzwerkkonnektivität verwenden. In den meisten Fällen wirkt sich das Befolgen dieser allgemeinen Prinzipien erheblich positiv auf die Latenz des Endbenutzers, die Zuverlässigkeit des Dienstes und die Gesamtleistung von Microsoft 365 aus.

Microsoft wird manchmal aufgefordert, Probleme mit der Netzwerkleistung mit Microsoft 365 für große Unternehmenskunden zu untersuchen, und diese haben häufig eine Ursache im Zusammenhang mit der Netzwerkperimeterinfrastruktur des Kunden. Wenn eine häufige Ursache für ein Problem mit dem Kundennetzwerkperimeter gefunden wird, versuchen wir, einfache Testmessungen zu identifizieren, die es identifizieren. Ein Test mit einem Messschwellenwert, der ein bestimmtes Problem identifiziert, ist nützlich, da wir die gleiche Messung an jedem Ort testen, feststellen können, ob diese Ursache vorhanden ist, und sie als Netzwerk-Einblick mit dem Administrator teilen können.

Einige Netzwerkerkenntnisse deuten lediglich auf ein Problem hin, das weiter untersucht werden muss. Eine Netzwerksicht, in der wir über genügend Tests verfügen, um eine bestimmte Korrekturaktion zum Beheben der Ursache anzuzeigen, wird als **empfohlene Aktion** aufgeführt. Diese Empfehlungen, basierend auf Livemetriken, die Werte anzeigen, die außerhalb eines vordefinierten Schwellenwerts liegen, sind viel wertvoller als allgemeine Empfehlungen für bewährte Methoden, da sie für Ihre Umgebung spezifisch sind und die tatsächliche Verbesserung zeigen, sobald die empfohlenen Änderungen vorgenommen wurden.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Übersicht über die Netzwerkkonnektivität im Microsoft 365 Admin Center

Microsoft verfügt über vorhandene Netzwerkmessungen von mehreren Office Desktop- und Webclients, die den Betrieb von Microsoft 365 unterstützen. Diese Messungen werden jetzt verwendet, um Einblicke in den Entwurf der Netzwerkarchitektur und eine Netzwerkbewertung zu erhalten, die auf der Seite **"Netzwerkkonnektivität"** im Microsoft 365 Admin Center angezeigt werden.

Standardmäßig identifizieren die mit den Netzwerkmessungen verbundenen ungefähren Standortinformationen den Ort, in dem sich Clientgeräte befinden. Die Netzwerkbewertung an jedem Standort wird mit Farbe angezeigt, und die relative Anzahl der Benutzer an jedem Standort wird durch die Größe des Kreises dargestellt.

> [!div class="mx-imgBorder"]
> ![Übersichtskarte für Netzwerkerkenntnisse](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

Auf der Übersichtsseite wird auch die Netzwerkbewertung für den Kunden als gewichteter Durchschnitt für alle Bürostandorte angezeigt.

> [!div class="mx-imgBorder"]
> ![Netzwerkbewertung](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Sie können eine Tabellenansicht der Speicherorte anzeigen, an denen sie auf der Registerkarte **"Speicherorte"** gefiltert, sortiert und bearbeitet werden können. Standorte mit spezifischen Empfehlungen können auch eine geschätzte potenzielle Latenzverbesserung umfassen. Dies wird berechnet, indem die Medianlatenz der Benutzer Ihrer Organisation am Standort verwendet und die mediane Latenz für alle Organisationen in derselben Stadt subtrahiert wird.

> [!div class="mx-imgBorder"]
> ![Netzwerk-Insights-Speicherorte](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="remote-worker-assessment-and-user-connection-metrics"></a>Remote worker assessment and user connection metrics

Wir klassifizieren Netzwerkdatenverkehrprotokolle als Remotebenutzer oder Benutzer vor Ort und zeigen deren Prozentsätze im Abschnitt "Benutzerverbindungsmetriken" des Übersichtsbereichs an. Für Städte, in denen Sie Remotebenutzer haben, finden Sie die standortspezifische Bewertungsbewertung des Remotenetzwerks, wenn Sie die Seite dieses Standorts öffnen. Die Standortliste enthält sowohl Bürostandorte als auch Remotearbeitsstandorte, die gefiltert und sortiert werden können. Wir stellen die Bewertungsbewertung von Remotemitarbeitern mit einer Punkteaufschlüsselung für Exchange, SharePoint und Teams bereit.

Einblicke in das Netzwerk von Heimbenutzern werden auf Stadtebene aggregiert und gemeldet und auf Städte mit mindestens 5 Remotemitarbeitern beschränkt. Wir identifizieren keine einzelnen Mitarbeiter, die von zu Hause aus arbeiten.

Speicherorte werden automatisch als lokale oder remote klassifiziert. Sie haben jedoch die Möglichkeit, alle Ihre IP-Adressen für den Vor-Ort-Ausgang manuell einzugeben, um eine Klassifizierung von 100 % sicherzustellen. Wenn Sie sich für diese Route entscheiden, müssen Sie das **Kontrollkästchen "Alle IP-Adressen** vor Ort eingeben" manuell in den Speicherorten Einstellungen Flyout aktivieren, nachdem Sie alle Ip-Adressen hinzugefügt haben. Wenn dies erfolgt ist, werden alle Netzwerkdatenverkehrprotokolle von ausgehenden IP-Adressen, die Sie als vor Ort gekennzeichnet haben, immer als Büros klassifiziert, und jede andere IP-Adresse des Ausgehenden wird als Remoteadresse klassifiziert.

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Übersicht über die Netzwerkleistung für bestimmte Standorte und Einblicke

Wenn Sie einen Bürostandort auswählen, wird eine standortspezifische Zusammenfassungsseite mit Details des Netzwerkausgangs geöffnet, der anhand von Messungen für diesen Bürostandort identifiziert wurde.

> [!div class="mx-imgBorder"]
> ![Details zu Netzwerkerkenntnissen nach Standort](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Eine Karte des Umkreisnetzwerks für Ihre Organisationsbenutzer am Standort wird mit einigen oder allen dieser Elemente angezeigt:

- **Office Standort** – Der Bürostandort für die Seite, die Sie sich ansehen
- **Netzwerkperimeter** – Der Speicherort der QUELL-IP-Adresse für Verbindungen vom Bürostandort aus. Dies hängt von der Genauigkeit von Geo-IP-Standortdatenbanken ab.
- **Exchange optimale Service-Front-Door** – eine der empfohlenen Exchange Service-Eingangstüren, mit denen Benutzer an diesem Bürostandort eine Verbindung herstellen sollten
- **Exchange suboptimale Front door** – Eine Exchange Service-Front-Door, mit der Benutzer verbunden sind, wird jedoch nicht empfohlen.
- **SharePoint optimale Service-Front-Door** – eine der empfohlenen SharePoint Service-Eingangstüren, mit denen Benutzer an diesem Bürostandort eine Verbindung herstellen sollten
- **SharePoint suboptimale Service-Front-Door** – Eine SharePoint Service-Front-Door, mit der Benutzer verbunden sind, wird jedoch nicht empfohlen.
- **DNS-rekursive Resolver-Server** – Der Speicherort aus einer Geo-IP-Datenbank des erkannten rekursiven DNS-Resolvers, der für Exchange Online verwendet wird (sofern verfügbar)
- **Ihr Proxyserver** – Der Speicherort aus einer geo-IP-Datenbank des erkannten Proxyservers (sofern verfügbar) 

Die Zusammenfassungsseite des Bürostandorts enthält darüber hinaus die Netzwerkbewertung des Standorts, den Netzwerkbewertungsverlauf, einen Vergleich der Bewertung dieses Standorts mit anderen Kunden in derselben Stadt sowie eine Liste mit spezifischen Einblicken und Empfehlungen, die Sie zur Verbesserung der Netzwerkleistung und Zuverlässigkeit ergreifen können.

Vergleiche zwischen Kunden in derselben Stadt basieren auf der Erwartung, dass alle Kunden gleichen Zugriff auf Netzwerkdienstanbieter, Telekommunikationsinfrastruktur und in der Nähe befindliche Microsoft-Netzwerkpunkte haben.

Standortnamen können angepasst werden, wenn ein neuer Speicherort hinzugefügt oder ein vorhandener Speicherort im Positions-Flyout bearbeitet wird. Dies bietet Ihnen die Flexibilität, Ihre Standortnamen jederzeit anzupassen. Darüber hinaus wird beim direkten Hinzufügen von LAN-Subnetzen im Standort-Flyout eine Dropdownliste mit lan-Subnetzen mit weicher Übereinstimmung angezeigt, aus der Sie auswählen können. Schaltungsnamen für bestimmte IP-Adressen von Office-Ausgangspunkten können auch hinzugefügt und bearbeitet werden.

Auf der Registerkarte "Details" auf der Office-Standortseite werden die spezifischen Messergebnisse angezeigt, die verwendet wurden, um Einblicke, Empfehlungen und die Netzwerkbewertung zu erhalten. Dies wird bereitgestellt, damit Netzwerktechniker die Empfehlungen überprüfen und alle Einschränkungen oder Spezifik in ihrer Umgebung berücksichtigen können. Sie finden auch die geschätzte Anzahl der Benutzer für gesammelte Beispiele an diesen Bürostandorten sowie die Remotemitarbeiter in dieser Stadt.

> [!div class="mx-imgBorder"]
> ![Standortspezifische Details](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)


## <a name="sharing-network-assessment-data-with-microsoft"></a>Freigeben von Netzwerkbewertungsdaten für Microsoft

Standardmäßig werden die Netzwerkbewertungen für Ihre Organisation und die Netzwerkerkenntnisse für Microsoft-Mitarbeiter freigegeben. Dies umfasst keine personenbezogenen Daten Von Ihren Mitarbeitern, sondern nur die spezifischen Metriken zur Netzwerkbewertung und Netzwerkerkenntnisse, die im Admin Center für Ihre Bürostandorte angezeigt werden. Es enthält auch keine Bürostandortnamen oder Straßenadressen, daher müssen Sie ihnen die Stadt und die Support-ID des Büros mitteilen, das Sie besprechen möchten. Wenn dies deaktiviert ist, können die Microsoft-Techniker, mit denen Sie Ihre Netzwerkkonnektivität besprechen, keine dieser Informationen anzeigen. Wenn Sie diese Einstellung aktivieren, werden zukünftige Daten erst am Tag nach der Aktivierung freigegeben.

## <a name="csv-import-for-lan-subnet-office-locations"></a>CSV-Import für LAN-Subnetzstandorte

Für die LAN-Subnetz-Office-Identifikation müssen Sie jeden Standort im Voraus hinzufügen. Anstatt einzelne Bürostandorte auf der Registerkarte **"Speicherorte"** hinzuzufügen, können Sie sie aus einer CSV-Datei importieren. Möglicherweise können Sie diese Daten von anderen Orten abrufen, an denen Sie sie gespeichert haben, z. B. das Anrufqualitätsdashboard oder Active Directory-Websites und -Dienste

In der CSV-Datei wird ein ermittelter Ort in der Spalte "userEntered" als leer und ein manuell hinzugefügter Bürostandort als 1 angezeigt.

1. Klicken Sie im Hauptfenster _Konnektivität mit Microsoft 365_ auf die Registerkarte **Speicherorte .**

1. Klicken Sie auf die Schaltfläche **"Importieren"** direkt über der Speicherortliste. Das **Flyout "Office-Speicherorte importieren"** wird angezeigt.

   > [!div class="mx-imgBorder"]
   > ![CSV-Importnachricht](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Klicken Sie auf den Link **"Aktuelle Office-Speicherorte herunterladen (.csv),um** die Liste der aktuellen Speicherorte in eine CSV-Datei zu exportieren und auf Ihrer lokalen Festplatte zu speichern. Dadurch erhalten Sie eine korrekt formatierte CSV-Datei mit Spaltenüberschriften, zu denen Sie Speicherorte hinzufügen können. Sie können die vorhandenen exportierten Speicherorte so belassen, wie sie sind. sie werden beim Importieren der aktualisierten CSV-Datei nicht dupliziert. Wenn Sie die Adresse eines vorhandenen Speicherorts ändern möchten, wird sie beim Importieren der CSV aktualisiert. Sie können die Adresse einer entdeckten Stadt nicht ändern.

1. Öffnen Sie die CSV-Datei, und fügen Sie Ihre Standorte hinzu, indem Sie die folgenden Felder in einer neuen Zeile für jeden Hinzuzufügenden Speicherort ausfüllen. Lassen Sie alle anderen Felder leer. Werte, die Sie in andere Felder eingeben, werden ignoriert.

   1. **userEntered** (erforderlich): Muss 1 sein, damit ein neuer LAN-Subnetzstandort hinzugefügt wird
   1. **Name** (erforderlich): Der Name des Bürostandorts
   1. **Adresse** (erforderlich): Die physische Adresse des Büros
   1. **Breitengrad** (optional): Aufgefüllt von Bing Kartensuche der Adresse, wenn leer
   1. **Längengrad** (optional): Aufgefüllt von Bing Kartensuche der Adresse, wenn leer
   1. **Egress IP-Adressbereiche 1 bis 5** (optional): Geben Sie für jeden Bereich den Namen der Schaltung gefolgt von einer durch Leerzeichen getrennten Liste gültiger IPv4- oder IPv6-CIDR-Adressen ein. Diese Werte werden verwendet, um mehrere Bürostandorte zu unterscheiden, an denen Sie dieselben LAN-Subnetz-IP-Adressen verwenden. Egress Alle IP-Adressbereiche müssen die Netzwerkgröße /24 aufweisen, und die /24 ist nicht in der Eingabe enthalten.
   1. **LanIps** (erforderlich): Listet die LAN-Subnetzbereiche auf, die an diesem Bürostandort verwendet werden. LAN-Subnetz-IDs müssen eine CIDR-Netzwerkgröße enthalten, bei der die Netzwerkgröße zwischen /8 und /29 liegen kann. Mehrere LAN-Subnetzbereiche können durch ein Komma oder ein Semikolon getrennt werden.
   
1. Wenn Sie Ihre Bürostandorte hinzugefügt und die Datei gespeichert haben, klicken Sie auf die Schaltfläche **"Durchsuchen"** neben dem **Hochladen dem abgeschlossenen** Feld, und wählen Sie die gespeicherte CSV-Datei aus.

1. Die Datei wird automatisch überprüft. Wenn Validierungsfehler auftreten, wird die Fehlermeldung angezeigt: _Es gibt einige Fehler in der Importdatei. Überprüfen Sie die Fehler, korrigieren Sie die Importdatei, und versuchen Sie es dann erneut._ Klicken Sie auf den Link **"Fehlerdetails öffnen"** für eine Liste bestimmter Feldüberprüfungsfehler.

   > [!div class="mx-imgBorder"]
   > ![CSV-Importfehlermeldung](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Wenn die Datei keine Fehler enthält, wird die Meldung angezeigt: _Der Bericht ist bereit. Es wurden X-Speicherorte zum Hinzufügen und x zu aktualisierende Speicherorte gefunden._ Klicken Sie auf die Schaltfläche **"Importieren",** um die CSV hochzuladen.

   > [!div class="mx-imgBorder"]
   > ![CSV import ready message](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="what-is-a-microsoft-365-service-front-door"></a>Was ist eine Microsoft 365 Service-Eingangstür?

Die Microsoft 365 Service-Front-Door ist ein Einstiegspunkt im globalen Microsoft-Netzwerk, an dem Office Clients und Dienste ihre Netzwerkverbindung beenden. Für eine optimale Netzwerkverbindung mit Microsoft 365 wird empfohlen, die Netzwerkverbindung in der nächstgelegenen Microsoft 365 Front-Door zu beenden.

>[!NOTE]
>Microsoft 365 Service-Front-Door hat keine direkte Beziehung zum Azure Front Door Service-Produkt, das im Azure Marketplace verfügbar ist.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Was ist eine optimale Microsoft 365 Service-Front-Door?

Eine optimale Microsoft 365 Service-Front-Door ist eine, die ihrem Netzwerkausgang am nächsten ist, in der Regel in Ihrer Stadt oder Ihrem Netzbereich. Verwenden Sie das [Microsoft 365-Konnektivitätstesttool (Vorschau),](office-365-network-mac-perf-onboarding-tool.md) um den Speicherort Ihrer verwendeten Microsoft 365 Service-Front-Door und optimaler Service-Front-Door zu ermitteln. Wenn das Tool feststellt, dass Ihre in-use-Front door optimal ist, stellen Sie eine optimale Verbindung mit dem globalen Microsoft-Netzwerk bereit.

### <a name="what-is-an-internet-egress-location"></a>Was ist ein Internetausgangsspeicherort?

Der Internetausgangsspeicherort ist der Ort, an dem Ihr Netzwerkdatenverkehr Ihr Unternehmensnetzwerk verlässt und eine Verbindung mit dem Internet herstellt. Dies wird auch als Standort identifiziert, an dem Sie über ein NAT-Gerät (Network Address Translation) verfügen und in der Regel, an dem Sie eine Verbindung mit einem Internetdienstanbieter (INTERNET Service Provider, ISP) herstellen. Wenn ein langer Abstand zwischen Ihrem Standort und Ihrem Internetausgangsstandort angezeigt wird, kann dies auf einen signifikanten WAN-Backhaul hindeuten.

### <a name="what-license-is-needed-for-this-capability"></a>Welche Lizenz ist für diese Funktion erforderlich?

Sie benötigen eine Lizenz, die Zugriff auf die Microsoft 365 Admin Center ermöglicht.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 Netzwerk-Insights (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365-Konnektivitätstesttool (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Netzwerkkonnektivitätsdienste (Vorschau)](office-365-network-mac-location-services.md)
