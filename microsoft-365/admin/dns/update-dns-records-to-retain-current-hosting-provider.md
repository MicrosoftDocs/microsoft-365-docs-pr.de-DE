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
description: Erfahren Sie, wie Sie Datenverkehr an eine vorhandene öffentliche Website weiterleiten, die außerhalb von Microsoft gehostet wird, wenn Sie Microsoft so konfiguriert haben, dass DNS-Einträge für Ihre benutzerdefinierte Domäne verwaltet werden.
ms.openlocfilehash: d54aa4583862ce19907a3b8494a333bbb925e436
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228123"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen

 **Wenn Sie die Microsoft-Einträge Ihrer Domäne bei Ihrem DNS-Hostinganbieter verwalten,** müssen Sie sich keine Gedanken über die Schritte in diesem Thema machen. Ihre Website bleibt, wo sie ist, und Benutzer können die Site weiterhin aufrufen. 
  
 **Wenn Microsoft Ihre DNS-Einträge verwaltet,** führen Sie die folgenden Schritte aus, um den Datenverkehr an eine vorhandene öffentliche Website weiterzuleiten, die außerhalb von Microsoft gehostet wird, nachdem Sie Ihre Domäne zu Microsoft hinzugefügt haben: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Aktualisieren von DNS-Einträgen im Microsoft 365 Admin Center
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

1. Wählen Sie auf der Seite **Domänen** die Domäne aus, und wählen Sie dann **DNS-Einträge** aus.

1. Wählen Sie **+Datensatz hinzufügen aus,** und geben Sie Folgendes ein: 
    
   - Geben Sie **als Typ** ein: **A (Adresse)**
    
   - Geben Sie unter **Hostname oder Alias** Folgendes ein: **@**
    
   - Geben Sie unter **IP-Adresse** die statische IP-Adresse für Ihre Website ein, unter der diese derzeit gehostet wird, beispielsweise "172.16.140.1". 
    
   Es muss eine  *statische*  IP-Adresse für die Website sein, keine  *dynamische*  . Überprüfen Sie bei der Website, auf der Ihre Website gehostet wird, dass Sie eine statische IP-Adresse für Ihre öffentliche Website erhalten können. 
    
1. Klicken Sie auf **Speichern**. 
    
Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.
  
1. Wählen Sie **+Datensatz hinzufügen aus,** und geben Sie Folgendes ein: 
    
   - Geben **Sie für typ:** **CNAME (Alias)**
    
   - Geben Sie unter **Hostname oder Alias** Folgendes ein: **www**
    
   - Geben Sie unter **Verweist auf die Adresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Website ein, beispielsweise contoso.com. 
    
2. Wählen Sie **Speichern** aus. 
    
Führen Sie schließlich die folgenden Schritte aus:
  
Aktualisieren Sie die [NS-Einträge Ihrer Domäne](../setup/add-domain.md) so, dass sie auf Microsoft verweisen. 
  
Wenn die NS-Einträge aktualisiert wurden, um auf Microsoft zu verweisen, ist Ihre Domäne eingerichtet. E-Mails werden an Microsoft weitergeleitet, und der Datenverkehr zu Ihrer Websiteadresse wird weiterhin zu Ihrem aktuellen Websitehost geleitet.
