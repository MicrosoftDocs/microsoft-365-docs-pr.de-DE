---
title: Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter
f1.keywords:
- NOCSH
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
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Microsoft 365 erstellen.
ms.custom: okr_smb
ms.openlocfilehash: 2cf28cdd3cc2f85e448d512e72f5b022177e8f1e
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053722"
---
# <a name="create-dns-records-at-any-dns-hosting-provider"></a>Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Suchen Sie in der Liste der [hostspezifischen Anweisungen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus. 
  
Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).
  
Wenn Sie die Einträge selbst einrichten möchten, finden Sie hier die Einträge, die hinzugefügt werden müssen. Beachten Sie, dass Ihr Überprüfungseintrag und der MX-Eintrag für Ihre Domäne einzigartig sind. Zum Einrichten dieser Einträge benötigen Sie einen "Token"-Wert für Ihre Domäne. Im Folgenden wird beschrieben, wie Sie hierfür vorgehen müssen.
  
> [!IMPORTANT]
> Die genauen Namen der Kästchen oder  *Felder*, in die Sie Informationen eingeben oder einfügen müssen, um die einzelnen DNS-Eintragstypen zu erstellen, sind bei jedem DNS-Host verschieden. Möglicherweise stellt Ihr DNS-Hostinganbieter auf seiner Website Hilfe bereit, damit Sie die hier angegebenen Anweisungen den entsprechenden Feldern auf seiner Website zuordnen können. Denken Sie daran, unter [Erstellen eines DNS-Eintrags für Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) zu überprüfen, ob es schrittweise Anleitungen speziell für Ihren DNS-Host gibt. >  Bei einigen DNS-Hosts können Sie nicht alle erforderlichen Eintragstypen erstellen. Dies führt zu [Diensteinschränkungen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) in Microsoft 365. Wenn Ihr Anbieter SRV-, TXT- oder CNAME-Einträge nicht unterstützt, empfiehlt sich ein [Übertragen Ihrer Domäne](../get-help-with-domains/buy-a-domain-name.md) zu einem DNS-Host, der alle erforderlichen Eintragstypen unterstützt. Für einen schnellen, automatisierten Prozess zum Einrichten von Microsoft 365 empfehlen wird die Übertragung Ihrer Domäne zu GoDaddy. 
  
> [!NOTE]
> Normalerweise dauert es nur einige Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>Hinzufügen eines TXT- oder MX-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

> [!NOTE]
> Sie müssen nur einen der beiden Einträge erstellen. TXT ist der bevorzugte Eintragstyp, jedoch wird er von einigen DNS-Hostinganbietern nicht unterstützt. In diesem Fall können Sie stattdessen einen MX-Datensatz erstellen. 
  
Bevor Sie Ihre Domäne in Microsoft 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
 **Suchen Sie den Bereich auf der Website Ihres DNS-Hostinganbieters, in dem ein neuer Eintrag erstellt werden kann.**
  
1. Melden Sie sich bei der Website Ihres DNS-Hostinganbieters an.
    
2.  Wählen Sie Ihre Domäne aus.
    
3. Suchen Sie die Seite, auf der Sie DNS-Datensätze für Ihre Domäne bearbeiten können.
    
 **Erstellen Sie den Eintrag.**
  
