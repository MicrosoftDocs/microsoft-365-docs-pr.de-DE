---
title: Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Hier erfahren Sie, wie Sie Datenverkehr an eine vorhandene öffentliche Website weiterleiten, die außerhalb von Office 365 gehostet wird, wenn Sie Office 365 für die Verwaltung von DNS-Einträgen für Ihre benutzerdefinierte Domäne festgelegt haben.
ms.openlocfilehash: 3e71925f9b50e5520bd383aa5318db513202f6ec
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142539"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen

 [] **Wenn Sie alle Office 365-Einträge Ihrer Domäne bei Ihrem DNS-Hostinganbieter verwalten**, sind die Schritte in diesem Artikel für Sie irrelevant. Ihre Website bleibt, wo sie ist, und Benutzer können die Site weiterhin aufrufen. 
  
 **Wenn Ihre DNS-Einträge von Office 365 verwaltet werden**, gehen Sie, nachdem Sie Ihre Domäne zu Office 365 hinzugefügt haben, wie folgt vor, um den Datenverkehr auf eine vorhandene öffentliche Website zu leiten, die außerhalb von Office 365 gehostet wird. 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Aktualisieren von DNS-Einträgen im Microsoft 365 Admin Center
1. Wechseln Sie im Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .

2. Wählen Sie auf der Seite **Domänen** in der Liste der Domänen die Domäne aus, die Sie für Ihre Website verwenden, und wählen Sie dann im Verwaltungsbereich **DNS-Einstellungen** aus. 
    
3. Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein: 
    
  - Geben Sie unter **DNS-Typ** ein: **A (Adresse)**
    
  - Geben Sie unter **Hostname oder Alias** Folgendes ein: **@**
    
  - Geben Sie unter **IP-Adresse** die statische IP-Adresse für Ihre Website ein, unter der diese derzeit gehostet wird, beispielsweise "172.16.140.1". 
    
    Es muss eine  *statische*  IP-Adresse für die Website sein, keine  *dynamische*  . Überprüfen Sie bei der Website, auf der Ihre Website gehostet wird, dass Sie eine statische IP-Adresse für Ihre öffentliche Website erhalten können. 
    
3. Klicken Sie auf **Speichern**. 
    
Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.
  
1. Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein: 
    
  - Geben Sie unter **DNS-Typ** ein: **CNAME (Alias)**
    
  - Geben Sie unter **Hostname oder Alias** Folgendes ein: **www**
    
  - Geben Sie unter **Verweist auf die Adresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Website ein, beispielsweise contoso.com. 
    
2. Wählen Sie **Speichern** aus. 
    
Führen Sie schließlich die folgenden Schritte aus:
  
[Aktualisieren Ihrer Domänennamenservereinträge](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx), sodass sie auf Office 365 verweisen. 
  
Wenn die Namenservereinträge so aktualisiert wurden, dass sie auf Office 365 verweisen, ist Ihre Domäne wie folgt eingerichtet: E-Mail-Nachrichten werden an Office 365 weitergeleitet, und der an Ihre Websiteadresse gerichtete Datenverkehr geht weiterhin bei Ihrem aktuellen Websitehost ein.
 
