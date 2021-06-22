---
title: Netzwerkgeräteermittlung und Sicherheitsrisikomanagement
description: Sicherheitsempfehlungen und die Erkennung von Sicherheitsrisiken sind jetzt für Betriebssysteme von Switches, Routern, WLAN-Controllern und Firewalls verfügbar.
keywords: Netzwerkgeräte, Sicherheitsrisikoerkennung für Netzwerkgeräte, Betriebssysteme von Switches, Routern, WLAN-Controllern und Firewalls
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
ms.openlocfilehash: 86b8a37fd6b2d6f9906321b5d74de0e21c45fca3
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062139"
---
# <a name="network-device-discovery-and-vulnerability-management"></a>Netzwerkgeräteermittlung und Sicherheitsrisikomanagement

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> Der Am 13.04.2021 veröffentlichte Blog ["Ermittlung von Netzwerkgeräten und Sicherheitsrisikobewertungen"](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) bietet Einblicke in die neuen Funktionen zur \( Ermittlung von \) **Netzwerkgeräten** in Defender für Endpunkt. Dieser Artikel enthält eine Übersicht über die Herausforderung, die die Ermittlung von **Netzwerkgeräten** zu bewältigen hat, sowie detaillierte Informationen zu den ersten Schritten mit diesen neuen Funktionen.

Netzwerkermittlungsfunktionen sind im Abschnitt **"Geräteinventur"** des Microsoft 365 Security Centers und Microsoft Defender Security Center Konsolen verfügbar.  

Ein bestimmtes Microsoft Defender für Endpunkt-Gerät wird in jedem Netzwerksegment verwendet, um regelmäßige authentifizierte Scans von vorkonfigurierten Netzwerkgeräten durchzuführen. Nach der Erkennung bieten die Bedrohungs- und Sicherheitsrisikomanagement-Funktionen von Defender für Endpunkt integrierte Workflows, um ermittelte Switches, Router, WLAN-Controller, Firewalls und VPN-Gateways zu sichern.  

Sobald die Netzwerkgeräte ermittelt und klassifiziert wurden, können Sicherheitsadministratoren die neuesten Sicherheitsempfehlungen erhalten und kürzlich erkannte Sicherheitsrisiken auf Netzwerkgeräten überprüfen, die in ihrer Organisation bereitgestellt wurden.

## <a name="approach"></a>Ansatz

Netzwerkgeräte werden nicht als Standardendpunkte verwaltet, da Defender für Endpunkt keinen sensor in die Netzwerkgeräte selbst integriert hat. Diese Gerätetypen erfordern einen agentlosen Ansatz, bei dem ein Remotescan die erforderlichen Informationen von den Geräten abruft. Je nach Netzwerktopologie und -merkmalen führt ein einzelnes Gerät oder einige geräte, die in Microsoft Defender für Endpunkt integriert sind, authentifizierte Scans von Netzwerkgeräten mithilfe von SNMP durch (schreibgeschützt).

Es gibt zwei Arten von Geräten, die Sie berücksichtigen sollten:

- **Bewertungsgerät:** Ein bereits integriertes Gerät, das Sie zum Scannen der Netzwerkgeräte verwenden.
- **Netzwerkgeräte:** Die Netzwerkgeräte, die Sie scannen und integrieren möchten.

### <a name="vulnerability-management-for-network-devices"></a>Sicherheitsrisikoverwaltung für Netzwerkgeräte 

Sobald die Netzwerkgeräte ermittelt und klassifiziert wurden, können Sicherheitsadministratoren die neuesten Sicherheitsempfehlungen erhalten und kürzlich erkannte Sicherheitsrisiken auf Netzwerkgeräten überprüfen, die in ihrer Organisation bereitgestellt wurden.  

## <a name="operating-systems-that-are-supported"></a>Unterstützte Betriebssysteme

Die folgenden Betriebssysteme werden derzeit unterstützt:

- Cisco IOS, IOS-XE, NX-OS
- Juniper JUNOS
- HPE IntuneOS, Procurve Switch Software
- Palo Alto Networks PAN-OS

