---
title: Konfigurieren von Micro Focus ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen
description: Konfigurieren von Micro Focus ArcSight zum Empfangen und Ziehen von Erkennungen Microsoft Defender Security Center
keywords: Konfigurieren von Micro Focus ArcSight, Sicherheitsinformations- und Ereignisverwaltungstools, arcsight
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166185"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>Konfigurieren von Micro Focus ArcSight zum Ziehen von Defender for Endpoint-Erkennungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

Sie müssen einige Dateien und Tools für die Verwendung von Micro Focus ArcSight installieren und konfigurieren, damit Defender for Endpoint-Erkennungen verwendet werden können.

>[!Note]
>- [Defender for Endpoint Alert](alerts.md) besteht aus einer oder mehreren Erkennungen
>- [Defender for Endpoint Detection besteht](api-portal-mapping.md) aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Für die Konfiguration des Micro Focus ArcSight Connector-Tools sind mehrere Konfigurationsdateien erforderlich, um Erkennungen aus Ihrer Azure Active Directory (AAD)-Anwendung zu ziehen und zu analysieren.

In diesem Abschnitt erhalten Sie die erforderlichen Informationen zum ordnungsgemäßen Festlegen und Verwenden der erforderlichen Konfigurationsdateien.

- Stellen Sie sicher, dass Sie das SIEM-Integrationsfeature im Menü **Einstellungen** haben. Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Defender for Endpoint](enable-siem-integration.md).

- Die Datei, die Sie beim Aktivieren des SIEM-Integrationsfeatures gespeichert haben, ist bereit. Sie müssen die folgenden Werte erhalten:
  - OAuth 2.0 Tokenaktualisierungs-URL
  - OAuth 2.0-Client-ID
  - OAuth 2.0 Geheimer Clientgeheimnis

- Die folgenden Konfigurationsdateien sind bereit:
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    Sie hätten eine .zip gespeichert, die diese beiden Dateien enthält, wenn Sie Micro Focus ArcSight als siem-Typ ausgewählt haben, den Sie in Ihrer Organisation verwenden.

- Stellen Sie sicher, dass Sie die folgenden Token generieren und bereit sind:
  - Zugriffstoken
  - Aktualisierungstoken

  Sie können diese Token im Abschnitt **SIEM-Integrationseinrichtung** des Portals generieren.

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>Installieren und Konfigurieren von Micro Focus ArcSight FlexConnector

