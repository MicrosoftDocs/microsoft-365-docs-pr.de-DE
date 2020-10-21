---
title: Erstellen von DNS-Einträgen bei easyDNS für Microsoft
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter easyDNS für Microsoft einrichten.
ms.openlocfilehash: 4909a02ec56fc9720a2636e822da0339e89bccf8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645551"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Erstellen von DNS-Einträgen bei easyDNS für Microsoft

[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen. 
  
Sie müssen alle folgenden DNS-Einträge auf der Website Ihrer Registrierungsstelle hinzufügen, um e-Mails an Microsoft weiterzuleiten, Ihre Domäne für Teams und Skype for Business zu verwenden usw.
  
Hinweis: SRV-Einträge sind derzeit nicht in allen easyDNS-Dienst Paketen verfügbar. Möglicherweise müssen Sie ein Upgrade auf ein höheres Service Level mit easyDNS durchführen, um SRV-Einträge hinzuzufügen, die für Skype for Business erforderlich sind.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Überprüfen, ob Sie die Domäne mit einem TXT-Eintrag besitzen

1. Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an. 
    
2. Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**
    
3. Wählen Sie unter der Überschrift **TXT-Datensätze** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus. 
    
4. Geben Sie die folgenden Einträge in die Textfelder ein:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX (verwenden Sie den auf der Seite Admin Center-Domänen bereitgestellten Wert)  <br/> |
   
5. Wählen Sie **weiter**aus. 
    
6. Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus. 
    
7. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag über das Internet verbreitet und von Microsoft erkannt werden kann.
    
8. Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.
    
9. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
10. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
11. Wählen Sie auf der Seite **Setup** die Option **Setup starten aus.**
    
12. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Hinzufügen eines MX-Eintrags zum Weiterleiten von e-Mail an Microsoft

1. Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an. 
    
2. Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**
    
3. Wählen Sie unter der Überschrift **MX Records** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus. 
    
4. Geben Sie die folgenden Einträge in die Textfelder ein:
    
    |**e-Mail für Zone**|**e-Mail-Server**|**Präferenz**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>. Mail.Protection.Outlook.com (Abrufen Ihres \<domain-key\> Werts über die Admin Center-Domänen Seite)  <br/> |0  <br/> |
   
2. Wenn Sie Ihre anderen MX-Einträge zu Sicherungszwecken speichern möchten, kopieren Sie Sie an einer beliebigen Stelle. Bevor Sie fortfahren, entfernen Sie alle anderen MX-Einträge hier.
    
5. Wählen Sie **weiter**aus. 
    
6. Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus. 
    
## <a name="add-the-required-cname-records"></a>Hinzufügen der erforderlichen CNAME-Einträge

1. Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an. 
    
2. Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**
    
3. Wählen Sie unter der Überschrift **CNAME/Alias Datensätze** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus. 
    
4. Geben Sie die folgenden Einträge in die Textfelder ein:


    |**HOST**|**Address (muss mit einem "." enden)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Wählen Sie **weiter**aus. 
    
6. Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern

1. Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an. 
    
2. Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**
    
3. Wählen Sie unter der Überschrift **TXT-Datensätze** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus. 
    
4. Geben Sie die folgenden Einträge in die Textfelder ein:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Wählen Sie **weiter**aus. 
    
6. Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus. 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge

Hinweis: SRV-Einträge sind derzeit unter easyDNS ' Domain plus Service Level nicht verfügbar. Möglicherweise müssen Sie ein Upgrade auf ein höheres Service Level mit easyDNS durchführen, um SRV-Einträge hinzuzufügen. 
  
1. Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an. 
    
2. Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**
    
3. Wählen Sie unter der Überschrift **SRV-Datensätze** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus. 
    
4. Geben Sie die folgenden Einträge in die Textfelder ein:
    
    |**SERVICE**|**Proto**|**HOST**|**PRI**|**WGT**|**PORT**|**Target (muss mit einem "." enden)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Wählen Sie **weiter**aus. 
    
6. Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus. 
    

