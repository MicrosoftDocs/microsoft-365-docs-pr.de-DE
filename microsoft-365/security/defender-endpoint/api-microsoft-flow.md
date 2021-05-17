---
title: Microsoft Defender for Endpoint Flow Connector
ms.reviewer: ''
description: Verwenden Sie Microsoft Defender for Endpoint Flow Connector, um die Sicherheit zu automatisieren und einen Fluss zu erstellen, der bei jedem Auftreten einer neuen Warnung für Ihren Mandanten ausgelöst wird.
keywords: flow, supported apis, api, Microsoft flow, query, automation
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 33a7c7b1907ac761dfdde43a70bfb8f515235150
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929299"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (früher Microsoft Flow) und Azure Functions

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Das Automatisieren von Sicherheitsverfahren ist eine Standardanforderung für jedes moderne Security Operations Center. Der Mangel an professionellen Cyber defenders zwingt SOC, auf effizienteste Weise zu arbeiten, und Automatisierung ist ein Muss. Microsoft Power Automate unterstützt verschiedene Connectors, die genau dafür erstellt wurden. Sie können eine End-to-End-Prozedurautomatisierung innerhalb weniger Minuten erstellen.

Microsoft Defender API verfügt über einen offiziellen Flow Connector mit vielen Funktionen.

![Abbildung der Anmeldeinformationen bearbeiten1](images/api-flow-0.png)

> [!NOTE]
> Weitere Informationen zu den Voraussetzungen für die Lizenzierung von PremiumConnectors finden Sie unter [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).


## <a name="usage-example"></a>Verwendungsbeispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie eine Flow, die jedes Mal ausgelöst wird, wenn eine neue Warnung für Ihren Mandanten auftritt.

1. Melden Sie sich bei [Microsoft Power Automate an.](https://flow.microsoft.com)

2. Wechseln Sie **zu My flows**  >  **New**  >  **Automated-from leer**.

    ![Abbildung der Anmeldeinformationen für die Bearbeitung2](images/api-flow-1.png)

3. Wählen Sie einen Namen für Flow, suchen Sie nach "Microsoft Defender ATP Trigger" als Trigger, und wählen Sie dann den neuen Alerts-Trigger aus.

    ![Abbildung der Anmeldeinformationen bearbeiten3](images/api-flow-2.png)

Jetzt haben Sie eine Flow, die jedes Mal ausgelöst wird, wenn eine neue Warnung auftritt.

![Abbildung der Anmeldeinformationen bearbeiten4](images/api-flow-3.png)

Jetzt müssen Sie nur noch die nächsten Schritte auswählen.
Beispielsweise können Sie das Gerät isolieren, wenn der Schweregrad der Warnung hoch ist, und eine E-Mail darüber senden.
Der Warnungsauslöser stellt nur die Warnungs-ID und die Computer-ID zur Verfügung. Sie können den Connector verwenden, um diese Entitäten zu erweitern.

### <a name="get-the-alert-entity-using-the-connector"></a>Get the Alert entity using the connector

1. Wählen **Microsoft Defender ATP** für den neuen Schritt aus.

2. Wählen Sie **Warnungen – Abrufen einer einzelnen Warnungs-API aus.**

3. Legen Sie **die Warnungs-ID** aus dem letzten Schritt als **Eingabe .**

    ![Abbildung der Anmeldeinformationen bearbeiten5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Isolieren des Geräts, wenn der Schweregrad der Warnung hoch ist

1. Fügen **Sie Condition** als neuen Schritt hinzu.

2. Überprüfen Sie, ob der Schweregrad der Warnung **dem Wert High** entspricht.

   Wenn ja, fügen Sie die **Microsoft Defender ATP - Computeraktion** mit der Computer-ID und einem Kommentar isolieren hinzu.

    ![Abbildung der Anmeldeinformationen bearbeiten6](images/api-flow-5.png)

3. Fügen Sie einen neuen Schritt zum Senden von E-Mails zu Warnung und Isolation hinzu. Es gibt mehrere E-Mail-Connectors, die sehr einfach zu verwenden sind, z. B. Outlook oder Gmail.

4. Speichern Sie Ihren Flow.

Sie können auch einen **geplanten Fluss** erstellen, in dem Erweiterte Suchabfragen und vieles mehr ausgeführt werden.

## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)
