---
title: Erstellen von DNS-Einträgen bei Wix für Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste bei Wix für Microsoft einrichten.
ms.openlocfilehash: 3ec2ea0dc24e1872ba22e591fae96b39a9a0deee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916106"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>Erstellen von DNS-Einträgen bei Wix für Microsoft

**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
[] Wenn Wix Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.

Das sind die wichtigsten hinzuzufügenden Einträge. 
  
- [Hinzufügen eines TXT-Eintrags zur Überprüfung](#add-a-txt-record-for-verification)
    
- [Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft gesendet werden.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Fügen Sie die fünf CNAME-Datensätze hinzu, die für Microsoft erforderlich sind.](#add-the-five-cname-records-that-are-required-for-microsoft)
    
- [Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nachdem Sie diese Datensätze bei Wix hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft-Diensten eingerichtet.
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_txt"> </a>

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 

> [!NOTE]
> WIX unterstützt keine DNS-Einträge für Unterdomänen.
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der** Seite Meine Domänen im Bereich **Erweitert** die Schaltfläche **DNS bearbeiten** aus. 
    
3. Wählen **Sie in der** Zeile TXT (Text) des **DNS-Editors** + Add another aus. 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
   ||||
   |:-----|:-----|:-----|
   | Hostname <br/> | TXT Value <br/> | TTL <br/> |
   |Automatisch aufgefüllt  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.  [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |
   
5. Wählen Sie **oben im DNS-Editor** die Schaltfläche DNS speichern aus. 
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
   
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.
<a name="BKMK_mx"> </a>

1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der** Seite Meine Domänen im Bereich **Postfächer** den Link Konfigurieren **Ihrer MX-Einträge** aus. 
    
3. Wählen **Sie in** der **Dropdownliste Ihr E-Mail-Anbieter** andere aus. 
    
4. Wählen **Sie + Weitere hinzufügen aus.**
    
5. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:
    
   | Hostname | Points to  | Priority | TTL |
   |:-----|:-----|:-----|:-----|
   |Automatisch aufgefüllt <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Hinweis:** Erhalten Sie Ihren *\<domain-key\>* über Ihr Microsoft-Konto.   [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml) | 1 Hour|
   
6. Wenn andere MX-Einträge aufgelistet sind, löschen Sie jeden dieser Einträge. 
    
7. Wählen Sie **OK** aus.
    
8. Wählen Sie im Bestätigungsdialogfeld OK **aus.**
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge
<a name="BKMK_cname"> </a>

1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der** Seite Meine Domänen im Bereich **Erweitert** die Schaltfläche **DNS bearbeiten** aus. 
    
3. Wählen **Sie für jeden CNAME-Eintrag** in der **Zeile CNAME (Aliases)** des #A0 einen weiteren aus. 
    
4. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:
    
   | Hostname | Points to  | TTL |
   |:-----|:-----|:-----|
   |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
   |sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour <br/> |
   |lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 Hour  <br/> |
   |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 Hour <br/> |
   |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. Wählen Sie **oben im DNS-Editor** die Schaltfläche DNS speichern aus. 
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.  
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der** Seite Meine Domänen im Bereich **Erweitert** die Schaltfläche **DNS bearbeiten** aus. 
    
3. Wählen **Sie in der** Zeile TXT (Text) des **DNS-Editors** + Add another aus. 
    
4. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:
    
   | Hostname | TXT Value | TTL |
   |:-----|:-----|:-----|
   |[Lassen Sie dies leer]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.<br/> |TXT  <br/> | 1 Hour |
   
5. Wählen Sie **oben im DNS-Editor** die Schaltfläche DNS speichern aus. 
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge
<a name="BKMK_srv"> </a>

1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der** Seite Meine Domänen im Bereich **Erweitert** die Schaltfläche **DNS bearbeiten** aus. 
    
3. Wählen **Sie in der** Zeile SRV des **DNS-Editors** + Hinzufügen eine weitere aus. 
    
4. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:
    
   | Dienst | Protokoll | Name | Schriftbreite | Port | Ziel | Priority | TTL |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |Automatisch aufgefüllt |1  |443   |sipdir.online.lync.com |100 |1 Hour |
   |sipfed|tcp |Automatisch aufgefüllt|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. Wählen Sie **oben im DNS-Editor** die Schaltfläche DNS speichern aus. 
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
