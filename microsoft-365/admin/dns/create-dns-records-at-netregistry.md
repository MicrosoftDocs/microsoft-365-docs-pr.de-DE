---
title: Erstellen von DNS-Einträgen bei Netregistry für Office 365
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei Netregistry für Office 365 einrichten.
ms.openlocfilehash: e1f2414817357b8435bc002860a35c6e76d4314e
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211134"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a>Erstellen von DNS-Einträgen bei Netregistry für Office 365

[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn Netregistry Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Das sind die wichtigsten hinzuzufügenden Einträge.
  
- [Hinzufügen eines TXT-Eintrags zur Überprüfung](#add-a-txt-record-for-verification)
    
- [Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Office 365 geleitet werden](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [Hinzufügen der für Office 365 erforderlichen CNAME-Einträge](#add-the-cname-records-that-are-required-for-office-365)
    
- [Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Hinzufügen der zwei für Office 365 erforderlichen SRV-Einträge](#add-the-two-srv-records-that-are-required-for-office-365)
    
Nachdem Sie diese Einträge bei Netregistry hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365 Diensten eingerichtet.
  
Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="bkmk_txt"> </a>

Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. Wählen Sie **Zone Manager** aus.
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **TXT-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > Sie müssen vor und nach dem Eintrag im Feld txt Anführungszeichen setzen. 
  
    Geben Sie im Formular **New TXT Record** (Neuer TXT-Eintrag) die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**Name**|**TTL (SEC)**|**TXT (Verweist auf die Adresse oder den Wert)**|
    |:-----|:-----|:-----|
    |(leer lassen)  <br/> |3600 (Sekunden)  <br/> |"MS = msXXXXXXXX"  <br/> **Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. Wählen Sie **Add Record**aus.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.
  
Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
    
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
    
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden
<a name="bkmk_mx"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. Wählen Sie **Zone Manager** aus.
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. Entfernen Sie unter **aktuelle Zoneneinträge**die standardmäßigen MX-Einträge, indem Sie neben jedem MX-Eintrag in der Liste **Entfernen** auswählen. 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **MX-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. Geben Sie im **neuen MX-Eintrags** Formular die Werte aus der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein. 
    
    |**Name**|**TTL (SEC)**|**Exchange (verweist auf Adresse oder Wert)**|**Ist der Host vollständig qualifiziert?**|**Präferenz (Priorität)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(leer lassen)  <br/> |3600 (Sekunden)  <br/> | *\<Domänenschlüssel\>*  .mail.protection.outlook.com  <br/> **Hinweis:** Rufen Sie Ihren * \<Domänenschlüssel\> * aus Ihrem Office 365-Konto ab.  [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)      |(aktivieren Sie das Kontrollkästchen)  <br/> |10    <br/> Weitere Informationen zur Priorität finden Sie unter Was ist MX-Priorität?  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. Wählen Sie **Add Record** (Eintrag hinzufügen) aus.
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen CNAME-Einträge
<a name="bkmk_cname"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. Wählen Sie **Zone Manager** aus.
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **CNAME-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    |**Name**|**Typ**|**TTL**|**Host (Punkt-zu-oder Adresswert)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. Wählen Sie **Add Record**aus.
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen.
    
    Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. If you already have an SPF record for your domain, don't create a new one for Office 365. Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. Wählen Sie **Zone Manager** aus.
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **TXT-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    > [!NOTE]
    > Sie müssen vor und nach dem Eintrag im Feld txt Anführungszeichen setzen. 
  
    |**Name**|**Typ**|**TTL**|**TXT-Daten (Ziel)**|
    |:-----|:-----|:-----|:-----|
    |(leer lassen)  <br/> |TXT  <br/> |3600 (Sekunden)  <br/> |"v = spf1 include:SPF. Protection. Outlook. com-all"  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. Wählen Sie **Add Record** (Eintrag hinzufügen) aus.
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge
<a name="bkmk_srv"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. Wählen Sie neben der Domäne, die Sie verwalten möchten, die Option **Manage**aus.
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. Wählen Sie **Zone Manager** aus.
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **SRV-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    > [!NOTE]
    > Das Feld Name ist eine Kombination aus dem Dienst (beispielsweise _sip) und dem Protokoll (beispielsweise _tls). 
  
    |**Typ**|**Name**|**TTL (SEC)**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Dienst)  <br/> |_sip._tls  <br/> |3600 (Sekunden)  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV (Dienst)  <br/> |_sipfederationtls._tcp  <br/> |3600 (Sekunden)  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. Wählen Sie **Add Record** (Eintrag hinzufügen) aus.
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. Wiederholen Sie die vorherigen Schritte, um den anderen SRV-Eintrag zu erstellen.
    
    Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  

