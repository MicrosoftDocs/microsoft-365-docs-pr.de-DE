---
title: Netzwerkgeräteerkennung und Sicherheitsrisikoverwaltung
description: Sicherheitsempfehlungen und Die Erkennung von Sicherheitsrisiken sind jetzt für Betriebssysteme von Switches, Routern, WLAN-Controllern und Firewalls verfügbar.
keywords: Netzwerkgeräte, Erkennung von Sicherheitslücken bei Netzwerkgeräten, Betriebssysteme von Switches, Routern, WLAN-Controllern und Firewalls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: da15519211599bfc248c20c36cfab456c1661caa
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862067"
---
# <a name="network-device-discovery-and-vulnerability-management"></a>Netzwerkgeräteerkennung und Sicherheitsrisikoverwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Das Scannen und Verwalten von Netzwerkgeräten befindet sich derzeit in der öffentlichen Vorschau.**<br>
> Diese Vorschauversion wird ohne Vereinbarung zum Servicelevel bereitgestellt und wird für Produktionsworkloads nicht empfohlen. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.
> Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint Preview Features](preview.md).

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> Der [Blog zur](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Ermittlung und Bewertung von Sicherheitslücken für Netzwerkgeräte in \( 04-13-2021 bietet Einblicke in die neuen Netzwerkgeräteerkennungsfunktionen \) in Defender for Endpoint.  Dieser Artikel enthält eine Übersicht  über die Herausforderung, die die Netzwerkgeräteermittlung bewältigen soll, sowie ausführliche Informationen über die ersten Schritte mit diesen neuen Funktionen.

Netzwerkerkennungsfunktionen sind im  Abschnitt Gerätebestand des Microsoft 365 Security Center und der Microsoft Defender Security Center-Konsolen verfügbar.  

Für jedes Netzwerksegment wird ein bestimmtes Microsoft Defender for Endpoint-Gerät verwendet, um regelmäßig authentifizierte Scans vorkonfigurierter Netzwerkgeräte durchzuführen. Nach dem Entdecken bieten die Bedrohungs- und Sicherheitsmanagementfunktionen von Defender for Endpoint integrierte Workflows, um ermittelte Switches, Router, WLAN-Controller, Firewalls und VPN-Gateways zu sichern.  

Sobald die Netzwerkgeräte erkannt und klassifiziert wurden, können Sicherheitsadministratoren die neuesten Sicherheitsempfehlungen erhalten und kürzlich festgestellte Sicherheitsrisiken auf Netzwerkgeräten überprüfen, die in ihren Organisationen bereitgestellt wurden.

## <a name="approach"></a>Ansatz

Netzwerkgeräte werden nicht als Standardendpunkte verwaltet, da Defender for Endpoint keinen Sensor in die Netzwerkgeräte selbst integrierte. Diese Gerätetypen erfordern einen agentlosen Ansatz, bei dem eine Remotescan die erforderlichen Informationen von den Geräten erhält. Je nach Netzwerktopologie und -merkmalen führt ein einzelnes Gerät oder einige wenige In Microsoft Defender for Endpoint integrierte Geräte authentifizierte Scans von Netzwerkgeräten mithilfe von SNMP durch (schreibgeschützt).

Es gibt zwei Arten von Geräten, die Sie beachten sollten:

- **Bewertungsgerät:** Ein Gerät, das bereits onboarded ist, mit dem Sie die Netzwerkgeräte überprüfen.
- **Netzwerkgeräte:** Die Netzwerkgeräte, die Sie überprüfen und onboarden möchten.

### <a name="vulnerability-management-for-network-devices"></a>Sicherheitsrisikoverwaltung für Netzwerkgeräte 

Sobald die Netzwerkgeräte erkannt und klassifiziert wurden, können Sicherheitsadministratoren die neuesten Sicherheitsempfehlungen erhalten und kürzlich festgestellte Sicherheitsrisiken auf Netzwerkgeräten überprüfen, die in ihren Organisationen bereitgestellt wurden.  

## <a name="operating-systems-that-are-supported"></a>Unterstützte Betriebssysteme

Die folgenden Betriebssysteme werden derzeit unterstützt:

- Cisco IOS, IOS-XE, NX-OS
- Juniper JUNOS
- HPE ArubaOS, Procurve Switch Software
- Palo Alto Networks PAN-OS

Weitere Netzwerkanbieter und Betriebssysteme werden im Laufe der Zeit hinzugefügt, basierend auf daten, die aus der Kundennutzung gesammelt werden. Daher wird empfohlen, alle Netzwerkgeräte zu konfigurieren, auch wenn sie nicht in dieser Liste angegeben sind.

## <a name="how-to-get-started"></a>Erste Schritte

Im ersten Schritt wählen Sie ein Gerät aus, auf dem die authentifizierten Netzwerkscans ausgeführt werden.

1. Entscheiden Sie sich für ein integriertes Defender for Endpoint-Gerät (Client oder Server), das über eine Netzwerkverbindung zum Verwaltungsport für die Netzwerkgeräte verfügt, die Sie scannen möchten. 

2. Der SNMP-Datenverkehr zwischen dem Defender for Endpoint-Bewertungsgerät und den zielgerichteten Netzwerkgeräten muss zulässig sein (z. B. durch die Firewall).

3. Entscheiden Sie, welche Netzwerkgeräte auf Sicherheitsrisiken geprüft werden (z. B. ein Cisco Switch oder eine Palo Alto Networks-Firewall).  

4. Stellen Sie sicher, dass SNMP schreibgeschützt auf allen konfigurierten Netzwerkgeräten aktiviert ist, damit das Defender for Endpoint-Bewertungsgerät die konfigurierten Netzwerkgeräte abfragen kann. "SNMP write" ist für die ordnungsgemäße Funktionalität dieses Features nicht erforderlich.

5. Rufen Sie die IP-Adressen der zu scannenden Netzwerkgeräte ab (oder die Subnetze, in denen diese Geräte bereitgestellt werden).

6. Rufen Sie die SNMP-Anmeldeinformationen der Netzwerkgeräte ab (z. B. Community String, noAuthNoPriv, authNoPriv, authPriv). Sie müssen die Anmeldeinformationen beim Konfigurieren eines neuen Bewertungsauftrags angeben.  

7. Proxyclientkonfiguration: Außer den Anforderungen des Defender for Endpoint-Geräteproxys ist keine zusätzliche Konfiguration erforderlich.

8. Damit der Netzwerkscanner authentifiziert werden kann und ordnungsgemäß funktioniert, müssen Sie unbedingt die folgenden Domänen/URLs hinzufügen:

    - login.windows.net  
    - *.securitycenter.windows.com
    - login.microsoftonline.com
    - *.blob.core.windows.net/networkscannerstable/ *

    > [!NOTE]
    > Nicht alle URLs sind in der dokumentierten Liste der zulässigen Datensammlungen von Defender for Endpoint angegeben.

## <a name="permissions"></a>Berechtigungen

Zum Konfigurieren von Bewertungsaufträgen ist die folgende Benutzerberechtigungsoption erforderlich: **Verwalten von Sicherheitseinstellungen in Security Center**. Sie können die Berechtigung finden, indem Sie zu **Einstellungen**  >  **Rollen .** Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung](user-roles.md).

