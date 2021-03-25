---
title: Behandeln von Problemen mit der Integration von SIEM-Tools in Microsoft Defender ATP
description: Behandeln von Problemen, die bei der Verwendung von SIEM-Tools mit Microsoft Defender ATP auftreten können.
keywords: Problembehandlung, Siem, geheimer Client, Geheimer Schlüssel
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 7a6bb0c455ed0406c941e9269b8b04b5cfe738be
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064839"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Problembehandlung bei der Integration von SIEM-Tools

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Möglicherweise müssen Sie Beim Ziehen von Erkennungen in Ihren SIEM-Tools Probleme beheben.

Auf dieser Seite finden Sie detaillierte Schritte zur Problembehandlung.


## <a name="learn-how-to-get-a-new-client-secret"></a>Erfahren Sie, wie Sie einen neuen Geheimen Clientgeheimnis erhalten
Wenn Ihr Geheimer Clientgeheimnis abläuft oder Sie die beim Aktivieren der SIEM-Toolanwendung bereitgestellte Kopie falsch platziert haben, müssen Sie einen neuen Schlüssel erhalten.

1. Melden Sie sich beim [Azure-Verwaltungsportal an.](https://portal.azure.com)

2. Wählen Sie **Azure Active Directory** aus.

3. Wählen Sie Ihren Mandanten aus.

4. Klicken Sie **auf App-Registrierungen**. Wählen Sie dann in der Liste Anwendungen die Anwendung aus.

5. Wählen **Sie Den** Abschnitt Schlüssel aus, geben Sie eine Schlüsselbeschreibung an, und geben Sie die Gültigkeitsdauer des Schlüssels an.

6. Klicken Sie auf **Speichern**. Der Schlüsselwert wird angezeigt.

7. Kopieren Sie den Wert, und speichern Sie ihn an einem sicheren Ort.


## <a name="error-when-getting-a-refresh-access-token"></a>Fehler beim Abrufen eines Aktualisierungszugriffstokens
Wenn beim Versuch, ein Aktualisierungstoken zu erhalten, beim Verwenden der Threat Intelligence-API oder der SIEM-Tools ein Fehler auftritt, müssen Sie die Antwort-URL für die relevante Anwendung in Azure Active Directory hinzufügen.

1. Melden Sie sich beim [Azure-Verwaltungsportal an.](https://ms.portal.azure.com)

2. Wählen Sie **Azure Active Directory** aus.

3. Wählen Sie Ihren Mandanten aus.

4. Klicken Sie **auf App-Registrierungen**. Wählen Sie dann in der Liste Anwendungen die Anwendung aus.

5. Fügen Sie die folgende URL hinzu:
   - Für die Europäische Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - Für Großbritannien: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - Für die Vereinigten Staaten:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .
 
6. Klicken Sie auf **Speichern**.

## <a name="error-while-enabling-the-siem-connector-application"></a>Fehler beim Aktivieren der SIEM-Connectoranwendung
Wenn beim Versuch, die SIEM-Connectoranwendung zu aktivieren, ein Fehler auftritt, überprüfen Sie die Popupblockereinstellungen Ihres Browsers. Möglicherweise wird das neue Fenster blockiert, das geöffnet wird, wenn Sie die Funktion aktivieren.




>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a>Verwandte Themen
- [Aktivieren der SIEM-Integration in Microsoft Defender for Endpoint](enable-siem-integration.md)
- [Konfigurieren von ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen](configure-arcsight.md)
- [Ziehen von Erkennungen an Ihre SIEM-Tools](configure-siem.md)
- [Microsoft Defender for Endpoint Detection-Felder](api-portal-mapping.md)
- [Abrufen von Microsoft Defender for Endpoint-Erkennungen mithilfe der REST-API](pull-alerts-using-rest-api.md)
