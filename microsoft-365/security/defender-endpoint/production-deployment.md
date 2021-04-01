---
title: Einrichten der Bereitstellung von Microsoft Defender for Endpoint
description: Informationen zum Einrichten der Bereitstellung für Microsoft Defender for Endpoint
keywords: Bereitstellen, Einrichten, Lizenzierungsüberprüfung, Mandantenkonfiguration, Netzwerkkonfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7abf1c9e4115c928ae581da3789270fd8ed036d3
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476310"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>Einrichten der Bereitstellung von Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Die Bereitstellung von Defender for Endpoint ist ein drei phasenweiser Prozess:

| [![Bereitstellungsphase – Vorbereiten](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Phase 1: Vorbereiten](prepare-deployment.md) | ![Bereitstellungsphase – Setup](images/phase-diagrams/setup.png)<br>Phase 2: Setup | [![Bereitstellungsphase – onboard](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Phase 3: Onboarding](onboarding.md) |
| ----- | ----- | ----- |
| | *Sie sind hier!*||

Sie befinden sich derzeit in der Einrichtungsphase.

In diesem Bereitstellungsszenario werden Sie durch die folgenden Schritte geführt:
- Lizenzierungsüberprüfung
- Mandantenkonfiguration
- Netzwerkkonfiguration


>[!NOTE]
>Um Sie durch eine typische Bereitstellung zu führen, wird in diesem Szenario nur die Verwendung von Microsoft Endpoint Configuration Manager beschrieben. Defender for Endpoint unterstützt die Verwendung anderer Onboardingtools, diese Szenarien werden jedoch nicht im Bereitstellungshandbuch beschrieben. Weitere Informationen finden Sie unter [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).

## <a name="check-license-state"></a>Überprüfen des Lizenzstatus

Die Überprüfung auf den Lizenzstatus und ob er ordnungsgemäß bereitgestellt wurde, kann über das Admin Center oder über das **Microsoft Azure-Portal durchgeführt werden.**

1. Um Ihre Lizenzen anzeigen zu können, wechseln Sie zum **Microsoft Azure-Portal,** und navigieren Sie zum [Microsoft Azure-Portallizenzabschnitt](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).

   ![Abbildung der Azure-Lizenzierungsseite](images/atp-licensing-azure-portal.png)

1. Navigieren Sie im Admin Center alternativ zu **Abrechnungsabonnements**  >  .

    Auf dem Bildschirm werden alle bereitgestellten Lizenzen und deren aktueller **Status angezeigt.**

    ![Abbildung von Abrechnungslizenzen](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a>Überprüfung des Clouddienstanbieters

Um Zugriff darauf zu erhalten, welche Lizenzen für Ihr Unternehmen bereitgestellt werden, und um den Status der Lizenzen zu überprüfen, wechseln Sie zum Admin Center.

1. Wählen Sie **im Partnerportal** Die Option **Dienste > Office 365 verwalten aus.**

2. Wenn Sie auf den **Link Partnerportal** klicken, wird die Option **Admin im** Namen geöffnet, und Sie erhalten Zugriff auf das Customer Admin Center.

   ![Abbildung des O365-Verwaltungsportals](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a>Mandantenkonfiguration

Beim ersten Zugriff auf Microsoft Defender Security Center ein Assistent, der Sie durch einige erste Schritte führt. Am Ende des Setup-Assistenten wird eine dedizierte Cloudinstanz von Defender for Endpoint erstellt. Die einfachste Methode besteht in der Ausführung dieser Schritte auf einem Windows 10-Clientgerät.

1. Navigieren Sie in einem Webbrowser zu <https://securitycenter.windows.com> .

    ![Abbildung von Einrichten Ihrer Berechtigungen für Microsoft Defender for Endpoint](images/atp-setup-permissions-wdatp-portal.png)

2. Wenn Sie eine TRIAL-Lizenz durchgehen, wechseln Sie zu dem Link ( <https://signup.microsoft.com/Signup?OfferId=6033e4b5-c320-4008-a936-909c2825d83c&dl=WIN_DEF_ATP&pc=xxxxxxx-xxxxxx-xxx-x> )

    Sobald der Autorisierungsschritt abgeschlossen ist, wird der **Willkommensbildschirm** angezeigt.
3. Gehen Sie durch die Autorisierungsschritte.

    ![Abbildung des Willkommensbildschirms für die Einrichtung des Portals](images/welcome1.png)

4. Richten Sie Einstellungen ein.

   **Datenspeicherort:** Es ist wichtig, dass Sie dies ordnungsgemäß einrichten. Bestimmen Sie, wo der Kunde hauptsächlich gehostet werden möchte: USA, EU oder Großbritannien. Sie können den Speicherort nach dieser Einrichtung nicht mehr ändern, und Microsoft übertstrat die Daten nicht von der angegebenen Geolocation. 

    **Datenaufbewahrung** – Der Standardwert ist sechs Monate.

    **Aktivieren von Vorschaufeatures** – Der Standardwert ist aktiviert, kann später geändert werden.

    ![Abbildung des geografischen Standorts in der Einrichtung](images/setup-preferences.png)

5. Klicken Sie auf **Weiter**.

     ![Abbildung der endgültigen Einstellungseinstellung](images/setup-preferences2.png)

6. Wählen Sie **Weiter** aus.


## <a name="network-configuration"></a>Netzwerkkonfiguration
Wenn die Organisation nicht erfordert, dass die Endpunkte einen Proxy für den Zugriff auf das Internet verwenden, überspringen Sie diesen Abschnitt.

Der Microsoft Defender für Endpunkt-Sensor setzt Microsoft Windows HTTP (WinHTTP) voraus, um Sensordaten zu melden und mit dem Microsoft Defender für Endpunkt-Dienst zu kommunizieren. Der eingebettete Microsoft Defender for Endpoint-Sensor wird im Systemkontext mithilfe des LocalSystem-Kontos ausgeführt. Der Sensor verwendet Microsoft Windows-HTTP-Dienste (WinHTTP), um die Kommunikation mit dem Microsoft Defender für Endpunkt-Clouddienst zu ermöglichen. Die WinHTTP-Konfigurationseinstellung ist unabhängig von den Windows Internet (WinINet)-Internet-Browserproxyeinstellungen und kann nur mithilfe der folgenden Ermittlungsmethoden einen Proxyserver ermitteln:

**AutoErmittlungsmethoden:**

-   Transparenter Proxy

-   Webproxy-AutoErmittlungsprotokoll (WPAD)

Wenn in der Netzwerktopologie ein transparenter Proxy oder ein WPAD implementiert wurde, sind keine speziellen Konfigurationseinstellungen erforderlich. Weitere Informationen zu Microsoft Defender for Endpoint-URL-Ausschlüssen im Proxy finden Sie im Abschnitt [Proxydienst-URLs](production-deployment.md#proxy-service-urls) in diesem Dokument für die Liste der URLs zulassen oder unter Konfigurieren von Geräteproxy- und [Internetkonnektivitätseinstellungen.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

**Manuelle Konfiguration von statischen Proxys:**

-   Registrierungsbasierte Konfiguration

-   WinHTTP mit netsh-Befehl konfiguriert <br> Nur für Desktops in einer stabilen Topologie geeignet (z. B. ein Desktop in einem Unternehmensnetzwerk hinter demselben Proxy)

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Manuelles Konfigurieren des Proxyservers mithilfe eines registrierungsbasierten statischen Proxys

Konfigurieren Sie einen registrierungsbasierten statischen Proxy, damit nur der Microsoft Defender for Endpoint-Sensor Diagnosedaten melden und mit Microsoft Defender for Endpoint-Diensten kommunizieren kann, wenn ein Computer keine Verbindung mit dem Internet herstellen darf. Der statische Proxy kann mithilfe von Gruppenrichtlinien konfiguriert werden. Die Gruppenrichtlinien finden Sie unter:

 - Administrative Vorlagen \> Windows-Komponenten Datensammlungs- und Vorschaubuilds Konfigurieren der authentifizierten Proxyverwendung für den verbundenen \> \> Benutzererfahrungs- und Telemetriedienst
     - Legen Sie sie auf **Aktiviert,** und wählen **Sie Authentifizierte Proxyverwendung deaktivieren aus.**

1. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole.
2. Erstellen Sie eine Richtlinie, oder bearbeiten Sie eine vorhandene Richtlinie basierend auf den Organisationspraktiken.
3. Bearbeiten Sie die Gruppenrichtlinie, und navigieren Sie zu **Administrative Vorlagen Windows Components Data Collection and Preview Builds Configure \> \> \> Authenticated Proxy usage for the Connected User Experience and Telemetry Service**. 
    ![Abbildung der Gruppenrichtlinienkonfiguration](images/atp-gpo-proxy1.png)

4. Wählen Sie **Aktiviert** aus.
5. Wählen **Sie Authentifizierte Proxyverwendung deaktivieren aus.**
   
6. Navigieren Sie **zu Administrative Vorlagen \> Windows-Komponenten \> Datensammlung und Vorschaubuilds Konfigurieren \> von verbundenen Benutzererfahrungen und Telemetrie**.
    ![Abbildung der Gruppenrichtlinienkonfigurationseinstellung](images/atp-gpo-proxy2.png)
7. Wählen Sie **Aktiviert** aus.
8. Geben Sie den **Proxyservernamen ein.**

Die Richtlinie setzt zwei Registrierungswerte (`TelemetryProxyServer` als "REG_SZ" und `DisableEnterpriseAuthProxy` als "REG_DWORD") unter dem Registrierungsschlüssel `HKLM\Software\Policies\Microsoft\Windows\DataCollection` fest.

Der Registrierungswert `TelemetryProxyServer` hat das folgende Zeichenfolgenformat:

```text
<server name or ip>:<port>
```

Beispiel: 10.0.0.6:8080.

Der Registrierungswert `DisableEnterpriseAuthProxy` sollte auf 1 festgelegt werden.

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Konfigurieren des Proxyservers manuell mithilfe des Befehls netsh

Verwenden Sie den netsh-Befehl, um einen systemweiten statischen Proxy zu konfigurieren.

> [!NOTE]
> - Dies wirkt sich auf alle Anwendungen aus, einschließlich Windows-Diensten, die WinHTTP mit Standardproxy verwenden.</br>
> - Laptops, die die Topologie ändern (z. B. von Büro zu Haus) können mit netsh nicht mehr verwendet werden. Verwenden Sie die registrierungsbasierte Konfiguration für statische Proxys.

1. Öffnen Sie eine Befehlszeile mit erhöhten Rechten:

    1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

    1. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

2. Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Beispiel: netsh winhttp set proxy 10.0.0.6:8080


###  <a name="proxy-configuration-for-down-level-devices"></a>Proxykonfiguration für Geräte auf ebener ebener Ebene

Down-Level gehören Windows 7 SP1- und Windows 8.1-Arbeitsstationen sowie Windows Server 2008 R2,Windows Server 2012, Windows Server 2012 R2 und Versionen von Windows Server 2016 vor Windows Server CB 1803. Für diese Betriebssysteme wird der Proxy als Teil des Microsoft Management Agent konfiguriert, um die Kommunikation vom Endpunkt an Azure zu verarbeiten. Informationen zur Konfiguration eines Proxys auf diesen Geräten finden Sie im Microsoft Management Agent Fast Deployment Guide.

### <a name="proxy-service-urls"></a>Proxydienst-URLs
URLs, die v20 enthalten, werden nur benötigt, wenn Sie Über Windows 10, Version 1803 oder höher, verfügen. Ist beispielsweise nur erforderlich, wenn sich das ```us-v20.events.data.microsoft.com``` Gerät unter Windows 10, Version 1803 oder höher befindet.
 

Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, da der Microsoft Defender for Endpoint-Sensor eine Verbindung aus dem Systemkontext verbindet, stellen Sie sicher, dass anonymer Datenverkehr in den aufgeführten URLs zulässig ist.

In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann. Stellen Sie sicher, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die  den Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen.

|**Tabellenkalkulation der Domänenliste**|**Beschreibung**|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme. <br><br>[Laden Sie die Tabelle hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a>Microsoft Defender for Endpoint Service-Back-End-IP-Bereiche

Wenn Ihre Netzwerkgeräte KEINE DNS-basierten Regeln unterstützen, verwenden Sie stattdessen IP-Bereiche.

Defender for Endpoint ist in der Azure-Cloud aufgebaut und wird in den folgenden Regionen bereitgestellt:

- AzureCloud.eastus
- AzureCloud.eastus2
- AzureCloud.westcentralus
- AzureCloud.northeurope
- AzureCloud.westeurope
- AzureCloud.uksouth
- AzureCloud.ukwest

Die Azure-IP-Bereiche finden Sie unter [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).

> [!NOTE]
> Als cloudbasierte Lösung können sich die IP-Adressbereiche ändern. Es wird empfohlen, zu DNS-basierten Regeln zu wechseln.

> [!NOTE]
> Wenn Sie ein Us Government-Kunde sind, lesen Sie den entsprechenden Abschnitt auf der [Seite Defender for Endpoint für US Government.](gov.md#service-backend-ip-ranges)

## <a name="next-step"></a>Nächster Schritt

![**Phase 3: Onboard**](images/onboard.png) <br>[Phase 3: Onboarding:](onboarding.md)Onboarding devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them. 
