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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719238"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Zugreifen auf die Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar. Diese APIs unterstützen Sie bei der Automatisierung von Workflows und der vollständigen Nutzung der Funktionen von Microsoft 365 Defender.

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:

- Erstellen einer Azure Active Directory-Anwendung
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

> [!NOTE]
> Für den API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Nachdem Sie diese Schritte ausgeführt haben, können Sie mithilfe eines bestimmten Kontexts auf die Microsoft 365 Defender-API zugreifen.

## <a name="application-context-recommended"></a>Anwendungskontext (empfohlen)

Verwenden Sie diesen Kontext für apps, die ohne einen angemeldeten Benutzer ausgeführt werden, beispielsweise Hintergrunddienste oder Daemons.

1. Erstellen Sie eine Azure Active Directory-Webanwendung.
2. Weisen Sie der Anwendung die gewünschten Berechtigungen zu.
3. Erstellen Sie einen Schlüssel für die Anwendung.
4. Abrufen eines Sicherheitstokens mithilfe der Anwendung und des zugehörigen Schlüssels.
5. Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.

Weitere Informationen finden Sie unter **[Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne einen Benutzer](api-create-app-web.md)**.

## <a name="user-context"></a>Benutzerkontext

Verwenden Sie diesen Kontext, um Aktionen im Auftrag eines einzelnen Benutzers auszuführen.

1. Erstellen Sie eine Azure Active Directory systemeigene Anwendung.
2. Weisen Sie der Anwendung die gewünschte Berechtigung zu.
3. Abrufen eines Sicherheitstokens mithilfe der Benutzeranmeldeinformationen für die Anwendung.
4. Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.

Weitere Informationen finden Sie unter **[Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Namen eines Benutzers](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Partner Kontext

Verwenden Sie diesen Kontext, wenn Sie eine APP für viele Benutzer in [mehreren Mandanten](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)bereitstellen müssen.

1. Erstellen Sie eine Azure Active Directory mandantenfähige Anwendung.
2. Weisen Sie der Anwendung die gewünschte Berechtigung zu.
3. Holen Sie sich von jedem Mandanten die [Zustimmung des Administrators](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) für die app.
4. Abrufen eines Sicherheitstokens mithilfe von Benutzeranmeldeinformationen basierend auf der Mandanten-ID eines Kunden.
5. Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.

Weitere Informationen finden Sie unter **[Erstellen einer APP mit Partner Zugriff auf Microsoft 365 Defender-APIs](api-partner-access.md)**.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender-APIs (Übersicht)](api-overview.md)
- [OAuth 2,0 Autorisierung für Benutzeranmeldung und API-Zugriff](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Verwalten von geheimen Schlüsseln in Ihren Server-apps mit Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Erstellen einer "Hello World"-Anwendung, die auf die Microsoft 365-APIs zugreift](api-hello-world.md)
