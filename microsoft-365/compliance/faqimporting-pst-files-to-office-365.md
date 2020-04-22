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
description: 'Häufig gestellte Fragen an Administratoren zur Verwendung des Office 365-Import Diensts zum Importieren der PST-Dateien Ihrer Organisation in Microsoft 365-Postfächer. '
ms.openlocfilehash: c2eb673ea8be2b628496df0e7b0412cbf3312ba9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615949"
---
# <a name="faq-about-importing-pst-files"></a>Häufig gestellte Fragen zum Importieren von PST-Dateien

**Dieser Artikel richtet sich an Administratoren. Möchten Sie PST-Dateien in Ihr eigenes Postfach importieren? Siehe [Importieren von e-Mails, Kontakten und Kalendern aus einer Outlook. PST-Datei](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Im folgenden finden Sie einige häufig gestellte Fragen zur Verwendung des Office 365 Import Diensts für den Massenimport von PST-Dateien in Microsoft 365-Postfächer. Weitere Informationen zum Importieren von PST-Dateien finden Sie unter [Übersicht über das Importieren von PST-Dateien in Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Verwenden des Netzwerkuploads zum Importieren von PST-Dateien

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Verwenden des Netzwerk Uploads zum Importieren von PST-Dateien in Office 365](use-network-upload-to-import-pst-files.md).
  
 **Welche Berechtigungen sind für das Erstellen von Importaufträgen im Office 365-Importdienst erforderlich?**
  
Sie müssen in Exchange Online über die Rolle "Postfachimport export" verfügen, um PST-Dateien in Microsoft 365-Postfächer zu importieren. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Alternativ können Sie eine neue Rollengruppe erstellen, dieser die Rolle für den Postfachimport/-export zuweisen und sich selbst oder andere Benutzer dann als Mitglied hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppe in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Darüber hinaus muss eine der folgenden Bedingungen erfüllt sein, um Importaufträge im Security & Compliance Center erstellen zu können:
  
- Ihnen muss in Exchange Online die Rolle „E-Mail-Empfänger“ zugewiesen sein. Standardmäßig wird diese Rolle den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen.
    
    Oder
    
- Sie müssen ein globaler Administrator in Ihrer Organisation sein.
    
> [!TIP]
> Erwägen Sie, in Exchange Online eine neue Rollengruppe speziell zum Importieren von PST-Dateien nach Office 365 zu erstellen. Legen Sie für die neue Rollengruppe als mindestens erforderliche Berechtigungen zum Importieren von PST-Dateien die Rollen "Postfachimport/-export" und "E-Mail-Empfänger" fest, und fügen Sie anschließend Mitglieder hinzu. 
  
 **Wo ist der Netzwerkupload verfügbar?**
  
Netzwerk Upload ist derzeit in diesen Regionen verfügbar: USA, Kanada, Brasilien, Vereinigtes Königreich, Frankreich, Europa, Indien, Ostasien, Südostasien, Japan, Südkorea und Australien. Network upload will be available in more regions soon.

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
  
Das hängt von der Kapazität des Netzwerks ab, doch normalerweise dauert es mehrere Stunden für jedes Terabyte (TB) an Daten, bis es in den Azure-Speicherbereich für Ihr Unternehmen hochgeladen wurde. Nachdem die PST-Dateien in den Azure-Speicherbereich kopiert wurden, wird eine PST-Datei mit einer Rate von mindestens 24 GB pro Tag in ein Microsoft 365-Postfach importiert. Wenn diese Rate nicht Ihren Anforderungen entspricht, sollten Sie ggf. andere Methoden zum Migrieren von E-Mail-Daten zu Office 365 in Betracht ziehen. Weitere Informationen finden Sie unter [Methoden zum Migrieren von mehreren E-Mail-Konten zu Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Wenn verschiedene PST-Dateien in unterschiedliche Zielpostfächer importiert werden, erfolgt der Importvorgang parallel, d. h. jedes PST-Postfach-Paar wird gleichzeitig importiert. Wenn mehrere PST-Dateien in dasselbe Postfach importiert werden, werden sie ebenfalls gleichzeitig importiert.
  
 **Wie behandelt der PST-Importprozess doppelte E-Mail-Elemente?**

Beim PST-Importprozess wird eine Überprüfung auf doppelte Elemente durchgeführt, und die Elemente werden nicht aus einer PST-Datei in das Postfach oder Archiv kopiert, wenn ein übereinstimmendes Element im Zielordner im Zielpostfach oder -archiv vorliegt. Wenn Sie dieselbe PST-Datei erneut importieren und einen anderen Zielordner (mithilfe der TargetRootFolder-Eigenschaft in der PST-Importzuordnungsdatei) angeben als den, den Sie in einem vorherigen Importauftrag angegeben haben, werden alle Elemente in der PST-Datei erneut importiert.

 **Gibt es eine Beschränkung der Nachrichtengröße beim Importieren von PST-Dateien?**
  
Ja. Wenn eine PST-Datei ein Postfachelement enthält, das größer als 150 MB ist, wird das Element beim Importvorgang übersprungen.
  
 **Werden Nachrichteneigenschaften, beispielsweise beim Senden oder empfangen der Nachricht, der Liste der Empfänger und anderer Eigenschaften, beibehalten, wenn PST-Dateien in ein Microsoft 365-Postfach importiert werden?**
  
Ja. Beim Importvorgang werden die Metadaten der ursprünglichen Nachricht nicht geändert.
  
 **Gibt es eine Beschränkung der Anzahl der Ebenen in einer Ordnerhierarchie für eine PST-Datei, die ich in ein Postfach importieren möchten?**
  
Ja. Sie können keine PST-Dateien mit 300 oder mehr Ebenen von geschachtelten Ordnern importieren.
  
 **Kann ich PST-Dateien über den Netzwerkupload in ein inaktives Postfach in Office 365 importieren?**
  
Ja, diese Funktion ist jetzt verfügbar.
  
 **Kann ich PST-Dateien über den Netzwerkupload in ein Onlinearchivpostfach in einer Exchange-Hybridbereitstellung importieren?**
  
Ja, diese Funktion ist jetzt verfügbar. 
  
 **Kann ich den Netzwerkupload zum Importieren von PST-Dateien in öffentliche Ordner in Exchange Online verwenden?**
  
Nein, Sie können keine PST-Dateien in öffentliche Ordner importieren.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Verwenden des Laufwerkversands zum Importieren von PST-Dateien

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Verwenden des Laufwerk Versands zum Importieren von PST-Dateien in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **Welche Berechtigungen sind für das Erstellen von Importaufträgen im Office 365-Importdienst erforderlich?**
  
Sie müssen die Rolle "Postfachimport export" besitzen, um PST-Dateien in Microsoft 365-Postfächer zu importieren. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Alternativ können Sie eine neue Rollengruppe erstellen, dieser die Rolle für den Postfachimport/-export zuweisen und sich selbst oder andere Benutzer dann als Mitglied hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppe in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
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
  
Laufwerk Versand zum Importieren von PST-Dateien nach Microsoft 365 steht über einen Microsoft Enterprise-Vertrag (EA) zur Verfügung. Der Laufwerkversand steht nicht im Rahmen von Microsoft Products und Services Agreement (MPSA) zur Verfügung.
  
 **Wie hoch sind die Preise für die Verwendung des Laufwerk Versands zum Importieren von PST-Dateien nach Microsoft 365?**
  
Die Kosten für die Verwendung des Laufwerk Versands zum Importieren von PST-Dateien in Microsoft 365-Postfächer beläuft sich auf $2 USD pro GB Daten. Wenn Sie z. B. eine Festplatte versenden, die 1.000 GB (1 TB) an PST-Dateien enthält, betragen die Kosten beispielsweise 2.000 Euro. Um die Importgebühren zu zahlen, können Sie mit einem Partner zusammenarbeiten. Informationen zum Suchen eines Partners finden Sie unter [Suchen Ihres Microsoft-Partners oder-Händlers](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **Welche Festplattentypen werden für den Laufwerkversand unterstützt?**
  
Nur 2,5-Zoll-Festkörperlaufwerke (SSDs) oder interne 2,5-/3,5-Zoll-Festplatten (SATA II/III) werden für die Verwendung mit dem Office 365-Importdienst unterstützt. Sie können Festplatten bis zu 10 TB verwenden. Bei Importaufträgen wird nur das erste Datenvolume auf der Festplatte verarbeitet. Das Datenvolume muss mit NTFS formatiert sein. Beim Kopieren von Daten auf ein Festplattenlaufwerk kann der Anschluss direkt mithilfe eines 2,5-Zoll-SSD- oder eines 2,5- oder 3,5-Zoll-SATA II/III-Verbinders oder extern über einen externen 2,5-Zoll-SSD- oder einen 2,5- oder 3,5-Zoll-SATA II/III-USB-Adapter erfolgen.
  
> [!IMPORTANT]
> Externe Festplatten mit einem integrierten USB-Adapter werden vom Office 365-Importdienst nicht unterstützt. Darüber hinaus kann der Datenträger innerhalb des Gehäuses einer externen Festplatte nicht verwendet werden. Versenden Sie keine externen Festplatten. 
  
 **Wie viele Festplatten kann ich für einen einzelnen Importauftrag versenden?**
  
Sie können maximal 10 Festplatten für einen einzelnen Importauftrag versenden.
  
 **Wie lange dauert es nach dem Versand meiner Festplatten, bis sie im Microsoft-Rechenzentrum ankommen?**
  
Dies hängt von ein paar Dingen ab, z. B. von der Entfernung zum Microsoft-Rechenzentrum und der Art der Zustellung, die Sie zum Versenden Ihrer Festplatte verwendet haben (z. B. Lieferung am nächsten Tag, Lieferung in zwei Tagen oder Zustellung auf dem Landweg). Bei den meisten Zustelldiensten können Sie Sendungsverfolgungsnummern verwenden, um den Status der Lieferung nachzuverfolgen.
  
 **Wie lange dauert das Hochladen meiner PST-Dateien nach Azure, nachdem meine Festplatte im Microsoft Data Center eingetroffen ist?**
  
Nachdem Ihre Festplatte im Microsoft-Rechenzentrum empfangen wurde, dauert es zwischen 7 und 10 Werktage, bis Sie die PST-Dateien in den Azure-Speicherbereich Ihrer Organisation hochgeladen haben. Die PST-Dateien werden in einen Azure-BLOB-Container mit dem Namen **ingestiondata**hochgeladen. 
  
 **Wie lange dauert das Importieren einer PST-Datei in ein Postfach?**
  
Nachdem die PST-Dateien in den Azure-Speicherbereich hochgeladen wurden, analysiert Microsoft 365 die Daten in den PST-Dateien (auf sichere und sichere Weise), um das Alter der Elemente und die unterschiedlichen Nachrichtentypen zu identifizieren, die in den PST-Dateien enthalten sind. Nach Abschluss der Analyse können Sie alle in den PST-Dateien enthaltenen Daten importieren oder Filter festlegen, die steuern, welche Daten importiert werden sollen. Nachdem Sie den Importauftrag gestartet haben, wird eine PST-Datei in ein Microsoft 365-Postfach mit einer Rate von mindestens 24 GB pro Tag importiert. Wenn diese Rate nicht Ihren Anforderungen entspricht, sollten Sie ggf. andere Methoden zum Importieren von E-Mail-Daten in Office 365 in Betracht ziehen. Weitere Informationen finden Sie unter [Methoden zum Migrieren von mehreren E-Mail-Konten zu Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Wenn verschiedene PST-Dateien in unterschiedliche Zielpostfächer importiert werden, erfolgt der Importvorgang parallel, d. h. jedes PST-Postfach-Paar wird gleichzeitig importiert. Wenn mehrere PST-Dateien in dasselbe Postfach importiert werden, werden sie ebenfalls gleichzeitig importiert.
  
 **Wie lange verbleiben meine PST-Dateien, nachdem Microsoft sie in Azure hochgeladen hat, in Azure, bevor sie gelöscht werden?**
  
Alle PST-Dateien am Azure-Speicherort für Ihre Organisation (im BLOB-Container mit dem Namen **ingestiondata**) werden 30 Tage nach dem Erstellen des letzten importauftrags auf der Seite **PST-Dateien importieren** im Security & Compliance Center gelöscht. 
  
Dies bedeutet auch, dass aus dem Azure-Speicherbereich gelöschte PST-Dateien im Security & Compliance Center nicht mehr in der Dateiliste für einen abgeschlossenen Importauftrag angezeigt werden. Es kann zwar sein, dass auf der Seite **PST-Dateien importieren** im Security & Compliance Center ältere Importaufträge noch aufgeführt sind, die Liste der PST-Dateien könnte jedoch leer sein, wenn Sie die Details anzeigen. 
  
 **Welche Version des PST-Dateiformats wird für den Import in Microsoft 365 unterstützt?**
  
Es gibt zwei Versionen des PST-Dateiformats: ANSI und Unicode. Wir empfehlen den Import von PST-Dateien im Unicode-Format. Dateien, die das ANSI-PST-Dateiformat verwenden, wie die für Sprachen, die einen Doppelbyte-Zeichensatz (DBCS) verwenden, können jedoch auch in Microsoft 365 importiert werden. Weitere Informationen zum Importieren von ANSI-PST-Dateien finden Sie unter Schritt 3: [Verwenden des Laufwerk Versands zum Importieren von PST-Dateien in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Darüber hinaus können PST-Dateien aus Outlook 2007 und neueren Versionen in Office 365 importiert werden.
  
 **Gibt es eine Beschränkung der Nachrichtengröße beim Importieren von PST-Dateien?**
  
Ja. Wenn eine PST-Datei ein Postfachelement enthält, das größer als 150 MB ist, wird das Element beim Importvorgang übersprungen.
  
  **Wie behandelt der PST-Importprozess doppelte E-Mail-Elemente?**

Beim PST-Importprozess wird eine Überprüfung auf doppelte Elemente durchgeführt, und die Elemente werden nicht aus einer PST-Datei in das Postfach oder Archiv kopiert, wenn ein übereinstimmendes Element im Zielordner im Zielpostfach oder -archiv vorliegt. Wenn Sie dieselbe PST-Datei erneut importieren und einen anderen Zielordner (mithilfe der TargetRootFolder-Eigenschaft in der PST-Importzuordnungsdatei) angeben als den, den Sie in einem vorherigen Importauftrag angegeben haben, werden alle Elemente in der PST-Datei erneut importiert.
 
 **Werden Nachrichteneigenschaften, beispielsweise beim Senden oder empfangen der Nachricht, der Liste der Empfänger und anderer Eigenschaften, beibehalten, wenn PST-Dateien in ein Microsoft 365-Postfach importiert werden?**
  
Ja. Beim Importvorgang werden die Metadaten der ursprünglichen Nachricht nicht geändert.
  
 **Gibt es eine Beschränkung der Anzahl der Ebenen in einer Ordnerhierarchie für eine PST-Datei, die ich in ein Postfach importieren möchten?**
  
Ja. Sie können keine PST-Dateien mit 300 oder mehr Ebenen von geschachtelten Ordnern importieren.
  
 **Kann ich den Laufwerk Versand verwenden, um PST-Dateien in ein inaktives Postfach in Microsoft 365 zu importieren?**
  
Ja, diese Funktion ist jetzt verfügbar.
  
 **Kann ich PST-Dateien über den Laufwerksversand in ein Onlinearchivpostfach in einer Exchange-Hybridbereitstellung importieren?**
  
Ja, diese Funktion ist jetzt verfügbar. 
  
 **Kann ich den Laufwerkversand zum Importieren von PST-Dateien in öffentliche Ordner in Exchange Online verwenden?**
  
Nein, Sie können keine PST-Dateien in öffentliche Ordner importieren.
  
 **Kann Microsoft meine Festplatte zurücksetzen, bevor sie wieder an mich zurückgesendet wird?**
  
Nein, Microsoft kann Festplatten vor der Rücksendung an den Kunden nicht zurücksetzen. Festplatten werden in demselben Zustand zurückgesendet, in dem sie bei Microsoft eingegangen sind.
  
 **Kann Microsoft meine Festplatte vernichten, anstatt sie zurückzusenden?**
  
Nein, Microsoft kann Ihre Festplatte nicht vernichten. Festplatten werden in demselben Zustand zurückgesendet, in dem sie bei Microsoft eingegangen sind.
  
 **Welche Kurierdienste werden für die Rücksendung unterstützt?**
  
Wenn Sie Kunde in den Vereinigten Staaten oder in Europa sind, verwendet Microsoft FedEx für die Rücksendung Ihrer Festplatte. Für alle Regionen verwendet Microsoft DHL.
  
 **Wie hoch sind die Kosten für die Rücksendung?**
  
Die Kosten für die Rücksendung variieren je nach Entfernung zum Microsoft-Rechenzentrum, an das Sie Ihre Festplatte gesendet haben. Microsoft belastet Ihr FedEx- oder DHL-Konto für die Rücksendung Ihrer Festplatte. Sie tragen die Kosten für die Rücksendung.
  
 **Kann ich einen benutzerdefinierten Kurierdienst verwenden, z. B. FedEx Custom Shipping, um meine Festplatte an Microsoft zu senden?**
  
Ja.
  
 **Was muss ich beachten, wenn ich meine Festplatte in ein anderes Land versenden muss?**
  
Die an Microsoft versendete Festplatte muss möglicherweise internationale Grenzen überqueren. In diesem Falls sind Sie dafür verantwortlich, dass die Festplatte und die darin enthaltenen Daten in Übereinstimmung mit den geltenden Gesetzen importiert und/oder exportiert wurden. Stellen Sie vor dem Versenden einer Festplatten mit Ihren Beratern sicher, dass Ihre Festplatte und die Daten gesetzmäßig an das angegebene Microsoft-Rechenzentrum gesendet werden können. Dies hilft sicherzustellen, dass die Festplatte Microsoft zeitgerecht erreicht.
