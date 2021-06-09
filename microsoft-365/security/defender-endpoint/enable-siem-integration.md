---
title: Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt
description: Aktivieren Sie die SIEM-Integration, um Erkennungen in Ihrer SIEM-Lösung (Security Information and Event Management) zu empfangen.
keywords: Aktivieren von Siem-Connector, Siem, Connector, Sicherheitsinformationen und -ereignissen
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
ms.openlocfilehash: 87078bb7bfc6b38788fea2a6a4c3c9108be1d5b4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842962"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a>Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)


>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

Aktivieren Sie die SIEM-Integration (Security Information and Event Management), damit Sie Erkennungen aus Microsoft Defender Security Center abrufen können. Abrufen von Erkennungen mithilfe Ihrer SIEM-Lösung oder durch direktes Herstellen einer Verbindung mit der REST-API für Erkennungen.

>[!NOTE]
>- [Microsoft Defender für Endpunkt-Warnung](alerts.md) besteht aus einer oder mehreren Erkennungen.
>- [Die Microsoft Defender für Endpunkterkennung](api-portal-mapping.md) besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.
>- Die Microsoft Defender für Endpunkt-Warnungs-API ist die neueste API für die Benachrichtigungsnutzung und enthält eine detaillierte Liste der zugehörigen Nachweise für jede Warnung. Weitere Informationen finden Sie unter ["Warnungsmethoden und -eigenschaften"](alerts.md) und ["Warnungen auflisten".](get-alerts.md)

## <a name="prerequisites"></a>Voraussetzungen

- Der Benutzer, der die Einstellung aktiviert, muss über Berechtigungen zum Erstellen einer App in Azure Active Directory (AAD) verfügen. Dies ist eine Person mit den folgenden Rollen: 

  - Sicherheitsadministrator und globaler Administrator
  - Cloudanwendungsadministrator
  - Anwendungsadministrator
  - Besitzer des Dienstprinzipals

- Während der anfänglichen Aktivierung wird ein Popupbildschirm für die Eingabe von Anmeldeinformationen angezeigt. Stellen Sie sicher, dass Sie Popups für diese Website zulassen.

## <a name="enabling-siem-integration"></a>Aktivieren der SIEM-Integration 
1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **SIEM** aus.

    ![Abbildung der SIEM-Integration aus Einstellungen Menü1](images/enable_siem.png)

    >[!TIP]
    >Wenn beim Versuch, die SIEM-Connectoranwendung zu aktivieren, ein Fehler auftritt, überprüfen Sie die Popupblockereinstellungen Ihres Browsers. Möglicherweise blockiert es, dass das neue Fenster geöffnet wird, wenn Sie die Funktion aktivieren. 

2. Wählen Sie **"SIEM-Integration aktivieren"** aus. Dadurch wird der **Abschnitt "SIEM-Connector-Zugriffsdetails"** mit vordefinierten Werten aktiviert, und eine Anwendung wird unter Ihrem Azure Active Directory (Azure AD)-Mandanten erstellt.

    > [!WARNING]
    >Der geheime Clientschlüssel wird nur einmal angezeigt. Stellen Sie sicher, dass Sie eine Kopie davon an einem sicheren Ort aufbewahren.<br>
     

    ![Abbildung der SIEM-Integration aus Einstellungen Menü2](images/siem_details.png)

3. Wählen Sie den SIEM-Typ aus, den Sie in Ihrer Organisation verwenden.

   > [!NOTE]
   > Wenn Sie HP ArcSight auswählen, müssen Sie diese beiden Konfigurationsdateien speichern:<br>
   > - WDATP-connector.jsonparser.properties
   > - WDATP-connector.properties <br>

   Wenn Sie über programmgesteuerten Zugriff eine direkte Verbindung mit der REST-API für Erkennungen herstellen möchten, wählen Sie **generische API** aus.

4. Kopieren Sie die einzelnen Werte, oder wählen **Sie "Details speichern" aus, um** eine Datei herunterzuladen, die alle Werte enthält.

5. Wählen Sie **"Token generieren"** aus, um ein Zugriffs- und Aktualisierungstoken abzurufen.
  
   > [!NOTE]
   > Sie müssen alle 90 Tage ein neues Aktualisierungstoken generieren. 

6. Befolgen Sie die Anweisungen zum [Erstellen einer Azure AD-App-Registrierung für Microsoft Defender für Endpunkt,](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) und weisen Sie ihr die richtigen Berechtigungen zum Lesen von Warnungen zu.

Sie können jetzt mit der Konfiguration Ihrer SIEM-Lösung fortfahren oder eine Verbindung mit der REST-API für Erkennungen über programmgesteuerten Zugriff herstellen. Sie müssen die Token verwenden, wenn Sie Ihre SIEM-Lösung konfigurieren, damit sie Erkennungen von Microsoft Defender Security Center empfangen kann.

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a>Integrieren von Microsoft Defender für Endpunkt in IBM QRadar 
Sie können IBM QRadar konfigurieren, um Erkennungen von Microsoft Defender für Endpunkt zu sammeln. Weitere Informationen finden Sie im [IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

## <a name="see-also"></a>Siehe auch
- [Konfigurieren von HP ArcSight zum Abrufen von Microsoft Defender für Endpunkterkennungen](configure-arcsight.md)
- [Microsoft Defender für Endpunkterkennungsfelder](api-portal-mapping.md)
- [Abrufen von Microsoft Defender für Endpunkterkennungen mithilfe der REST-API](pull-alerts-using-rest-api.md)
- [Behandeln von Problemen mit der Integration von SIEM-Tools](troubleshoot-siem.md)