Im Laufe der Zeit werden weitere Netzwerkanbieter und Das Betriebssystem hinzugefügt, basierend auf den von der Kundennutzung gesammelten Daten. Daher wird empfohlen, alle Ihre Netzwerkgeräte zu konfigurieren, auch wenn sie in dieser Liste nicht angegeben sind.

## <a name="how-to-get-started"></a>Erste Schritte

Der erste Schritt besteht darin, ein Gerät auszuwählen, das die authentifizierten Netzwerküberprüfungen durchführt.

1. Entscheiden Sie sich für ein integriertes Defender für Endpunkt-Gerät (Client oder Server), das über eine Netzwerkverbindung mit dem Verwaltungsport für die Netzwerkgeräte verfügt, die Sie überprüfen möchten. 

2. SNMP-Datenverkehr zwischen dem Defender für Endpunkt-Bewertungsgerät und den Zielnetzwerkgeräten muss zulässig sein (z. B. durch die Firewall).

3. Entscheiden Sie, welche Netzwerkgeräte auf Sicherheitsrisiken überprüft werden (z. B. ein Cisco-Switch oder eine Firewall von Palo Alto Networks).  

4. Stellen Sie sicher, dass SNMP schreibgeschützt auf allen konfigurierten Netzwerkgeräten aktiviert ist, damit das Defender für Endpunkt-Bewertungsgerät die konfigurierten Netzwerkgeräte abfragen kann. "SNMP-Schreibvorgang" ist für die ordnungsgemäße Funktionalität dieses Features nicht erforderlich.

5. Rufen Sie die IP-Adressen der zu scannenden Netzwerkgeräte ab (oder die Subnetze, in denen diese Geräte bereitgestellt werden).

6. Rufen Sie die SNMP-Anmeldeinformationen der Netzwerkgeräte ab (z. B.: Community String, noAuthNoPriv, authNoPriv, authPriv). Sie müssen die Anmeldeinformationen angeben, wenn Sie einen neuen Bewertungsauftrag konfigurieren.  

7. Proxyclientkonfiguration: Außer den Proxyanforderungen des Defender für Endpunkt-Geräts ist keine zusätzliche Konfiguration erforderlich.

8. Damit der Netzwerkscanner authentifiziert werden kann und ordnungsgemäß funktioniert, müssen Sie unbedingt die folgenden Domänen/URLs hinzufügen:

    - login.windows.net  
    - *.securitycenter.windows.com
    - login.microsoftonline.com
    - *.blob.core.windows.net/networkscannerstable/ *

    > [!NOTE]
    > Nicht alle URLs werden in der dokumentierten Liste der zulässigen Datensammlungen von Defender für Endpunkt angegeben.

## <a name="permissions"></a>Berechtigungen

Zum Konfigurieren von Bewertungsaufträgen ist die folgende Benutzerberechtigungsoption erforderlich: **Verwalten von Sicherheitseinstellungen im Security Center.** Sie finden die Berechtigung unter **Einstellungen**  >  **Rollen.** Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung.](user-roles.md)

## <a name="install-the-network-scanner"></a>Installieren des Netzwerkscanners

1. Wechseln Sie zu **Microsoft 365**  >  **Sicherheits-Einstellungen**  >  **Endpunktbewertungsaufträgen**  >   (unter **Netzwerkbewertungen).**
    1. Wechseln Sie im Microsoft Defender Security Center zur Seite Einstellungen > Bewertungsaufträge.

