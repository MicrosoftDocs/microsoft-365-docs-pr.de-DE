---
title: Microsoft 365 informiertes Netzwerkrouting
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 informiertes Netzwerkrouting
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717594"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 Informiertes Netzwerkrouting (Vorschau)

Informiertes Netzwerkrouting ist ein Feature, das verschiedene Microsoft 365-Anwendungen in Sd-WAN-Lösungen (Software Defined Network) von Drittanbietern integriert, um Ihre Netzwerkkonnektivität mit Microsoft-Dienstendpunkten zu optimieren und zu verbessern. Optimierte SD-WAN-Konnektivität kann zu einer verbesserten Benutzererfahrung und -leistung führen.

>[!IMPORTANT]
>Microsoft 365 Informiertes Netzwerkrouting befindet sich derzeit im Vorschaustatus. Weitere Informationen zu dieser Vorschau einschließlich Anleitungen für den Empfang von Unterstützung finden Sie unter [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).

## <a name="overview"></a>Übersicht

Informiertes Netzwerkrouting bietet einen bidirektionalen Datenfreigabekanal zwischen Microsoft und Ihrer SD-WAN-Lösung. Für jeden von Ihnen konfigurierten Bürostandort und Internetkreis teilt Microsoft regelmäßig Feedback mit der SD-WAN-Lösung zur Qualität ausgewählter Microsoft 365-Anwendungserfahrungen für den Netzwerkdatenverkehr, der jeder bestimmten Internetverbindung zugeordnet ist. Mithilfe dieses Feedbacks kann die SD-WAN-Lösung dann intelligente Wiederherstellungsaktionen ausführen, indem sie den Microsoft 365-Anwendungsdatenverkehr über alternative verfügbare Links weiterleitet. 

Beeinträchtigungen der Dienstqualität im Pfad einer bestimmten Internetschaltung, z. B. erhöhte Latenz oder hoher Paketverlust, sind nur schwer dauerhaft zu erkennen. Diese Beeinträchtigungen können sich negativ auf die Benutzererfahrung für Anwendungen wie Exchange Online, SharePoint, OneDrive und Microsoft Teams auswirken. Häufige Symptome sind die langsame Suche nach #A0, hohe Übertragungszeiten bei der Interaktion mit SharePoint- oder OneDrive-Dokumentbibliotheken oder schlechte Anruf- oder Besprechungsqualität in Microsoft Teams.

Der Feedback- und Wiederherstellungsmechanismus innerhalb des über das Netzwerk informierten Routings versucht, solche Probleme in nahezu Echtzeit dynamisch zu erkennen und informiert die bereitgestellte SD-WAN-Lösung, automatische Wiederherstellungsaktionen zu ergreifen.

Der Datenfreigabekanal wird auch zum regelmäßigen Empfangen von Optischen Daten auf Netzwerkebene von der SD-WAN-Lösung verwendet, einschließlich Konfigurationsinformationen und Verwendungsstatistiken, die dem Gerät und den angeschlossenen Schaltungen zugeordnet sind. Es werden keine personenbezogenen Informationen gesammelt oder gespeichert. Alle gesammelten Informationen werden zu Bürostandorten und verbundenen Internetschaltungen aggregiert. Diese Informationen können Microsoft dabei unterstützen, gemeldete Probleme bei der Verwendung von Microsoft 365-Diensten und -Anwendungen effizienter und effektiver zu beheben.

>[!NOTE]
>Das informierte Netzwerkrouting von Microsoft 365 unterstützt Mandanten in der Cloud ww Commercial, aber nicht die GCC Moderate, GCC High, DoD, Germany oder China Clouds.

## <a name="requirements"></a>Anforderungen

### <a name="integrated-sd-wan-solutions"></a>Integrierte SD-WAN-Lösungen

Microsoft arbeitet mit verschiedenen Partnern zusammen, um die Integration in das informierte Netzwerkrouting von Microsoft 365 zu ermöglichen. Derzeit aktivierte Lösungen umfassen Folgendes:

