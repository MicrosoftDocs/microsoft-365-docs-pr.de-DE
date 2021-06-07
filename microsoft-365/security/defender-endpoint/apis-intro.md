---
title: Zugreifen auf die Microsoft Defender für Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie, wie Sie APIs verwenden können, um Workflows zu automatisieren und Innovationen basierend auf den Microsoft Defender für Endpunkt-Funktionen zu automatisieren.
keywords: APIs, API, wdatp, offene API, Microsoft Defender für Endpunkt-API, Microsoft Defender atp, öffentliche API, unterstützte APIs, Warnungen, Gerät, Benutzer, Domäne, IP, Datei, erweiterte Suche, Abfrage
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
ms.topic: conceptual
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 43c797dc8ee9f431ceda6ddecb0a1eada0e362f5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769653"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Zugreifen auf die Microsoft Defender für Endpoint-APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Gilt für:** 
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender für Endpunkt macht einen Großteil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Diese APIs ermöglichen es Ihnen, Workflows zu automatisieren und Innovationen basierend auf den Defender für Endpunkt-Funktionen zu entwickeln. Der API-Zugriff erfordert die OAuth2.0-Authentifizierung. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Sehen Sie sich dieses Video an, um einen schnellen Überblick über die APIs von Defender für Endpunkt zu erhalten. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen einer [AAD-Anwendung](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf die Defender für Endpunkt-API


Sie können auf die Defender für Endpunkt-API mit **Anwendungskontext** oder **Benutzerkontext** zugreifen.

- **Anwendungskontext: (Empfohlen)** <br>
    Wird von Apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden. Beispielsweise Apps, die als Hintergrunddienste oder Daemons ausgeführt werden.

    Schritte, die für den Zugriff auf die Defender für Endpunkt-API mit Anwendungskontext ausgeführt werden müssen:

  1. Erstellen Sie eine AAD-Webanwendung.
  2. Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren". 
  3. Erstellen Sie einen Schlüssel für diese Anwendung.
  4. Token mithilfe der Anwendung mit ihrem Schlüssel abrufen.
  5. Verwenden des Tokens für den Zugriff auf die Microsoft Defender für Endpunkt-API

     Weitere Informationen finden Sie unter ["Zugriff mit Anwendungskontext erhalten".](exposed-apis-create-app-webapp.md)


- **Benutzerkontext:** <br>
    Wird verwendet, um Aktionen in der API im Auftrag eines Benutzers auszuführen.

    Schritte für den Zugriff auf die Defender für Endpunkt-API mit Anwendungskontext:

  1. Erstellen Sie AAD Native-Application.
  2. Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren" usw. 
  3. Token mithilfe der Anwendung mit Benutzeranmeldeinformationen abrufen.
  4. Verwenden des Tokens für den Zugriff auf die Microsoft Defender für Endpunkt-API

     Weitere Informationen finden Sie unter ["Zugriff mit Benutzerkontext erhalten".](exposed-apis-create-app-nativeapp.md)


## <a name="related-topics"></a>Verwandte Themen
- [Microsoft Defender für Endpunkt-APIs](exposed-apis-list.md)
- [Zugreifen auf Microsoft Defender für Endpunkt mit Anwendungskontext](exposed-apis-create-app-webapp.md)
- [Zugreifen auf Microsoft Defender für Endpunkt mit Benutzerkontext](exposed-apis-create-app-nativeapp.md)
