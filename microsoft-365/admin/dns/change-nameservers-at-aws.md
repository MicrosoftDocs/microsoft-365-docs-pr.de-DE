---
title: Ändern von Namenservern zum Einrichten von Office 365 bei Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Erfahren Sie, wie Sie Office 365 einrichten können, um Ihre DNS-Einträge bei Amazon Webdienste (AWS) zu verwalten. '
ms.openlocfilehash: a7125cf0add8200fe152c426f47e7f27a8f6226c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212353"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a>Ändern von Namenservern zum Einrichten von Office 365 bei Amazon Web Services (AWS)

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Führen Sie die folgenden Anweisungen aus, wenn Office 365 Ihre Office 365-DNS-Einträge automatisch verwalten soll. (Wenn es Ihnen lieber ist, können Sie [alle Ihre Office 365-DNS-Einträge bei AWS selbst verwalten](create-dns-records-at-aws.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung

Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.
    
3. Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten. 
    
4. Wählen Sie **Daten Satz Satz erstellen**aus.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Typ** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
|(Lassen Sie dieses Feld leer)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Simple <br/> |
   
6. Wählen Sie **Erstellen** aus.
    
7. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.
  
Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändern der Namenservereinträge (NS) Ihrer Domäne

Zum Abschluss der Einrichtung Ihrer Domäne in Office 365 ändern Sie die NS-Einträge bei Ihrer Domänenregistrierungsstelle so, dass sie auf die primären und sekundären Office 365-Namenserver verweisen. Dadurch wird Office 365 zum Aktualisieren der DNS-Einträge der Domäne eingerichtet. Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.
  
> [!CAUTION]
> Wenn Sie die Namenservereinträge Ihrer Domäne so ändern, dass sie auf die Office 365-Namenserver verweisen, hat dies Auswirkungen auf alle Dienste, die aktuell mit Ihrer Domäne verbunden sind. So gehen beispielsweise alle an Ihre Domäne (z. B. an Bernd@ *Ihre_Domäne*  .com) gesendeten E-Mail-Nachrichten bei Office 365 ein, nachdem Sie diese Änderung vorgenommen haben. 
  
> [!IMPORTANT]
>  Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind. > Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: > ns1.BDM.microsoftonline.com > ns2.BDM.microsoftonline.com > NS3.BDM.microsoftonline.com > NS4.BDM.microsoftonline.com 
  
1. Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.
    
3. Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten. 
    
4. Wählen Sie den **Namenserver**-Eintragssatz aus. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard. 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (Das heißt, löschen Sie nur aktuelle Namenserver, die *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.) 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. Wählen Sie in der **Gültigkeitsdauer (Sekunden):** **1H** (1 Stunde) aus. 
    
    ![Wählen Sie 1H für eine Stunde aus.](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. Geben Sie, weiterhin im Eintragssatz **NS - Name server**, in das Feld **Value** den Wert aus der **ersten Zeile** der folgenden Tabelle direkt oder durch Kopieren und Einfügen ein, drücken Sie dann die **EINGABETASTE**, und geben Sie den Wert der nächsten **Zeile** direkt oder durch Kopieren und Einfügen ein. 
    
    > [!IMPORTANT]
    > Jeder Namenserverwert  *muss*  in seiner eigenen separaten Zeile im Feld **Value** stehen (siehe folgende Abbildung). 
  
|||
|:-----|:-----|
|**Erste Zeile** <br/> |ns1.BDM.microsoftonline.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
|**Zweite Zeile** <br/> |ns2.BDM.microsoftonline.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
|**Dritte Zeile** <br/> |NS3.BDM.microsoftonline.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
|**Vierte Zeile** <br/> |NS4.BDM.microsoftonline.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
   
   ![Geben Sie den Wert der ersten Textreihe in das Feld Wert ein oder fügen Sie ihn ein.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. Wählen Sie **Speichersatz speichern**aus.
    
    ![Daten Satz Satz speichern auswählen](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet. 
