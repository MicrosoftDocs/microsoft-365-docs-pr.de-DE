---
title: API-Explorer in Microsoft Defender für Endpunkt
ms.reviewer: ''
description: Verwenden des API-Explorers zum Erstellen und Ausführen von API-Abfragen, zum Testen und Senden von Anforderungen für alle verfügbaren APIs
keywords: API, Explorer, senden, anfordern, abrufen, posten,
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
ms.custom: api
ms.openlocfilehash: 6a5684d71d34b3efdfe915ae674b4fcb90342154
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769797"
---
# <a name="api-explorer"></a>API-Explorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)


Der Microsoft Defender für Endpunkt-API-Explorer ist ein Tool, mit dem Sie verschiedene Defender für Endpunkt-APIs interaktiv erkunden können. 

Der API-Explorer erleichtert das Erstellen und Ausführen von API-Abfragen, das Testen und Senden von Anforderungen für alle verfügbaren Defender für Endpunkt-API-Endpunkte. Verwenden Sie den API-Explorer, um Aktionen auszuführen oder Daten zu suchen, die möglicherweise noch nicht über die Benutzeroberfläche verfügbar sind.

Das Tool ist während der App-Entwicklung nützlich. Sie können API-Abfragen ausführen, die Ihre Benutzerzugriffseinstellungen berücksichtigen, wodurch die Notwendigkeit reduziert wird, Zugriffstoken zu generieren.

Sie können das Tool auch verwenden, um den Katalog der Beispielabfragen zu erkunden, Ergebniscodebeispiele zu kopieren und Debuginformationen zu generieren.

Mit dem API-Explorer haben Sie folgende Möglichkeiten:

- Ausführen von Anforderungen für eine beliebige Methode und Anzeigen von Antworten in Echtzeit
- Durchsuchen Sie schnell die API-Beispiele, und erfahren Sie, welche Parameter sie unterstützen.
- Einfache API-Aufrufe; Keine Authentifizierung über die Anmeldung im Verwaltungsportal hinaus erforderlich

## <a name="access-api-explorer"></a>Access-API-Explorer

Wählen Sie im linken Navigationsmenü **Partner & APIs-API-Explorer**  >  aus.

## <a name="supported-apis"></a>Unterstützte APIs

Der API-Explorer unterstützt alle APIs, die von Defender für Endpunkt angeboten werden.
  
Die Liste der unterstützten APIs finden Sie in der [APIs-Dokumentation.](apis-intro.md) 

## <a name="get-started-with-the-api-explorer"></a>Erste Schritte mit dem API-Explorer

1. Im linken Bereich gibt es eine Liste der Beispielanforderungen, die Sie verwenden können. 
2. Folgen Sie den Links, und klicken Sie auf **"Abfrage ausführen".** 

Einige Beispiele erfordern möglicherweise die Angabe eines Parameters in der URL, z. B. {machine- ID}.

## <a name="faq"></a>Häufig gestellte Fragen

**Muss ich über ein API-Token verfügen, um den API-Explorer zu verwenden?** <br>
Anmeldeinformationen für den Zugriff auf eine API sind nicht erforderlich. Der API-Explorer verwendet das Token des Defender für Endpunkt-Verwaltungsportals, wenn er eine Anforderung sendet.

Die Anmeldeinformationen für die angemeldete Benutzerauthentifizierung werden verwendet, um zu überprüfen, ob der API-Explorer für den Zugriff auf Daten in Ihrem Auftrag autorisiert ist.

Bestimmte API-Anforderungen sind basierend auf Ihren RBAC-Berechtigungen eingeschränkt. Beispielsweise ist eine Anforderung an "Indikator übermitteln" auf die Rolle des Sicherheitsadministrators beschränkt. 