In den folgenden Schritten wird davon ausgegangen, dass Sie alle erforderlichen Schritte unter [Before you begin abgeschlossen haben.](#before-you-begin)

1. Installieren Sie das neueste 32-Bit-Windows FlexConnector-Installationsprogramm. Dies finden Sie im HPE Software Center. Das Tool wird in der Regel am folgenden Standardspeicherort installiert: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</br></br>Sie können auswählen, wo das Tool gespeichert werden soll, z. B. C: \\ *folder_location*\current\bin, wobei folder_location Installationsspeicherort darstellt. 

2. Führen Sie den Installationsassistenten durch die folgenden Aufgaben aus:
   - Einführung
   - Wählen Sie Ordner installieren aus
   - Wählen Sie Installationssatz aus.
   - Auswählen des Verknüpfungsordners
   - Zusammenfassung vor der Installation
   - Installieren...

   Sie können die Standardwerte für jede dieser Aufgaben behalten oder die Auswahl an Ihre Anforderungen anpassen.

3. Öffnen Sie den Datei-Explorer, und suchen Sie die beiden Konfigurationsdateien, die Sie beim Aktivieren des SIEM-Integrationsfeatures gespeichert haben. Legen Sie die beiden Dateien am Installationsspeicherort von FlexConnector ab, z. B.:

   - WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   - WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   > [!NOTE]
   > 
   > Sie müssen die Konfigurationsdateien an  diesem Speicherort speichern, folder_location dem Speicherort darstellt, an dem Sie das Tool installiert haben.

4. Nachdem die Installation des Hauptconnector abgeschlossen ist, wird das Fenster Connector-Setup geöffnet. Wählen Sie im Fenster Connectoreinrichtung die Option **Connector hinzufügen aus.**

5. Wählen Sie Typ: **ArcSight FlexConnector REST aus,** und klicken Sie auf **Weiter**.

6. Geben Sie die folgenden Informationen im Formular parameterdetails ein. Alle anderen Werte im Formular sind optional und können leer gelassen werden.

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th>Feld</th>
    <th>Wert</th>
    </tr>
    <tr>
    <td>Konfigurationsdatei</td>
    <td>Geben Sie den Namen der Clienteigenschaftsdatei ein. Der Name muss mit der Datei übereinstimmen, die im .zip heruntergeladen wurde.
Wenn die Konfigurationsdatei im Verzeichnis flexagent beispielsweise den Namen &quot; &quot;WDATP-Connector.js&quot; onparser.properties hat, müssen Sie &quot; &quot; WDATP-Connector &quot; als Namen der Clienteigenschaftsdatei eingeben.</td>
    </tr>
    <td>Ereignis-URL</td>
    <td>Wählen Sie je nach Standort Ihres Rechenzentrums entweder die EU- oder die US-URL aus: </br></br> <b>Für EU</b>: https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br>
   </br><b>For US:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br> <br> <b>For UK</b>: https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</td>
    <tr>
    <td>Authentifizierungstyp</td>
    <td>OAuth 2</td>
    </tr>
    <td>OAuth 2-Clienteigenschaftendatei</td>
    <td>Navigieren Sie zum Speicherort der <em>Datei wdatp-connector.properties.</em> Der Name muss mit der Datei übereinstimmen, die im .zip heruntergeladen wurde.</td>
    <tr>
    <td>Aktualisierungstoken</td>
    <td>Sie können ein Aktualisierungstoken auf zwei Arten abrufen: durch Generieren eines Aktualisierungstokens auf der <b>Seite mit den SIEM-Einstellungen</b> oder mithilfe des Restutil-Tools. <br><br> Weitere Informationen zum Generieren eines <b>Aktualisierungstokens</b> aus dem Setup der Einstellungen finden Sie unter Aktivieren der <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">SIEM-Integration in Defender for Endpoint</a>. </br> </br><b>Mit dem restutil-Tool können Sie Ihr Aktualisierungstoken erhalten:</b> </br> a. Öffnen Sie eine Eingabeaufforderung. Navigieren Sie zu C:\<em>folder_location</em>\current\bin, folder_location den Speicherort darstellt, an dem Sie das Tool installiert haben. <em></em> </br></br> b. Typ: <code>arcsight restutil token -config</code> aus dem Bin-Verzeichnis. Beispiel: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> ein Webbrowserfenster wird geöffnet. </br> </br>c. Geben Sie Ihre Anmeldeinformationen ein, und klicken Sie dann auf das Kennwortfeld, damit die Seite umgeleitet wird. Geben Sie in der Anmeldeaufforderung Ihre Anmeldeinformationen ein. </br> </br>d. In der Eingabeaufforderung wird ein Aktualisierungstoken angezeigt. </br></br> e. Kopieren Sie sie, und fügen Sie sie in das <b>Feld Aktualisierungstoken</b> ein.
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. Ein Browserfenster wird vom Connector geöffnet. Melden Sie sich mit Ihren Anmeldeinformationen an. Nach der Anmeldung werden Sie aufgefordert, Ihrem OAuth2-Client die Berechtigung zu erteilen. Sie müssen Ihrem OAuth 2-Client die Berechtigung erteilen, damit die Connectorkonfiguration authentifiziert werden kann.

   Wenn es <code>redirect_uri</code> sich bei der um eine https-URL handelt, werden Sie zu einer URL auf dem lokalen Host umgeleitet. Es wird eine Seite angezeigt, die anfordert, dem Zertifikat zu vertrauen, das vom Connector bereitgestellt wird, der auf dem lokalen Host ausgeführt wird. Sie müssen diesem Zertifikat vertrauen, wenn redirect_uri https ist.
   
   Wenn Sie jedoch eine http-URL für die redirect_uri, müssen Sie keine Zustimmung zum Vertrauen des Zertifikats erteilen.

8. Fahren Sie mit der Connectoreinrichtung fort, indem Sie zum Fenster Micro Focus ArcSight Connector Setup zurückkehren.

9. Wählen Sie **den ArcSight Manager (verschlüsselt)** als Ziel aus, und klicken Sie auf **Weiter**.

10. Geben Sie die Ziel-IP/Hostname in **Manager Hostname** und Ihre Anmeldeinformationen im Parameterformular ein. Alle anderen Werte im Formular sollten mit den Standardwerten beibehalten werden. Klicken Sie auf **Weiter**.

11. Geben Sie im Connectordetailseformular einen Namen für den Connector ein. Alle anderen Werte im Formular sind optional und können leer gelassen werden. Klicken Sie auf **Weiter**.

12. Das Importzertifikatfenster des ESM-Managers wird angezeigt. Wählen **Sie Zertifikat vom Ziel in Connector importieren aus,** und klicken Sie auf **Weiter**. Das **Fenster Connector-Zusammenfassung** hinzufügen wird angezeigt, und das Zertifikat wird importiert.

13. Stellen Sie sicher, dass die Details im **Fenster** Connector-Zusammenfassung hinzufügen korrekt sind, und klicken Sie dann auf **Weiter**.

14. Wählen **Sie Als Dienst installieren aus,** und klicken Sie auf **Weiter**.

15. Geben Sie einen Namen in das **Feld Dienst interner Name** ein. Alle anderen Werte im Formular können mit den Standardwerten beibehalten oder leer gelassen werden. Klicken Sie auf **Weiter**.

16. Geben Sie die Dienstparameter ein, und klicken Sie auf **Weiter**. Ein Fenster mit der **Installationsdienstzusammenfassung** wird angezeigt. Klicken Sie auf **Weiter**.

17. Beenden Sie die Installation, indem Sie **Exit und** **Next auswählen.**

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>Installieren und Konfigurieren der Micro Focus ArcSight-Konsole

1. Führen Sie den Installationsassistenten durch die folgenden Aufgaben aus:
   - Einführung
   - Lizenzvertrag
   - Sonderbenachrichtigung
   - Auswählen des ArcSight-Installationsverzeichnisses
   - Auswählen des Verknüpfungsordners
   - Zusammenfassung vor der Installation

2. Klicken Sie auf **Installieren**. Nach Abschluss der Installation wird der Assistent für die Konfiguration der ArcSight-Konsole geöffnet.

3. Geben Sie localhost im **Managerhostnamen** und 8443 im **Managerport ein,** und klicken Sie dann auf **Weiter**.

4. Wählen **Sie Direkte Verbindung verwenden** aus, und klicken Sie dann auf **Weiter**.

5. Wählen **Sie Kennwortbasierte Authentifizierung** aus, und klicken Sie dann auf **Weiter**.

6. Wählen **Sie This is a single user installation aus. (Empfohlen)**, und klicken Sie dann auf **Weiter**.

7. Klicken Sie **auf Fertig,** um das Installationsprogramm zu beenden.

8. Melden Sie sich bei der Micro Focus ArcSight-Konsole an.

9. Navigieren Sie zu **Active channel set** New  >  **Condition**  >    >  **Device Device Product**.

10. Set **Device Product = Microsoft Defender ATP**. Wenn Sie überprüft haben, dass Ereignisse an das Tool fließen, beenden Sie den Prozess erneut, und wechseln Sie zu Windows Services, und starten Sie den ArcSight FlexConnector REST.

Sie können jetzt Abfragen in der Micro Focus ArcSight-Konsole ausführen.

Defender for Endpoint-Erkennungen werden als diskrete Ereignisse mit "Microsoft" als Anbieter und "Windows Defender ATP" als Gerätename angezeigt.


## <a name="troubleshooting-micro-focus-arcsight-connection"></a>Problembehandlung bei der Micro Focus ArcSight-Verbindung

**Problem:** Fehler beim Aktualisieren des Tokens. Sie finden das Protokoll in C: \\ *folder_location*\current\logs, wobei folder_location den Speicherort darstellt, an dem Sie das Tool installiert haben.  Öffnen _Sie agent.log,_ und suchen Sie nach `ERROR/FATAL/WARN` .

**Symptom:** Die folgende Fehlermeldung wird angezeigt:

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**Lösung:**

1. Beenden Sie den Vorgang, indem Sie im Connectorfenster auf STRG + C klicken. Klicken **Sie auf Y,** wenn Sie "Batchauftrag Y/N beenden?" gefragt werden.

2. Navigieren Sie zu dem Ordner, in dem Sie die Datei WDATP-connector.properties gespeichert haben, und bearbeiten Sie sie, um den folgenden Wert hinzuzufügen: `reauthenticate=true` .

3. Starten Sie den Connector neu, indem Sie den folgenden Befehl ausführen: `arcsight.bat connectors` .

   Ein Browserfenster wird angezeigt. Lassen Sie die Ausführung zu, es sollte ausgeblendet werden, und der Connector sollte nun ausgeführt werden.

> [!NOTE]
> Stellen Sie sicher, dass der Connector ausgeführt wird, indem Sie den Prozess erneut beenden. Starten Sie dann den Connector erneut, und es sollte kein Browserfenster angezeigt werden.

## <a name="related-topics"></a>Verwandte Themen
- [Aktivieren der SIEM-Integration in Defender for Endpoint](enable-siem-integration.md)
- [Ziehen von Erkennungen an Ihre SIEM-Tools](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [Pull Defender for Endpoint-Erkennungen mithilfe der REST-API](pull-alerts-using-rest-api.md)
- [Behandeln von Problemen mit der Integration von SIEM-Tools](troubleshoot-siem.md)
