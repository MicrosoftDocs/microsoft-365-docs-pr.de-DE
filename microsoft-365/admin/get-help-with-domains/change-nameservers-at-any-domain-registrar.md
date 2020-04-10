---
title: Ändern von Namenservern zum Einrichten von Office 365 bei einer beliebigen Domänenregistrierungsstelle
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Hier erfahren Sie, wie Sie Ihre Domäne in Office 365 hinzufügen und einrichten, sodass Ihre Dienste wie e-Mail und Skype for Business Online ihren eigenen Domänennamen verwenden.
ms.custom: okr_smb
ms.openlocfilehash: 838025002443ec35787ea91775c60d3829545af4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210492"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a>Ändern von Namenservern zum Einrichten von Office 365 bei einer beliebigen Domänenregistrierungsstelle

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Aktivieren Sie zuerst die Informationen zum [Einrichten Ihrer Domäne (hostspezifische Anweisungen)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) , um zu sehen, ob wir Anweisungen für Ihre Registrierungsstelle haben. 
  
Befolgen Sie diese Anleitungen, um Ihre Domäne in Office 365 hinzuzufügen und so einzurichten, dass Ihre Dienste wie E-Mail und Skype for Business Online Ihren eigenen Domänennamen verwenden. Hierzu überprüfen Sie Ihre Domäne und ändern dann deren Namenserver zu Office 365, damit die richtigen DNS-Einträge für Sie eingerichtet werden können. Führen Sie die folgenden Schritte aus, wenn die folgende Anweisung Ihre Situation beschreibt:
  
- Sie verfügen über eine eigene Domäne und möchten diese in Verbindung mit Office 365 einrichten.
    
- Sie möchten, dass Office 365 Ihre DNS-Einträge für Sie verwaltet. (Wenn Sie es Ihnen lieber ist, können Sie [Ihre eigenen DNS-Einträge verwalten](../setup/add-domain.md).)
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Hinzufügen eines TXT- oder MX-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

> [!NOTE]
> Sie müssen nur einen der beiden Einträge erstellen. TXT ist der bevorzugte Eintragstyp, jedoch wird er von einigen DNS-Hostinganbietern nicht unterstützt. In diesem Fall können Sie stattdessen einen MX-Datensatz erstellen. 
  
Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Suchen Sie den Bereich auf der Website Ihres DNS-Host Anbieters, auf dem Sie einen neuen Datensatz erstellen können.

1. Melden Sie sich bei der Website Ihres DNS-Hostinganbieters an.
    
2.  Wählen Sie Ihre Domäne aus.
    
3. Suchen Sie die Seite, auf der Sie DNS-Datensätze für Ihre Domäne bearbeiten können.
    
### <a name="create-the-record"></a>Erstellen des Datensatzes

Je nachdem, ob Sie einen TXT-Eintrag oder einen MX-Eintrag erstellen möchten, führen Sie einen der folgenden Schritte aus:
  
**Wenn Sie einen TXT-Eintrag erstellen, verwenden Sie die folgenden Werte:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type ** <br/> |**Alias** oder **Hostname** <br/> |**Wert** <br/> |**TTL** <br/> |
|TXT  <br/> |Führen Sie eine der folgenden Aktionen aus: Geben Sie **@** ein, lassen Sie das Feld leer, oder geben Sie Ihren Domänennamen ein.    <br/> > [!NOTE]> Die Anforderungen für dieses Feld sind je nach DNS-Host unterschiedlich.           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest.  <br/> |
   
**Wenn Sie einen MX-Eintrag erstellen, verwenden Sie die folgenden Werte:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type **|**Alias** oder **Hostname**|**Value**|**Priorität**|**TTL**|
|MX|Geben Sie **@** oder Ihren Domänennamen ein. |MS=ms *XXXXXXXX* > [!NOTE]> Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |Für **Priority** (Priorität) verwenden Sie eine geringere Priorität als für die bereits vorhandenen MX-Einträge, um Konflikte mit dem MX-Eintrag für den E-Mail-Verkehr zu vermeiden. Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.md#what-is-mx-priority) |Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest. |
   
### <a name="save-the-record"></a>Speichern des Datensatzes

Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.
  
Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.
  

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
 
    
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändern der Namenservereinträge (NS) Ihrer Domäne
<a name="BKMK_nameservers"> </a>

