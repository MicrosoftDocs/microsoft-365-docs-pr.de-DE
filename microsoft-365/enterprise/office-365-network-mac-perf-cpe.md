---
title: Microsoft 365 informiertes Netzwerkrouting
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/21/2020
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
ms.openlocfilehash: 40b4345ca80c5e90a07583b83b82368d4a35535a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611436"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 informiertes Netzwerkrouting (Vorschau)

Das informierte Netzwerkrouting ist ein Feature, das verschiedene Microsoft 365-Anwendungen mit Software Defined Network (SD-WAN)-Lösungen von Drittanbietern integriert, um Ihre Netzwerkkonnektivität mit Microsoft-Dienstendpunkten zu optimieren und zu verbessern. Optimierte SD-WAN-Konnektivität kann zu verbesserten Benutzerfreundlichkeit und Leistung führen.

>[!IMPORTANT]
>Das von Microsoft 365 informierte Netzwerkrouting befindet sich derzeit im Vorschaustatus. Weitere Informationen zu dieser Vorschau einschließlich Anleitungen für den Erhalt von Unterstützung finden Sie unter [Microsoft 365 informiertes Netzwerkrouting Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).

## <a name="overview"></a>Übersicht

Das informierte Netzwerkrouting stellt einen bidirektionalen Datenfreigabe Kanal zwischen Microsoft und Ihrer SD-WAN-Lösung bereit. Für alle von Ihnen konfigurierten Bürostandorte und Internet Schaltungen teilt Microsoft in regelmäßigen Abständen Feedback mit der SD-WAN-Lösung über die Qualität ausgewählter Microsoft 365-Anwendungserfahrungen für den Netzwerkdatenverkehr, der mit den einzelnen Internet Schaltkreisen verknüpft ist. Mithilfe dieses Feedbacks kann die SD-WAN-Lösung dann intelligente Wiederherstellungsaktionen durchführen, indem Microsoft 365-Anwendungsdatenverkehr über alternative verfügbare Links geroutet wird. 

Dienst Qualitätsbeeinträchtigungen im Pfad eines bestimmten Internet Zirkels wie erhöhte Latenz oder hoher Paketverlust werden auf kontinuierlicher Basis nur schwer erkannt. Diese Beeinträchtigungen können sich nachteilig auf Benutzeroberflächen für Anwendungen wie Exchange Online, SharePoint, OneDrive und Microsoft Teams auswirken. Häufige Symptome sind die langsame Suche von Exchange-Inhalten, hohe Übertragungszeiten bei der Interaktion mit SharePoint-oder OneDrive-Dokumentbibliotheken oder die schlechte Anruf-oder Besprechungs Qualität in Microsoft Teams.

Der Feedback-und Wiederherstellungsmechanismus im netzwerkorientierten Routing zielt darauf ab, solche Probleme in nahezu Echtzeit dynamisch zu erkennen und informiert die bereitgestellte SD-WAN-Lösung, um automatische Wiederherstellungsaktionen durchführen zu können.

Der Datenfreigabe Kanal wird auch verwendet, um regelmäßige optische Daten auf Netzwerkebene aus der SD-WAN-Lösung zu erhalten, einschließlich Konfigurationsinformationen und Nutzungsstatistiken, die dem Gerät und den angeschlossenen Schaltkreisen zugeordnet sind. Es werden keine personenbezogenen Daten erfasst oder gespeichert. Alle gesammelten Informationen werden zu Office-Standorten und verbundenen Internet-Schaltkreisen aggregiert. Mithilfe dieser Informationen können Sie Microsoft bei der Verwendung von Microsoft 365-Diensten und-Anwendungen helfen, die gemeldeten Probleme effizienter und effektiver zu beheben.

>[!NOTE]
>Microsoft 365 informiertes Netzwerkrouting unterstützt Mandanten in der WW-kommerziellen Cloud, jedoch nicht in den Clouds gcc moderat, gcc High, DoD, Deutschland oder China.

