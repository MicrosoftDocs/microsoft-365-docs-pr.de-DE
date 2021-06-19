---
title: Zugreifen auf die Microsoft 365 Defender-APIs
description: Erfahren Sie, wie Sie auf die Microsoft 365 Defender-APIs zugreifen
keywords: Access, APIs, Anwendungskontext, Benutzerkontext, aad-Anwendung, Zugriffstoken
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 03fd82cd5dc24653b6d67fa47cc225d355bfac45
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028799"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Zugreifen auf die Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Diese APIs helfen Ihnen, Workflows zu automatisieren und die Funktionen Microsoft 365 Defender voll zu nutzen.

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:

- Erstellen einer Azure Active Directory Anwendung
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

> [!NOTE]
> DER API-Zugriff erfordert die OAuth2.0-Authentifizierung. Weitere Informationen finden Sie unter [OAuth 2.0-Autorisierungscode Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Nachdem Sie diese Schritte ausgeführt haben, können Sie mithilfe eines bestimmten Kontexts auf die Microsoft 365 Defender-API zugreifen.

## <a name="application-context-recommended"></a>Anwendungskontext (empfohlen)

Verwenden Sie diesen Kontext für Apps, die ohne angemeldeten Benutzer ausgeführt werden, z. B. Hintergrunddienste oder Daemons.

1. Erstellen Sie eine Azure Active Directory Webanwendung.
2. Weisen Sie der Anwendung die gewünschten Berechtigungen zu.
3. Erstellen Sie einen Schlüssel für die Anwendung.
4. Rufen Sie ein Sicherheitstoken mithilfe der Anwendung und ihres Schlüssels ab.
5. Verwenden Sie das Token, um auf Microsoft 365 Defender-API zuzugreifen.

Weitere Informationen finden Sie unter **[Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer.](api-create-app-web.md)**

## <a name="user-context"></a>Benutzerkontext

Verwenden Sie diesen Kontext, um Aktionen im Namen eines einzelnen Benutzers auszuführen.

1. Erstellen Sie eine Azure Active Directory systemeigene Anwendung.
2. Weisen Sie der Anwendung die gewünschte Berechtigung zu.
3. Rufen Sie ein Sicherheitstoken mithilfe der Benutzeranmeldeinformationen für die Anwendung ab.
4. Verwenden Sie das Token, um auf Microsoft 365 Defender-API zuzugreifen.

Weitere Informationen finden Sie unter **[Erstellen einer App für den Zugriff auf Microsoft 365 Defender APIs im Namen eines Benutzers.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Partnerkontext

Verwenden Sie diesen Kontext, wenn Sie vielen Benutzern über [mehrere Mandanten](/azure/active-directory/develop/single-and-multi-tenant-apps)hinweg eine App bereitstellen müssen.

1. Erstellen Sie eine Azure Active Directory mehrinstanzenfähige Anwendung.
2. Weisen Sie der Anwendung die gewünschte Berechtigung zu.
3. Holen Sie sich die [Administratorzustimmung](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) für die App von jedem Mandanten.
4. Rufen Sie ein Sicherheitstoken mithilfe von Benutzeranmeldeinformationen basierend auf der Mandanten-ID eines Kunden ab.
5. Verwenden Sie das Token, um auf Microsoft 365 Defender-API zuzugreifen.

Weitere Informationen finden Sie unter **[Erstellen einer App mit Partnerzugriff auf Microsoft 365 Defender APIs.](api-partner-access.md)**

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender ÜBERSICHT ÜBER APIs](api-overview.md)
- [OAuth 2.0-Autorisierung für benutzeranmeldung und API-Zugriff](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Verwalten geheimer Schlüssel in Ihren Server-Apps mit Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Erstellen einer "Hello World"-Anwendung, die auf die Microsoft 365-APIs zugreift](api-hello-world.md)