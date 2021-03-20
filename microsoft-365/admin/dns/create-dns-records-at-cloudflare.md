---
title: Erstellen von DNS-Einträgen bei Cloudflare für Microsoft
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste bei Cloudflare für Microsoft einrichten.
ms.openlocfilehash: 0a80cf059a3a69dcb8aa48251875410f35684286
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910378"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>Erstellen von DNS-Einträgen bei Cloudflare für Microsoft

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
[] Wenn Cloudflare Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Nachdem Sie diese Datensätze bei Cloudflare hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft 365-Diensten eingerichtet.
  
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändern der Nameservereinträge (NS) Ihrer Domäne
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben. 
  
Als Sie sich bei Cloudflare registriert haben, haben Sie mithilfe des **Setup**-Prozesses von Cloudflare eine Domäne hinzugefügt. 
  
Die hinzugefügte Domäne wurde von Cloudflare oder einer separaten Domänenregistrierungsstelle erworben. Zum Überprüfen und Erstellen von DNS-Einträgen für Ihre Domäne in Microsoft 365 müssen Sie zunächst die Namenserver bei Ihrer Domänenregistrierungsstelle so ändern, dass sie die Namenserver von Cloudflare verwenden.
  
Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:
  
1. Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.
    
2. Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.
    
    |||
    |:-----|:-----|
    |Erster Namenserver  <br/> |Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.  <br/> |
    |Zweiter Namenserver  <br/> |Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.  <br/> |
   
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
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
  
2. Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**

  
4. Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der folgenden Tabelle aus. 
    
    | Typ | Name | Automatic TTL | Inhalt |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 Minuten  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Wählen Sie **Speichern** aus.
  
  
9. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, wechseln Sie zu Microsoft und suchen nach dem Datensatz.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
    
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
    
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.
<a name="BKMK_add_MX"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
  
2. Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**

  
4. Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der folgenden Tabelle aus. 
    
    | Typ | Name | Mail server | Priority | TTL |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Hinweis:** Holen Sie  *\<domain-key\>*  sich Ihre von Ihrem Microsoft 365-Konto.   [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md) |1  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml) <br/>|30 Minuten  <br/> |
   

  
5. Wählen Sie **Speichern** aus.
  
9. Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie einen davon durch Klicken auf das Symbol **Löschen (X)**. 
  
10. Wählen Sie im Bestätigungsdialogfeld **Löschen** aus, um Ihre Änderungen zu bestätigen. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der sechs CNAME-Datensätze, die für Microsoft erforderlich sind
<a name="BKMK_add_CNAME"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
    
  
2. Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**

  
4. Fügen Sie den ersten der fünf CNAME-Einträge hinzu.
    
    Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der folgenden Tabelle aus.
    
    
    | Typ | Name | Ziel | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 Minuten  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 Minuten  <br/> |
    
  
5. Wählen Sie das **SYMBOL FÜR DNS-Datenverkehr** (Orange Cloud in Grau ändern), um die Cloudflare-Server zu umgehen.
  
6. Wählen Sie **Speichern** aus.
  
7. Fügen Sie die fünf anderen CNAME-Einträge hinzu.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen, sondern fügen Sie die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
    
  
2. Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**

  
4. Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der folgenden Tabelle aus.  
    
    | Typ | Name | TTL | Inhalt |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 Minuten  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.   |

 
5. Wählen Sie **Speichern** aus.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Beachten Sie, dass Cloudflare für die Verfügbarkeit dieser Funktionalität verantwortlich ist. Falls Unterschiede zwischen den unten aufgeführten Schritten und der aktuellen Cloudflare-GUI (Grafische Benutzeroberfläche) auftreten, verwenden Sie bitte die [Cloudflare Community](https://community.cloudflare.com/). 

1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.
      
2. Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten. 
  
3. Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**
  
4. Fügen Sie den ersten der zwei SRV-Einträge hinzu.

    Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der ersten Zeile der folgenden Tabelle aus.
        
    | Typ | Dienst | Protokoll | Name | TTL | Priorität | Schriftbreite | Port | Ziel |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Verwenden Sie *Domain_name*; Beispiel: contoso.com  |30 Minuten | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Verwenden Sie *Domain_name*; Beispiel: contoso.com   |30 Minuten |100 |1 |5061 | sipfed.online.lync.com |

  
5. Wählen Sie **Speichern** aus.

  
6. Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen. 

    
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
