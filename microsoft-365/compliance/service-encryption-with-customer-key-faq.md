---
title: Häufig gestellte Fragen zur Dienstverschlüsselung mit Kundenschlüssel für Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: Zusätzlich zur standardmäßigen Verschlüsselung auf Volumen Ebene, die über BitLocker und den Distributed Key Manager (DKM) aktiviert ist, bietet Office 365 eine zusätzliche Verschlüsselungsebene auf Anwendungsebene für Kunden Inhalte in Office 365, einschließlich Daten aus Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen. Dies wird als Dienst Verschlüsselung bezeichnet.
ms.openlocfilehash: 0dbc3839d5dfda98460db70de667e2f469bc1291
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "38686176"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Häufig gestellte Fragen zur Dienstverschlüsselung mit Kundenschlüssel für Office 365

Zusätzlich zur standardmäßigen Verschlüsselung auf Volumen Ebene, die über BitLocker und den Distributed Key Manager (DKM) aktiviert ist, bietet Office 365 eine zusätzliche Verschlüsselungsebene auf Anwendungsebene für Kunden Inhalte in Office 365, einschließlich Daten aus Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen. Dies wird als Dienst Verschlüsselung bezeichnet.
  
Der Kundenschlüssel basiert auf der Dienst Verschlüsselung und ermöglicht es Ihnen, Schlüssel bereitzustellen und zu steuern, die zum Verschlüsseln der Daten in Rest in Office 365 verwendet werden, wie in den [Online Services Terms (Ost)](https://www.microsoft.com/Licensing/product-licensing/products.aspx)beschrieben. Mit dem Kundenschlüssel können Sie Auflagen erfüllen, da Sie die Verschlüsselungsschlüssel steuern, mit denen Office 365 die Daten entschlüsselt.
  
Um Feedback zum Kundenschlüssel bereitzustellen, einschließlich der Dokumentation, senden Sie Ihre Ideen, Vorschläge und Perspektiven an customerkeyfeedback@Microsoft.com.
  
## <a name="what-is-service-encryption-with-customer-key"></a>Was ist die Dienst Verschlüsselung mit dem Kundenschlüssel?

Kundenschlüssel verbessert die Fähigkeit Ihrer Organisation, die Anforderungen der Compliance-Anforderungen zu erfüllen, die wichtige Vereinbarungen mit dem Cloud-Dienstanbieter festlegen. Mit dem Kundenschlüssel stellen und Steuern Sie die Verschlüsselungsschlüssel für Ihre Office 365-Rest-Daten auf Anwendungsebene. Daher können Sie die Kontrolle übernehmen und die Schlüssel Ihrer Organisation widerrufen, wenn Sie sich entscheiden, den Dienst zu beenden. Durch das Aufheben der Schlüssel können die Daten für den Dienst unlesbar gemacht werden. Die Schlüssel Sperrung ist der erste Schritt auf dem Weg zum Löschen von Daten.

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>Welche Office 365 Daten im Ruhezustand werden über den Kundenschlüssel abgedeckt?
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

SharePoint Online Websiteinhalt und die auf dieser Website gespeicherten Dateien und Dateien, die in OneDrive für Unternehmen hochgeladen wurden, werden abgedeckt. Es werden Exchange Online Postfachinhalte (e-Mail-Text, Kalendereinträge und Inhalt von e-Mail-Anlagen) behandelt. Text Unterhaltungen von Skype for Business werden abgedeckt, aber Skype-Broadcast-Aufzeichnungen und Inhalts Uploads für Skype-Besprechungsinhalte werden nicht behandelt. Uploads von Skype-Besprechungs-und Skype-Besprechungsinhalten werden zusammen mit allen anderen Inhalten in Office 365 verschlüsselt, wir bieten jedoch derzeit keine Kunden Steuerung der Verschlüsselungsschlüssel an.
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>Was ist der Unterschied zwischen dem Kundenschlüssel und dem Holen Ihres eigenen Schlüssels (BYOK) mit Azure Information Protection für Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Mit beiden Optionen können Sie Ihre eigenen Verschlüsselungsschlüssel bereitstellen und steuern. die Dienst Verschlüsselung mit dem Kundenschlüssel verschlüsselt jedoch Ihre Daten im Ruhezustand und befindet sich in Office 365-Servern bei-Rest, während BYOK mit Azure Information Protection für Exchange Online Ihre Daten verschlüsselt und persistent Online und Offline bereitstellt. Schutz für e-Mail-Nachrichten und Anlagen für Office 365. Kundenschlüssel und BYOK mit Azure Information Protection für Exchange Online ergänzen sich, und unabhängig davon, ob Sie die Dienst verwalteten Schlüssel von Microsoft oder Ihre eigenen Schlüssel verwenden, können Sie durch Verschlüsseln Ihrer Daten – bei der Rest-und bei der Übertragung – einen zusätzlichen Schutz vor böswillige Angriffe.
  
BYOK mit Azure Information Protection für Exchange Online wird in den Office 365 Nachrichten Verschlüsselungsfunktionen angeboten.
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Verschlüsseln Office 365 Nachrichtenverschlüsselung und bringen Sie Ihren eigenen Schlüssel mit Azure Information Protection, ändern Sie den Microsoft-Ansatz für Datenanforderungen von Drittanbietern wie Vorladungen?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Nein. Office 365 Nachrichtenverschlüsselung und die Option zum Bereitstellen und Steuern ihrer eigenen Verschlüsselungsschlüssel mit "Holen Sie sich Ihren eigenen Schlüssel" (BYOK) für Azure Information Protection wurde nicht entwickelt, um auf Strafverfolgungs Vorladungen zu reagieren. Office 365 Nachrichtenverschlüsselung mit BYOK für AIP wurde für Compliance-orientierte Kunden entwickelt, die ihre internen oder externen Compliance-Verpflichtungen erfüllen müssen. Microsoft nimmt Anfragen von Drittanbietern für Kundendaten sehr ernst. Als Anbieter von Cloud-Diensten plädieren wir immer für den Schutz von Kundendaten. Für den Fall, dass wir eine Vorladung erhalten, versuchen wir immer, den dritten an den Kunden umzuleiten, um die Informationen zu erhalten. (Lesen Sie bitte Brad Smith es Blog: [Schützen von Kundendaten vor Regierungs snoopings](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Wir veröffentlichen regelmäßig detaillierte Informationen über die Anfrage, die wir [hier](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data)erhalten.
  
Weitere Informationen finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trustcenter/default.aspx) in Bezug auf Datenanforderungen von Drittanbietern und "Offenlegung von Kundendaten" in den [Online Dienstleistungsbedingungen (Ost) ](https://www.microsoft.com/Licensing/product-licensing/products.aspx).
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Ändert die Dienst Verschlüsselung mit dem Kundenschlüssel den Microsoft-Ansatz für Datenanforderungen von Drittanbietern wie beispielsweise Vorladungen?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Nein. Der Kundenschlüssel wurde nicht für die Reaktion auf Vorladungen der Strafverfolgungsbehörden entwickelt. Es wurde für regulierte Kunden entwickelt, um Ihre internen oder externen Compliance-Verpflichtungen zu erfüllen. Microsoft nimmt Anfragen von Drittanbietern für Kundendaten sehr ernst. Als Anbieter von Cloud-Diensten plädieren wir immer für den Schutz von Kundendaten. Für den Fall, dass wir eine Vorladung erhalten, versuchen wir immer, den dritten an den Kunden umzuleiten, um die Informationen zu erhalten. (Lesen Sie bitte Brad Smith es Blog: [Schützen von Kundendaten vor Regierungs snoopings](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Wir veröffentlichen regelmäßig detaillierte Informationen über die Anfrage, die wir [hier](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)erhalten.
  
Weitere Informationen finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) in Bezug auf Datenanforderungen von Drittanbietern und "Offenlegung von Kundendaten" in den [Online Dienstleistungsbedingungen (Ost)](https://www.microsoft.com/Licensing/product-licensing/products.aspx) . 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>Steht der Kurzhilfe-Support für die Implementierung des Kunden Schlüssels zur Verfügung?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Nein. Der kurzstand wird nur zum Erfassen von Mandanten-und Dienstkonfigurationsinformationen verwendet, die für die Registrierung für den Kundenschlüssel erforderlich sind. Die Kundenschlüssel Angebote werden über die Schnelligkeit veröffentlicht, sodass Kunden und Partner diese erforderlichen Informationen mit derselben Methode übermitteln und die Daten, die Kunden im Angebot bereitstellen, einfacher archivieren können.
  
Wenn Sie weitere Unterstützung über die Dokumentation hinaus benötigen, wenden Sie sich an Microsoft Consulting Services (MCS), Premier Field Engineering (pfe) oder an einen Microsoft-Partner, um Hilfe zu erhalten.
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>Wie kann ich wiederhergestellt werden, wenn meine Schlüssel zerstört wurden?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Der Verfügbarkeits Schlüssel bietet Ihnen die Möglichkeit, nach dem unerwarteten Verlust von Stamm Schlüsseln, die Sie verwalten, eine Wiederherstellung durchführen zu können. Wenn Sie die Stammschlüssel verloren haben, wenden Sie sich an den Microsoft-Support, und Microsoft unterstützt Sie dabei, den Verfügbarkeits Schlüssel zu aktivieren. Sie verwenden den Verfügbarkeits Schlüssel, um zu einer neuen Daten Verschlüsselungsrichtlinie mit neuen von Ihnen bereitgestellten Schlüsseln zu migrieren. 
  
## <a name="what-is-the-availability-key"></a>Was ist der Verfügbarkeits Schlüssel?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Der Verfügbarkeits Schlüssel ist ein Stammschlüssel, der bereitgestellt wird, wenn Sie eine Daten Verschlüsselungsrichtlinie erstellen. Der Verfügbarkeits Schlüssel wird in Office 365 gespeichert und geschützt und ist funktional vergleichbar mit den beiden Stamm Schlüsseln, die von Ihnen für die Verwendung mit der Dienst Verschlüsselung mit dem Kundenschlüssel bereitgestellt werden. Im Gegensatz zu den Schlüsseln, die Sie in Azure Key Vault bereitstellen und verwalten, können Sie nicht direkt auf den Verfügbarkeits Schlüssel zugreifen. Das Speichern und Steuern des Verfügbarkeits Schlüssels unterscheiden sich absichtlich aus drei Gründen von den Schlüsseln zu Azure Key Vault: Erstens bietet der Verfügbarkeits Schlüssel eine hohe Verfügbarkeit für den Fall, dass Office 365 Dienste die in Azure Key gehosteten Schlüssel nicht erreichen können. Tresor Zweitens bietet der Verfügbarkeits Schlüssel eine "Break Glas"-Funktion für den Fall, dass beide Azure Key Vault-Schlüssel verloren gehen. und drittens bietet die Trennung von logischen Steuerelementen eine umfassende Verteidigung und schützt vor dem Verlust aller Schlüssel von einem einzelnen Angriff oder Fehlerpunkt. Wenn Sie die Verantwortung für den Schutz der Schlüssel Teilen und gleichzeitig eine Vielzahl von Schutzmaßnahmen und Prozessen für die Schlüsselverwaltung verwenden, verringert sich letztendlich das Risiko, dass alle Schlüssel (und damit Ihre Daten) verloren gehen oder zerstört werden. Microsoft stellt Ihnen die alleinige Autorität für die Vernichtung des Verfügbarkeits Schlüssels zur Verfügung. Per Entwurf hat niemand bei Microsoft Zugriff auf den Verfügbarkeits Schlüssel-er ist nur über Office 365-Dienstcode zugänglich.
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>Wie viele Daten Verschlüsselungsrichtlinien (DEPs) kann ich erstellen?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online und Skype for Business:** Sie können bis zu 50 DEPs erstellen. 
  
 **SharePoint Online und OneDrive für Unternehmen:** Eine DEP gilt für Daten an einem geografischen Standort, der auch als Geo bezeichnet wird. Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine DEP pro Geo erstellen. Wenn Sie keine Multi-Geo-Daten verwenden, können Sie eine DEP erstellen.
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>Kann ich eine Daten Verschlüsselungsrichtlinie zuweisen, bevor Sie ein Postfach in die Cloud migrieren?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Ja. Sie können das Cmdlet MailUser Windows PowerShell verwenden, um dem Benutzer vor der Migration des Postfachs zu Office 365 eine Daten Verschlüsselungsrichtlinie (Data Encryption Policy, DEP) zuzuweisen. Wenn Sie dies tun, wird der Inhalt des Postfachs mithilfe der zugewiesenen DEP verschlüsselt, wenn der Inhalt migriert wird. Dies kann effizienter sein als das Zuweisen einer Datenausführungsverhinderung, nachdem das Postfach bereits migriert wurde und dann darauf gewartet wird, dass eine Verschlüsselung stattfindet, was Stunden oder möglicherweise Tage dauern kann. 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>Wie kann ich überprüfen, ob die Verschlüsselung mit dem Kundenschlüssel aktiviert ist und Office 365 die Verschlüsselung mit dem Kundenschlüssel abgeschlossen hat?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online und Skype for Business:** Sie können [mithilfe von Remote-PowerShell eine Verbindung mit Exchange Online herstellen](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) und dann das Cmdlet **[Get-MailboxStatistics]** für jedes Postfach verwenden, das Sie überprüfen möchten. In der Ausgabe des Cmdlets Get-MailboxStatistics gibt die _IsEncrypted_ -Eigenschaft den Wert **true** zurück, wenn das Postfach verschlüsselt ist, und den Wert **false** , wenn dies nicht der Fall ist. Wenn das Postfach verschlüsselt ist, ist der für die _DataEncryptionPolicyID_ -Eigenschaft zurückgegebene Wert die GUID der DEP, mit der das Postfach verschlüsselt wird. Weitere Informationen zum Ausführen dieses Cmdlets finden Sie unter [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx) und using PowerShell with Exchange Online. 
  
Wenn die Postfächer nach dem warten auf 72 Stunden ab dem Zeitpunkt, an dem Sie die DEP zugewiesen haben, nicht verschlüsselt sind, initiieren Sie eine Post Fach Verlagerung. Stellen Sie hierzu [mithilfe von Remote-PowerShell eine Verbindung mit Exchange Online her](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) , und verwenden Sie dann das Cmdlet New-MoveRequest, und geben Sie den Alias des Postfachs wie folgt an: 
  
```powershell
New-MoveRequest <alias>
```

 **SharePoint Online und OneDrive für Unternehmen:** Sie können [eine Verbindung mit SharePoint Online PowerShell herstellen](https://technet.microsoft.com/library/fp161372.aspx)und dann das Cmdlet **[get-SPODataEncryptionPolicy]** verwenden, um den Status Ihres Mandanten zu überprüfen. Die * * _State_* *-Eigenschaft gibt den Wert " **registered** " zurück, wenn die Verschlüsselung von Kunden Schlüsseln aktiviert ist und alle Dateien an allen Standorten verschlüsselt wurden. Wenn die Verschlüsselung noch ausgeführt wird, bietet dieses Cmdlet Informationen darüber, welcher Prozentsatz der Websites abgeschlossen ist. 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>Wie lange dauert es, bis die neuen Schlüsselsätze meine Daten schützen, wenn ich zu einer anderen Gruppe von Tasten wechseln möchte?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online und Skype for Business:** Es kann bis zu 72 Stunden dauern, um ein Postfach gemäß einer neuen Daten Verschlüsselungsrichtlinie (Data Encryption Policy, DEP) zu schützen, ab dem Zeitpunkt, zu dem die neue DEP dem Postfach zugewiesen wurde. 
  
 **SharePoint Online und OneDrive für Unternehmen:** Es kann bis zu vier Stunden dauern, bis Sie den gesamten Mandanten erneut verschlüsseln, nachdem ein neuer Schlüssel zugewiesen wurde. 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>Werden meine vorhandenen Daten zu einem beliebigen Zeitpunkt ohne Verschlüsselung gespeichert, während Sie entschlüsselt oder mit dem Kundenschlüssel verschlüsselt werden?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Nein. Ihre Daten werden in Rest im Office 365 Dienst mit BitLocker und DKM immer verschlüsselt. Weitere Informationen finden Sie unter "Sicherheits-, Datenschutz-und Kompatibilitätsinformationen für Office 365" sowie dazu, [wie Exchange Online Ihre e-Mail-Geheimnisse sichert](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376).
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>Kann ich zu von Microsoft verwalteten Schlüsseln wechseln, wenn ich die von Kunden verwalteten Verschlüsselungsschlüssel nicht mehr verwenden möchte?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online und Skype for Business:** Noch nicht. Dies wird unterstützt, wenn die Dienst Verschlüsselung in Office 365 mit von Microsoft verwalteten Schlüsseln umfassend ausgeführt wird. Wir gehen davon aus, dass dieser Dienst im Dienst ausgeführt wird, nachdem die Dienst Verschlüsselung mit dem Kundenschlüssel veröffentlicht wurde. 
  
 **SharePoint Online und OneDrive für Unternehmen:** Ja. Sie können festlegen, dass für jeden Geo (wenn Sie das Multi-Geo-Feature verwenden) oder für alle Daten, wenn es sich um einen einzelnen Geo handelt, die Verwendung von von Microsoft verwalteten Schlüsseln separat wiederherzustellen. 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>Wie lange dauert es, bis die Dienstverfügbarkeit mithilfe des Wiederherstellungsschlüssels wiederhergestellt wurde, wenn ich die Schlüssel verliere?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online und Skype for Business:** Nachdem Sie den Verfügbarkeits Schlüssel verwendet haben, können Sie innerhalb von Minuten auf Postfächer zugreifen. 
  
 **SharePoint Online und OneDrive für Unternehmen:** Dieser Vorgang ist proportional zur Anzahl der Websites, die Sie haben. Nachdem Sie Microsoft aufgerufen haben, den Verfügbarkeits Schlüssel zu verwenden, sind Sie innerhalb von etwa vier Stunden vollständig online. 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>Wie wird der Verfügbarkeits Schlüssel für Exchange Online verwendet?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Es gibt drei Möglichkeiten, den Verfügbarkeits Schlüssel mit Exchange Online zu verwenden:
  
- Dienstverfügbarkeit – für den Fall, dass Azure Key Vault-Schlüssel nicht erreichbar sind.
    
- Aktionen, die durch Office 365 Dienstcode initiiert wurden-beispielsweise Such Indexerstellung oder Postfachverschiebungen.
    
- Wiederherstellen von Schlüssel Verlusten, beispielsweise des Verlusts beider Azure Key Vault-Schlüssel, die mit einer einzelnen DEP verbunden sind.
    
 **Verwenden des Verfügbarkeits Schlüssels für die Dienstverfügbarkeit im Ereignis Azure Key Vault Schlüssel sind nicht erreichbar.**
  
Office 365 verwendet den Verfügbarkeits Schlüssel sowohl für die Dienstverfügbarkeit als auch für die Wiederherstellung von einem fehlerhaften Kundenschlüssel Status für Exchange Online. Es gibt eine Hierarchie von Schlüsseln, die von Kunden Schlüsseln verwendet werden. Diese Hierarchie wird in der folgenden Abbildung dargestellt.
  
![Eine Grafik zeigt die Hierarchie von Schlüsseln im Kundenschlüssel](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Wenn beide Azure Key Vault-Schlüssel einer einzelnen Daten Verschlüsselungsrichtlinie (DEP) nicht verfügbar sind, können Office 365 den Verfügbarkeits Schlüssel verwenden, um zu einer neuen DEP zu wechseln. Office 365 bestimmt, ob der Verfügbarkeits Schlüssel für die Dienstverfügbarkeit unterschiedlich verwendet werden soll, je nachdem, ob eine vom Benutzer initiierte Aktivität, beispielsweise wenn ein Benutzer e-Mails an den Outlook-Client herunterlädt, oder eine vom System initiierte Aktivität wie die Indizierung Postfachinhalte oder für eDiscovery-suchen haben den Prozess ausgelöst.
  
Office 365 folgt diesem Prozess als Reaktion auf Benutzer initiierte Aktionen, um zu bestimmen, ob der Verfügbarkeits Schlüssel für Benutzerpostfächer verwendet werden soll:
  
1. Office 365 liest die DEP, der das Postfach zugewiesen ist, um den Speicherort der beiden Kundenschlüssel in Azure Key Vault zu ermitteln.
    
2. Office 365 wählt nach dem Zufallsprinzip einen der beiden Kundenschlüssel aus der DEP aus und sendet eine Anforderung an Azure Key Vault, um den DEP-Schlüssel mit dem Kundenschlüssel zu entpacken.
    
3. Wenn die Anforderung zum Aufräumen des DEP-Schlüssels mit dem Kundenschlüssel fehlschlägt und ein Fehler zurückgegeben wird, sendet Office 365 eine zweite Anforderung an Azure Key Vault, wobei Sie dieses Mal angewiesen wird, den Alternativen (zweiten) Kundenschlüssel zu verwenden.
    
4. Wenn die zweite Anforderung zum Aufziehen des DEP-Schlüssels mithilfe des Kunden Schlüssels fehlschlägt und ein Fehler zurückgegeben wird, untersucht Office 365 die Ergebnisse beider Anforderungen:
    
  - Wenn die Prüfung feststellt, dass die Fehler keine explizite Aktion einer Kundenidentität widerspiegeln, verwendet Office 365 den Verfügbarkeits Schlüssel, um den DEP-Schlüssel zu entschlüsseln. Der DEP-Schlüssel wird dann verwendet, um den postfachschlüssel zu entschlüsseln und die Benutzeranforderung abzuschließen.
    
    In diesem Fall kann Azure Key Vault aus irgendeinem Grund entweder nicht reagieren oder nicht erreichbar sein. Office 365 hat keine Möglichkeit zu ermitteln, ob der Benutzer den Zugriff auf die Schlüssel absichtlich aufgehoben hat.
    
  - Wenn die Prüfung darauf hinweist, dass absichtliche Aktionen ausgeführt wurden, um die Kundenschlüssel nicht verfügbar zu machen, wird der Verfügbarkeits Schlüssel nicht verwendet, die Benutzeranforderung schlägt fehl, und der Benutzer erhält eine Fehlermeldung, beispielsweise einen Anmeldefehler.
    
    In diesem Fall wird dem Kunden bewusst gemacht, dass der Dienst betroffen ist und dass der Zustand des Kunden Schlüssels ungesund ist. Wenn ein Kunde beispielsweise eine einzelne Datenausführungsverhinderung für alle Postfächer in der Organisation verwendet, tritt beim Kunden möglicherweise ein weit verbreiteter Fehler auf, wenn Benutzer nicht auf ihre Postfächer zugreifen können. Dadurch wird sichergestellt, dass der Kunde, wenn beide Kundenschlüssel fehlerhaft sind, darauf aufmerksam gemacht wird, dass die Situation korrigiert werden muss und dass der Dienst in einem fehlerfreien Zustand wiederhergestellt werden muss.
    
 **Verwenden des Verfügbarkeits Schlüssels für Aktionen, die von Office 365 Dienstcode initiiert wurden.**
  
Office 365-Dienstcode hat immer ein gültiges Anmeldetoken und kann nicht blockiert werden. Daher kann es, bis der Verfügbarkeits Schlüssel gelöscht wurde, für Aktionen verwendet werden, die von oder intern in Office 365 Dienstcode initiiert werden, beispielsweise Such Indexerstellung oder Verschieben von Postfächern.
  
 **Verwenden des Verfügbarkeits Schlüssels zur Wiederherstellung nach Schlüssel Verlusten.**
  
Sie können den Verfügbarkeits Schlüssel verwenden, um den Verlust beider Azure Key Vault-Schlüssel wiederherzustellen, die derselben Datenausführungsverhinderung zugeordnet sind, wie in der Antwort auf den FAQ-Eintrag "wenn meine Schlüssel zerstört sind, wie kann ich wiederherstellen?" beschrieben wird.
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>Wie wird der Verfügbarkeits Schlüssel für SharePoint Online und OneDrive für Unternehmen verwendet?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Die SharePoint Online und OneDrive für Unternehmen Architektur und Implementierung für den Schlüssel und die Verfügbarkeit von Kunden unterscheiden sich von Exchange Online und Skype for Business.
  
Wenn ein Kunde zu von Kunden verwalteten Schlüsseln wechselt, erstellt Office 365 einen mandantenspezifischen zwischen Schlüssel (tik). Office 365 verschlüsselt die tik zweimal, einmal mit jedem Kundenschlüssel, und speichert die beiden verschlüsselten Versionen des tik. Nur die verschlüsselten Versionen der tik werden gespeichert, und ein tik kann nur mit den Kunden Schlüsseln entschlüsselt werden. Die tik wird dann zum Verschlüsseln von Website Schlüsseln verwendet, die dann zum Verschlüsseln von BLOB-Schlüsseln verwendet werden. Die BLOBs selbst werden verschlüsselt und im Microsoft Azure BLOB-Speicherdienst gespeichert.
  
Office 365 folgt diesem Prozess für den Zugriff auf ein BLOB mit Kundendatei Daten:
  
1. Entschlüsseln Sie die tik mit dem Kundenschlüssel.
    
2. Verwenden Sie den entschlüsselten tik, um einen Standort Schlüssel zu entschlüsseln.
    
3. Verwenden Sie den entschlüsselten Standort Schlüssel, um einen BLOB-Schlüssel zu entschlüsseln.
    
4. Verwenden Sie den entschlüsselten BLOB-Schlüssel, um das BLOB zu entschlüsseln.
    
Beim Entschlüsseln eines tik gibt Office 365 zwei Entschlüsselungs Anforderungen an Azure Key Vault mit einem leichten Offset aus. Der erste, der fertig ist, liefert das Ergebnis und bricht die andere Anforderung ab.
  
Wenn der Kunde den Zugriff auf seine Kundenschlüssel verliert, verschlüsselt Office 365 auch die tik mit einem Verfügbarkeits Schlüssel und speichert diese zusammen mit den TIKs, die mit jedem Kundenschlüssel verschlüsselt sind. Die mit dem Verfügbarkeits Schlüssel verschlüsselte tik wird nur verwendet, wenn der Kunde Microsoft anruft, um den Wiederherstellungspfad einzutragen, wenn er böswillig oder versehentlich den Zugriff auf die Schlüssel verloren hat.
  
Aus Gründen der Verfügbarkeit und Skalierung werden entschlüsselte TIKs in einem zeitbegrenzten Arbeitsspeichercache zwischengespeichert. Zwei Stunden, bevor ein tik-Cache auf Ablauf festgelegt wird, versucht Office 365, die einzelnen tik zu entschlüsseln. Das Entschlüsseln des TIKs verlängert die Lebensdauer des Caches. Wenn die tik-Entschlüsselung für eine erhebliche Zeitspanne fehlschlägt, generiert Office 365 eine Warnung, die das Engineering vor dem Cache Ablauf benachrichtigt. Nur wenn der Kunde Microsoft anruft, Office 365 den Wiederherstellungsvorgang zu initiieren, bei dem die tik mit dem verfügbaren Verfügbarkeits Schlüssel entschlüsselt wird, der im geheimen Speicher von Microsoft gespeichert ist, und der den Mandanten erneut mit dem entschlüsselten tik und einer neuen Gruppe von vom Kunden bereitgestellte Azure Key-Tresorschlüssel.
  
Ab heute ist der Kundenschlüssel an der Verschlüsselungs-und Entschlüsselungs Kette von SharePoint Online Dateidaten beteiligt, die im Azure-BLOB-Speicher gespeichert sind, aber nicht SharePoint Online Listenelementen oder Metadaten, die in der SQL-Datenbank gespeichert sind. Office 365 verwendet nicht den Verfügbarkeits Schlüssel für SharePoint Online oder OneDrive für Unternehmen außer dem oben beschriebenen Fall, der vom Kunden initiiert wurde. Der menschliche Zugriff auf Kundendaten wird durch die Kunden-Lockbox geschützt.
  
## <a name="how-is-customer-key-licensed"></a>Wie wird der Kundenschlüssel lizenziert?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Der Kundenschlüssel wird in der Office 365 Enterprise Suite, "E5" und der Advanced Compliance-SKU angeboten. Darüber hinaus müssen Kunden auch die entsprechende Lizenz für die Verwendung von Azure Key Vault erwerben.
  
Jeder Benutzer, der von einem Kundenschlüssel profitiert, muss lizenziert werden, wenn er über den Kundenschlüssel abgedeckt werden soll.
  
Für SharePoint Online muss der Office 365 Administrator, der den Kundenschlüssel konfiguriert, ebenfalls lizenziert werden, um die Setupschritte auszuführen. Darüber hinaus müssen die Benutzer, die von dem Feature profitieren, lizenziert werden – dazu gehören der Websitebesitzer und alle Benutzer, die auf Dateien auf einer oder mehreren Websites zugreifen, die mit dem Kundenschlüssel verschlüsselt sind. Externe Benutzer müssen nicht für den Zugriff auf Dateien auf einem oder mehreren Websites, die mit dem Kundenschlüssel verschlüsselt sind, lizenziert werden.
  
Für Exchange Online müssen die Postfächer "Benutzer" und "e-Mail-Benutzer" lizenziert werden. Alle anderen, beispielsweise freigegebene Postfächer, benötigen keine Lizenz für den Kundenschlüssel. Führen Sie das folgende Cmdlet aus, um zu überprüfen, ob Ihr Exchange Online Postfach ordnungsgemäß lizenziert ist:
  
```powershell
(Get-Mailbox <alias >).PersistedCapabilities
```

Wenn die Zeichenfolge BPOS_S_EquivioAnalytics vorhanden ist, wird das Postfach ordnungsgemäß lizenziert. Wenn dies nicht der Fall ist, müssen Sie die entsprechende Lizenz anwenden, um das Kundenschlüssel Feature für dieses Postfach verwenden zu können.
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>Kann ich den Kundenschlüssel für ein Testabonnement aktivieren?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Nein. Per Definition haben Testabonnements eine beschränkte Lebensdauer. Verschlüsselungsschlüssel, die in Testabonnements gehostet werden, können am Ende der Lebensdauer der Testversion verloren gehen. Da Microsoft Kunden nicht daran hindert, wichtige Kundendaten in Testabonnements einzusetzen, ist die Verwendung von Kunden Schlüsseln mit Testabonnements untersagt.
  
## <a name="how-much-will-using-customer-key-cost"></a>In welchem Umfang werden die Kundenschlüssel Kosten verwendet?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Zusätzlich zur Lizenzierung, die für den Kundenschlüssel erforderlich ist, entstehen für Kunden Kosten für die Verwendung von Schlüssel Vaults. [Azure Key Vault Pricing Details](https://azure.microsoft.com/pricing/details/key-vault/) beschreibt das Kostenmodell und hilft bei der Schätzung. Es gibt keine Möglichkeit, die genauen Kosten vorherzusagen, die jedem Kunden entstehen, da sich die Nutzungsmuster unterscheiden. Die Erfahrung hat gezeigt, dass die Kosten sehr niedrig sind und im Allgemeinen im Bereich von $0,002 bis $0,005 pro Benutzer und Monat zuzüglich der Kosten von HSM-gebackenen Schlüsseln liegt. Die Kosten variieren auch je nach der vom Kunden gewählten Protokollierungskonfiguration und der Größe des Azure-Speichers, der für Azure Key Vault-Protokolle verwendet wird. 
  
## <a name="for-more-information"></a>Weitere Informationen
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Informationen zu den ersten Schritten mit dem Kundenschlüssel finden Sie unter [Steuern der Daten in Office 365 mit dem Kundenschlüssel](controlling-your-data-using-customer-key.md).
  

