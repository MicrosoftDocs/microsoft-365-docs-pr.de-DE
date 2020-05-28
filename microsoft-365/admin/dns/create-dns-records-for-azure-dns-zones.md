---
title: Erstellen von DNS-Einträgen für Azure-DNS-Zonen
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste in Azure-DNS-Zonen für Microsoft einrichten.
ms.openlocfilehash: fcc3ea42b7414cdd5fc0c34bfae91104287d2379
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400268"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>Erstellen von DNS-Einträgen für Azure-DNS-Zonen

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn Azure Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail, Skype for Business Online usw. einzurichten.
  
Das sind die wichtigsten hinzuzufügenden Einträge. 
  
- [Ändern der Namenservereinträge (NS) Ihrer Domäne](#change-your-domains-nameserver-ns-records)
    
- [Hinzufügen eines TXT-Eintrags zur Überprüfung](#add-a-txt-record-for-verification)

- [Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Hinzufügen der vier für Microsoft erforderlichen CNAME-Einträge](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nachdem Sie diese Einträge bei Azure hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändern der Namenservereinträge (NS) Ihrer Domäne
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben. 
  
Wenn Sie sich für Azure angemeldet haben, haben Sie eine Ressourcengruppe innerhalb einer DNS-Zone erstellt und anschließend Ihren Domänennamen dieser Ressourcengruppe zugewiesen. Dieser Domänenname ist für eine externe Domänenregistrierungsstelle registriert; Azure bietet keine Domänenregistrierungsdienste an.
  
Um DNS-Einträge für Ihre Domäne in Microsoft zu überprüfen und zu erstellen, müssen Sie zuerst die Namenserver bei Ihrer Domänenregistrierungsstelle ändern, damit Sie die Azure-Namenserver verwenden, die ihrer Ressourcengruppe zugewiesen sind.
  
Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:
  
1. Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.
    
2. Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen. Unten sehen Sie ein Beispiel für Azure zugewiesene Namenserver.
    


**Erster Nameserver:** Verwenden Sie den Namenserver Wert, der von Azure zugewiesen wird.  
**Zweiter Nameserver:** Verwenden Sie den Namenserver Wert, der von Azure zugewiesen wird.  

![Azure-BP-redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> You should use at least two name server records. Wenn auf der Website Ihrer Domänenregistrierungsstelle andere Namenserver aufgeführt sind, sollten Sie Sie löschen. 
  
3. Speichern Sie Ihre Änderungen.
    
> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt. 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure. Sie werden aufgefordert, sich zuerst anzumelden.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Geben Sie über die **Suchleiste** auf der **Dashboardseite** die Zeichen in **DNS-Zonen**ein. Wählen Sie in der Ergebnisanzeige **DNS-Zonen** unter dem Abschnitt **Dienste** aus. Nachdem Sie umgeleitet wurden, wählen Sie die Domäne aus, die Sie aktualisieren möchten.
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus. 
    
    (Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.) 
    
    |**Name**|**Type**|**TTL**|**TTL-Einheit**|**Wert**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1   <br/> |Stunden  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. Wählen Sie **OK** aus.
  
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
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

1. Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure. Sie werden aufgefordert, sich zuerst anzumelden.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten. 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus. 
    
    (Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.) 
    
    |**Name**|**Type**|**TTL**|**TTL-Einheit**|**Preference**|**E-Mail-Austausch**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1   <br/> |Stunden  <br/> |10    <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*. Mail.Protection.Outlook.com  <br/> **Hinweis:** Holen Sie sich Ihr *\<domain-key\>* Microsoft-Konto.   [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. Wählen Sie **OK** aus.
    
    ![Azure-BP-configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. Wenn im Abschnitt **MX Records** weitere MX-Einträge aufgeführt sind, müssen Sie Sie löschen. 
    
    Wählen Sie zuerst im Bereich **DNS-Zone** den **MX-Eintragssatz**aus.
    
    ![Azure-BP-configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    Wählen Sie als nächstes den MX-Eintrag aus, den Sie löschen möchten.
    
    ![Azure-BP-configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. Wählen Sie das **Kontextmenü (...)** aus, und klicken Sie dann auf **Entfernen**.
    
    ![Azure-BP-configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. Wählen Sie **Speichern**.
    
    ![Azure-BP-configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der vier für Microsoft erforderlichen CNAME-Einträge
<a name="BKMK_add_CNAME"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure. Sie werden aufgefordert, sich zuerst anzumelden.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten. 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Fügen Sie den ersten der vier CNAME-Einträge hinzu.
    
    Geben Sie im Bereich Daten Satz Satz hinzufügen in den Feldern für den neuen Daten Satz Satz die Werte aus der ersten Zeile in der folgenden Tabelle ein, oder kopieren und fügen **Sie Sie** ein. 
    
    (Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.) 
    
    |**Name**|**Type**|**TTL**|**TTL-Einheit**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1   <br/> |Stunden  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |1   <br/> |Stunden  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1   <br/> |Stunden  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Azure-BP-configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. Wählen Sie **OK** aus.
    
    ![Azure-BP-configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. Fügen Sie die drei anderen CNAME-Einträge hinzu.
    
    Wählen Sie im Bereich **DNS-Zone** die Option **+ Record-Satz**aus. Erstellen Sie dann im leeren Daten Satz Satz einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **OK** aus, um den Datensatz abzuschließen. 
    
    Wiederholen Sie diesen Vorgang, bis Sie alle vier CNAME-Einträge erstellt haben.
    
7.  Optional Fügen Sie zwei CNAME-Einträge für MDM hinzu.

> [!IMPORTANT]
> Wenn Sie über die Mobile Geräteverwaltung (MDM) für Microsoft verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (Wenn Sie nicht über MDM verfügen, können Sie diesen Schritt überspringen.) 
  
|**Name**|**Type**|**TTL**|**TTL-Einheit**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |1   <br/> |Stunden  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |1   <br/> |Stunden  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält. 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure. Sie werden aufgefordert, sich zuerst anzumelden.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten. 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Wählen Sie im Bereich **DNS-Zone** den **txt-Eintragssatz**aus.
    
    ![Azure-BP-configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. Wählen Sie im Bereich **Eigenschaften von Datensatzgruppe** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus. 
    
    (Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.) 
    
    |**Name**|**Type**|**TTL**|**TTL-Einheit**|**Wert**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1   <br/> |Stunden  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           

    ![Azure-BP-configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. Wählen Sie **Speichern**.
    
    ![Azure-BP-configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure. Sie werden aufgefordert, sich zuerst anzumelden.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten. 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Fügen Sie den ersten der zwei SRV-Einträge hinzu.
    
    Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der ersten Zeile in der folgenden Tabelle aus. 
    
    (Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.) 
    
    |**Name**|**Type**|**TTL**|**TTL-Einheit**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |1   <br/> |Stunden  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |1   <br/> |Stunden  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Azure-BP-configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. Wählen Sie **OK** aus.
    
    ![Azure-BP-configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. Fügen Sie den anderen SRV-Eintrag hinzu.
    
    Geben Sie in den Feldern für den neuen Datensatz die Werte aus der zweiten Zeile der Tabelle ein, oder kopieren Sie Sie, und fügen Sie Sie ein.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