## <a name="requirements"></a>Anforderungen

### <a name="integrated-sd-wan-solutions"></a>Integrierte SD-WAN-Lösungen

Microsoft arbeitet mit verschiedenen Partnern zusammen, um die Integration in das von Microsoft 365 informierte Netzwerkrouting zu ermöglichen. Zu den derzeit aktivierten Lösungen gehören folgende:

| Gerätehersteller | Solution Name | Minimale Version |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20,4/17.4 |

### <a name="network-topology"></a>Netzwerktopologie 

Das informierte Netzwerkrouting identifiziert derzeit Datenverkehr, der einem bestimmten Bürostandort und einer Internet Schaltung zugeordnet ist, basierend auf der öffentlichen IP-Adresse, die zum Senden von Netzwerkdatenverkehr an Microsoft verwendet wird. 

Wenn es nicht mindestens einen Netzwerk Stromkreis gibt, der direkten Internet Zugriff an einem Zweigstellenstandort bereitstellt, bietet das Netzwerk informiertes Routing möglicherweise keinen signifikanten Wert.

### <a name="application-usage"></a>Anwendungsverwendung

Anwendungs Erfahrungsdaten (werden durch Netzwerk Qualitäts Metriken reflektiert) werden über die Verwendung von Microsoft Outlook auf Geräten mit Windows, Microsoft Teams, SharePoint und OneDrive gesammelt. Bei der Bewertung der Integrität einer Netzwerk Schaltung wird kein anderer Anwendungsdatenverkehr berücksichtigt.

## <a name="enabling-informed-network-routing"></a>Aktivieren des informierten Netzwerk Routings

Um das informierte Netzwerkrouting zu ermöglichen, sind mehrere Schritte erforderlich, von denen einige in der Konfigurationsschnittstelle Ihrer SD-WAN-Lösung ausgeführt werden müssen. Wenden Sie sich an Ihren SD-WAN-Lösungsanbieter, um Anleitungen zum Initiieren des Prozesses zur Aktivierung des Netzwerk informierten Routings in der SD-WAN-Lösung zu erhalten, bevor Sie mit der Konfiguration im Microsoft 365 Admin Center fortfahren.

Wenn Sie bereit sind, das informierte Netzwerkrouting im Microsoft 365 Admin Center zu aktivieren, stellen Sie sicher, dass Sie über die erforderlichen globalen Administratorberechtigungen verfügen.

>[!IMPORTANT]
>Um die erforderlichen Berechtigungen auf Mandantenebene für die ausgewählte SD-WAN-Lösung für den Zugriff auf den informierten Netzwerkrouting-Datenfreigabe Kanal bereitzustellen, müssen Sie die folgenden Schritte als globaler Administrator ausführen.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Schritt 1: Öffnen der Konfigurationsoptionen für die SD-WAN-Lösung

Wählen Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)im linken Navigationsbereich die Option **Integritäts > Netzwerkkonnektivität** aus.

Dieser Abschnitt des Admin Centers enthält aggregierte Metriken für die Netzwerkkonnektivität für Ihre Organisation sowie Anleitungen zum Verbessern der Konnektivität. Unter [Netzwerkkonnektivität im Microsoft 365 Admin Center (Preview)](office-365-network-mac-perf-overview.md) finden Sie weitere Informationen zu diesen Funktionen, die im Admin Center zur Verfügung stehen.

Wählen Sie **Einstellungen > SD-WAN-Lösung** aus, um den Bereich informierte Netzwerkrouting Konfiguration zu öffnen. Die anderen Optionen, die unter **Einstellungen** angezeigt werden, gelten für die allgemeine Anleitung zur Netzwerkkonnektivität im Admin Center und sind nicht erforderlich, um das informierte Netzwerkrouting zu aktivieren.

Wählen Sie im Bereich Konfiguration die Option **SD-WAN-Lösung hinzufügen (Vorschau)** aus.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Schritt 2: Auswählen Ihrer SD-WAN-Lösung und ihres Datenspeicherorts

