---
title: API-Explorer in Microsoft Defender ATP
ms.reviewer: ''
description: Erstellen und Ausführen von API-Abfragen, Testen und Senden von Anforderungen für alle verfügbaren API mithilfe des API-Explorers
keywords: api, explorer, send, request, get, post,
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0cfe5227d5d1cdb1f1f4eaea2c859937d7e75264
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065063"
---
# <a name="api-explorer"></a>API-Explorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)


Der Microsoft Defender for Endpoint API Explorer ist ein Tool, mit dem Sie verschiedene Defender for Endpoint-APIs interaktiv erkunden können. 

Der API-Explorer erleichtert das Erstellen und Ausführen von API-Abfragen, Tests und Senden von Anforderungen für alle verfügbaren Defender for Endpoint-API-Endpunkte. Verwenden Sie den API-Explorer, um Aktionen zu ergreifen oder Daten zu finden, die möglicherweise noch nicht über die Benutzeroberfläche verfügbar sind.

Das Tool ist während der App-Entwicklung hilfreich. Es ermöglicht Ihnen, API-Abfragen durchzuführen, die Ihre Benutzerzugriffseinstellungen respektieren, wodurch die Notwendigkeit reduziert wird, Zugriffstoken zu generieren.

Sie können das Tool auch verwenden, um den Katalog von Beispielabfragen zu erkunden, Ergebniscodebeispiele zu kopieren und Debuginformationen zu generieren.

Mit dem API-Explorer können Sie:

- Ausführen von Anforderungen für jede Methode und Sehen von Antworten in Echtzeit
- Durchsuchen Sie schnell die API-Beispiele, und erfahren Sie, welche Parameter sie unterstützen
- Einfaches Erstellen von #A0 Keine Authentifizierung über die Anmeldung des Verwaltungsportals hinaus

## <a name="access-api-explorer"></a>Access-API-Explorer

Wählen Sie im linken Navigationsmenü **Partner & APIs**  >  **API Explorer aus.**

## <a name="supported-apis"></a>Unterstützte APIs

DER API-Explorer unterstützt alle APIs, die von Defender for Endpoint angeboten werden.
  
Die Liste der unterstützten APIs ist in der [APIs-Dokumentation verfügbar.](apis-intro.md) 

## <a name="get-started-with-the-api-explorer"></a>Erste Schritte mit dem API-Explorer

1. Im linken Bereich finden Sie eine Liste der Beispielanforderungen, die Sie verwenden können. 
2. Folgen Sie den Links, und klicken Sie **auf Abfrage ausführen.** 

Für einige Beispiele ist möglicherweise die Angabe eines Parameters in der URL erforderlich, z. B. {machine- ID}.

## <a name="faq"></a>Häufig gestellte Fragen

**Muss ich über ein API-Token verfügen, um den API-Explorer verwenden zu können?** <br>
Anmeldeinformationen für den Zugriff auf eine API sind nicht erforderlich. Der API-Explorer verwendet das Defender for Endpoint-Verwaltungsportaltoken, wenn eine Anforderung gestellt wird.

Die Anmeldeinformationen für die Benutzerauthentifizierung werden verwendet, um zu überprüfen, ob der API-Explorer autorisiert ist, in Ihrem Auftrag auf Daten zu zugreifen.

Bestimmte API-Anforderungen sind basierend auf Ihren RBAC-Berechtigungen eingeschränkt. Beispielsweise ist eine Anforderung zum "Indikator übermitteln" auf die Rolle des Sicherheitsadministrators beschränkt. 
