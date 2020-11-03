---
title: Zugreifen auf die Microsoft 365 Defender-APIs
description: Informationen zum Zugriff auf die Microsoft 365 Defender-APIs
keywords: Zugriff, APIs, Anwendungskontext, Benutzerkontext, AAD-Anwendung, Zugriffstoken
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845017"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Zugreifen auf die Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


 Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar. Mit diesen APIs können Sie Workflows Automatisieren und auf der Grundlage von Microsoft 365 Defender-Funktionen innovativ sein. Für den API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen einer Aad-Anwendung
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API


Sie können auf die Microsoft 365 Defender-API mit **Anwendungskontext** oder **Benutzerkontext** zugreifen.

- **Anwendungskontext: (empfohlen)** <br>
    Wird von apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden. beispielsweise apps, die als Hintergrunddienste oder Daemons ausgeführt werden.

    Schritte, die für den Zugriff auf die Microsoft 365 Defender-API mit Anwendungskontext ergriffen werden müssen:

  1. Erstellen Sie eine Aad-Webanwendung.
  2. Zuweisen der gewünschten Berechtigung zum applicationFor-Beispiel, **Incident. Read. all** , **AdvancedHunting. Read. all**. 
  3. Erstellen Sie einen Schlüssel für diese Anwendung.
  4. Get-Token mit der Anwendung mit dem Schlüssel.
  5. Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

     Weitere Informationen finden Sie unter [Get Access with Application Context](api-create-app-web.md).


- **Benutzerkontext:** <br>
    Dient zum Ausführen von Aktionen in der API im Namen eines Benutzers.

    Schritte, die für den Zugriff auf die Microsoft 365 Defender-API mit Anwendungskontext ergriffen werden müssen:
  1. Erstellen einer nativen Aad-Anwendung.
  2. Weisen Sie der Anwendung die gewünschte Berechtigung zu. Beispiel: **Incident. Read** , **AdvancedHunting. Read**.
  3. Abrufen eines Tokens mithilfe der Anwendung mit Benutzeranmeldeinformationen.
  4. Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

     Weitere Informationen finden Sie unter [Get Access with User Context](api-create-app-user-context.md).


## <a name="related-topics"></a>Verwandte Themen
- [Microsoft 365 Defender-APIs](api-supported.md)
- [Zugriff auf Microsoft 365 Defender mit Anwendungskontext](api-create-app-web.md)
- [Zugriff auf Microsoft 365 Defender mit Benutzerkontext](api-create-app-user-context.md)
