---
title: Zugreifen auf die Microsoft Defender für Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie, wie Sie APIs verwenden können, um Workflows zu automatisieren und Innovationen basierend auf Microsoft Defender for Endpoint-Funktionen zu entwickeln.
keywords: apis, api, wdatp, open api, microsoft defender for endpoint api, microsoft defender atp, public api, supported apis, alerts, device, user, domain, ip, file, advanced hunting, query
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
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571829"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Zugreifen auf die Microsoft Defender für Endpoint-APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Gilt für:** 
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint macht einen großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Mit diesen APIs können Sie Workflows automatisieren und innovationen basierend auf defender for Endpoint-Funktionen entwickeln. Für den API-Zugriff ist die OAuth2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Sehen Sie sich dieses Video an, um einen schnellen Überblick über die APIs von Defender for Endpoint zu erhalten. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen einer [AAD-Anwendung](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Zugreifen auf ein Zugriffstoken mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf die Defender for Endpoint-API


Sie können auf defender for Endpoint-API **mit Anwendungskontext oder** **Benutzerkontext zugreifen.**

- **Anwendungskontext: (Empfohlen)** <br>
    Wird von Apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden. Beispielsweise Apps, die als Hintergrunddienste oder Daemons ausgeführt werden.

    Schritte, die für den Zugriff auf die Defender for Endpoint-API mit Anwendungskontext erforderlich sind:

  1. Erstellen Sie eine AAD-Webanwendung.
  2. Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren". 
  3. Erstellen Sie einen Schlüssel für diese Anwendung.
  4. Token mit der Anwendung mit ihrem Schlüssel abzurufen.
  5. Verwenden des Tokens für den Zugriff auf die Microsoft Defender for Endpoint-API

     Weitere Informationen finden Sie unter [Zugriff mit Anwendungskontext erhalten.](exposed-apis-create-app-webapp.md)


- **Benutzerkontext:** <br>
    Wird verwendet, um Aktionen in der API im Namen eines Benutzers durchzuführen.

    Schritte zum Zugreifen auf die Defender for Endpoint-API mit Anwendungskontext:

  1. Erstellen Sie AAD Native-Application.
  2. Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren" usw. 
  3. Token mithilfe der Anwendung mit Benutzeranmeldeinformationen abzurufen.
  4. Verwenden des Tokens für den Zugriff auf die Microsoft Defender for Endpoint-API

     Weitere Informationen finden Sie unter [Get access with user context](exposed-apis-create-app-nativeapp.md).


## <a name="related-topics"></a>Verwandte Themen
- [Microsoft Defender für Endpunkt-APIs](exposed-apis-list.md)
- [Zugreifen auf Microsoft Defender for Endpoint mit Anwendungskontext](exposed-apis-create-app-webapp.md)
- [Zugreifen auf Microsoft Defender for Endpoint mit Benutzerkontext](exposed-apis-create-app-nativeapp.md)