1. Je nachdem, ob Sie einen TXT-Eintrag oder einen MX-Eintrag erstellen möchten, führen Sie einen der folgenden Schritte aus:
    
   - **Wenn Sie einen TXT-Eintrag erstellen, verwenden Sie die folgenden Werte:**
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**Record Type **|**Alias** oder **Hostname**|**Value**|**TTL**|
      |TXT|Führen Sie eine der folgenden Aktionen aus: Geben Sie **@** ein, lassen Sie das Feld leer, oder geben Sie Ihren Domänennamen ein.    <br/> **Hinweis:** Die Anforderungen für dieses Feld sind je nach DNS-Host unterschiedlich. |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365.  <br/>        [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest.  |
   
   - **Wenn Sie einen MX-Eintrag erstellen, verwenden Sie die folgenden Werte:**
    
      ||||||
      |:-----|:-----|:-----|:-----|:-----|
      |**Record Type **|**Alias** oder **Hostname**|**Value**|**Priorität**|**TTL**|
      |MX|Geben Sie **@** oder Ihren Domänennamen ein. |MS=ms *XXXXXXXX* <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.    <br/>       [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Für **Priority** (Priorität) verwenden Sie eine geringere Priorität als für die bereits vorhandenen MX-Einträge, um Konflikte mit dem MX-Eintrag für den E-Mail-Verkehr zu vermeiden. <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest. |
   
2. Speichern Sie den Eintrag.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.
  
Wenn Microsoft 365 den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
       
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.   
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-mx-record-to-route-email"></a>Hinzufügen eines MX-Eintrags zum Weiterleiten von E-Mails
<a name="BKMK_add_MX"> </a>

Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft 365 geleitet werden.  *Nachdem Sie den MX-Eintrag Ihrer Domäne aktualisiert haben, treffen alle neuen E-Mails für jeden Benutzer Ihr Domäne in Microsoft 365 ein*. Alle E-Mails, die Sie bereits erhalten haben, bleiben so lange auf Ihrem aktuellen E-Mail-Host gespeichert, bis Sie die [Migration von E-Mails und Kontakten zu Microsoft 365](../setup/migrate-email-and-contacts-admin.md) beschließen.

 **Aufgabe**
  
Suchen der Seite, auf der Sie DNS-Einträge für Ihre Domäne erstellen können
  
1. Melden Sie sich bei der Website Ihres DNS-Hosts an.
    
2.  Wählen Sie Ihre Domäne aus.
    
3. Suchen Sie die Seite, auf der Sie DNS-Datensätze für Ihre Domäne bearbeiten können.
    
::: moniker range="o365-worldwide"

  Der von Ihnen hinzugefügte MX-Eintrag enthält einen Wert (den Wert **Verweist auf die Adresse**), der Folgendem ähnelt: \<MX token\>.mail.protection.outlook.com, wobei \<MX-Token\> ein Wert wie z. B. MSxxxxxxx ist.   

::: moniker-end

::: moniker range="o365-germany"

  Der von Ihnen hinzugefügte MX-Eintrag enthält einen Wert (den Wert **Verweist auf die Adresse**), der Folgendem ähnelt: \<MX-Token\>.mail.protection.outlook.de, wobei \<MX-Token\> ein Wert wie z. B. MSxxxxxxx ist.   

::: moniker-end

4. Fügen Sie auf der Website Ihres DNS-Hosts einen neuen MX-Eintrag hinzu.
    
    Sie erhalten nun die [Informationen zu dem MX-Eintrag](../get-help-with-domains/information-for-dns-records.md) von Microsoft 365. 
    
5. Kopieren Sie für den MX-Eintrag (im vorherigen Schritt) den Wert unter **Verweist auf die Adresse**. 
    
    Sie verwenden diesen Wert in dem Eintrag, den Sie auf der Website Ihres DNS-Hosts erstellen, wie es im nächsten Schritt beschrieben ist.
    
6. Stellen Sie bei dem neuen MX-Eintrag auf der Website Ihres DNS-Hosts sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:
    
   - **Eintragstyp**: **MX**
    
   - **Priorität**: Setzen Sie die Priorität des MX-Eintrags auf den höchsten verfügbaren Wert. Dies ist in der Regel **0**.
    
      Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)
    
   - **Hostname**: **@**
    
   - **Verweisende Adresse**: Fügen Sie den Wert für **verweisende Adresse** ein, den Sie soeben aus Microsoft 365 kopiert haben. 
    
   - **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. 
    
7. Speichern Sie den Eintrag.
    
Entfernen Sie alle anderen MX-Einträge.
  
Wenn Sie über MX-Einträge für diese Domäne verfügen, mit denen E-Mails an einen anderen Ort als Microsoft 365 gesendet werden, löschen Sie diese.
  
## <a name="add-three-cname-records"></a>Hinzufügen von drei CNAME-Einträgen
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Führen Sie die nachstehenden Schritte aus, um die drei für Microsoft 365 erforderlichen CNAME-Einträge hinzuzufügen. Wenn in Microsoft 365 zusätzliche CNAME-Einträge aufgeführt sind, fügen Sie diese anhand der selben hier angegebenen allgemeinen Schritte hinzu.
  
Erstellen Sie auf der Website Ihres DNS-Hosts nacheinander drei neue CNAME-Einträge.
  
1. Geben Sie in den Feldern für jeden neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen. Nachdem Sie die ersten drei neuen Einträge hinzugefügt haben, geben Sie an, dass Sie einen weiteren CNAME-Eintrag erstellen möchten.
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
      |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hour  <br/> |
      |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 hour  <br/> |
      |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 Stunde  <br/> |
   
   > [!NOTE]
   > **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. > Diese Datensätze gelten nicht für hybride Bereitstellungen von Exchange, Lync oder Skype for Business. 
  
2. Wenn Sie fertig sind, speichern Sie die Einträge.
    
::: moniker-end
::: moniker range="o365-germany"

Führen Sie die nachstehenden Schritte aus, um die drei für Microsoft 365 erforderlichen CNAME-Einträge hinzuzufügen. Wenn in Microsoft 365 zusätzliche CNAME-Einträge aufgeführt sind, fügen Sie diese anhand der selben hier angegebenen allgemeinen Schritte hinzu.
  
Erstellen Sie auf der Website Ihres DNS-Hosts nacheinander drei neue CNAME-Einträge.
  
1. Geben Sie in den Feldern für jeden neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen. Nachdem Sie die ersten drei neuen Einträge hinzugefügt haben, geben Sie an, dass Sie einen weiteren CNAME-Eintrag erstellen möchten.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 Stunde  <br/> |
   
     > [!NOTE]
     > **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. > Diese Datensätze gelten nicht für hybride Bereitstellungen von Exchange, Lync oder Skype for Business. 
  
2. Wenn Sie fertig sind, speichern Sie die Einträge.
    
::: moniker-end

::: moniker range="o365-21vianet"

Führen Sie die nachstehenden Schritte aus, um die drei für Microsoft 365 erforderlichen CNAME-Einträge hinzuzufügen. Wenn in Microsoft 365 zusätzliche CNAME-Einträge aufgeführt sind, fügen Sie diese anhand der selben hier angegebenen allgemeinen Schritte hinzu.
  
Erstellen Sie auf der Website Ihres DNS-Hosts nacheinander drei neue CNAME-Einträge.
  
1. Geben Sie in den Feldern für jeden neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen. Nachdem Sie die ersten drei neuen Einträge hinzugefügt haben, geben Sie an, dass Sie einen weiteren CNAME-Eintrag erstellen möchten.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.partner.outlook.cn  <br/> |1 Stunde  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 Stunde  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 Stunde  <br/> |
   
     > [!NOTE]
     > **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. > Diese Datensätze gelten nicht für hybride Bereitstellungen von Exchange, Lync oder Skype for Business. 
  
2. Wenn Sie fertig sind, speichern Sie die Einträge.
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft-365"></a>Hinzufügen von zwei CNAME-Einträgen für MDM (Mobile Device Management) für Microsoft 365
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Wenn Sie über MDM (Mobile Device Management) für Microsoft 365 verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen. Folgen Sie den Schritten für die anderen vier CNAME-Einträge, geben Sie jedoch die Werte aus der nachstehenden Tabelle ein. > (Wenn Sie nicht mit MDM arbeiten, können Sie diesen Schritt überspringen.) 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
   |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hour  <br/> |
   |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 Stunde  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Wenn Sie über MDM (Mobile Device Management) für Microsoft 365 verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen. Folgen Sie den Schritten für die anderen vier CNAME-Einträge, geben Sie jedoch die Werte aus der nachstehenden Tabelle ein. > (Wenn Sie nicht mit MDM arbeiten, können Sie diesen Schritt überspringen.) 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
   |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 hour  <br/> |
   |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Stunde  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen, sondern fügen Sie die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.
  
Bearbeiten Sie auf der Website Ihres DNS-Hosts den vorhandenen SPF-Eintrag, oder erstellen Sie einen neuen TXT-Eintrag für SPF.
  
> [!IMPORTANT]
> SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann. Zum Schutz vor diesen Techniken sollten Sie, nachdem Sie SPF eingerichtet haben, auch DKIM und DMARC für Microsoft 365 konfigurieren. Um hiermit zu beginnen, lesen Sie [Verwenden von DKIM zur Überprüfung von ausgehenden E-Mails, die von Ihrer Domäne aus in Microsoft 365 gesendet wurden](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Lesen Sie danach [Verwenden von DMARC zur Überprüfung von E-Mails in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Geben Sie in den Feldern für den neuen Eintrag die nachstehenden auf Ihre Situation zutreffenden Werte ein. Sie können diese Werte auch kopieren und einfügen.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Record Type** <br/> |**Host** <br/> |**TXT VALUE** <br/> |**TTL** <br/> |
    |TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |1 Stunde  <br/> |
   
    Für **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. 
    
2. Wenn Sie fertig sind, speichern Sie den Eintrag.
    
3. Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) verwenden.

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen, sondern fügen Sie die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. 
  
Bearbeiten Sie auf der Website Ihres DNS-Hosts den vorhandenen SPF-Eintrag, oder erstellen Sie einen neuen TXT-Eintrag für SPF.
  
> [!IMPORTANT]
> SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann. Zum Schutz vor diesen Techniken sollten Sie, nachdem Sie SPF eingerichtet haben, auch DKIM und DMARC für Microsoft 365 konfigurieren. Um hiermit zu beginnen, lesen Sie [Verwenden von DKIM zur Überprüfung von ausgehenden E-Mails, die von Ihrer Domäne aus in Microsoft 365 gesendet wurden](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Lesen Sie danach [Verwenden von DMARC zur Überprüfung von E-Mails in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Geben Sie in den Feldern für den neuen Eintrag die nachstehenden auf Ihre Situation zutreffenden Werte ein. Sie können diese Werte auch kopieren und einfügen.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Record Type**|**Host**|**TXT VALUE**|**TTL**|
    |TXT (Text)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |1 Stunde|
   
    Für **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. 
    
2. Wenn Sie fertig sind, speichern Sie den Eintrag.
    
3. Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) verwenden.
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen, sondern fügen Sie die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. 
  
Bearbeiten Sie auf der Website Ihres DNS-Hosts den vorhandenen SPF-Eintrag, oder erstellen Sie einen neuen TXT-Eintrag für SPF.
  
> [!IMPORTANT]
> SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann. Zum Schutz vor diesen Techniken sollten Sie, nachdem Sie SPF eingerichtet haben, auch DKIM und DMARC für Microsoft 365 konfigurieren. Um hiermit zu beginnen, lesen Sie [Verwenden von DKIM zur Überprüfung von ausgehenden E-Mails, die von Ihrer Domäne aus in Microsoft 365 gesendet wurden](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Lesen Sie danach [Verwenden von DMARC zur Überprüfung von E-Mails in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Geben Sie in den Feldern für den neuen Eintrag die nachstehenden auf Ihre Situation zutreffenden Werte ein. Sie können diese Werte auch kopieren und einfügen.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Record Type**|**Host**|**TXT VALUE**|**TTL**|
    |TXT (Text)|@|v=spf1 include:spf.protection.partner.outlook.cn -all > [!NOTE] > Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |1 Stunde|
   
    Für **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. 
    
2. Wenn Sie fertig sind, speichern Sie den Eintrag.
    
3. Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) verwenden.
    
::: moniker-end

## <a name="add-two-srv-records"></a>Hinzufügen von zwei SRV-Einträgen
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Erstellen Sie auf der Website Ihres DNS-Hosts nacheinander zwei neue SRV-Einträge. Dies bedeutet, dass Sie nach dem Hinzufügen des ersten Eintrags auf der Website angeben, dass Sie einen weiteren SRV-Eintrag erstellen möchten.
  
1. Geben Sie in den Feldern für jeden neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen. **(In den Anmerkungen unten wird erläutert, wie Sie die SRV-Einträge erstellen, wenn Ihr DNS-Host nicht über separate Felder alle diese Einträge verfügt.)**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Record Type** <br/> |**Name** <br/> |**Target** <br/> |**Protocol** <br/> |**Service** <br/> |**Priority** <br/> |**Weight** <br/> |**Port** <br/> |**TTL** <br/> |
    |SRV (Dienst)  <br/> |@  <br/> (Oder leer lassen, wenn @ nicht zulässig ist)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hour  <br/> |
    |SRV (Dienst)  <br/> |@  <br/> (Oder leer lassen, wenn @ nicht zulässig ist)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 Stunde  <br/> |
   
    > [!NOTE]
    >  Für **Name**: Wenn Ihr DNS-Host die Einstellung auf **@** nicht zulässt, lassen Sie das Feld leer. Verwenden Sie diesen Ansatz *nur*, wenn Ihr DNS-Host über separate Felder für die Werte "Service" und "Protocol" verfügt. Andernfalls lesen Sie die Anmerkungen unten zu "Service" und "Protocol". 
    > 
    >  Für **Service** und **Protocol**: Wenn Ihr DNS-Host nicht über diese Felder für SRV-Einträge verfügt, müssen Sie die Werte für **Service** und **Protocol** als Werte für **Name** des Eintrags angeben. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Name** auch anders heißen, z. B: **Host**, **Hostname** oder **Subdomäne**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge und trennen die Werte durch einen Punkt.  Beispiel: **Name**: _sip._tls 
    > 
    >  Für **Priority**, **Weight** und **Port**: Wenn Ihr DNS-Host nicht über diese Felder für SRV-Einträge verfügt, müssen Sie sie als Wert für **Target** des Eintrags angeben. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Target** auch anders heißen, z. B: **Inhalt**, **IP-Adresse** oder **Zielhost**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge, trennen die Werte durch Leerzeichen und enden mit einem Punkt. Die Werte müssen in dieser Reihenfolge eingegeben werden: "Priority", "Weight", "Port", "Target". Beispiel: **Target**: 100 1 443 sipdir.online.lync.com. 
    > 
    >  Variation für **Priority**, **Weight** und **Port**: Bei einigen DNS-Hosts werden einige, jedoch nicht alle der erforderlichen Felder separat aufgeführt. Geben Sie bei solchen DNS-Hostwebsites die Werte, die nicht in getrennten Feldern eingegeben werden können, als kombinierte Zeichenfolge in der richtigen Reihenfolge als Wert für **Target** des Eintrags an. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Target** auch anders heißen, z. B: **Inhalt**, **IP-Adresse** oder **Zielhost**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge für Felder, die nicht separat angezeigt werden, und trennen die Werte durch Leerzeichen. Die Werte müssen in der *nachfolgenden Reihenfolge* eingegeben werden, wobei die Werte ausgelassen werden für die es separate Felder gibt: "Priority", "Weight", "Port", "Target". Wenn es beispielsweise ein separates Feld für "Priority" gibt, verketten Sie nur die Werte für "Weight", "Port" und "Target": **Target**: 1 443 sipdir.online.lync.com 
    > 
    > Für **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. 
  
2. Wenn Sie fertig sind, speichern Sie die Einträge.
    
    > [!NOTE]
    >  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-germany"

Erstellen Sie auf der Website Ihres DNS-Hosts nacheinander zwei neue SRV-Einträge. Dies bedeutet, dass Sie nach dem Hinzufügen des ersten Eintrags auf der Website angeben, dass Sie einen weiteren SRV-Eintrag erstellen möchten.
  
1. Geben Sie in den Feldern für jeden neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen. **(In den Anmerkungen unten wird erläutert, wie Sie die SRV-Einträge erstellen, wenn Ihr DNS-Host nicht über separate Felder alle diese Einträge verfügt.)**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Record Type** <br/> |**Name** <br/> |**Target** <br/> |**Protocol** <br/> |**Service** <br/> |**Priority** <br/> |**Weight** <br/> |**Port** <br/> |**TTL** <br/> |
    |SRV (Dienst)  <br/> |@  <br/> (Oder leer lassen, wenn @ nicht zulässig ist)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hour  <br/> |
    |SRV (Dienst)  <br/> |@  <br/> (Oder leer lassen, wenn @ nicht zulässig ist)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 Stunde  <br/> |
   
    > [!NOTE]
    >  Für **Name**: Wenn Ihr DNS-Host die Einstellung auf **@** nicht zulässt, lassen Sie das Feld leer. Verwenden Sie diesen Ansatz *nur*, wenn Ihr DNS-Host über separate Felder für die Werte "Service" und "Protocol" verfügt. Andernfalls lesen Sie die Anmerkungen unten zu "Service" und "Protocol". 
    > 
    >  Für **Service** und **Protocol**: Wenn Ihr DNS-Host nicht über diese Felder für SRV-Einträge verfügt, müssen Sie die Werte für **Service** und **Protocol** als Werte für **Name** des Eintrags angeben. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Name** auch anders heißen, z. B: **Host**, **Hostname** oder **Subdomäne**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge und trennen die Werte durch einen Punkt. > Beispiel: **Name**: _sip._tls 
    > 
    >  Für **Priority**, **Weight** und **Port**: Wenn Ihr DNS-Host nicht über diese Felder für SRV-Einträge verfügt, müssen Sie sie als Wert für **Target** des Eintrags angeben. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Target** auch anders heißen, z. B: **Inhalt**, **IP-Adresse** oder **Zielhost**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge, trennen die Werte durch Leerzeichen und enden mit einem Punkt. Die Werte müssen in dieser Reihenfolge eingegeben werden: "Priority", "Weight", "Port", "Target". > Beispiel: **Target**: 100 1 443 sipdir.online.lync.de. 
    > 
    >  Variation für **Priority**, **Weight** und **Port**: Bei einigen DNS-Hosts werden einige, jedoch nicht alle der erforderlichen Felder separat aufgeführt. Geben Sie bei solchen DNS-Hostwebsites die Werte, die nicht in getrennten Feldern eingegeben werden können, als kombinierte Zeichenfolge in der richtigen Reihenfolge als Wert für **Target** des Eintrags an. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Target** auch anders heißen, z. B: **Inhalt**, **IP-Adresse** oder **Zielhost**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge für Felder, die nicht separat angezeigt werden, und trennen die Werte durch Leerzeichen. Die Werte müssen in der *nachfolgenden Reihenfolge* eingegeben werden, wobei die Werte ausgelassen werden für die es separate Felder gibt: "Priority", "Weight", "Port", "Target". > Wenn es beispielsweise ein separates Feld für "Priority" gibt, verketten Sie nur die Werte für "Weight", "Port" und "Target": **Target**: 1 443 sipdir.online.lync.de 
    > 
    >  Für **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. 
  
2. Wenn Sie fertig sind, speichern Sie die Einträge.
    
    > [!NOTE]
    >  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-21vianet"

Erstellen Sie auf der Website Ihres DNS-Hosts nacheinander zwei neue SRV-Einträge. Dies bedeutet, dass Sie nach dem Hinzufügen des ersten Eintrags auf der Website angeben, dass Sie einen weiteren SRV-Eintrag erstellen möchten.
  
1. Geben Sie in den Feldern für jeden neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen. **(In den Anmerkungen unten wird erläutert, wie Sie die SRV-Einträge erstellen, wenn Ihr DNS-Host nicht über separate Felder alle diese Einträge verfügt.)**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Record Type** <br/> |**Name** <br/> |**Target** <br/> |**Protocol** <br/> |**Service** <br/> |**Priority** <br/> |**Weight** <br/> |**Port** <br/> |**TTL** <br/> |
    |SRV (Dienst)  <br/> |@  <br/> (Oder leer lassen, wenn @ nicht zulässig ist)  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hour  <br/> |
    |SRV (Dienst)  <br/> |@  <br/> (Oder leer lassen, wenn @ nicht zulässig ist)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 Stunde  <br/> |
   
    > [!NOTE]
    >  Für **Name**: Wenn Ihr DNS-Host die Einstellung auf **@** nicht zulässt, lassen Sie das Feld leer. Verwenden Sie diesen Ansatz *nur*, wenn Ihr DNS-Host über separate Felder für die Werte "Service" und "Protocol" verfügt. Andernfalls lesen Sie die Anmerkungen unten zu "Service" und "Protocol". 
    > 
    >  Für **Service** und **Protocol**: Wenn Ihr DNS-Host nicht über diese Felder für SRV-Einträge verfügt, müssen Sie die Werte für **Service** und **Protocol** als Werte für **Name** des Eintrags angeben. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Name** auch anders heißen, z. B: **Host**, **Hostname** oder **Subdomäne**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge und trennen die Werte durch einen Punkt. > Beispiel: **Name**: _sip._tls 
    > 
    >  Für **Priority**, **Weight** und **Port**: Wenn Ihr DNS-Host nicht über diese Felder für SRV-Einträge verfügt, müssen Sie sie als Wert für **Target** des Eintrags angeben. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Target** auch anders heißen, z. B: **Inhalt**, **IP-Adresse** oder **Zielhost**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge, trennen die Werte durch Leerzeichen und enden mit einem Punkt. Die Werte müssen in dieser Reihenfolge eingegeben werden: "Priority", "Weight", "Port", "Target". > Beispiel: **Target**: 100 1 443 sipdir.online.partner.lync.cn. 
    > 
    >  Variation für **Priority**, **Weight** und **Port**: Bei einigen DNS-Hosts werden einige, jedoch nicht alle der erforderlichen Felder separat aufgeführt. Geben Sie bei solchen DNS-Hostwebsites die Werte, die nicht in getrennten Feldern eingegeben werden können, als kombinierte Zeichenfolge in der richtigen Reihenfolge als Wert für **Target** des Eintrags an. (Hinweis: Abhängig von Ihrem DNS-Host kann das Feld **Target** auch anders heißen, z. B: **Inhalt**, **IP-Adresse** oder **Zielhost**). Zum Einrichten des kombinierten Werts erstellen Sie eine einzelne Zeichenfolge für Felder, die nicht separat angezeigt werden, und trennen die Werte durch Leerzeichen. Die Werte müssen in der *nachfolgenden Reihenfolge* eingegeben werden, wobei die Werte ausgelassen werden für die es separate Felder gibt: "Priority", "Weight", "Port", "Target". > Wenn es beispielsweise ein separates Feld für "Priority" gibt, verketten Sie nur die Werte für "Weight", "Port" und "Target": **Target**: 1 443 sipdir.online.partner.lync.cn 
    > 
    >  Für **TTL**: Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten (**60**), Sekunden (**3600**) usw. fest. 
  
2. Wenn Sie fertig sind, speichern Sie die Einträge.
    
    > [!NOTE]
    >  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>Weitere Informationen zum Aktualisieren von DNS-Einträgen
<a name="BKMK_MoreAbout"> </a>

 **Wenn Sie wissen, wie DNS-Einträge beim DNS-Host Ihrer Domäne aktualisiert werden**, verwenden Sie die DNS-Werte von Microsoft 365, um die Einträge beim DNS-Host Ihrer Domäne zu bearbeiten, also beispielsweise, um einen MX- oder SPF-Eintrag einzurichten. Die zu verwendenden Werte finden Sie, indem Sie [diesen Schritten folgen](../get-help-with-domains/information-for-dns-records.md) oder den Assistenten zum Einrichten von Domänen verwenden, der Sie schrittweise durch das Verfahren führt.
  
 **Wenn Sie Hilfe beim Hinzufügen der erforderlichen DNS-Einträge benötigen**, lesen Sie [Einrichten Ihrer Domäne (hostspezifische Anweisungen)](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide), und [sammeln Sie zunächst die erforderlichen Informationen zum Erstellen von DNS-Einträgen für Microsoft 365](../get-help-with-domains/information-for-dns-records.md). Führen Sie dann die allgemeinen Schritte in diesem Artikel aus, um Ihre DNS-Einträge Ihrer Domäne einzurichten, um diese in Verbindung mit Microsoft 365-Diensten wie E-Mail verwenden zu können.
  
 **Wenn Sie nicht über eine Website verfügen, die Sie in Verbindung mit Ihrer benutzerdefinierten Domäne verwenden**, können Sie Microsoft 365 nutzen, um DNS-Einträge für Ihre Domäne einzurichten und zu verwalten, anstatt die Einrichtung selbst vorzunehmen. Hier finden Sie weitere Informationen zu den [zwei Optionen zum Einrichten und Verwalten von DNS-Einträgen für eine benutzerdefinierte Domäne](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) in Microsoft 365. 
  

