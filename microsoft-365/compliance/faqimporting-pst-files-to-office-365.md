---
title: Häufig gestellte Fragen zum Importieren von PST-Dateien
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
ms.custom: seo-marvel-apr2020
description: Dieser Artikel enthält Antworten auf einige häufig gestellte Fragen an Administratoren zum Importieren von PST-Dateien in Microsoft 365 mithilfe des Office 365-Import Diensts.
ms.openlocfilehash: 0f490b7bae3f462bb07725bf14453a6b9a4d7b9e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817734"
---
# <a name="faq-about-importing-pst-files"></a>Häufig gestellte Fragen zum Importieren von PST-Dateien

**Dieser Artikel richtet sich an Administratoren. Möchten Sie PST-Dateien in Ihr eigenes Postfach importieren? Siehe [Importieren von e-Mails, Kontakten und Kalendern aus einer Outlook. PST-Datei](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Im folgenden finden Sie einige häufig gestellte Fragen zur Verwendung des Office 365 Import Diensts für den Massenimport von PST-Dateien in Microsoft 365-Postfächer. Weitere Informationen zum Importieren von PST-Dateien finden Sie unter [Übersicht über das Importieren von PST-Dateien in Office 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365).
  
## <a name="using-network-upload-to-import-pst-files"></a>Verwenden des Netzwerkuploads zum Importieren von PST-Dateien

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Verwenden des Netzwerk Uploads zum Importieren von PST-Dateien in Office 365](use-network-upload-to-import-pst-files.md).
  
 **Welche Berechtigungen sind für das Erstellen von Importaufträgen im Office 365-Importdienst erforderlich?**
  
Ihnen muss die Rolle für den Postfachimport/-export in Exchange Online zugewiesen werden, damit Sie PST-Dateien in Microsoft 365-Postfächer importieren können. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Alternativ können Sie eine neue Rollengruppe erstellen, dieser die Rolle für den Postfachimport/-export zuweisen und sich selbst oder andere Benutzer dann als Mitglied hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppe in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Darüber hinaus muss eine der folgenden Bedingungen erfüllt sein, um Importaufträge im Security & Compliance Center erstellen zu können:
  
- Ihnen muss in Exchange Online die Rolle „E-Mail-Empfänger“ zugewiesen sein. Standardmäßig wird diese Rolle den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen.
    
    Oder
    
- Sie müssen ein globaler Administrator in Ihrer Organisation sein.
    
> [!TIP]
> Erwägen Sie, in Exchange Online eine neue Rollengruppe speziell zum Importieren von PST-Dateien nach Office 365 zu erstellen. Legen Sie für die neue Rollengruppe als mindestens erforderliche Berechtigungen zum Importieren von PST-Dateien die Rollen "Postfachimport/-export" und "E-Mail-Empfänger" fest, und fügen Sie anschließend Mitglieder hinzu. 
  
 **Wo ist der Netzwerkupload verfügbar?**
  
Netzwerk Upload ist derzeit in diesen Regionen verfügbar: USA, Kanada, Brasilien, Vereinigtes Königreich, Frankreich, Europa, Indien, Ostasien, Südostasien, Japan, Südkorea, Australien und Vereinigte Arabische Emirate (VAE). Network upload will be available in more regions soon.

> [!NOTE]
> Zurzeit ist der Netzwerkupload von PST-Dateien in Deutschland und der Schweiz nicht verfügbar. Diese Häufig gestellten Fragen werden aktualisiert, sobald der Netzwerkupload in diesen Ländern verfügbar ist.
  
 **Welche Preise ergeben sich für den Import von PST-Dateien über den Netzwerkupload?**
  
Using network upload to import PST files is free.
  
Dies bedeutet auch, dass aus dem Azure-Speicherbereich gelöschte PST-Dateien im Microsoft 365 Admin Center nicht mehr in der Dateiliste für einen abgeschlossenen Importauftrag angezeigt werden. Es kann zwar vorkommen, dass ältere Importaufträge noch auf der Seite **Importieren von Daten in Office 365** aufgelistet sind, die Liste der PST-Dateien könnte jedoch leer sein, wenn Sie die Details anzeigen. 
  
 **Welche Version des PST-Dateiformats wird für den Import in Office 365 unterstützt?**
  
