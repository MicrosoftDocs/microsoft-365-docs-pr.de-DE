---
title: Erstellen von DNS-Einträgen für Office 365 bei Wix
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei WiX für Office 365 einrichten.
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211062"
---
# <a name="create-dns-records-at-wix-for-office-365"></a>Erstellen von DNS-Einträgen für Office 365 bei Wix

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
[] Wenn Wix Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Das sind die wichtigsten hinzuzufügenden Einträge. 
  
- [Hinzufügen eines TXT-Eintrags zur Überprüfung](#add-a-txt-record-for-verification)
    
- [Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Office 365 geleitet werden](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Fügen Sie die fünf CNAME-Einträge hinzu, die für Office 365 erforderlich sind](#add-the-five-cname-records-that-are-required-for-office-365).
    
- [Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Hinzufügen der zwei für Office 365 erforderlichen SRV-Einträge](#add-the-two-srv-records-that-are-required-for-office-365)
    
Nachdem Sie diese Einträge bei Wix hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_txt"> </a>

Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** . 
    
3. Wählen Sie **+ Add other** in der txt-Zeile **(Text)** des DNS-Editors aus. 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**TXT VALUE** <br/> |**TTL** <br/> |
|Automatisch aufgefüllt  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.  [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |
   
5. Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus. 
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.
  
Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
  
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
   
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden
<a name="BKMK_mx"> </a>

1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie auf der Seite **Meine Domänen** im Bereich **Postfächer** den Link **MX-Einträge konfigurieren** aus. 
    
3. Wählen Sie in der Dropdownliste **Ihres e-Mail-Anbieters** die Option **Sonstiges** aus. 
    
4. Wählen Sie **+ Add other**aus.
    
5. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:
    
|**Host Name**|**Points to**|**Priorität**|**TTL**|
|:-----|:-----|:-----|:-----|
|Automatisch aufgefüllt <br/> | *\<Domänenschlüssel\>*  .mail.protection.outlook.com  <br/> **Hinweis:** Rufen Sie Ihren * \<Domänenschlüssel\> * aus Ihrem Office 365-Konto ab.   [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83) | 1 Hour|
   
6. Wenn andere MX-Einträge aufgeführt sind, löschen Sie diese. 
    
7. Wählen Sie **OK** aus.
    
8. Wählen Sie im Dialogfeld Bestätigung die Option **OK**aus.
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Fügen Sie die für Office 365 erforderlichen fünf CNAME-Einträge hinzu.
<a name="BKMK_cname"> </a>

1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** . 
    
3. Wählen Sie **+ Add other** in der Zeile **CNAME (Aliases)** des DNS-Editors für jeden CNAME-Eintrag aus. 
    
4. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:
    
|**Host Name**|**Points to**|**TTL**|
|:-----|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 Hour  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 Hour <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus. 
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. If you already have an SPF record for your domain, don't create a new one for Office 365. Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.  
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** . 
    
3. Wählen Sie **+ Add other** in der txt-Zeile **(Text)** des DNS-Editors aus. 
    
4. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:
    
|**Host Name**|**TXT VALUE**|**TTL**|
|:-----|:-----|:-----|
|[leer lassen]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.<br/> |TXT  <br/> | 1 Hour |
   
5. Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus. 
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge
<a name="BKMK_srv"> </a>

1. Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** . 
    
3. Wählen Sie **+ Add other** in der Zeile **SRV** des DNS-Editors aus. 
    
4. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:
    
|**Service**|**Protocol**|**Name**|**Weight**|**Port**|**Target**|**Priorität**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |Automatisch aufgefüllt |1  |443   |sipdir.online.lync.com |100 |1 Hour |
|sipfed|tcp |Automatisch aufgefüllt|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus. 
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  

