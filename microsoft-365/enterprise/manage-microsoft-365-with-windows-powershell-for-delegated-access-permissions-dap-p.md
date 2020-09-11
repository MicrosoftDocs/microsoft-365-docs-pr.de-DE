---
title: Verwalten von Microsoft 365 mit Windows PowerShell für DAP-Partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Wie Anbieter von Syndication-und Cloud Solution Providern (CSP) Windows PowerShell zum Verwalten von Microsoft 365-Kundenmandanten verwenden können
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429878"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a>Vorgehensweise Verwalten von Microsoft 365 mit Windows PowerShell für Partner mit Delegierten Zugriffsberechtigungen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

DAP-Partner (Delegated Access Permission, delegierte Zugriffsberechtigung) sind Syndication-Partner und Cloudlösungsanbieter (Cloud Solution Providers, CSP). Viele sind Netzwerk-oder Telekom-Anbieter. Sie bündeln Microsoft 365-Abonnements in ihren Dienst angeboten. Wenn Sie ein Microsoft 365-Abonnement verkaufen, erhalten Sie automatisch verwalten im Namen von (AOBO) Berechtigungen für den Mandanten des Kunden, damit Sie diese Mandanten verwalten und melden können. Diese Aufgaben sind im Microsoft 365 Admin Center schwierig. Es ist viel einfacher, PowerShell für Microsoft 365 zu verwenden, um administrative Aufgaben wie:
- Auflisten aller Kunden- **TenantIds** und ihrer Domänen 
- Identifizieren aller Benutzer in einer Kunden Mandantschaft und ihrer zugewiesenen Lizenzen
> [!NOTE]
> Einige Verwaltungsaufgaben können nur in PowerShell durchgeführt werden.

In den folgenden Artikeln wird gezeigt, wie Syndication-und CSP-Partner PowerShell zur Verwaltung Ihrer Kundenmandanten verwenden:
  
- [Verwalten von Microsoft 365-Mandanten mit Windows PowerShell für Partner mit Delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [Hinzufügen einer Domäne zu einem Kundenmandanten mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [Herstellen einer Verbindung mit Exchange Online PowerShell](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [Abrufen von Kundenberichtsdaten über Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   