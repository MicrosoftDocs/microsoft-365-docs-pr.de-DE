---
title: Erstellen von DNS-Einträgen für Office 365 bei Cloudflare
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
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Cloudflare für Office 365 einrichten.
ms.openlocfilehash: 8d64824f880bab9e6691ebf47c9508c555562fe4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211811"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a>Erstellen von DNS-Einträgen für Office 365 bei Cloudflare

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
[] Wenn Cloudflare Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Nachdem Sie diese Einträge bei Cloudflare hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.
  
Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändern der Namenservereinträge (NS) Ihrer Domäne
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben. 
  
Als Sie sich bei Cloudflare registriert haben, haben Sie mithilfe des **Setup**-Prozesses von Cloudflare eine Domäne hinzugefügt. 
  
Die von Ihnen hinzugefügte Domäne wurde bei einer separaten Domänenregistrierungsstelle erworben. Cloudflare bietet keine Domänenregistrierungsdienste an. Um DNS-Einträge für Ihre Domäne in Office 365 zu überprüfen und zu erstellen, müssen Sie zuerst die Namenserver bei Ihrer Domänenregistrierungsstelle so ändern, dass Namenserver von Cloudflare verwendet werden.
  
Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:
  
1. Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.
    
2. Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.
    
    |||
    |:-----|:-----|
    |Erster Namenserver  <br/> |Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.  <br/> |
    |Zweiter Namenserver  <br/> |Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. Wenn andere Namenserver aufgeführt sind, sollten Sie Sie löschen. 
  
3. Speichern Sie Ihre Änderungen.
    
> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet. 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
  
2. Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.

  
4. Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus. 
    
    |**Typ**|**Name**|**Automatic TTL**|**Content**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 Minuten  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Klicken Sie auf **Speichern**.
  
  
9. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.
  
Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
    
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
    
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden
<a name="BKMK_add_MX"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
  
2. Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.

  
4. Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus. 
    
    |**Typ**|**Name**|**Mail server**|**Priorität**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<Domänenschlüssel\>*  .mail.protection.outlook.com  <br/> **Hinweis:** Rufen Sie Ihren * \<Domänenschlüssel\> * aus Ihrem Office 365-Konto ab.   [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md) |1  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/>|30 Minuten  <br/> |
   

  
5. Klicken Sie auf **Speichern**.
  
9. Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie einen davon durch Klicken auf das Symbol **Löschen (X)**. 
  
10. Wählen Sie im Dialogfeld Bestätigung die Option **Löschen** aus, um die Änderungen zu bestätigen. 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Fügen Sie die sechs CNAME-Einträge hinzu, die für Office 365 erforderlich sind.
<a name="BKMK_add_CNAME"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
    
  
2. Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.

  
4. Fügen Sie den ersten der fünf CNAME-Einträge hinzu.
    
    Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.
    
    
    |**Typ**|**Name**|**Target**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 Minuten  <br/> |
    
  
5. Wählen Sie das Symbol für den **DNS-Datenverkehr** (Orange Cloud) aus, um die Cloudflare-Server zu umgehen.
  
6. Klicken Sie auf **Speichern**.
  
7. Fügen Sie die fünf anderen CNAME-Einträge hinzu.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. If you already have an SPF record for your domain, don't create a new one for Office 365. Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind. 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
    
  
2. Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.

  
4. Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.  
    
    |**Typ**|**Name**|**TTL**|**Content**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 Minuten  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.   |

 
5. Klicken Sie auf **Speichern**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Beachten Sie, dass Cloudflare für die bereitstellungdieser Funktionalität verantwortlich ist. Wenn Sie Diskrepanzen zwischen den folgenden Schritten und der aktuellen Cloudflare-GUI (grafische Benutzeroberfläche) sehen, nutzen Sie die [Cloudflare-Community](https://community.cloudflare.com/). 

1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
      
2. Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.
  
4. Fügen Sie den ersten der zwei SRV-Einträge hinzu.

    Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der ersten Zeile der folgenden Tabelle aus.
        
    |**Type**|**Service**|**Protocol**|**Name**|**TTL**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Verwenden Sie Ihre *domain_name*; Beispiel: contoso.com  |30 Minuten | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Verwenden Sie Ihre *domain_name*; Beispiel: contoso.com   |30 Minuten |100 |1 |5061 | sipfed.online.lync.com |

  
5. Klicken Sie auf **Speichern**.

  
6. Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen. 

    
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