Wählen Sie in den Dropdownfeldern die von Ihnen bereitgestellte SD-WAN-Lösung und den Speicherort aus, an dem die Daten mit dem Netzwerk informierten Routing gespeichert werden sollen. Weitere Informationen finden Sie im Abschnitt [Datenspeicherung](#data-storage) .

Wählen Sie **Weiter** aus.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Schritt 3: akzeptieren von Bedingungen für die Freigabe von Daten

Lesen und bestätigen Sie die mit dem Freigeben von Daten zwischen Microsoft und ihrer ausgewählten SD-WAN-Lösung verbundenen Bedingungen sorgfältig, und wählen Sie dann das angegebene Kontrollkästchen aus.

Wählen Sie **Weiter** aus.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Schritt 4: Erteilen von Berechtigungen für die SD-WAN-Lösung

Dieser Schritt initiiert eine Permission Grant-Anforderung mit Azure Active Directory (Azure AD). Sie werden aufgefordert, Berechtigungen auf Mandantenebene zu erteilen, mit denen Ihre ausgewählte SD-WAN-Lösung auf das informierte Netzwerkrouting-Datenspeicher und die mit Ihrem Mandanten verknüpften Dienst Integritätsinformationen zugreifen können. Für diese Aktion sind globale Administratorrollen Berechtigungen erforderlich.

Wählen Sie den Link **Berechtigung für diese Anwendung erteilen** aus, und befolgten Sie die Azure AD Anforderungen.

Nachdem Sie den Berechtigungs Zuschuss abgeschlossen haben, wählen Sie **weiter** aus.

### <a name="step-5-confirm-your-configuration-settings"></a>Schritt 5: Überprüfen der Konfigurationseinstellungen

Der letzte Schritt beim Aktivieren des Network Information Routing für Ihren Mandanten ist eine Bestätigungsseite, auf der die von Ihnen bereitgestellten Einstellungen angezeigt werden. 

Das informierte Netzwerkrouting ist nun für Ihren Mandanten aktiviert.

Wählen Sie **Fertig** aus, und schließen Sie dann den Konfigurationsbereich SD-WAN Solution.

## <a name="configuring-network-informed-routing"></a>Konfigurieren des Netzwerks informiertes Routing

Sie führen einen Großteil der Konfiguration für das informierte Netzwerkrouting innerhalb Ihrer SD-WAN-Lösung aus, beispielsweise die Konfiguration der Weiterleitung des Datenverkehrs unter normalen Umständen und die alternativen Pfade, die bei der Erkennung von Problemen verwendet werden sollten. Ausführliche Informationen zu diesen Konfigurationsschritten finden Sie bei Ihrem SD-WAN-Lösungsanbieter.

Jeder Office-Standort muss im Microsoft 365 Admin Center konfiguriert sein, damit das informierte Netzwerkrouting ordnungsgemäß den Datenverkehr erkennt, der mit den Netz Stromkreisen verbunden ist, die Konnektivität zu diesen Standorten bereitstellen.

Office-Standorte werden möglicherweise automatisch als Teil der laufenden Sammlung von Microsoft-Netzwerk Telemetrie erkannt. Daher können einige Standorte im Admin Center für Ihren Mandanten vorab ausgefüllt werden. 

Wenn diese Speicherorte korrekt sind, müssen Sie einfach das informierte Netzwerkrouting Feature für jeden gewünschten Standort aktivieren und die Internet Schaltungen und ihre öffentlichen IP-Adressen konfigurieren. 

Wenn die automatisch erkannten Speicherorte nicht korrekt sind oder keine Speicherorte in Ihrem Mandanten vorab ausgefüllt sind, müssen Sie Orte manuell hinzufügen oder bearbeiten, um eine exakte Topologie Ihrer Organisation widerzuspiegeln.

### <a name="updating-locations"></a>Aktualisieren von Speicherorten

Standorte für Ihren Mandanten finden Sie unter der Registerkarte **Standorte** . Speicherorte können direkt in der Liste bearbeitet oder mithilfe einer CSV-Datei aktualisiert werden.

Stellen Sie sicher, dass alle Office-Standorte, an denen Sie das informierte Netzwerkrouting aktivieren möchten, in dieser Liste enthalten sind.

>[!NOTE]
>Die Spalten in der Liste **Speicherorte** für gesammelte Beispiele und andere bewertungsbezogene Informationen beziehen sich nicht auf das informierte Netzwerk Weiterleitungs Feature.

### <a name="enabling-a-location-for-informed-network-routing"></a>Aktivieren eines Standorts für das informierte Netzwerkrouting

1. Wählen Sie in der Liste **Speicherorte** im Menü schnell Aktionen die Option **Bearbeiten** aus, um den Bereich Standortkonfiguration zu öffnen.

2. Wählen Sie **an dieser Stelle Microsoft 365-informiertes Netzwerkrouting verwenden** aus.

3. Fügen Sie im Abschnitt **IP-Adressbereiche ausgehend zu diesem** Büro alle Netzwerk Schaltkreise mit Internet Konnektivität zu diesem Office-Standort hinzu. Stellen Sie sicher, dass jeder Schaltkreis mit den eindeutigen öffentlichen IP-Adressen-Subnetzen verknüpft ist, die ihren Netzwerkdatenverkehr darstellen.

4. Wählen Sie **Speichern** aus, um Ihre Änderungen zu speichern.

## <a name="disabling-network-informed-routing"></a>Deaktivieren des Netzwerks informiertes Routing

Das informierte Netzwerkrouting Feature kann für den gesamten Mandanten deaktiviert werden, indem die Einstellungen für die SD-WAN-Lösung zurückgesetzt werden. Während dies die gesamte Verarbeitung von Daten in Microsoft 365 stoppt, sollten Sie auch das Netzwerk informierte Routing im Admin Center deaktivieren.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Schritt 1: Öffnen der Konfigurationsoptionen für die SD-WAN-Lösung

Wählen Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/) im linken Navigationsbereich die Option **Integritäts > Netzwerkkonnektivität** aus.

