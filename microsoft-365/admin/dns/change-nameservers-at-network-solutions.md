---
title: Ändern von Namenservern zum Einrichten von Microsoft mit Netzwerklösungen
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Erfahren Sie, wie Sie Ihre benutzerdefinierte Microsoft-Domäne mit Netzwerklösungen einrichten, wenn Microsoft Ihre DNS-Einträge verwalten soll. '
ms.openlocfilehash: 502699cf3760460a13ee067b07737037f31fa4ee
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079877"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a>Ändern von Namenservern zum Einrichten von Microsoft mit Netzwerklösungen

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.
  
Befolgen Sie diese Anweisungen, wenn Microsoft Ihre DNS-Einträge für Sie verwalten soll. (Wenn es Ihnen lieber ist, können Sie [alle Ihre Microsoft-DNS-Einträge bei Netzwerklösungen verwalten](create-dns-records-at-network-solutions.md).)
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a>Hinzufügen eines TXT-Eintrags bei Network Solutions, um zu überprüfen, ob Sie der Besitzer der Domäne sind

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions. Sie werden aufgefordert, sich anzumelden.
    
    > [!IMPORTANT]
    > Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus.
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Wählen Sie **DNS bearbeiten**aus.
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scrollen Sie nach unten zum Abschnitt **Text (TXT Records)** , und wählen Sie dann **TXT-Einträge bearbeiten**aus.
    
    ![Bearbeiten von TXT-Einträgen auswählen](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
|**Host**|**TTL**|**Text**|
|:-----|:-----|:-----|
|@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Eingeben oder Einfügen von Werten in die Felder für den neuen Datensatz](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Wählen Sie **Save Changes**aus.
    
    ![Wählen Sie Save Changes aus.](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
    
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
    
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändern der Namenservereinträge (NS) Ihrer Domäne

Um die Einrichtung Ihrer Domäne bei Microsoft abzuschließen, ändern Sie die NS-Einträge Ihrer Domäne bei Ihrer Domänenregistrierungsstelle so, dass Sie auf den primären und sekundären Namenserver von Microsoft verweist. Dadurch wird Microsoft so eingerichtet, dass die DNS-Einträge der Domäne für Sie aktualisiert werden. Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.
  
> [!CAUTION]
> Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Microsoft Name-Server verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind. Beispielsweise werden alle e-Mails, die an Ihre Domäne gesendet werden (wie Rob@ *your_domain* . com), nach dem Ausführen dieser Änderung an Microsoft weitergeleitet.
  
Möchten Sie Ihre NS-Einträge so ändern, dass Microsoft Ihre Domäne einrichten kann? Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).
  
> [!IMPORTANT]
>  Wenn *Sie die Schritte* in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**und **NS4.BDM.microsoftonline.com**. Im folgenden Verfahren wird gezeigt, wie Sie andere, unerwünschte Namenserver aus der Liste löschen können, und Sie erfahren, wie Sie die  *richtigen*  Namenserver hinzufügen, wenn sie sich nicht bereits in der Liste befinden. 
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions. Sie werden aufgefordert, sich anzumelden.
    
    > [!IMPORTANT]
    > Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus. 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Wählen Sie **DNS bearbeiten**aus.
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Wählen Sie **DNS migrieren**aus.
    
    ![NetworkSolutionsBP-redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. Abhängig davon, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, setzen Sie den Vorgang mit einem der beiden folgenden Verfahren fort:
    
  - Wenn noch **KEINE** Namenserver aufgelistet sind, [Wenn noch KEINE Namenserver aufgelistet sind](#if-there-are-no-nameservers-already-listed).
    
  - Wenn **BEREITS** Namenserver aufgelistet sind, [Wenn Namenserver BEREITS aufgelistet sind](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Wenn noch KEINE Namenserver aufgelistet sind

1. Wählen Sie auf der Seite **Domains** im Abschnitt **Domain Name Servers angeben** die Option **Weitere Namenserver hinzufügen**aus.
    
    ![NetworkSolutionsBP-redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. Geben Sie Nameserver-Werte aus der folgenden Tabelle auf der Seite **Domain Names** ein. Sie können die Werte auch kopieren und einfügen. 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. Wählen Sie **DNS migrieren**aus.
    
    ![NetworkSolutionsBP-redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. Wählen Sie **Save Changes**aus.
    
    ![NetworkSolutionsBP-redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Wenn Namenserver BEREITS aufgelistet sind

> [!CAUTION]
> Folgen Sie diesen Schritten  *nur*  , wenn es andere Namenserver als die vier  *korrekten*  Namenserver gibt. (Das heißt, löschen Sie  *nur*  andere als die vier korrekten Namenserver, also  *nicht* **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** oder **ns4.bdm.microsoftonline.com**.
  
1. If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.
    
    ![NetworkSolutions-BP-redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. Wählen Sie **Weitere Namenserver hinzufügen**aus.
    
    ![NetworkSolutionsBP-redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. Geben Sie Nameserver-Werte aus der folgenden Tabelle auf der Seite **Domain Names** ein. Sie können die Werte auch kopieren und einfügen. 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. Wählen Sie **DNS migrieren**aus.
    
    ![NetworkSolutionsBP-redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. Wählen Sie **Save Changes aus.**
    
    ![NetworkSolutionsBP-redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.
