---
title: Suchen der Domänenregistrierungsstelle
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Erfahren Sie, wie Sie Ihre Domänenregistrierungsstelle und den DNS-Hostinganbieter mithilfe der InterNIC-Suche finden.
ms.openlocfilehash: 234578c5622a883296a001ce7f226627dd9d93b5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628458"
---
# <a name="find-your-domain-registrar"></a>Suchen der Domänenregistrierungsstelle

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
## <a name="domain-registrar"></a>Domänenregistrierungsstelle
  
### <a name="find-your-domain-name-registrar"></a>Finden Ihrer Domänenregistrierungsstelle

>[!NOTE]
> Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.
  
1. Geben Sie auf der [InterNIC-Suchseite](https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois Search** Ihre Domäne ein. Zum Beispiel *contoso.com.* 
    
2. Wählen Sie die Option **Domain** aus, und klicken Sie dann auf **Submit**.
    
3. Suchen Sie auf der Seite **Whois Search Results** nach dem Eintrag **Registrar**. Hier finden Sie die Organisation, die den Registrierungsstellendienst für Ihre Domäne bereitstellt. 
    
## <a name="dns-hosting-provider"></a>DNS-Hostinganbieter
  
### <a name="find-your-dns-hosting-provider"></a>Finden Ihres DNS-Hostinganbieters

>[!NOTE]
> Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.
  
1. Geben Sie auf der [InterNIC-Suchseite]( https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois Search** Ihre Domäne ein. Zum Beispiel „contoso.com“. 
    
2. Wählen Sie die Option **Domain** aus, und klicken Sie dann auf **Submit**.
    
3. Suchen Sie auf der Seite **Whois Search Results** nach dem ersten **Name Server**-Eintrag. 
    
4. Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Wählen Sie **Nameserver**und dann **Submit** aus.
    
5. Suchen Sie auf der Seite **Whois Search Results** nach dem Eintrag **Registrar**. Hier finden Sie Ihren DNS-Hostinganbieter, den DNS-Dienstanbieter, dem der Namenserver für Ihre Domäne gehört. 
    
---

