---
title: Erstellen von DNS-Einträgen web.com Microsoft
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
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste unter web.com Microsoft einrichten.
ms.openlocfilehash: b667b2e69822fcd69babda7790a6468b640b073b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909982"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>Erstellen von DNS-Einträgen web.com Microsoft

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn web.com Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und so weiter zu erstellen.
  
Nachdem Sie diese Datensätze unter web.com hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft-Diensten eingerichtet.

  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändern der Nameservereinträge (NS) Ihrer Domäne
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben. 
  
Wenn Sie sich für web.com angemeldet haben, haben Sie mithilfe des Setupprozesses web.com **hinzugefügt.** 
  
Zum Überprüfen und Erstellen von DNS-Einträgen für Ihre Domäne in Microsoft müssen Sie zunächst die Namenserver bei Ihrer Domänenregistrierungsstelle so ändern, dass sie die Namenserver von web.com verwenden.
  
Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:
  
1. Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.
    
2. Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.
    
    |||
    |:-----|:-----|
    |Erster Namenserver  <br/> |Verwenden Sie den nameserver-Wert, der von web.com.  <br/> |
    |Zweiter Namenserver  <br/> |Verwenden Sie den nameserver-Wert, der von web.com.  <br/> |
   
    > [!TIP]
    > Verwenden Sie mindestens zwei Nameservereinträge. Wenn andere Namenserver aufgelistet sind, sollten Sie sie löschen. 
  
3. Speichern Sie Ihre Änderungen.
    
> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Microsoft-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet. 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp). Melden Sie sich zuerst an.
  
2. Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.** 
  
3. Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**

  
4. Klicken Sie **auf der** Seite Domänennamen unter **Text (TXT-Einträge)** auf **TXT-Einträge** bearbeiten, und wählen Sie dann die Werte aus der folgenden Tabelle aus. 
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Wählen Sie **Weiter** aus.
  
  
6. Warten Sie einige Minuten, bevor Sie ihren neuen TXT-Eintrag überprüfen, damit der gerade erstellte Datensatz über das Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
    
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
    
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.
<a name="BKMK_add_MX"> </a>

1. Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp). Melden Sie sich zuerst an.
  
2. Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.** 
  
3. Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**

4. Klicken **Sie unter E-Mail-Server (MX-Einträge)** auf **MX-Einträge bearbeiten,** und wählen Sie dann die Werte aus der folgenden Tabelle aus. 
    
    |**Priorität**|**TTL**|**Mail server**|
    |:-----|:-----|:-----|
    |1  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml) <br/> |3600  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Hinweis:** Erhalten Sie Ihren *\<domain-key\>* über Ihr Microsoft-Konto.   [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md) |
   

5. Wählen Sie **Speichern** aus.
  
6. Wenn im Abschnitt MX Records  weitere MX-Einträge aufgeführt sind, aktivieren Sie das Kontrollkästchen neben dem Eintrag unter **Löschen**, und wählen Sie **Speichern aus.** 
  
7. Wählen Sie auf dem Bestätigungsbildschirm Änderungen **speichern aus.** 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der sechs CNAME-Datensätze, die für Microsoft erforderlich sind
<a name="BKMK_add_CNAME"> </a>

1. Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp). Sie werden aufgefordert, sich zuerst anzumelden.
     
2. Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.** 
  
3. Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**

4. Fügen Sie den ersten der sechs CNAME-Einträge hinzu.
    
    Klicken **Sie unter Hostaliases (CNAME Records)** auf **CNAME-Datensätze** bearbeiten, und wählen Sie dann die Werte aus der folgenden Tabelle aus.
    
    
    |**Alias**|**TTL**|**Refers to Host Name**|**Anderer Host**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (none)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (none)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (none)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (none)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (none)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (none)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. Wählen Sie **Weiter** aus.
  
6. Fügen Sie die fünf anderen CNAME-Einträge hinzu.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. 
  
1. Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp). Melden Sie sich zuerst an.
    
  
2. Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.** 
  
3. Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**

  
4. Klicken Sie **auf der** Seite Domänennamen unter **Text (TXT-Einträge)** auf **TXT-Einträge** bearbeiten, und wählen Sie dann die Werte aus der folgenden Tabelle aus.   
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.   |

 
5. Wählen Sie **Weiter** aus.

6. Wählen Sie **Änderungen speichern** aus.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Beachten Sie, dass web.com dafür verantwortlich ist, diese Funktionalität verfügbar zu machen. Falls Unterschiede zwischen den unten aufgeführten Schritten und der aktuellen gui(Graphical User Interface web.com angezeigt werden), verwenden Sie bitte die web.com [Community](https://community.web.com.com/). 

1. Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp). Melden Sie sich zuerst an.
      
2. Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.** 
  
3. Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**
  
4. Fügen Sie den ersten der zwei SRV-Einträge hinzu.

    Klicken **Sie unter Dienst (SRV-Einträge)** auf **SRV-Einträge bearbeiten,** und wählen Sie dann die Werte aus der folgenden Tabelle aus. 
        
    |**Service**|**Protocol**|**TTL**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen. 
  
6. Wählen Sie **Weiter** aus.

7. Wählen Sie **Änderungen speichern** aus.

    
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
