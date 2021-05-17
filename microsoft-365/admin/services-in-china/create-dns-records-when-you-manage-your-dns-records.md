---
title: Erstellen von DNS-Einträgen für Office 365, wenn Sie Ihre DNS-Einträge verwalten
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Erfahren Sie, wie Sie DNS-Einträge für Office 365, die von 21Vianet betrieben werden, wenn Sie Ihre DNS-Einträge verwalten. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914354"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>Erstellen von DNS-Einträgen für Office 365, wenn Sie Ihre DNS-Einträge verwalten

Ausführliche Anweisungen zum Erstellen von DNS-Einträgen für Office 365 betrieben von 21Vianet, einschließlich des für das E-Mail-Routing erforderlichen MX-Eintrags, finden Sie unter [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). 
  
  
Weitere Optionen und einige Dinge, die Sie beachten sollten:
      
-  Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md). Beschreibungen der Funktionen der DNS-Einträge finden Sie unter [DNS-Grundlagen](../get-help-with-domains/dns-basics.md).
    
-  Bei einigen #A0 können Sie nicht alle erforderlichen Datensatztypen erstellen, was zu Diensteinschränkungen führt, wenn Ihr Hostinganbieter [SRV, CNAME, TXT](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)oder Umleitung nicht unterstützt. Wenn Ihr Anbieter keine SRV-, TXT- oder #A0 [](../get-help-with-domains/buy-a-domain-name.md) unterstützt, wird empfohlen, ihre Domäne an einen Anbieter zu übertragen, der alle erforderlichen [Datensatztypen unterstützt.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77) 
    
- Informationen dazu, welche DNS-Einträge erforderlich sind und welche Werte für jeden Eintrag verwendet werden sollen, einschließlich des MX-Eintrags für E-Mails, finden Sie unter [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md). Beschreibungen der Funktionen der DNS-Einträge finden Sie unter [DNS-Grundlagen](../get-help-with-domains/dns-basics.md).
