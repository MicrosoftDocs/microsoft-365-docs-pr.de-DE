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
description: Erfahren Sie, wie Sie Datenverkehr an eine vorhandene öffentliche Website, die außerhalb von Microsoft gehostet wird, weiterrouten, wenn Sie Microsoft zum Verwalten von DNS-Einträgen für Ihre benutzerdefinierte Domäne festgelegt haben.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572141"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen

 **Wenn Sie die Microsoft-Einträge** Ihrer Domäne bei Ihrem DNS-Hostinganbieter verwalten, müssen Sie sich keine Gedanken über die Schritte in diesem Thema machen. Ihre Website bleibt, wo sie ist, und Benutzer können die Site weiterhin aufrufen. 
  
 **Wenn Microsoft Ihre DNS-Einträge** verwaltet, um Datenverkehr an eine vorhandene öffentliche Website zu routen, die außerhalb von Microsoft gehostet wird, gehen Sie nach dem Hinzufügen Ihrer Domäne zu Microsoft wie folgt vor: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Aktualisieren von DNS-Einträgen im Microsoft 365 Admin Center
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

1. Wählen Sie auf der Seite **Domänen** die Domäne aus, und wählen Sie dann **DNS-Einträge** aus.

1. Wählen **Sie + Datensatz hinzufügen aus,** und geben Sie Folgendes ein: 
    
   - Für **Typ eingeben:** **A (Adresse)**
    
   - Geben Sie unter **Hostname oder Alias** Folgendes ein: **@**
    
   - Geben Sie unter **IP-Adresse** die statische IP-Adresse für Ihre Website ein, unter der diese derzeit gehostet wird, beispielsweise "172.16.140.1". 
    
   Es muss eine  *statische*  IP-Adresse für die Website sein, keine  *dynamische*  . Überprüfen Sie bei der Website, auf der Ihre Website gehostet wird, dass Sie eine statische IP-Adresse für Ihre öffentliche Website erhalten können. 
    
1. Klicken Sie auf **Speichern**. 
    
Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.
  
1. Wählen **Sie + Datensatz hinzufügen aus,** und geben Sie Folgendes ein: 
    
   - Für **Typ eingeben:** **CNAME (Alias)**
    
   - Geben Sie unter **Hostname oder Alias** Folgendes ein: **www**
    
   - Geben Sie unter **Verweist auf die Adresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Website ein, beispielsweise contoso.com. 
    
2. Wählen Sie **Speichern** aus. 
    
Führen Sie schließlich die folgenden Schritte aus:
  
[Aktualisieren Sie die NS-Einträge Ihrer Domäne so, dass](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) sie auf Microsoft verweisen. 
  
Wenn die NS-Einträge so aktualisiert wurden, dass sie auf Microsoft verweisen, ist Ihre Domäne alle eingerichtet. E-Mails werden an Microsoft geroutet, und der Datenverkehr zu Ihrer Websiteadresse wird weiterhin an Ihren aktuellen Websitehost gesendet.
