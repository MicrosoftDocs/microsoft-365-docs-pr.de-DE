---
title: Ändern von Namenservern zum Einrichten von Office 365 bei Hostgator
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Erfahren Sie, wie Sie Office 365 einrichten können, um die DNS-Einträge Ihrer benutzerdefinierten Domäne bei Hostgator zu verwalten.
ms.openlocfilehash: f0d3b495285685c3f666560816f99b07a1a5f6d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242742"
---
# <a name="change-nameservers-to-set-up-office-365-with-hostgator"></a>Ändern von Namenservern zum Einrichten von Office 365 bei Hostgator

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.
  
Führen Sie die folgenden Anweisungen aus, wenn Office 365 Ihre Office 365-DNS-Einträge automatisch verwalten soll. (Wenn es Ihnen lieber ist, können Sie [alle Ihre Office 365-DNS-Einträge bei Hostgator verwalten](create-dns-records-at-hostgator.md).)
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Verweisen Sie Ihre Domäne auf Ihr Hostingkonto.

> [!IMPORTANT]
> Sie müssen dieses Verfahren ausführen, bevor Sie das Verfahren im folgenden Abschnitt, **Hinzufügen eines TXT-Eintrags zur Überprüfung** durchführen.
  
Führen Sie die folgenden Schritte aus, um Ihre Domäne und Hostingkonten zu verknüpfen.
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://portal.hostgator.com/domain/manage) zur Kundenportalseite bei Hostgator. Sie werden aufgefordert, sich anzumelden.
    
    ![Hostgator-BP-Redelegate-1-0](../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Wählen Sie die Registerkarte **Domänen** aus.
    
    ![Hostgator-BP-Redelegate-1-1](../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Wählen Sie auf der Seite " **Domänen verwalten** " im Bereich " **Meine Domänen** " die Domäne aus, die Sie aktualisieren möchten.
    
    ![Hostgator-BP-Redelegate-1-2](../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Wählen Sie auf der Seite **Domänenübersicht** im Bereich **Name Servers** die Option **Change**aus.
    
    ![Hostgator-BP-Redelegate-1-3](../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Wählen Sie auf der Seite **Namensserver** für Ihre Domäne in der Dropdownliste **Host Konto auswählen** das **Hostingkonto** aus, das Ihrer Domäne zugeordnet ist.
    
    ![Hostgator-BP-Redelegate-1-4](../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Wählen Sie **Namenserver speichern**aus.
    
    ![Hostgator-BP-Redelegate-1-9](../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung

> [!IMPORTANT]
> Bevor Sie dieses Verfahren ausführen, müssen Sie zuerst das Verfahren im ersten Abschnitt dieses Artikels ausführen, indem Sie [Ihre Domäne auf Ihr Hostingkonto hinweisen.](#point-your-domain-to-your-hosting-account).
  
Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.
  
1. Um zu beginnen, wechseln Sie zu Ihrer cPanel-Seite bei Hostgator. Sie werden aufgefordert, sich zuerst anzumelden.
    
    (Jedem gehosteten Konto bei Hostgator ist eine eindeutige cPanel-Adresse zugewiesen. Ihre cPanel-Adresse sollte wie folgt aussehen: https://YourSiteAddress:secure-port-number. Diese Adresse ist in der Anmelde-E-Mail, die Sie von Hostgator erhalten, angegeben.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Um mit Office 365 zu beginnen, können Sie entweder ein Hostingkonto von Hostgator kaufen oder [Ihre Namenservereinträge (NS) Ihrer Domäne so ändern](#change-your-domains-nameserver-ns-records) , dass Sie auf Office 365 verweist. 
  
2. Wählen Sie auf der Seite **Systemsteuerung** im Bereich **Domänen** die Option **Erweiterter DNS-Zonen-Editor**aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.) 
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
|Verwenden Sie Ihren  *Domänennamen*  (z. B. "fourthcoffee.com").  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Wählen Sie **Add Record** (Eintrag hinzufügen) aus.
    
5. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
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
> Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind. Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**und **NS4.BDM.microsoftonline.com**.
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://portal.hostgator.com/domain/manage) zur Kundenportalseite bei Hostgator. Sie werden aufgefordert, sich anzumelden.
    
    ![Hostgator-BP-Redelegate-1-0](../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Wählen Sie die Registerkarte **Domänen** aus. 
    
    ![Hostgator-BP-Redelegate-1-1](../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Wählen Sie auf der Seite " **Domänen verwalten** " im Bereich " **Meine Domänen** " die Domäne aus, die Sie aktualisieren möchten. 
    
    ![Hostgator-BP-Redelegate-1-2](../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Wählen Sie auf der Seite **Domain Overview** im Bereich **Name Servers** die Option **Change**aus.
    
    ![Hostgator-BP-Redelegate-1-3](../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Wählen Sie auf der Seite **Namensserver** für Ihre Domäne in der Dropdownliste **Host Konto auswählen** das **Hostingkonto** aus, das Ihrer Domäne zugeordnet ist. 
    
    ![Hostgator-BP-Redelegate-1-4](../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Wählen Sie " **meine Namenserver manuell festlegen**" aus.
    
    ![Hostgator-BP-Redelegate-1-5](../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **Vorsicht**: Befolgen Sie diese Schritte nur, wenn Sie andere Namenserver als die vier richtigen Namenserver haben. (Das heißt, löschen Sie nur aktuelle Namenserver, die *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.)
  
        Während Sie sich noch auf der Seite **Name Servers** für Ihre Domäne befinden, löschen Sie in der Liste der Nameserver jeden Nameserver in dieser Liste, indem Sie ihn auswählen und dann die **ENTF**-TASTE auf der Tastatur drücken. 
    
   ![Hostgator-BP-Redelegate-1-6](../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. Während Sie sich noch in der Liste der Nameserver befinden, geben Sie die beiden ersten Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
|||
|:-----|:-----|
|**Name Server 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2:** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator-BP-redelegate-1-7-1](../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Fügen Sie die anderen Namenserverwerte hinzu.
    
    Wählen Sie **(+)** hinzufügen aus, und geben Sie den Wert aus der nächsten Zeile der Tabelle in das Feld für den Datensatz ein, oder kopieren und fügen Sie ihn ein. 
    
    Wiederholen Sie diesen Vorgang, bis Sie alle vier Namenservereinträge erstellt haben.
    
    ![Hostgator-BP-Redelegate-1-7-2](../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Wählen Sie **Namenserver speichern**aus.
    
    ![Hostgator-BP-Redelegate-1-8](../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.