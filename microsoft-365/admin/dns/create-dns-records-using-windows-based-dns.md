---
title: Erstellen von DNS-Einträgen für Microsoft mithilfe von Windows-basiertem DNS
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste unter Windows-basiertem DNS für Microsoft einrichten.
ms.openlocfilehash: 9e5e42f847e740571944ea3db205282ec9a7a0e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916046"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Erstellen von DNS-Einträgen für Microsoft mithilfe von Windows-basiertem DNS

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
   
Wenn Sie Ihre eigenen DNS-Einträge mit Windows-basiertem DNS hosten, führen Sie die in diesem Artikel aufgeführten Schritte aus, um die Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Für die ersten Schritte müssen Sie Ihre [DNS-Einträge in Windows-basiertem DNS suchen,](#find-your-dns-records-in-windows-based-dns) damit Sie sie aktualisieren können. Wenn Sie planen, Ihr lokales Active Directory mit Microsoft zu synchronisieren, finden Sie weitere Informationen unter [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Probleme mit dem Nachrichtenfluss oder anderen Problemen nach dem Hinzufügen von DNS-Einträgen finden Sie unter Problembehandlung nach dem Ändern Ihres [Domänennamens oder Ihrer DNS-Einträge.](../get-help-with-domains/find-and-fix-issues.md) 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Suche nach Ihren DNS-Einträgen in einem Windows-basierten DNS
<a name="BKMK_find_your_dns_1"></a> Wechseln Sie zu der Seite mit den DNS-Einträgen für Ihre Domäne. Wenn Sie in Windows Server 2008 arbeiten, wechseln Sie zu **Start**  >  **Run**. Wenn Sie in der Windows Server 2012, drücken Sie die Windows-TASTE und **r**. Geben **Sie dnsmgmnt.msc ein,** und wählen Sie dann **OK aus.** Erweitern Sie im DNS-Manager **\<DNS server name\> \> die Erweiterung Forward Lookup Zones**. Wählen Sie Ihre Domäne aus. Jetzt können Sie die DNS-Einträge erstellen.
   
## <a name="add-mx-record"></a>Hinzufügen eines MX-Eintrags
<a name="BKMK_add_MX"> </a>

Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft gesendet werden.
- Der hinzugefügte MX-Eintrag enthält einen Wert (den **Wert Points to address),** der etwa wie dies aussieht: .mail.protection.outlook.com, wobei ein Wert wie \<MX token\> \<MX token\> MSxxxxxxx ist. 
- Kopieren Sie aus der Zeile MX im Abschnitt Exchange Online auf der Seite DNS-Einträge hinzufügen in Microsoft den unter Points to address aufgeführten Wert. Sie verwenden diesen Wert in dem Eintrag, den Sie im Rahmen dieser Aufgabe erstellen. 
- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Action**  >  **Mail Exchanger (MX)**. Informationen zu dieser Seite für die Domäne finden Sie unter [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).  
- Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind: 
    - Hostname:  
    - @Address: Fügen Sie hier den Wert Points to address ein, den Sie gerade von Microsoft kopiert haben.  
    - Pref: 
- Wählen **Sie Änderungen speichern aus.**
- Entfernen Sie veraltete MX-Einträge. Wenn Sie über alte MX-Einträge für diese Domäne verfügen, die E-Mails an einen anderen Ort weiterrouten, aktivieren Sie das Kontrollkästchen neben jedem alten Datensatz, und wählen Sie **dann Ok**  >  **löschen aus.** 
   
## <a name="add-cname-records"></a>Hinzufügen von CNAME-Einträgen
<a name="BKMK_add_CNAME"> </a>

Fügen Sie die CNAME-Datensätze hinzu, die für Microsoft erforderlich sind. Wenn zusätzliche #A0 in Microsoft aufgeführt sind, fügen Sie diese nach den hier gezeigten allgemeinen Schritten hinzu.
  
> [!IMPORTANT]
> Wenn Sie über MDM (Mobile Device Management) für Microsoft verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen. Folgen Sie den Schritten für die anderen vier CNAME-Einträge, geben Sie jedoch die Werte aus der nachstehenden Tabelle ein. (Wenn Sie nicht mit MDM arbeiten, können Sie diesen Schritt überspringen.) 

- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion**  >  **CNAME (CNAME)**.
- Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    - Hostname: autoErmittlung
    - Typ: 
    - CNAMEAddress: autodiscover.outlook.com
- Wählen **Sie O** K aus.

Hinzufügen des CNAME-Eintrags für SIP 
- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion** \> **CNAME (CNAME)**. 
- Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    - Hostname: sip
    - Typ: CNAME
    - Adresse: sipdir.online.lync.com
- Wählen Sie **OK** aus.

Hinzufügen des CNAME-Eintrags für Skype for Business Online-AutoErmittlung  
- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion** \> **CNAME (CNAME)**. Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    - Hostname: lyncdiscover
    - Typ: CNAME
    - Adresse: webdir.online.lync.com
- Wählen Sie **OK** aus.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Hinzufügen von zwei #A0 für mobile Geräteverwaltung (Mobile Device Management, MDM) für Microsoft

> [!IMPORTANT]
> Wenn Sie über MDM (Mobile Device Management) für Microsoft verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen. Folgen Sie den Schritten für die anderen vier CNAME-Einträge, geben Sie jedoch die Werte aus der nachstehenden Tabelle ein. >(Wenn Sie nicht über MDM verfügen, können Sie diesen Schritt überspringen.) 
  

Hinzufügen des CNAME-Eintrags für MDM-Enterpriseregistration  
- Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion** \> **CNAME (CNAME)**. 
- Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
- Hostname: enterpriseregistration
- Typ: CNAME
- Adresse: enterpriseregistration.windows.net
- Wählen Sie **OK** aus. 

Hinzufügen des CNAME-Eintrags für MDM-Enterpriseenrollment 
-  Wechseln Sie auf der Seite DNS-Manager für die Domäne zu **Aktion** \> **CNAME (CNAME)**. 
-  Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    - Hostname: enterpriseenrollment
    - Typ: CNAME
    - Adresse: enterpriseenrollment-s.manage.microsoft.com
- Wählen Sie **OK** aus.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. 
  
Fügen Sie den SPF TXT-Eintrag für Ihre Domäne hinzu, um E-Mail-Spam zu verhindern.
  
- Es sind möglicherweise bereits andere Zeichenfolgen im TXT-Wert für diesen Eintrag enthalten (z. B. Zeichenfolgen für Marketing-E-Mail). Das ist vollkommen in Ordnung. Behalten Sie diese Zeichenfolgen bei, und fügen Sie die folgende hinzu, wobei Sie die einzelnen Zeichenfolgen in doppelte Anführungszeichen setzen, um sie voneinander zu trennen. 
- Wechseln Sie auf der Seite DNS-Manager für Ihre Domäne zu  \> **Aktionstext (TXT).** 
-  Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder genau auf die folgenden Werte festgelegt sind. 
 > [!IMPORTANT]
> In einigen Versionen von Windows DNS Manager wurde die Domäne möglicherweise so eingerichtet, dass beim Erstellen eines txt-Eintrags der Startname standardmäßig auf die übergeordnete Domäne festgelegt ist. Legen Sie in diesem Fall beim Hinzufügen eines TXT-Eintrags den Hostnamen als leer (kein Wert) und nicht auf "@" oder den Domänennamen fest. 

-  Hosttyp: @
-  Datensatztyp: TXT
-  Adresse: v=spf1 include:spf.protection.outlook.com -all 
         
-  Wählen Sie **OK** aus.
   
## <a name="add-srv-records"></a>Hinzufügen von SRV-Einträgen
<a name="BKMK_add_SRV"> </a>

Fügen Sie die beiden für Microsoft erforderlichen SRV-Einträge hinzu.

Hinzufügen des SIP SRV-Eintrags für Skype for Business Online-Webkonferenzen  <br/> 
-  Wechseln Sie auf der Seite DNS-Manager für Ihre Domäne zu **Action** \> **Other New Records**. 
-   Wählen Sie **im** Fenster Ressourcendatensatztyp die Option **Dienstspeicherort (SRV)** aus, und wählen Sie dann **Datensatz erstellen aus.** 
-   Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    -  Dienst: _sip
    -  Protokoll: _tls
    -  Priority (Priorität): 100
    -  Weight (Gewichtung): 1
    -  Port: 443
    -  Ziel (Hostname): sipdir.online.lync.com
-  Wählen Sie **OK** aus. 


Hinzufügen des SIP SRV-Eintrags für den Skype for Business Online-Partnerverbund  
-  Wechseln Sie auf der Seite DNS-Manager für Ihre Domäne zu **Action** \> **Other New Records**.  
-  Wählen Sie **im** Fenster Ressourcendatensatztyp die Option **Dienstspeicherort (SRV)** aus, und wählen Sie dann **Datensatz erstellen aus.** 
-   Stellen Sie im Dialogfeld Neuer **Ressourcendatensatz** sicher, dass die Felder auf genau die folgenden Werte festgelegt sind:  
    -  Dienst: _sipfederationtls
    -  Protokoll: _tcp
    -  Priority (Priorität): 100
    -  Weight (Gewichtung): 1
    -  Port: 5061
    -  Target (Hostname): sipfed.online.lync.com
-  Wählen Sie **OK** aus. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Hinzufügen eines Eintrags zum Überprüfen des Domänenbesitzes, sofern das noch nicht geschehen ist
<a name="BKMK_verify"> </a>

Bevor Sie die DNS-Einträge zum Einrichten Ihrer Microsoft-Dienste hinzufügen, muss Microsoft bestätigen, dass Sie DerEnt der Domäne sind, die Sie hinzufügen. Dazu fügen Sie einen Eintrag anhand der nachfolgenden Schritte hinzu.
  
> [!NOTE]
> Dieser Eintrag dient nur zum Überprüfen, dass Sie der Besitzer Ihrer Domäne sind; er wirkt sich auf nichts anderes aus. 
  

1. Sammeln von Informationen von Microsoft.  <br/> 
2. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>. 
3. Wählen Sie **auf der** Seite Domänen in der Spalte **Aktionen** für die domäne, die Sie überprüfen, Setup **starten aus.** 
4. Wählen Sie **auf der Seite Domäne zu Microsoft** hinzufügen schritt **1 aus.** 
5. Wählen Sie **auf der** Seite Bestätigen,  dass Sie Ihre Domäne besitzen, in der Dropdownliste Siehe Anweisungen zum Ausführen dieses Schritts mit der Dropdownliste **Allgemeine Anweisungen aus.** 
6. Kopieren Sie in der Tabelle den Wert unter Ziel oder verweisende Adresse. Sie benötigen ihn für den nächsten Schritt. Es wird empfohlen, diesen Wert zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.

Hinzufügen eines TXT-Eintrags 
-  Wechseln Sie auf der Seite DNS-Manager für Ihre Domäne zu  \> **Aktionstext (TXT).** 
-   Wählen Sie **im Dialogfeld Neuer Ressourcendatensatz** bearbeiten **aus.**  
-  Stellen Sie im Bereich  Benutzerdefinierte **Hostnamen** des Dialogfelds Neuer Ressourcendatensatz sicher, dass die Felder genau auf die folgenden Werte festgelegt sind. 

> [!IMPORTANT] 
> In einigen Versionen von Windows DNS Manager wurde die Domäne möglicherweise so eingerichtet, dass beim Erstellen eines txt-Eintrags der Startname standardmäßig auf die übergeordnete Domäne festgelegt ist. Legen Sie in diesem Fall beim Hinzufügen eines TXT-Eintrags den Hostnamen als leer (kein Wert) und nicht auf "@" oder den Domänennamen fest. 

- Hostname: @
- Typ: TXT
- Adresse: Fügen Sie hier den Wert Destination oder Points to Address ein, den Sie gerade von Microsoft kopiert haben.  
- Wählen Sie **OK**  >  **Fertig aus.**

Überprüfen Sie Ihre Domäne in Microsoft.  
> [!IMPORTANT]
> Warten Sie ungefähr 15 Minuten, bevor Sie dies tun, damit der gerade erstellte Datensatz über das Internet aktualisiert werden kann.       

- Wechseln Sie zurück zu Microsoft, und führen Sie die folgenden Schritte aus, um eine Überprüfung an zu fordern. Bei der Überprüfung wird nach dem TXT-Eintrag gesucht, den Sie im vorherigen Schritt hinzugefügt haben. Wenn der richtige TXT-Eintrag gefunden wird, ist die Domäne überprüft.  
1. Wechseln Sie im Admin  Center zur Seite \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setupdomänen.</a>
2. Wählen Sie **auf der** Seite Domänen in der **Spalte Aktion** für die Domäne, die Sie überprüfen, Setup **starten aus.** 
3. Wählen Sie **auf** der Seite Bestätigen, dass Sie Ihre Domäne besitzen die Option Fertig **aus,** überprüfen Sie jetzt , und wählen Sie dann im Bestätigungsdialogfeld **Fertig stellen aus.** 
   
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Nicht routbare E-Mail-Adresse, die als UPN in Ihrem lokalen Active Directory verwendet wird
<a name="BKMK_ADNote"> </a>

Wenn Sie planen, Ihr lokales Active Directory mit Microsoft zu synchronisieren, sollten Sie sicherstellen, dass das UpN-Suffix (Active Directory User Principal Name) ein gültiges Domänensuffix und kein nicht unterstütztes Domänensuffix wie @contoso.local ist. Wenn Sie Ihr UPN-Suffix ändern müssen, lesen Sie So bereiten Sie eine nicht routingfähige Domäne für [die Verzeichnissynchronisierung vor.](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
