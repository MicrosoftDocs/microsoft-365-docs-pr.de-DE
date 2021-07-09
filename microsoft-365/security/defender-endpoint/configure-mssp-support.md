---
title: Konfigurieren der Unterstützung von verwalteten Sicherheitsdienstanbietern
description: Führen Sie die erforderlichen Schritte aus, um die MSSP-Integration mit Microsoft Defender für Endpunkt zu konfigurieren.
keywords: managed security service provider, mssp, configure, integration
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
ms.openlocfilehash: d82bffd6eea54256f2c6773f843030a19e27275d
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339358"
---
# <a name="configure-managed-security-service-provider-integration"></a>Konfigurieren von verwalteten Sicherheitsdienstanbietern (Managed Security Service Provider, MSSP)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

Sie müssen die folgenden Konfigurationsschritte ausführen, um die Integration des verwalteten Sicherheitsdienstanbieters (Managed Security Service Provider, MSSP) zu aktivieren.

>[!NOTE]
>Die folgenden Begriffe werden in diesem Artikel verwendet, um zwischen dem Dienstanbieter und dem Dienstanbieter zu unterscheiden:
> - MSSPs: Sicherheitsorganisationen, die anbieten, Sicherheitsgeräte für eine Organisation zu überwachen und zu verwalten.
> - MSSP-Kunden: Organisationen, die die Dienste von MSSPs nutzen.

Die Integration ermöglicht MSSPs die folgenden Aktionen:

- Zugriff auf das Microsoft 365 Defender-Portal des MSSP-Kunden
- Abrufen von E-Mail-Benachrichtigungen und 
- Abrufen von Warnungen über SIEM-Tools (Security Information and Event Management)

Bevor MSSPs diese Aktionen ausführen können, muss der MSSP-Kunde Zugriff auf den Defender für Endpunkt-Mandanten gewähren, damit der MSSP auf das Portal zugreifen kann. 
 

In der Regel führen MSSP-Kunden die anfänglichen Konfigurationsschritte aus, um MSSPs Zugriff auf ihren Windows Defender Security Central-Mandanten zu gewähren. Nachdem der Zugriff gewährt wurde, können andere Konfigurationsschritte entweder vom MSSP-Kunden oder vom MSSP ausgeführt werden.


Im Allgemeinen müssen die folgenden Konfigurationsschritte ausgeführt werden:


- **Gewähren des MSSP-Zugriffs auf Microsoft 365 Defender** <br>
Diese Aktion muss vom MSSP-Kunden ausgeführt werden. Sie gewährt dem MSSP Zugriff auf den Defender für Endpunkt-Mandanten des MSSP-Kunden.
 

- **Konfigurieren von Warnungsbenachrichtigungen, die an MSSPs gesendet werden** <br>
Diese Aktion kann entweder vom MSSP-Kunden oder von MSSP ausgeführt werden. Dadurch können die MSSPs wissen, welche Warnungen sie für den MSSP-Kunden behandeln müssen.

- **Abrufen von Warnungen vom Mandanten des MSSP-Kunden in das SIEM-System** <br> Diese Aktion wird vom MSSP ausgeführt. Es ermöglicht MSSPs, Warnungen in SIEM-Tools abzurufen.

- **Abrufen von Warnungen vom Mandanten des MSSP-Kunden mithilfe von APIs** <br>
Diese Aktion wird vom MSSP ausgeführt. Es ermöglicht MSSPs, Warnungen mithilfe von APIs abzurufen.

## <a name="multi-tenant-access-for-mssps"></a>Mehrinstanzenfähiger Zugriff für MSSPs
Informationen zum Implementieren eines delegierten Mehrmandantenzugriffs finden Sie unter ["Mehrinstanzenzugriff für Verwaltete Sicherheitsdienstanbieter".](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)



## <a name="related-topics"></a>Verwandte Themen
- [Gewähren von MSSP-Zugriff auf das Portal](grant-mssp-access.md)
- [Zugreifen auf das MSSP-Kundenportal](access-mssp-portal.md)
- [Warnungsbenachrichtigungen konfigurieren](configure-mssp-notifications.md)
- [Abrufen von Benachrichtigungen vom Kunden-Mandanten](fetch-alerts-mssp.md)