Es gibt zwei Versionen des PST-Dateiformats: ANSI und Unicode. Wir empfehlen den Import von PST-Dateien im Unicode-Format. Allerdings können auch PST-Dateien im ANSI-Format (z. B. bei Sprachen mit Doppelbyte-Zeichensatz) in Office 365 importiert werden. Weitere Informationen zum Importieren von ANSI-PST-Dateien finden Sie unter Schritt 4 in [Verwenden des Netzwerk Uploads zum Importieren der PST-Dateien Ihrer Organisation in Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Darüber hinaus können PST-Dateien aus Outlook 2007 und neueren Versionen in Office 365 importiert werden.
  
 **Wie lange verbleiben meine PST-Dateien, nachdem ich sie in den Azure-Speicherbereich hochgeladen habe, in Azure, bevor sie gelöscht werden?**
  
Wenn Sie PST-Dateien mit der Netzwerkupload-Methode importieren, werden die Dateien in einen Azure-BLOB-Container namens **ingestiondata** hochgeladen. Wenn auf der Seite **PST-Dateien importieren** im Security & Compliance Center keine Importaufträge in Bearbeitung sind, werden alle PST-Dateien im Container **ingestiondata** in Azure 30 Tage nach Erstellung des letzten Importauftrags im Security & Compliance Center gelöscht. Daraus folgt, dass Sie innerhalb von 30 Tagen nach dem Hochladen von PST-Dateien nach Azure einen neuen Importauftrag im Security & Compliance Center erstellen müssen (wie in Schritt 5 in den Netzwerkupload-Anweisungen beschrieben). 
  
Dies bedeutet auch, dass aus dem Azure-Speicherbereich gelöschte PST-Dateien im Security & Compliance Center nicht mehr in der Dateiliste für einen abgeschlossenen Importauftrag angezeigt werden. Es kann zwar sein, dass auf der Seite **PST-Dateien importieren** im Security & Compliance Center ältere Importaufträge noch aufgeführt sind, die Liste der PST-Dateien könnte jedoch leer sein, wenn Sie die Details anzeigen. 
  
 **Wie lange dauert das Importieren einer PST-Datei in ein Postfach?**
  
Das hängt von der Kapazität des Netzwerks ab, doch normalerweise dauert es mehrere Stunden für jedes Terabyte (TB) an Daten, bis es in den Azure-Speicherbereich für Ihr Unternehmen hochgeladen wurde. Nachdem die PST-Dateien in den Azure-Speicherbereich kopiert wurden, wird eine PST-Datei mit einer Übertragungsrate von mindestens 24 GB pro Tag in ein Microsoft 365-Postfach importiert. Wenn diese Rate nicht Ihren Anforderungen entspricht, sollten Sie ggf. andere Methoden zum Migrieren von E-Mail-Daten zu Office 365 in Betracht ziehen. Weitere Informationen finden Sie unter [Methoden zum Migrieren von mehreren E-Mail-Konten zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Wenn verschiedene PST-Dateien in unterschiedliche Zielpostfächer importiert werden, erfolgt der Importvorgang parallel, d. h. jedes PST-Postfach-Paar wird gleichzeitig importiert. Wenn mehrere PST-Dateien in dasselbe Postfach importiert werden, werden sie ebenfalls gleichzeitig importiert.
  
 **Wie behandelt der PST-Importprozess doppelte E-Mail-Elemente?**

Beim PST-Importprozess wird eine Überprüfung auf doppelte Elemente durchgeführt, und die Elemente werden nicht aus einer PST-Datei in das Postfach oder Archiv kopiert, wenn ein übereinstimmendes Element im Zielordner im Zielpostfach oder -archiv vorliegt. Wenn Sie dieselbe PST-Datei erneut importieren und einen anderen Zielordner (mithilfe der TargetRootFolder-Eigenschaft in der PST-Importzuordnungsdatei) angeben als den, den Sie in einem vorherigen Importauftrag angegeben haben, werden alle Elemente in der PST-Datei erneut importiert.

 **Gibt es eine Beschränkung der Nachrichtengröße beim Importieren von PST-Dateien?**
  
Ja. Wenn eine PST-Datei ein Postfachelement enthält, das größer als 150 MB ist, wird das Element beim Importvorgang übersprungen.
  
 **Bleiben die Eigenschaften der Nachrichten (z. B. Sende- oder Empfangsdatum, Empfängerliste und andere Eigenschaften) erhalten, wenn PST-Dateien in ein Microsoft 365-Postfach importiert werden?**
  
Ja. Beim Importvorgang werden die Metadaten der ursprünglichen Nachricht nicht geändert.
  
 **Gibt es eine Beschränkung der Anzahl der Ebenen in einer Ordnerhierarchie für eine PST-Datei, die ich in ein Postfach importieren möchten?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Kann ich PST-Dateien über den Netzwerkupload in ein inaktives Postfach in Office 365 importieren?**
  
Ja, diese Funktion ist jetzt verfügbar.
  
 **Kann ich PST-Dateien über den Netzwerkupload in ein Onlinearchivpostfach in einer Exchange-Hybridbereitstellung importieren?**
  
Ja, diese Funktion ist jetzt verfügbar. 
  
 **Kann ich den Netzwerkupload zum Importieren von PST-Dateien in öffentliche Ordner in Exchange Online verwenden?**
  
Nein, Sie können keine PST-Dateien in öffentliche Ordner importieren.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Verwenden des Laufwerkversands zum Importieren von PST-Dateien

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Verwenden des Laufwerk Versands zum Importieren von PST-Dateien in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **Welche Berechtigungen sind für das Erstellen von Importaufträgen im Office 365-Importdienst erforderlich?**
  
Zum Importieren von PST-Dateien in Microsoft 365-Postfächer muss Ihnen die Rolle „Postfachimport/-export“ zugewiesen sein. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Alternativ können Sie eine neue Rollengruppe erstellen, dieser die Rolle für den Postfachimport/-export zuweisen und sich selbst oder andere Benutzer dann als Mitglied hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppe in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Darüber hinaus muss eine der folgenden Bedingungen erfüllt sein, um Importaufträge im Security & Compliance Center erstellen zu können:
  
- Ihnen muss in Exchange Online die Rolle „E-Mail-Empfänger“ zugewiesen sein. Standardmäßig wird diese Rolle den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen.
    
    Oder
    
- Sie müssen ein globaler Administrator in Ihrer Organisation sein.
    
> [!TIP]
> Erwägen Sie, in Exchange Online eine neue Rollengruppe speziell zum Importieren von PST-Dateien nach Office 365 zu erstellen. Legen Sie für die neue Rollengruppe als mindestens erforderliche Berechtigungen zum Importieren von PST-Dateien die Rollen "Postfachimport/-export" und "E-Mail-Empfänger" fest, und fügen Sie anschließend Mitglieder hinzu. 
  
 **Wo ist der Laufwerkversand verfügbar?**
  
Der Laufwerkversand ist derzeit in den USA, Kanada, Brasilien, Vereinigtem Königreich, Europa, Indien, Ostasien, Südostasien, Japan, Republik Korea und Australien verfügbar. Der Laufwerkversand wird in Kürze in weiteren Regionen zur Verfügung gestellt.

> [!NOTE]
> Zurzeit ist der Laufwerkversand um PST-Dateien zu importieren in Deutschland und der Schweiz nicht verfügbar. Diese Häufig gestellten Fragen werden aktualisiert, sobald der Laufwerkversand in diesen Ländern verfügbar ist.
  
 **Welche kommerziellen Lizenzvereinbarungen unterstützen den Laufwerksversand?**
  
Der Laufwerkversand zum Importieren von PST-Dateien in Microsoft 365 steht über ein Microsoft Enterprise Agreement (EA) zur Verfügung. Der Laufwerkversand steht nicht im Rahmen von Microsoft Products und Services Agreement (MPSA) zur Verfügung.
  
 **Was kostet die Verwendung des Laufwerkversands zum Importieren von PST-Dateien in Microsoft 365?**
  
Die Kosten für den Laufwerksversand zum Importieren von PST-Dateien in Microsoft 365-Postfächer betragen ca. 2 Euro pro GB an Daten. Wenn Sie z. B. eine Festplatte versenden, die 1.000 GB (1 TB) an PST-Dateien enthält, betragen die Kosten beispielsweise 2.000 Euro. Um die Importgebühren zu zahlen, können Sie mit einem Partner zusammenarbeiten. Informationen zum Suchen von Partnern finden Sie unter [Microsoft-Partner oder -Händler finden](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **Welche Festplattentypen werden für den Laufwerkversand unterstützt?**
  
Nur 2,5-Zoll-Festkörperlaufwerke (SSDs) oder interne 2,5-/3,5-Zoll-Festplatten (SATA II/III) werden für die Verwendung mit dem Office 365-Importdienst unterstützt. Sie können Festplatten bis zu 10 TB verwenden. Bei Importaufträgen wird nur das erste Datenvolume auf der Festplatte verarbeitet. Das Datenvolume muss mit NTFS formatiert sein. Beim Kopieren von Daten auf ein Festplattenlaufwerk kann der Anschluss direkt mithilfe eines 2,5-Zoll-SSD- oder eines 2,5- oder 3,5-Zoll-SATA II/III-Verbinders oder extern über einen externen 2,5-Zoll-SSD- oder einen 2,5- oder 3,5-Zoll-SATA II/III-USB-Adapter erfolgen.
  
> [!IMPORTANT]
> Externe Festplatten mit einem integrierten USB-Adapter werden vom Office 365-Importdienst nicht unterstützt. Darüber hinaus kann der Datenträger innerhalb des Gehäuses einer externen Festplatte nicht verwendet werden. Versenden Sie keine externen Festplatten. 
  
 **Wie viele Festplatten kann ich für einen einzelnen Importauftrag versenden?**
  
Sie können maximal 10 Festplatten für einen einzelnen Importauftrag versenden.
  
 **Wie lange dauert es nach dem Versand meiner Festplatten, bis sie im Microsoft-Rechenzentrum ankommen?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Wie lange dauert das Hochladen meiner PST-Dateien nach Azure, nachdem meine Festplatte im Microsoft Data Center eingetroffen ist?**
  
Nachdem Ihre Festplatte im Microsoft-Rechenzentrum empfangen wurde, dauert es zwischen 7 und 10 Werktage, bis Sie die PST-Dateien in den Azure-Speicherbereich Ihrer Organisation hochgeladen haben. Die PST-Dateien werden in einen Azure-BLOB-Container mit dem Namen **ingestiondata**hochgeladen. 
  
 **Wie lange dauert das Importieren einer PST-Datei in ein Postfach?**
  
Nachdem die PST-Dateien in den Azure-Speicherbereich hochgeladen wurden, werden die Daten in den PST-Dateien (auf gefahrlose und sichere Weise) von Microsoft 365 analysiert, um das Alter der Elemente und die unterschiedlichen Nachrichtentypen zu bestimmen, die in den PST-Dateien enthalten sind. Nach Abschluss der Analyse können Sie alle in den PST-Dateien enthaltenen Daten importieren oder Filter festlegen, die steuern, welche Daten importiert werden sollen. Nachdem Sie den Importvorgang gestartet haben, wird eine PST-Datei mit einer Übertragungsrate von mindestens 24 GB pro Tag in ein Microsoft 365-Postfach importiert. Wenn diese Rate nicht Ihren Anforderungen entspricht, sollten Sie ggf. andere Methoden zum Importieren von E-Mail-Daten in Office 365 in Betracht ziehen. Weitere Informationen finden Sie unter [Methoden zum Migrieren von mehreren E-Mail-Konten zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Wenn verschiedene PST-Dateien in unterschiedliche Zielpostfächer importiert werden, erfolgt der Importvorgang parallel, d. h. jedes PST-Postfach-Paar wird gleichzeitig importiert. Wenn mehrere PST-Dateien in dasselbe Postfach importiert werden, werden sie ebenfalls gleichzeitig importiert.
  
 **Wie lange verbleiben meine PST-Dateien, nachdem Microsoft sie in Azure hochgeladen hat, in Azure, bevor sie gelöscht werden?**
  
Alle PST-Dateien am Azure-Speicherort für Ihre Organisation (im BLOB-Container mit dem Namen **ingestiondata**) werden 30 Tage nach dem Erstellen des letzten importauftrags auf der Seite **PST-Dateien importieren** im Security & Compliance Center gelöscht. 
  
Dies bedeutet auch, dass aus dem Azure-Speicherbereich gelöschte PST-Dateien im Security & Compliance Center nicht mehr in der Dateiliste für einen abgeschlossenen Importauftrag angezeigt werden. Es kann zwar sein, dass auf der Seite **PST-Dateien importieren** im Security & Compliance Center ältere Importaufträge noch aufgeführt sind, die Liste der PST-Dateien könnte jedoch leer sein, wenn Sie die Details anzeigen. 
  
 **Welche Version des PST-Dateiformats wird für den Import in Microsoft 365 unterstützt?**
  
Es gibt zwei Versionen des PST-Dateiformats: ANSI und Unicode. Wir empfehlen den Import von PST-Dateien im Unicode-Format. Allerdings können auch PST-Dateien im ANSI-Format (z. B. bei Sprachen mit Doppelbyte-Zeichensatz) in Microsoft 365 importiert werden. Weitere Informationen zum Importieren von ANSI-PST-Dateien finden Sie unter Schritt 3: [Verwenden des Laufwerk Versands zum Importieren von PST-Dateien in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Darüber hinaus können PST-Dateien aus Outlook 2007 und neueren Versionen in Office 365 importiert werden.
  
 **Gibt es eine Beschränkung der Nachrichtengröße beim Importieren von PST-Dateien?**
  
Ja. Wenn eine PST-Datei ein Postfachelement enthält, das größer als 150 MB ist, wird das Element beim Importvorgang übersprungen.
  
  **Wie behandelt der PST-Importprozess doppelte E-Mail-Elemente?**

Beim PST-Importprozess wird eine Überprüfung auf doppelte Elemente durchgeführt, und die Elemente werden nicht aus einer PST-Datei in das Postfach oder Archiv kopiert, wenn ein übereinstimmendes Element im Zielordner im Zielpostfach oder -archiv vorliegt. Wenn Sie dieselbe PST-Datei erneut importieren und einen anderen Zielordner (mithilfe der TargetRootFolder-Eigenschaft in der PST-Importzuordnungsdatei) angeben als den, den Sie in einem vorherigen Importauftrag angegeben haben, werden alle Elemente in der PST-Datei erneut importiert.
 
 **Bleiben die Eigenschaften der Nachrichten (z. B. Sende- oder Empfangsdatum, Empfängerliste und andere Eigenschaften) erhalten, wenn PST-Dateien in ein Microsoft 365-Postfach importiert werden?**
  
Ja. Beim Importvorgang werden die Metadaten der ursprünglichen Nachricht nicht geändert.
  
 **Gibt es eine Beschränkung der Anzahl der Ebenen in einer Ordnerhierarchie für eine PST-Datei, die ich in ein Postfach importieren möchten?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Kann ich PST-Dateien über den Laufwerksversand in ein inaktives Postfach in Microsoft 365 importieren?**
  
Ja, diese Funktion ist jetzt verfügbar.
  
 **Kann ich PST-Dateien über den Laufwerksversand in ein Onlinearchivpostfach in einer Exchange-Hybridbereitstellung importieren?**
  
Ja, diese Funktion ist jetzt verfügbar. 
  
 **Kann ich den Laufwerkversand zum Importieren von PST-Dateien in öffentliche Ordner in Exchange Online verwenden?**
  
Nein, Sie können keine PST-Dateien in öffentliche Ordner importieren.
  
 **Kann Microsoft meine Festplatte zurücksetzen, bevor sie wieder an mich zurückgesendet wird?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Kann Microsoft meine Festplatte vernichten, anstatt sie zurückzusenden?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Welche Kurierdienste werden für die Rücksendung unterstützt?**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **Wie hoch sind die Kosten für die Rücksendung?**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **Kann ich einen benutzerdefinierten Kurierdienst verwenden, z. B. FedEx Custom Shipping, um meine Festplatte an Microsoft zu senden?**
  
Ja.
  
 **Was muss ich beachten, wenn ich meine Festplatte in ein anderes Land versenden muss?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
