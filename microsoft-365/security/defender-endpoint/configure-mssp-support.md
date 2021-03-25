---
title: Konfigurieren der Unterstützung von verwalteten Sicherheitsdienstanbietern
description: Ausführen der erforderlichen Schritte zum Konfigurieren der MSSP-Integration mit Microsoft Defender for Endpoint
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
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165249"
---
# <a name="configure-managed-security-service-provider-integration"></a>Konfigurieren der Integration von verwalteten Sicherheitsdienstanbietern

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

Sie müssen die folgenden Konfigurationsschritte ausführen, um die Integration des anbieters für verwaltete Sicherheit (Managed Security Service Provider, MSSP) zu aktivieren.

>[!NOTE]
>Die folgenden Begriffe werden in diesem Artikel verwendet, um zwischen dem Dienstanbieter und dem Dienstanbieter zu unterscheiden:
> - MSSPs: Sicherheitsorganisationen, die anbieten, Sicherheitsgeräte für eine Organisation zu überwachen und zu verwalten.
> - MSSP-Kunden: Organisationen, die die Dienste von MSSPs nutzen.

Die Integration ermöglicht es MSSPs, die folgenden Aktionen zu ergreifen:

- Zugriff auf das Microsoft Defender Security Center-Portal des MSSP-Kunden
- Erhalten von E-Mail-Benachrichtigungen und 
- Abrufen von Warnungen über SieM-Tools (Security Information and Event Management)

Bevor MSSPs diese Aktionen ausführen können, muss der MSSP-Kunde zugriff auf seinen Defender for Endpoint-Mandanten gewähren, damit der MSSP auf das Portal zugreifen kann. 
 

In der Regel ergreifen MSSP-Kunden die ersten Konfigurationsschritte, um MSSPs Zugriff auf ihren Windows Defender Security Central-Mandanten zu gewähren. Nachdem der Zugriff gewährt wurde, können andere Konfigurationsschritte vom MSSP-Kunden oder vom MSSP durchgeführt werden.


Im Allgemeinen müssen die folgenden Konfigurationsschritte unternommen werden:


- **Gewähren des MSSP-Zugriffs auf Microsoft Defender Security Center** <br>
Diese Aktion muss vom MSSP-Kunden durchgeführt werden. Es gewährt dem MSSP Zugriff auf den Defender for Endpoint-Mandanten des MSSP-Kunden.
 

- **Konfigurieren von Benachrichtigungen, die an MSSPs gesendet werden** <br>
Diese Aktion kann vom MSSP-Kunden oder vom MSSP ergriffen werden. Dadurch erfahren die MSSPs, welche Warnungen sie für den MSSP-Kunden adressiert werden müssen.

- **Abrufen von Warnungen vom Mandanten des MSSP-Kunden in das SIEM-System** <br> Diese Aktion wird vom MSSP ergriffen. Es ermöglicht MSSPs das Abrufen von Warnungen in SIEM-Tools.

- **Abrufen von Warnungen vom Mandanten des MSSP-Kunden mithilfe von APIs** <br>
Diese Aktion wird vom MSSP ergriffen. Es ermöglicht MSSPs das Abrufen von Warnungen mithilfe von APIs.

## <a name="multi-tenant-access-for-mssps"></a>Mehr-Mandanten-Zugriff für MSSPs
Informationen zum Implementieren eines delegierten Zugriffs mit mehreren Mandanten finden Sie unter [Multi-Tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).



## <a name="related-topics"></a>Verwandte Themen
- [Gewähren von MSSP-Zugriff auf das Portal](grant-mssp-access.md)
- [Zugreifen auf das MSSP-Kundenportal](access-mssp-portal.md)
- [Konfigurieren von Benachrichtigungen](configure-mssp-notifications.md)
- [Abrufen von Warnungen vom Kunden-Mandanten](fetch-alerts-mssp.md)