Wählen Sie **Einstellungen > SD-WAN-Lösung** aus, um den Bereich informierte Netzwerkrouting Konfiguration zu öffnen.

Im Konfigurationsbereich wird eine Zusammenfassung der derzeit konfigurierten SD-WAN-Lösung angezeigt.

### <a name="step-2-reset-your-configuration"></a>Schritt 2: Zurücksetzen der Konfiguration

Wählen Sie im Bereich Konfiguration die Option Einstellungen für die **SD-WAN-Lösung zurücksetzen** aus.

Ihre Einstellungen wurden nun zurückgesetzt, und das informierte Netzwerkrouting wurde deaktiviert. Sie können es jederzeit wieder aktivieren, indem Sie die Schritte unter Aktivieren des [informierten Netzwerk Routings](#enabling-informed-network-routing)befolgen.

## <a name="data-storage"></a>Datenspeicher

Daten, die zwischen Microsoft und dem SD-WAN-Lösungsanbieter ausgetauscht werden, werden an dem Datenspeicher Speicherort gespeichert, der bei der erstmaligen Aktivierung des Netzwerks informierten Routings ausgewählt wurde. Die Optionen für Datenspeicherorte stellen geographische Bereiche dar, die Microsoft Azure Regionen enthalten, in denen die Daten gespeichert sind.

>[!NOTE]
>Während der Vorschauphase ist der einzige verfügbare Datenspeicherort **Nordamerika**. Zusätzliche Datenspeicherorte werden vor der allgemeinen Verfügbarkeit des informierten Netzwerk Routings zur Verfügung gestellt.

Die Daten werden an diesem Speicherort für bis zu 30 Tage aufbewahrt. Wenn diese Option deaktiviert ist, werden alle verbleibenden Daten innerhalb dieses 30-tägigen Aufbewahrungs Fensters entfernt.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