Als letzten Schritt im Domäneneinrichtungs-Assistenten in Office 365 müssen Sie nur noch eine einzige Aufgabe ausführen. Um Ihre Domäne mit Office 365-Diensten wie E-Mail einzurichten, ändern Sie die Namenservereinträge (oder NS) bei Ihrer Domänenregistrierungsstelle so, dass sie auf die primären und sekundären Office 365-Namenserver verweisen. Anschließend werden, weil Ihr DNS von Office 365 gehostet wird, die erforderlichen DNS-Einträge für Ihre Dienste automatisch für Sie eingerichtet. Sie können die Namenservereinträge selbst aktualisieren, indem Sie die Schritte ausführen, die Ihre Domänenregistrierungsstelle eventuell in den Hilfeinhalten auf ihrer Website bereitstellt. Wenn Sie mit DNS nicht vertraut sind, wenden Sie sich an den Support bei der Domänenregistrierungsstelle.

::: moniker range="o365-worldwide"
  
Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:
  
1. Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.
    
2. Erstellen Sie zwei Namenservereinträge, oder bearbeiten Sie die vorhandenen Namenservereinträge so, dass sie den folgenden Werten entsprechen:
    
|||
|:-----|:-----|
|Erster Namenserver  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Zweiter Namenserver  <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > Sie sollten mindestens zwei Nameserver-Einträge verwenden. Wenn andere Namenserver aufgelistet sind, können Sie Sie entweder löschen oder in **NS3.BDM.microsoftonline.com** und **NS4.BDM.microsoftonline.com**ändern. 
  
3. Speichern Sie Ihre Änderungen.
    
> [!CAUTION]
> Wenn Sie die NS-Einträge für Ihre Domäne so ändern, dass sie auf die Office 365-Namenserver verweisen, sind hiervon alle Dienste betroffen, die zu diesem Zeitpunkt mit Ihrer Domäne verbunden sind. Wenn Sie irgendeinen Schritt des Assistenten ausgelassen haben, z. B. das Hinzufügen von E-Mail-Adressen, oder die Domäne für Blogs, Onlinehandel oder andere Dienste verwenden, sind weitere Schritte erforderlich. Andernfalls könnte diese Änderung zu Dienstunterbrechungen führen wie kein Zugriff auf E-Mails oder eine nicht erreichbare Website. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.
    
2. Erstellen Sie zwei Namenservereinträge, oder bearbeiten Sie die vorhandenen Namenservereinträge so, dass sie den folgenden Werten entsprechen:
    
|||
|:-----|:-----|
|Erster Namenserver  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Zweiter Namenserver  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > Sie sollten mindestens zwei Nameserver-Einträge verwenden. Wenn andere Namenserver aufgelistet sind, können Sie Sie entweder löschen oder in **NS3.DNS.Partner.microsoftonline.cn** und **NS4.DNS.Partner.microsoftonline.cn**ändern. 
  
3. Speichern Sie Ihre Änderungen.
    
> [!CAUTION]
> Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Office 365, die von 21Vianet-Namenservern betrieben werden, hinweisen, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind. Wenn Sie alle Schritte des Assistenten übersprungen haben, beispielsweise das Hinzufügen von e-Mail-Adressen oder wenn Sie Ihre Domäne für Blogs, Einkaufswagen oder andere Dienste verwenden, sind zusätzliche Schritte erforderlich. Andernfalls kann diese Änderung zu Dienstunterbrechungen führen, beispielsweise bei fehlendem e-Mail-Zugriff oder beim Zugriff auf Ihre aktuelle Website. 

::: moniker-end
  
Hier einige weitere Schritte, die beispielsweise für E-Mail- und Websitehosting erforderlich sein können:
  
- Verschieben Sie alle E-Mail-Adressen, die Ihre Domäne verwenden, auf Office 365, bevor Sie die NS-Einträge ändern.
    
- Möchten Sie eine Domäne hinzufügen, die zurzeit mit einer Websiteadresse verwendet wird, beispielsweise "www.fourthcoffee.com"? Sie können die folgenden Schritte ausführen, während Sie die Domäne hinzufügen, damit die Website gehostet wird, in der die Website gehostet wird, damit Benutzer weiterhin auf die Website gelangen können, nachdem Sie die NS-Datensätze der Domäne so geändert haben, dass Sie auf Office 365 zeigen.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

3. Wählen Sie auf der Seite Domänen eine Domäne aus.

4. Wählen Sie unter **DNS-Einstellungen**die Option **Benutzerdefinierte Datensätze**aus, und wählen Sie dann **neuer benutzerdefinierter Datensatz**aus.

5. Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Datensatz ein.

6. Klicken Sie auf **Speichern**.
    
> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet. 
  

