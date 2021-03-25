---
title: Konfigurieren von Benachrichtigungen, die an MSSPs gesendet werden
description: Konfigurieren von Benachrichtigungen, die an MSSPs gesendet werden
keywords: Managed Security Service Provider, mssp, configure, integration
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166053"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Konfigurieren von Benachrichtigungen, die an MSSPs gesendet werden 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>Dieser Schritt kann entweder vom MSSP-Kunden oder vom MSSP durchgeführt werden. MSSPs müssen über die entsprechenden Berechtigungen verfügen, um dies im Namen des MSSP-Kunden zu konfigurieren.

Nachdem der Zugriff auf das Portal gewährt wurde, können Benachrichtigungsregeln erstellt werden, damit E-Mails an MSSPs gesendet werden, wenn dem Mandanten zugeordnete Warnungen erstellt und festgelegte Bedingungen erfüllt werden.

 
Weitere Informationen finden Sie unter [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).
 

Diese Kontrollkästchen müssen aktiviert sein:
- **Name der Organisation hinzufügen** – Der Name des Kunden wird E-Mail-Benachrichtigungen hinzugefügt.
- **Mandantenspezifischer Portallink hinzufügen** – Url des Warnungslinks hat mandantenspezifischen Parameter (tid=target_tenant_id), der direkten Zugriff auf das Zielmandantportal ermöglicht


## <a name="related-topics"></a>Verwandte Themen
- [Gewähren von MSSP-Zugriff auf das Portal](grant-mssp-access.md)
- [Zugreifen auf das MSSP-Kundenportal](access-mssp-portal.md)
- [Abrufen von Warnungen vom Kunden-Mandanten](fetch-alerts-mssp.md)