| Device Maker | Solution Name | Mindestversion |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Netzwerktopologie 

Informiertes Netzwerkrouting identifiziert derzeit Datenverkehr, der einem bestimmten Bürostandort und einer bestimmten Internetleitung zugeordnet ist, basierend auf der öffentlichen IP-Adresse, die zum Senden von Netzwerkdatenverkehr an Microsoft verwendet wird. 

Wenn es nicht mindestens eine Netzwerkleitung gibt, die direkten Internetzugriff an einem Zweigstellenstandort bietet, bietet das netzwerkintegte Routing möglicherweise keinen signifikanten Nutzen.

### <a name="application-usage"></a>Anwendungsverwendung

Anwendungserfahrungsdaten (die durch Metriken zur Netzwerkqualität widerspiegelt werden) werden mithilfe bestimmter Microsoft-Clientanwendungen gesammelt. Exchange-Metriken spiegeln die Verwendung des Outlook-Clients sowie einige Outlook Web App-Nutzung wider. SharePoint- und #A0 spiegeln die Verwendung der mandantenspezifischen #A1 wider, unabhängig von der Clientanwendung. Die Teams-Metriken spiegeln die Verwendung des Teams-Desktopclients wider. Anderer Anwendungsdatenverkehr wird bei der Auswertung der Integrität einer Netzwerkverbindung nicht berücksichtigt.

## <a name="enabling-informed-network-routing"></a>Aktivieren des informierten Netzwerkroutings

Das Aktivieren des informierten Netzwerkroutings erfordert mehrere Schritte, von denen einige innerhalb der Konfigurationsschnittstelle Ihrer SD-WAN-Lösung ausgeführt werden müssen. Wenden Sie sich an den Anbieter der SD-WAN-Lösung, um Anleitungen zum Aktivieren des netzwerkinitiiert-informierten Routings innerhalb der SD-WAN-Lösung zu erhalten, bevor Sie mit der Konfiguration im Microsoft 365 Admin Center fortfahren.

Nachdem Sie bereit sind, das informierte Netzwerkrouting im Microsoft 365 Admin Center zu aktivieren, stellen Sie sicher, dass Sie über die erforderlichen globalen Administratorberechtigungen verfügen.

>[!IMPORTANT]
>Um die erforderliche Zustimmung für Anwendungen auf Mandantenebene für die ausgewählte SD-WAN-Lösung für den Zugriff auf den informierten Netzwerkroutingdatenfreigabekanal zu erteilen, müssen Sie die folgenden Schritte als globaler Administrator ausführen.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Schritt 1: Öffnen von Konfigurationsoptionen für SD-WAN-Lösungen

Wählen Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com/)die Option Integrität > **Netzwerkkonnektivität** im linken Navigationsbereich aus.

Dieser Abschnitt des Admin Centers enthält aggregierte Netzwerkkonnektivitätsmetriken für Ihre Organisation und Anleitungen zur Verbesserung Ihrer Konnektivität. Weitere Informationen zu diesen Im Admin Center verfügbaren Features finden Sie unter Netzwerkkonnektivität im [Microsoft 365 Admin Center (Vorschau).](office-365-network-mac-perf-overview.md)

Wählen **Sie Einstellungen > SD-WAN-Lösung aus,** um den Konfigurationsbereich für informiertes Netzwerkrouting zu öffnen. Die anderen Optionen, die unter **Einstellungen** angezeigt werden, gelten für die allgemeinen Richtlinien zur Netzwerkkonnektivität im Admin Center und sind nicht erforderlich, um informiertes Netzwerkrouting zu aktivieren.

Wählen Sie im Konfigurationsbereich **Sd-WAN-Lösung hinzufügen (Vorschau) aus.**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Schritt 2: Auswählen der SD-WAN-Lösung und des Datenspeicherorts

