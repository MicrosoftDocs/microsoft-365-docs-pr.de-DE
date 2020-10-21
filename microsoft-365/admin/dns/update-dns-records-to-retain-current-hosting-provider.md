---
title: Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen
f1.keywords:
- NOCSH
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
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Hier erfahren Sie, wie Sie Datenverkehr zu einer vorhandenen öffentlichen Website weiterleiten, die außerhalb von Microsoft gehostet wird, wenn Sie Microsoft zum Verwalten von DNS-Einträgen für Ihre benutzerdefinierte Domäne festgelegt haben.
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645563"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen

 **Wenn Sie die Microsoft-Einträge Ihrer Domäne bei Ihrem DNS-Hostinganbieter verwalten**, müssen Sie sich keine Gedanken über die Schritte in diesem Thema machen. Ihre Website bleibt, wo sie ist, und Benutzer können die Site weiterhin aufrufen. 
  
 **Wenn Microsoft Ihre DNS-Einträge verwaltet**, führen Sie die folgenden Schritte aus, um Datenverkehr an eine vorhandene öffentliche Website zu leiten, die außerhalb von Microsoft gehostet wird, nachdem Sie Ihre Domäne zu Microsoft hinzugefügt haben: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Aktualisieren von DNS-Einträgen im Microsoft 365 Admin Center
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

2. Wählen Sie auf der Seite **Domänen** die Domäne aus, und wählen Sie dann **DNS-Einträge**aus.

3. Wählen Sie unter **DNS-Einstellungen**die Option **Benutzerdefinierte Datensätze**aus.

4. Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein: 
    
   - Geben Sie unter **DNS-Typ** ein: **A (Adresse)**
    
   - Geben Sie unter **Hostname oder Alias** Folgendes ein: **@**
    
   - Geben Sie unter **IP-Adresse** die statische IP-Adresse für Ihre Website ein, unter der diese derzeit gehostet wird, beispielsweise "172.16.140.1". 
    
   Es muss eine  *statische*  IP-Adresse für die Website sein, keine  *dynamische*  . Überprüfen Sie bei der Website, auf der Ihre Website gehostet wird, dass Sie eine statische IP-Adresse für Ihre öffentliche Website erhalten können. 
    
5. Klicken Sie auf **Speichern**. 
    
Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.
  
1. Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein: 
    
   - Geben Sie unter **DNS-Typ** ein: **CNAME (Alias)**
    
   - Geben Sie unter **Hostname oder Alias** Folgendes ein: **www**
    
   - Geben Sie unter **Verweist auf die Adresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Website ein, beispielsweise contoso.com. 
    
2. Wählen Sie **Speichern** aus. 
    
Führen Sie schließlich die folgenden Schritte aus:
  
[Aktualisieren Sie die NS-Einträge Ihrer Domäne](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) so, dass Sie auf Microsoft verweist. 
  
Wenn die NS-Einträge so aktualisiert wurden, dass Sie auf Microsoft verweist, ist Ihre Domäne eingerichtet. E-Mail-Nachrichten werden an Microsoft weitergeleitet, und der Datenverkehr zu Ihrer Website-Adresse wird weiterhin an Ihren aktuellen Website-Host weitergeleitet.
 
