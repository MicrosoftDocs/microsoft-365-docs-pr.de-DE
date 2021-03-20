---
title: Zugreifen auf die Microsoft 365 Defender-APIs
description: Informationen zum Zugriff auf die Microsoft 365 Defender-APIs
keywords: access, apis, application context, user context, aad application, access token
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 17fa47fd9998f4097ff323e670b9e442d7126a94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903976"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Zugreifen auf die Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Mit diesen APIs können Sie Workflows automatisieren und die Funktionen von Microsoft 365 Defender vollständig nutzen.

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:

- Erstellen einer Azure Active Directory-Anwendung
- Zugreifen auf ein Zugriffstoken mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

> [!NOTE]
> Für den API-Zugriff ist die OAuth2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Nachdem Sie diese Schritte durchgeführt haben, können Sie über einen bestimmten Kontext auf die Microsoft 365 Defender-API zugreifen.

## <a name="application-context-recommended"></a>Anwendungskontext (empfohlen)

Verwenden Sie diesen Kontext für Apps, die ohne angemeldeten Benutzer ausgeführt werden, z. B. Hintergrunddienste oder Daemons.

1. Erstellen Sie eine Azure Active Directory-Webanwendung.
2. Weisen Sie der Anwendung die gewünschten Berechtigungen zu.
3. Erstellen Sie einen Schlüssel für die Anwendung.
4. Mit der Anwendung und ihrem Schlüssel können Sie ein Sicherheitstoken erhalten.
5. Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.

Weitere Informationen finden Sie unter **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.

## <a name="user-context"></a>Benutzerkontext

Verwenden Sie diesen Kontext, um Aktionen im Auftrag eines einzelnen Benutzers durchzuführen.

1. Erstellen Sie eine systemeigene Azure Active Directory-Anwendung.
2. Weisen Sie der Anwendung die gewünschte Berechtigung zu.
3. Mit den Benutzeranmeldeinformationen für die Anwendung können Sie ein Sicherheitstoken erhalten.
4. Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.

Weitere Informationen finden Sie unter Erstellen einer App für den Zugriff auf **[Microsoft 365 Defender-APIs im Auftrag eines Benutzers.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Partnerkontext

Verwenden Sie diesen Kontext, wenn Sie eine App für viele Benutzer in [mehreren Mandanten bereitstellen müssen.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Erstellen Sie eine Azure Active Directory-Mehr-Mandanten-Anwendung.
2. Weisen Sie der Anwendung die gewünschte Berechtigung zu.
3. Erhalten [Sie die Administratoreinwilligung](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) für die App von jedem Mandanten.
4. Erhalten Sie ein Sicherheitstoken mithilfe von Benutzeranmeldeinformationen basierend auf der Mandanten-ID eines Kunden.
5. Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.

Weitere Informationen finden Sie unter **[Erstellen einer App mit Partnerzugriff auf Microsoft 365 Defender-APIs](api-partner-access.md)**.

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Microsoft 365 Defender-APIs](api-overview.md)
- [OAuth 2.0-Autorisierung für die Benutzer-Anmeldung und den API-Zugriff](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Verwalten von Geheimschlüsseln in Ihren Server-Apps mit Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Erstellen einer "Hello world"-Anwendung, die auf die Microsoft 365-APIs zu zugegriffen hat](api-hello-world.md)