Wählen Sie in den Dropdownfeldern die bereitgestellte SD-WAN-Lösung und den Speicherort aus, an dem die Daten gespeichert werden sollen, die dem netzwerkintehierten Routing zugeordnet sind. Weitere Informationen finden Sie [im](#data-storage) Abschnitt Datenspeicher.

Wählen Sie **Weiter** aus.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Schritt 3: Akzeptieren von Bedingungen für die Freigabe von Daten

Lesen Und bestätigen Sie sorgfältig die bereitgestellten Bedingungen für die Freigabe von Daten zwischen Microsoft und Ihrer ausgewählten SD-WAN-Lösung, und aktivieren Sie dann das angegebene Kontrollkästchen.

Wählen Sie **Weiter** aus.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Schritt 4: Erteilen von Berechtigungen für die SD-WAN-Lösung

In diesem Schritt wird eine Berechtigungserteilungsanforderung mit Azure Active Directory (Azure AD) initiiert. Sie werden aufgefordert, Berechtigungen auf Mandantenebene zu erteilen, die Ihrer ausgewählten SD-WAN-Lösung Zugriff auf den informierten Netzwerkroutingdatenspeicher und die Dienstintehzustandsinformationen gewähren, die Ihrem Mandanten zugeordnet sind. Für diese Aktion sind globale Administratorrolleberechtigungen erforderlich.

Wählen Sie **den Link Berechtigung für diese Anwendung erteilen** aus, und folgen Sie den Azure AD-Anforderungen.

Nachdem Sie die Berechtigungserteilung abgeschlossen haben, wählen Sie **Weiter aus.**

### <a name="step-5-confirm-your-configuration-settings"></a>Schritt 5: Bestätigen der Konfigurationseinstellungen

Der letzte Schritt beim Aktivieren des routing informierten Netzwerks für Ihren Mandanten ist eine Bestätigungsseite, auf der die von Ihnen angegebenen Einstellungen angezeigt werden. 

Informiertes Netzwerkrouting ist jetzt für Ihren Mandanten aktiviert.

Wählen **Sie Fertig** aus, und schließen Sie dann den Konfigurationsbereich der SD-WAN-Lösung.

## <a name="configuring-network-informed-routing"></a>Konfigurieren des informierten Routings im Netzwerk

Sie führen einen großen Teil der Konfiguration für das informierte Netzwerkrouting in Ihrer SD-WAN-Lösung aus, z. B. konfigurieren, wie Ihr Datenverkehr unter normalen Umständen geroutet werden soll, und die alternativen Pfade, die verwendet werden sollten, wenn Probleme erkannt werden. Weitere Informationen zu diesen Konfigurationsschritten finden Sie bei Ihrem SD-WAN-Lösungsanbieter.

Jeder Bürostandort muss im Microsoft 365 Admin Center konfiguriert sein, damit das informierte Netzwerkrouting den Datenverkehr, der den Netzwerkleitungen zugeordnet ist, die verbindungen zu diesen Standorten bereitstellen, ordnungsgemäß identifizieren kann.

Office-Standorte können im Rahmen der fortlaufenden Sammlung von Netzwerktelemetrie von Microsoft automatisch erkannt werden. Als Ergebnis können einige Speicherorte im Admin Center für Ihren Mandanten vorab ausgefüllt werden. 

Wenn diese Speicherorte korrekt sind, müssen Sie einfach die Funktion für das informierte Netzwerkrouting für jeden gewünschten Standort aktivieren und die Internetschaltungen und ihre öffentlichen IP-Adressen konfigurieren. 

Wenn die automatisch erkannten Speicherorte nicht genau sind oder es keine bereits aufgefüllten Speicherorte in Ihrem Mandanten gibt, müssen Sie Standorte manuell hinzufügen oder bearbeiten, um eine genaue Topologie Ihrer Organisation widerzuspiegeln.

### <a name="updating-locations"></a>Aktualisieren von Speicherorten

Speicherorte für Ihren Mandanten finden Sie unter der Registerkarte **Speicherorte.** Speicherorte können direkt in der Liste bearbeitet oder mithilfe einer CSV-Datei aktualisiert werden.

Stellen Sie sicher, dass jeder Bürostandort, an dem Sie das informierte Netzwerkrouting aktivieren möchten, in dieser Liste vorhanden ist.

>[!NOTE]
>Die Spalten in der **Liste Speicherorte** für gesammelte Beispiele und andere bewertungsbezogene Informationen stehen nicht im Zusammenhang mit dem informierten Netzwerkroutingfeature.

### <a name="enabling-a-location-for-informed-network-routing"></a>Aktivieren eines Standorts für informiertes Netzwerkrouting

1. Wählen Sie **in der** Liste Speicherorte **im** Menü Schnellaktionen Bearbeiten aus, um den Konfigurationsbereich des Speicherorts zu öffnen.

2. Wählen Sie an diesem Speicherort Das **informierte Netzwerkrouting von Microsoft 365 verwenden aus.**

3. Fügen Sie alle Netzwerkschaltungen hinzu, die internetkonnektivität zu diesem Bürostandort in den **Egress-IP-Adressbereichen** an diesem Bürostandort bereitstellen. Stellen Sie sicher, dass jede Schaltung den eindeutigen öffentlichen IP-Adresssubnetzen zugeordnet ist, die Den Netzwerkdatenverkehr darstellen.

4. Wählen Sie **Speichern** aus, um Ihre Änderungen zu speichern.

## <a name="disabling-network-informed-routing"></a>Deaktivieren des informierten Routings im Netzwerk

Das Feature für das informierte Netzwerkrouting kann für den gesamten Mandanten deaktiviert werden, indem Sie die Einstellungen ihrer SD-WAN-Lösung zurücksetzen. Dadurch wird zwar die verarbeitung von Daten in Microsoft 365 beendet, sie sollten jedoch auch das Netzwerkrouting im Admin Center deaktivieren.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Schritt 1: Öffnen von Konfigurationsoptionen für SD-WAN-Lösungen

Wählen Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com/) die Option Integrität > **Netzwerkkonnektivität** im linken Navigationsbereich aus.

