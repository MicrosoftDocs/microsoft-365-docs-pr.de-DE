---
title: Microsoft Defender für Endpunkt Flow Connector
ms.reviewer: ''
description: Verwenden Sie Microsoft Defender für Endpunkt Flow Connector, um die Sicherheit zu automatisieren und einen Fluss zu erstellen, der jedes Mal ausgelöst wird, wenn eine neue Warnung auf Ihrem Mandanten auftritt.
keywords: Flow, unterstützte APIs, API, Microsoft-Fluss, Abfrage, Automatisierung
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd0cc3c2da134750f905b1f80746d6ec65cc70b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769703"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (früher Microsoft Flow) und Azure-Funktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Die Automatisierung von Sicherheitsverfahren ist eine Standardanforderung für jedes moderne Security Operations Center. Der Mangel an professionellen Cyber defendern zwingt SOC, auf die effizienteste Weise zu arbeiten, und Automatisierung ist ein Muss. Microsoft Power Automate unterstützt verschiedene Connectors, die genau dafür erstellt wurden. Sie können innerhalb weniger Minuten eine End-to-End-Prozedurautomatisierung erstellen.

Die Microsoft Defender-API verfügt über einen offiziellen Flow Connector mit vielen Funktionen.

![Abbildung der Anmeldeinformationen bearbeiten1](images/api-flow-0.png)

> [!NOTE]
> Weitere Informationen zu den Voraussetzungen für die Lizenzierung von Premium-Connectors finden Sie unter ["Lizenzierung für Premium-Connectors".](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)


## <a name="usage-example"></a>Verwendungsbeispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie ein Flow erstellen, das jedes Mal ausgelöst wird, wenn eine neue Warnung auf Ihrem Mandanten auftritt.

1. Melden Sie sich bei [Microsoft Power Automate](https://flow.microsoft.com)an.

2. Wechseln Sie zu **"My flows**  >  **New**  >  **Automated-from blank".**

    ![Abbildung der Anmeldeinformationen bearbeiten2](images/api-flow-1.png)

3. Wählen Sie einen Namen für Ihre Flow aus, suchen Sie nach "Microsoft Defender ATP Triggers" als Auslöser, und wählen Sie dann den neuen Trigger "Alerts" aus.

    ![Abbildung der Anmeldeinformationen bearbeiten3](images/api-flow-2.png)

Jetzt haben Sie eine Flow, die jedes Mal ausgelöst wird, wenn eine neue Warnung auftritt.

![Abbildung der Anmeldeinformationen bearbeiten4](images/api-flow-3.png)

Sie müssen nur noch die nächsten Schritte auswählen.
Sie können das Gerät beispielsweise isolieren, wenn der Schweregrad der Warnung hoch ist, und eine E-Mail darüber senden.
Der Warnungsauslöser stellt nur die Warnungs-ID und die Computer-ID bereit. Sie können den Connector verwenden, um diese Entitäten zu erweitern.

### <a name="get-the-alert-entity-using-the-connector"></a>Abrufen der Warnungsentität mithilfe des Connectors

1. Wählen Sie **Microsoft Defender ATP** für den neuen Schritt aus.

2. Wählen Sie **Warnungen aus – Rufen Sie die api für einzelne Warnungen** ab.

3. Legen Sie die **Warnungs-ID** aus dem letzten Schritt als **Eingabe** fest.

    ![Abbildung der Anmeldeinformationen bearbeiten5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Isolieren des Geräts, wenn der Schweregrad der Warnung hoch ist

1. Fügen Sie **"Bedingung"** als neuen Schritt hinzu.

2. Überprüfen Sie, ob der Schweregrad der Warnung **"Hoch" ist.**

   Wenn ja, fügen Sie die **Microsoft Defender ATP – Computeraktion isolieren** mit der Computer-ID und einem Kommentar hinzu.

    ![Abbildung der Anmeldeinformationen bearbeiten6](images/api-flow-5.png)

3. Fügen Sie einen neuen Schritt für die E-Mail-Nachricht über die Warnung und die Isolation hinzu. Es gibt mehrere E-Mail-Connectors, die sehr einfach zu verwenden sind, z. B. Outlook oder Gmail.

4. Speichern Sie Ihren Flow.

Sie können auch einen **geplanten** Fluss erstellen, der Abfragen der erweiterten Suche ausführt und vieles mehr!

## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)