2. Laden Sie den Netzwerkscanner herunter, und installieren Sie ihn auf dem angegebenen Defender für Endpunkt-Bewertungsgerät.

    > [!div class="mx-imgBorder"]
    > ![Schaltfläche "Scanner herunterladen"](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a>Netzwerkscanner-Installation & Registrierung

Der Anmeldevorgang kann auf dem angegebenen Bewertungsgerät selbst oder auf einem anderen Gerät (z. B. Ihrem persönlichen Clientgerät) abgeschlossen werden.

So schließen Sie den Registrierungsvorgang für den Netzwerkscanner ab:

1. Kopieren Und folgen Sie der URL, die in der Befehlszeile angezeigt wird, und verwenden Sie den bereitgestellten Installationscode, um den Registrierungsprozess abzuschließen.

    > [!NOTE]
    > Möglicherweise müssen Sie die Eingabeaufforderungseinstellungen ändern, um die URL kopieren zu können.

2. Geben Sie den Code ein, und melden Sie sich mit einem Microsoft-Konto an, das über die Defender für Endpunkt-Berechtigung "Verwalten von Sicherheitseinstellungen im Security Center" verfügt.

3. Wenn Sie fertig sind, sollte eine Meldung angezeigt werden, die bestätigt, dass Sie sich angemeldet haben.

## <a name="configure-a-new-assessment-job"></a>Konfigurieren eines neuen Bewertungsauftrags  

Wählen Sie auf der Seite "Bewertungsaufträge" in **Einstellungen** die Option **"Netzwerkbewertungsauftrag hinzufügen"** aus. Folgen Sie dem Einrichtungsprozess, um Netzwerkgeräte auszuwählen, die regelmäßig überprüft und dem Gerätebestand hinzugefügt werden sollen.

Um eine Geräteduplizierung im Netzwerkgerätebestand zu verhindern, stellen Sie sicher, dass jede IP-Adresse auf mehreren Bewertungsgeräten nur einmal konfiguriert ist.

> [!div class="mx-imgBorder"]
> ![Schaltfläche "Netzwerkbewertungsauftrag hinzufügen"](images/assessment-jobs-add.png)

Hinzufügen von Netzwerkbewertungsauftragsschritten:

1. Wählen Sie den Namen "Bewertungsauftrag" und das "Bewertungsgerät" aus, auf dem der Netzwerkscanner installiert wurde. Dieses Gerät führt die regelmäßigen authentifizierten Scans durch.

2. Fügen Sie IP-Adressen von Zielnetzwerkgeräten hinzu, die gescannt werden sollen (oder die Subnetze, in denen diese Geräte bereitgestellt werden). 

3. Fügen Sie die erforderlichen SNMP-Anmeldeinformationen der Zielnetzwerkgeräte hinzu. 

4. Speichern Sie den neu konfigurierten Netzwerkbewertungsauftrag, um die regelmäßige Netzwerküberprüfung zu starten. 

### <a name="scan-and-add-network-devices"></a>Scannen und Hinzufügen von Netzwerkgeräten

Während des Einrichtungsprozesses können Sie einen einmaligen Testscan durchführen, um Folgendes zu überprüfen:

- Es besteht eine Verbindung zwischen dem Defender für Endpunkt-Bewertungsgerät und den konfigurierten Zielnetzwerkgeräten.
- Die konfigurierten SNMP-Anmeldeinformationen sind korrekt.

Jedes Bewertungsgerät kann bis zu 1.500 erfolgreiche IP-Adressenüberprüfungen unterstützen. Wenn Sie beispielsweise 10 verschiedene Subnetze scannen, in denen nur 100 IP-Adressen erfolgreiche Ergebnisse zurückgeben, können Sie 1.400 zusätzliche IP-Adressen aus anderen Subnetzen auf demselben Bewertungsgerät überprüfen.  

Wenn mehrere IP-Adressbereiche/Subnetze überprüft werden müssen, dauert es mehrere Minuten, bis die Testscanergebnisse angezeigt werden. Ein Testscan wird für bis zu 1.024 Adressen verfügbar sein.

Sobald die Ergebnisse angezeigt werden, können Sie auswählen, welche Geräte in den regelmäßigen Scan einbezogen werden. Wenn Sie die Anzeige der Scanergebnisse überspringen, werden alle konfigurierten IP-Adressen dem Netzwerkbewertungsauftrag hinzugefügt (unabhängig von der Antwort des Geräts). Die Scanergebnisse können auch exportiert werden.

## <a name="device-inventory"></a>Geräteübersicht

Neu ermittelte Geräte werden auf der Seite **"Gerätebestand"** auf der Registerkarte "Neue **Netzwerkgeräte"** angezeigt. Es kann bis zu zwei Stunden nach dem Hinzufügen eines Bewertungsauftrags dauern, bis die Geräte aktualisiert wurden.

> [!div class="mx-imgBorder"]
> ![Abschnitt "Netzwerkgeräte" im Gerätebestand](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a>Problembehandlung

### <a name="network-scanner-installation-has-failed"></a>Installation des Netzwerkscanners fehlgeschlagen

Stellen Sie sicher, dass die erforderlichen URLs den zulässigen Domänen in den Firewalleinstellungen hinzugefügt werden. Stellen Sie außerdem sicher, dass Proxyeinstellungen wie unter [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen](configure-proxy-internet.md)beschrieben konfiguriert sind.

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a>Die Microsoft.com/devicelogin Webseite wurde nicht angezeigt

Stellen Sie sicher, dass die erforderlichen URLs den zulässigen Domänen in Ihrer Firewall hinzugefügt werden. Stellen Sie außerdem sicher, dass Proxyeinstellungen wie unter [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen](configure-proxy-internet.md)beschrieben konfiguriert sind.

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a>Netzwerkgeräte werden nach mehreren Stunden nicht im Gerätebestand angezeigt

Die Scanergebnisse sollten einige Stunden nach der ersten Überprüfung aktualisiert werden, die nach Abschluss der Konfiguration des Bewertungsauftrags durchgeführt wurde.

Wenn Geräte weiterhin nicht angezeigt werden, überprüfen Sie, ob der Dienst "MdatpNetworkScanService" auf Ihren Bewertungsgeräten ausgeführt wird, auf denen Sie den Netzwerkscanner installiert haben, und führen Sie in der entsprechenden Konfiguration des Bewertungsauftrags eine "Überprüfung ausführen" aus.  

Wenn Sie nach 5 Minuten immer noch keine Ergebnisse erhalten, starten Sie den Dienst neu.  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a>Geräte, die zuletzt gesehen wurden, sind länger als 24 Stunden.

Überprüfen Sie, ob der Scanner ordnungsgemäß ausgeführt wird. Wechseln Sie dann zur Scandefinition, und wählen Sie "Test ausführen" aus. Überprüfen Sie, welche Fehlermeldungen von den entsprechenden IP-Adressen zurückgegeben werden.

### <a name="required-threat-and-vulnerability-management-user-permission"></a>Erforderliche Bedrohungs- und Sicherheitsrisikomanagement Benutzerberechtigung

Die Registrierung wurde mit einem Fehler abgeschlossen: "Es sieht so aus, als ob Sie nicht über ausreichende Berechtigungen zum Hinzufügen eines neuen Agents verfügen. Die erforderliche Berechtigung lautet "Sicherheitseinstellungen im Security Center verwalten"."

Drücken Sie eine beliebige Taste, um zu beenden.

Bitten Sie Ihren Systemadministrator, Ihnen die erforderlichen Berechtigungen zuzuweisen. Bitten Sie alternativ ein anderes relevantes Mitglied, Ihnen beim Anmeldevorgang zu helfen, indem Sie ihnen den Anmeldecode und den Link zur Verfügung stellen.

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a>Registrierungsvorgang schlägt bei Verwendung des bereitgestellten Links in der Befehlszeile im Registrierungsprozess fehl

Probieren Sie einen anderen Browser aus, oder kopieren Sie den Anmeldelink und den Code auf ein anderes Gerät.

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a>Text zu klein oder Text kann nicht aus der Befehlszeile kopiert werden

Ändern Sie die Befehlszeileneinstellungen auf Ihrem Gerät, um das Kopieren und Ändern der Textgröße zuzulassen.

## <a name="related-articles"></a>Verwandte Artikel

- [Gerätebestand](machines-view-overview.md)
- [Konfigurieren erweiterter Funktionen](advanced-features.md)