Wählen **Sie Einstellungen > SD-WAN-Lösung aus,** um den Konfigurationsbereich für informiertes Netzwerkrouting zu öffnen.

Im Konfigurationsbereich wird eine Zusammenfassung der derzeit konfigurierten SD-WAN-Lösung angezeigt.

### <a name="step-2-reset-your-configuration"></a>Schritt 2: Zurücksetzen der Konfiguration

Wählen Sie im Konfigurationsbereich **Einstellungen der SD-WAN-Lösung zurücksetzen aus.**

Ihre Einstellungen wurden jetzt zurückgesetzt, und das informierte Netzwerkrouting wurde deaktiviert. Sie können sie jederzeit erneut aktivieren, indem Sie die Schritte unter Aktivieren des informierten [Netzwerkroutings ausführen.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Datenspeicher

Daten, die zwischen Microsoft und dem SD-WAN-Lösungsanbieter ausgetauscht werden, werden an dem Datenspeicherort gespeichert, der während der anfänglichen Aktivierung des Netzwerkroutings ausgewählt wurde. Die Datenspeicherortoptionen stellen geografische Bereiche dar, die Microsoft Azure-Regionen enthalten, in denen die Daten gespeichert werden.

>[!NOTE]
>Während der Vorschauphase ist der einzige verfügbare Datenspeicherort **Nordamerika**. Zusätzliche Datenspeicherorte werden vor der allgemeinen Verfügbarkeit des informierten Netzwerkroutings verfügbar.

Daten werden an diesem Speicherort für bis zu 30 Tage aufbewahrt. Wenn dies deaktiviert ist, werden alle verbleibenden Daten innerhalb dieses 30-tägigen Aufbewahrungsfensters entfernt.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