## <a name="install-the-network-scanner"></a>Installieren des Netzwerkscanners

1. Wechseln Sie **zu Microsoft 365 Security**  >  **Settings**  >  **Endpoints**  >  **Assessment jobs** (under Network **assessments**).
    1. Wechseln Sie im Microsoft Defender Security Center zur Seite Einstellungen > Bewertungsaufträge.

2. Laden Sie den Netzwerkscanner herunter, und installieren Sie ihn auf dem dafür vorgesehenen Defender for Endpoint-Bewertungsgerät.

    > [!div class="mx-imgBorder"]
    > ![Schaltfläche "Scanner herunterladen"](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a>Netzwerkscannerinstallation & Registrierung

Der Anmeldungsprozess kann auf dem festgelegten Bewertungsgerät selbst oder auf einem anderen Gerät (z. B. Ihrem persönlichen Clientgerät) abgeschlossen werden.

So führen Sie den Registrierungsprozess für Netzwerkscanner aus:

1. Kopieren Und folgen Sie der URL, die in der Befehlszeile angezeigt wird, und verwenden Sie den bereitgestellten Installationscode, um den Registrierungsprozess abzuschließen.

    > [!NOTE]
    > Möglicherweise müssen Sie die Eingabeaufforderungseinstellungen ändern, um die URL kopieren zu können.

2. Geben Sie den Code ein, und melden Sie sich mit einem Microsoft-Konto an, das die Defender for Endpoint-Berechtigung "Sicherheitseinstellungen in Security Center verwalten" besitzt.

3. Wenn Sie fertig sind, sollte eine Meldung angezeigt werden, in der Sie bestätigen, dass Sie sich angemeldet haben.

## <a name="configure-a-new-assessment-job"></a>Konfigurieren eines neuen Bewertungsauftrags  

Wählen Sie auf der Seite Bewertungsaufträge unter **Einstellungen** die Option **Netzwerkbewertungsauftrag hinzufügen aus.** Führen Sie den Einrichtungsvorgang aus, um Netzwerkgeräte zu wählen, die regelmäßig überprüft und dem Gerätebestand hinzugefügt werden sollen.

Stellen Sie sicher, dass jede IP-Adresse nur einmal auf mehreren Bewertungsgeräten konfiguriert ist, um eine Geräteduplizierung im Netzwerkgerätebestand zu verhindern.

> [!div class="mx-imgBorder"]
> ![Hinzufügen einer Netzwerkbewertungsauftragsschaltfläche](images/assessment-jobs-add.png)

Hinzufügen eines Auftrags zur Netzwerkbewertung:

1. Wählen Sie den Namen "Bewertungsauftrag" und das "Bewertungsgerät", auf dem der Netzwerkscanner installiert wurde. Dieses Gerät führt die regelmäßig authentifizierten Scans aus.

2. Fügen Sie IP-Adressen der zu scannenden Zielnetzwerkgeräte (oder der Subnetze, in denen diese Geräte bereitgestellt werden) hinzu. 

3. Fügen Sie erforderliche SNMP-Anmeldeinformationen der Zielnetzwerkgeräte hinzu. 

4. Speichern Sie den neu konfigurierten Netzwerkbewertungsauftrag, um die regelmäßige Netzwerkprüfung zu starten. 

### <a name="scan-and-add-network-devices"></a>Überprüfen und Hinzufügen von Netzwerkgeräten

Während des Einrichtungsprozesses können Sie eine einmal durchgeführte Testprüfung durchführen, um zu überprüfen, dass:

- Es besteht eine Verbindung zwischen dem Defender for Endpoint-Bewertungsgerät und den konfigurierten Zielnetzwerkgeräten.
- Die konfigurierten SNMP-Anmeldeinformationen sind richtig.

Jedes Bewertungsgerät kann bis zu 1.500 erfolgreiche ÜBERPRÜFUNGen von IP-Adressen unterstützen. Wenn Sie beispielsweise 10 verschiedene Subnetze überprüfen, in denen nur 100 IP-Adressen erfolgreiche Ergebnisse zurückgeben, können Sie 1.400 ZUSÄTZLICHE IP-Adressen aus anderen Subnetzen auf demselben Bewertungsgerät überprüfen.  

Wenn mehrere IP-Adressbereiche/Subnetze zu überprüfen sind, dauert es einige Minuten, bis die Testscanergebnisse angezeigt werden. Ein Testscan ist für bis zu 1.024 Adressen verfügbar.

Sobald die Ergebnisse angezeigt werden, können Sie auswählen, welche Geräte in die regelmäßige Überprüfung einbezogen werden sollen. Wenn Sie die Anzeige der Scanergebnisse überspringen, werden alle konfigurierten IP-Adressen dem Netzwerkbewertungsauftrag hinzugefügt (unabhängig von der Antwort des Geräts). Die Scanergebnisse können auch exportiert werden.

## <a name="device-inventory"></a>Geräteübersicht

Neu ermittelte Geräte werden  auf der Seite Geräteinventar unter der Registerkarte Neue **Netzwerkgeräte** angezeigt. Es kann bis zu zwei Stunden nach dem Hinzufügen eines Bewertungsauftrags dauern, bis die Geräte aktualisiert wurden.

> [!div class="mx-imgBorder"]
> ![Abschnitt "Netzwerkgeräte" im Geräteinventar](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a>Problembehandlung

### <a name="network-scanner-installation-has-failed"></a>Fehler bei der Installation von Netzwerkscannern

Stellen Sie sicher, dass die erforderlichen URLs den zulässigen Domänen in den Firewalleinstellungen hinzugefügt werden. Stellen Sie außerdem sicher, dass Proxyeinstellungen wie unter Konfigurieren von Geräteproxy- und [Internetkonnektivitätseinstellungen beschrieben konfiguriert sind.](configure-proxy-internet.md)

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a>Die Microsoft.com/devicelogin webseite wurde nicht angezeigt

Stellen Sie sicher, dass die erforderlichen URLs den zulässigen Domänen in Ihrer Firewall hinzugefügt werden. Stellen Sie außerdem sicher, dass Proxyeinstellungen wie unter Konfigurieren von Geräteproxy- und [Internetkonnektivitätseinstellungen beschrieben konfiguriert sind.](configure-proxy-internet.md)

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a>Netzwerkgeräte werden nach mehreren Stunden nicht im Gerätebestand angezeigt

Die Scanergebnisse sollten einige Stunden nach der ersten Überprüfung aktualisiert werden, die nach Abschluss der Konfiguration des Bewertungsauftrags stattgefunden hat.

Wenn geräte weiterhin nicht angezeigt werden, überprüfen Sie, ob der Dienst "MdatpNetworkScanService" auf Ihren Bewertungsgeräten ausgeführt wird, auf denen Sie den Netzwerkscanner installiert haben, und führen Sie in der entsprechenden Bewertungsauftragskonfiguration einen "Scan ausführen" aus.  

Wenn Sie nach 5 Minuten immer noch keine Ergebnisse erhalten, starten Sie den Dienst neu.  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a>Geräte, die zuletzt gesehen wurden, sind länger als 24 Stunden

Überprüfen Sie, ob der Scanner ordnungsgemäß ausgeführt wird. Wechseln Sie dann zur Scandefinition, und wählen Sie "Test ausführen" aus. Überprüfen Sie, welche Fehlermeldungen von den relevanten IP-Adressen zurückgegeben werden.

### <a name="required-threat-and-vulnerability-management-user-permission"></a>Erforderliche Benutzerberechtigung für die Bedrohungs- und Sicherheitsrisikoverwaltung

Die Registrierung wurde mit einem Fehler abgeschlossen: "Es sieht so aus, als ob Sie nicht über ausreichende Berechtigungen zum Hinzufügen eines neuen Agents verfügen. Die erforderliche Berechtigung ist 'Sicherheitseinstellungen in Security Center verwalten'."

Drücken Sie eine beliebige Taste, um zu beenden.

Bitten Sie Ihren Systemadministrator, Ihnen die erforderlichen Berechtigungen zu erteilen. Bitten Sie ein anderes relevantes Mitglied, Ihnen beim Anmeldevorgang zu helfen, indem Sie ihnen den Anmeldecode und den Link bereitstellen.

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a>Registrierungsprozess schlägt fehl, wenn der bereitgestellte Link in der Befehlszeile beim Registrierungsprozess verwendet wird

Probieren Sie einen anderen Browser aus, oder kopieren Sie den Anmeldelink und den Code auf ein anderes Gerät.

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a>Text zu klein oder kann keinen Text aus der Befehlszeile kopieren

Ändern Sie die Befehlszeileneinstellungen auf Ihrem Gerät, um das Kopieren und Ändern der Textgröße zu ermöglichen.

## <a name="related-articles"></a>Verwandte Artikel

- [Geräteinventar](machines-view-overview.md)
- [Konfigurieren erweiterter Funktionen](advanced-features.md)
