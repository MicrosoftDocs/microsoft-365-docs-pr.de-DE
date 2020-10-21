---
title: Erstellen von DNS-Einträgen für Microsoft mit Windows-basiertem DNS
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Hier erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Windows-basiertem DNS für Microsoft einrichten.
ms.openlocfilehash: 471aa0323bd59b09c672431ef39bb33f5c89b555
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645575"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Erstellen von DNS-Einträgen für Microsoft mit Windows-basiertem DNS

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
   
Wenn Sie Ihre eigenen DNS-Einträge mit Windows-basiertem DNS hosten, führen Sie die in diesem Artikel aufgeführten Schritte aus, um die Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Um zu beginnen, müssen Sie [Ihre DNS-Einträge in Windows-basiertem DNS Suchen](#find-your-dns-records-in-windows-based-dns) , damit Sie diese aktualisieren können. Wenn Sie beabsichtigen, Ihre lokale Active Directory mit Microsoft zu synchronisieren, finden Sie weitere Informationen unter [nicht routingfähige e-Mail-Adresse, die als UPN in Ihrem Active Directory auf dem Prem verwendet wird](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Probleme mit dem Nachrichtenfluss oder anderen Problemen nach dem Hinzufügen von DNS-Einträgen finden Sie unter [Problembehandlung bei Problemen nach dem Ändern des Domänennamens oder der DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Suche nach Ihren DNS-Einträgen in einem Windows-basierten DNS
<a name="BKMK_find_your_dns_1"> </a> Wechseln Sie zu der Seite mit den DNS-Einträgen für Ihre Domäne. Wenn Sie in Windows Server 2008 arbeiten, wechseln Sie zu **Start**  >  **Ausführen**. Wenn Sie in Windows Server 2012 arbeiten, drücken Sie die Windows-Taste und **r**. Geben Sie **dnsmgmnt. msc**ein, und wählen Sie dann **OK**aus. Erweitern Sie im DNS-Manager den Knoten ** \<DNS server name\> \> Forward-Lookupzonen  **. Wählen Sie Ihre Domäne aus. Jetzt können Sie die DNS-Einträge erstellen.
   
## <a name="add-mx-record"></a>Hinzufügen eines MX-Eintrags
<a name="BKMK_add_MX"> </a>

Fügen Sie einen MX-Eintrag hinzu, damit e-Mails für Ihre Domäne an Microsoft gesendet werden.
- Der MX-Eintrag, den Sie hinzufügen, enthält einen Wert (den **Punkt auf den Adress** Wert), der etwa wie folgt aussieht: \<MX token\> . Mail.Protection.Outlook.com, wobei \<MX token\> ein Wert wie MSxxxxxxx ist. 
- Kopieren Sie in der Zeile MX im Abschnitt Exchange Online der Seite hinzufügen von DNS-Einträgen in Microsoft den Wert Unterpunkte in Adresse aufgeführt. Sie verwenden diesen Wert in dem Eintrag, den Sie im Rahmen dieser Aufgabe erstellen. 
- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion**  >  **Mail Exchanger (MX)**. Informationen zur Suche dieser Seite für die Domäne finden Sie unter [Suchen nach DNS-Einträgen in Windows-basiertem DNS](#find-your-dns-records-in-windows-based-dns).  
- Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind: 
    - Hostname:  
    - @Address: Fügen Sie hier den Punkt-zu-Adresse-Wert ein, den Sie soeben von Microsoft kopiert haben.  
    - Präferenz 
- Wählen Sie **Save Changes**aus.
- Entfernen Sie veraltete MX-Einträge. Wenn Sie über eine alte MX-Einträge für diese Domäne verfügen, die e-Mails an eine andere Stelle weiterleiten, aktivieren Sie das Kontrollkästchen neben jedem alten Datensatz, und wählen Sie dann **Löschen**  >  **OK**aus. 
   
## <a name="add-cname-records"></a>Hinzufügen von CNAME-Einträgen
<a name="BKMK_add_CNAME"> </a>

Fügen Sie die für Microsoft erforderlichen CNAME-Einträge hinzu. Wenn zusätzliche CNAME-Einträge in Microsoft aufgeführt werden, fügen Sie die folgenden allgemeinen Schritte wie hier beschrieben hinzu.
  
> [!IMPORTANT]
> Wenn Sie über die Mobile Geräteverwaltung (MDM) für Microsoft verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (Wenn Sie nicht über MDM verfügen, können Sie diesen Schritt überspringen.) 

- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion**  >  **CNAME (CNAME)**.
- Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    - Hostname: AutoErmittlung
    - Typ: 
    - Cnameadresse: autodiscover.Outlook.com
- Wählen Sie **O**K aus.

Hinzufügen des CNAME-Eintrags für SIP 
- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion** \> **CNAME (CNAME)**. 
- Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    - Hostname: SIP
    - Typ: CNAME
    - Adresse: sipdir.online.lync.com
- Wählen Sie **OK** aus.

Hinzufügen des CNAME-Eintrags für Skype for Business Online-AutoErmittlung  
- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion** \> **CNAME (CNAME)**. Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    - Hostname: lyncdiscover
    - Typ: CNAME
    - Adresse: WebDir.online.lync.com
- Wählen Sie **OK** aus.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Hinzufügen von zwei CNAME-Einträgen für die Mobile Geräteverwaltung (Mobile Device Management, MDM) für Microsoft

> [!IMPORTANT]
> Wenn Sie über die Mobile Geräteverwaltung (MDM) für Microsoft verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (wenn Sie nicht über MDM verfügen, können Sie diesen Schritt überspringen.) 
  

Hinzufügen des CNAME-Eintrags für MDM-Enterpriseregistration  
- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion** \> **CNAME (CNAME)**. 
- Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
- Hostname: enterpriseregistration
- Typ: CNAME
- Adresse: enterpriseregistration.Windows.net
- Wählen Sie **OK** aus. 

Hinzufügen des CNAME-Eintrags für MDM-Enterpriseenrollment 
-  Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion** \> **CNAME (CNAME)**. 
-  Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    - Hostname: enterpriseenrollment
    - Typ: CNAME
    - Adresse: enterpriseenrollment-s.Manage.Microsoft.com
- Wählen Sie **OK** aus.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen  *einzelnen*  SPF-Eintrag haben, der beide Wertegruppen enthält. 
  
Fügen Sie den SPF TXT-Eintrag für Ihre Domäne hinzu, um E-Mail-Spam zu verhindern.
  
- Es sind möglicherweise bereits andere Zeichenfolgen im TXT-Wert für diesen Eintrag enthalten (z. B. Zeichenfolgen für Marketing-E-Mail). Das ist vollkommen in Ordnung. Behalten Sie diese Zeichenfolgen bei, und fügen Sie die folgende hinzu, wobei Sie die einzelnen Zeichenfolgen in doppelte Anführungszeichen setzen, um sie voneinander zu trennen. 
- Wechseln Sie auf der Seite "DNS-Manager" für Ihre Domäne zu **Aktions** \> **Text (txt)**. 
-  Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind. 
 > [!IMPORTANT]
> In einigen Versionen von Windows DNS Manager ist die Domäne möglicherweise so eingerichtet, dass beim Erstellen eines txt-Eintrags standardmäßig der Name Home auf die übergeordnete Domäne festgelegt wird. Legen Sie in diesem Fall beim Hinzufügen eines TXT-Eintrags den Hostnamen als leer (kein Wert) und nicht auf "@" oder den Domänennamen fest. 

-  Hosttyp: @
-  Record Type: txt
-  Adresse: v = spf1 include:SPF. Protection. Outlook. com-all 
         
-  Wählen Sie **OK** aus.
   
## <a name="add-srv-records"></a>Hinzufügen von SRV-Einträgen
<a name="BKMK_add_SRV"> </a>

Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.

Hinzufügen des SIP SRV-Eintrags für Skype for Business Online-Webkonferenzen  <br/> 
-  Wechseln Sie auf der Seite "DNS-Manager" für Ihre Domäne zu **Aktion** \> **Weitere neue Einträge**. 
-   Wählen Sie im Fenster **Ressourceneintragstyp** die Option **Dienststandort (SRV)** aus, und wählen Sie dann **Datensatz erstellen**aus. 
-   Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    -  Dienst: _sip
    -  Protokoll: _tls
    -  Priority (Priorität): 100
    -  Weight (Gewichtung): 1
    -  Port: 443
    -  Ziel (Hostname): sipdir.online.lync.com
-  Wählen Sie **OK** aus. 


Hinzufügen des SIP SRV-Eintrags für den Skype for Business Online-Partnerverbund  
-  Wechseln Sie auf der Seite "DNS-Manager" für Ihre Domäne zu **Aktion** \> **Weitere neue Einträge**.  
-  Wählen Sie im Fenster **Ressourceneintragstyp** die Option **Dienststandort (SRV)** aus, und wählen Sie dann **Datensatz erstellen**aus. 
-   Stellen Sie im Dialogfeld **neuen Ressourceneintrag** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    -  Dienst: _sipfederationtls
    -  Protokoll: _tcp
    -  Priority (Priorität): 100
    -  Weight (Gewichtung): 1
    -  Port: 5061
    -  Ziel (Hostname): sipfed.online.lync.com
-  Wählen Sie **OK** aus. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Hinzufügen eines Eintrags zum Überprüfen des Domänenbesitzes, sofern das noch nicht geschehen ist
<a name="BKMK_verify"> </a>

Bevor Sie die DNS-Einträge zum Einrichten Ihrer Microsoft-Dienste hinzufügen, muss Microsoft bestätigen, dass Sie der Besitzer der Domäne sind, die Sie hinzufügen. Dazu fügen Sie einen Eintrag anhand der nachfolgenden Schritte hinzu.
  
> [!NOTE]
> Dieser Eintrag dient nur zum Überprüfen, dass Sie der Besitzer Ihrer Domäne sind; er wirkt sich auf nichts anderes aus. 
  

1. Sammeln von Informationen von Microsoft.  <br/> 
2. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>. 
3. Wählen Sie auf der Seite **Domänen** in der Spalte **Aktionen** für die Domäne, die Sie überprüfen möchten, **Setup starten**aus. 
4. Wählen Sie auf der Seite **Domäne zu Microsoft hinzufügen** die Option **Schritt 1 starten**aus. 
5. Wählen Sie auf der Seite **bestätigen, dass Sie Ihre Domäne besitzen** im **Abschnitt Anweisungen zum Ausführen dieses Schritts mit** der Dropdownliste die Option **Allgemeine Anweisungen**aus. 
6. Kopieren Sie in der Tabelle den Wert unter Ziel oder verweisende Adresse. Sie benötigen ihn für den nächsten Schritt. Es wird empfohlen, diesen Wert zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.

Hinzufügen eines TXT-Eintrags 
-  Wechseln Sie auf der Seite "DNS-Manager" für Ihre Domäne zu **Aktions** \> **Text (txt)**. 
-   Wählen Sie im Dialogfeld **neuer Ressourceneintrag** die Option **Bearbeiten**aus.  
-  Stellen Sie im Dialogfeld **neuer Ressourceneintrag** im Bereich **Benutzerdefinierte Host Namen** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind. 

> [!IMPORTANT] 
> In einigen Versionen von Windows DNS Manager ist die Domäne möglicherweise so eingerichtet, dass beim Erstellen eines txt-Eintrags standardmäßig der Name Home auf die übergeordnete Domäne festgelegt wird. Legen Sie in diesem Fall beim Hinzufügen eines TXT-Eintrags den Hostnamen als leer (kein Wert) und nicht auf "@" oder den Domänennamen fest. 

- Hostname: @
- Typ: txt
- Address: Fügen Sie den Ziel-oder Punkt-zu-Adresse-Wert ein, den Sie hier soeben von Microsoft kopiert haben.  
- Wählen Sie **OK**  >  **Fertig**aus.

Überprüfen Sie Ihre Domäne in Microsoft.  
> [!IMPORTANT]
> Warten Sie etwa 15 Minuten, bevor Sie dies tun, sodass der soeben erstellte Eintrag über das Internet aktualisiert werden kann.       

- Gehen Sie zurück zu Microsoft, und führen Sie die folgenden Schritte aus, um eine Überprüfungs Überprüfung anzufordern. Bei der Überprüfung wird nach dem TXT-Eintrag gesucht, den Sie im vorherigen Schritt hinzugefügt haben. Wenn der richtige TXT-Eintrag gefunden wird, ist die Domäne überprüft.  
1. Wechseln Sie im Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .
2. Wählen Sie auf der Seite **Domänen** in der Spalte **Aktion** für die Domäne, die Sie überprüfen möchten, **Setup starten**aus. 
3. Wählen Sie auf der Seite **bestätigen, dass Sie Ihre Domäne besitzen** die Option **fertig, jetzt überprüfen**aus, und wählen Sie dann im Dialogfeld Bestätigung die Option **Fertig stellen**aus. 
   
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Nicht routbare E-Mail-Adresse, die als UPN in Ihrem lokalen Active Directory verwendet wird
<a name="BKMK_ADNote"> </a>

Wenn Sie beabsichtigen, Ihre lokale Active Directory mit Microsoft zu synchronisieren, sollten Sie sicherstellen, dass das UPN-Suffix (Active Directory User Principal Name) ein gültiges Domänensuffix und kein nicht unterstütztes Domänensuffix wie @contoso. local ist. Wenn Sie das UPN-Suffix ändern müssen, finden Sie weitere Informationen unter [Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
