---
title: Übersicht über das Importieren von PST-Dateien Ihrer Organisation in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 'Für Administratoren: Im Folgenden wird erläutert, wie der Importdienst im Security & Compliance Center verwendet werden kann, um E-Mail-Daten (PST-Dateien) in einem Massenimport in Benutzerpostfächer in Exchange Online zu importieren. In diesem Thema wird auf häufig gestellte Fragen eingegangen und erläutert, wie der PST-Importprozess funktioniert.'
ms.openlocfilehash: 948ba22ff88b72a3af92edb39bfdc28cfde4c385
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "39218840"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Übersicht über das Importieren von PST-Dateien Ihrer Organisation in Office 365

> [!NOTE]
> Dieser Artikel richtet sich an Administratoren. Möchten Sie PST-Dateien in Ihr eigenes Postfach importieren? Siehe [Importieren von E-Mails, Kontakten und Kalendern aus einer Outlook-PST-Datei](https://go.microsoft.com/fwlink/p/?LinkID=785075).

Sie können den Importdienst im Security & Compliance Center verwenden, um PST-Dateien in einem Massenimportvorgang schnell in Exchange Online-Postfächer in Ihrer Office 365-Organisation zu importieren. Es gibt zwei Methoden zum Importieren von PST-Dateien in Office 365:
   
- **Netzwerk-Upload** ![Cloud-Upload](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png): Laden Sie die PST-Dateien über das Netzwerk in einen temporären Azure-Speicherort in der Microsoft-Cloud hoch. Verwenden Sie anschließend den Office 365-Importdienst, um die PST-Daten in Postfächer in Ihrer Office 365-Organisation zu importieren. 

- **Laufwerkversand** ![Festplatte](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png): Sie kopieren die PST-Dateien auf eine mit BitLocker verschlüsselte Festplatte und senden das Laufwerk dann physisch an Microsoft. Nachdem Microsoft die Festplatte erhalten hat, laden Mitarbeiter im Rechenzentrum die Daten in einen temporären Azure-Speicherort in der Microsoft-Cloud hoch. Anschließend verwenden Sie den Office 365-Importdienst, um die Daten in Postfächer in Ihrer Office 365-Organisation zu importieren. 

## <a name="step-by-step-instructions"></a>Schrittweise Anweisungen
  
Ausführliche schrittweise Anweisungen zum Massenimport von PST-Dateien Ihrer Organisation in Office 365 finden Sie in den folgenden Artikeln. 
   
- [Verwenden des Netzwerkuploads zum Importieren von PST-Dateien in Office 365](use-network-upload-to-import-pst-files.md)
- [Verwenden des Laufwerkversands zum Importieren von PST-Dateien in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Wie das Importieren von PST-Dateien abläuft

Es folgen eine Darstellung und Beschreibung des vollständigen PST-Importprozesses. In der Darstellung ist der wesentliche Workflow abgebildet und sind die Unterschiede zwischen den Methoden Netzwerkupload und Laufwerkversand hervorgehoben.
  
![Workflow eines PST-Importprozesses](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **PST-Importtool und Schlüssel für den privaten Azure-Speicherort herunterladen**: Der erste Schritt besteht darin, das Tool und den Zugriffsschlüssel herunterzuladen, die dazu verwendet werden, die PST-Dateien hochzuladen oder auf eine Festplatte zu kopieren. Sie erhalten das Tool und den Schlüssel über die Seite **Import** im Security & Compliance Center. Der Schlüssel stellt Ihnen (oder Mitarbeitern im Microsoft-Rechenzentrum) die Berechtigungen bereit, die erforderlich sind, um PST-Dateien in einen privaten und sicheren Azure-Speicherort hochzuladen. Dieser Zugriffsschlüssel ist für Ihr Unternehmen eindeutig und verhindert nicht autorisierten Zugriff auf Ihre PST-Dateien, nachdem diese in die Microsoft-Cloud hochgeladen wurden. Für das Importieren von PST-Dateien in Office 365 ist es nicht erforderlich, dass Ihre Organisation über ein eigenes Azure-Abonnement verfügt. 
    
2. **PST-Dateien hochladen oder kopieren**: Der nächste Schritt hängt davon ab, ob Sie die PST-Dateien über Netzwerkupload oder Laufwerkversand importieren. In beiden Fällen verwenden Sie das Tool und den sicheren Speicherschlüssel, die Sie im vorherigen Schritt erhalten haben.
    
    - **Netzwerkupload**: Ihre PST-Dateien werden mithilfe des Tools "AzCopy.exe" (heruntergeladen in Schritt 1) in einen Azure-Speicherort in der Microsoft-Cloud hochgeladen. Der Azure-Speicherort, in den Sie Ihre PST-Dateien hochladen, befindet sich im selben regionalen Microsoft-Rechenzentrum wie Ihre Office 365-Organisation. 
    
      Damit Sie die PST-Dateien, die Sie in Office 365 importieren möchten, hochladen können, müssen sich diese in einer Dateifreigabe oder auf einem Dateiserver in Ihrer Organisation befinden.
    
    - **Laufwerkversand**: Ihre PST-Dateien werden mithilfe des Tools "WAImportExport.exe" (heruntergeladen in Schritt 1) auf die Festplatte kopiert. Dieses Tool verschlüsselt die Festplatte mit BitLocker und kopiert die PST-Dateien dann auf die Festplatte. Wie bei einem Netzwerkupload müssen sich die PST-Dateien, die Sie auf die Festplatte kopieren möchten, in einer Dateifreigabe oder auf einem Dateiserver in Ihrer Organisation befinden.
    
3. **Erstellung einer PST-Importzuordnungsdatei**: Nachdem die PST-Dateien in den Azure-Speicherort hochgeladen oder auf eine Festplatte kopiert wurden, besteht der nächste Schritt darin, eine Datei mit kommagetrennten Werten (CSV-Datei) zu erstellen, die angibt, in welche Benutzerpostfächer die PST-Dateien importiert werden (wobei eine PST-Datei in das primäre Postfach eines Benutzers oder in dessen Archivpostfach importiert werden kann). Der Office 365-Importdienst verwendet die Informationen, um die PST-Dateien importieren. 
    
4. **Erstellung eines PST-Importauftrag**: Im nächsten Schritt wird auf der Seite **Import** im Security & Compliance Center ein PST-Importauftrag erstellt und die im vorherigen Schritt erstellte PST-Importzuordnungsdatei gesendet. Bei einem Netzwerkupload (die PST-Dateien wurden in Azure hochgeladen) analysiert Office 365 die Daten in den PST-Dateien und gibt Ihnen die Möglichkeit, Filter festzulegen, mit denen gesteuert wird, welche Daten tatsächlich in die Postfächer importiert werden, die in der PST-Importzuordnungsdatei angegeben sind. 
    
    Bei einem Laufwerkversand werden an diesem Punkt des Prozesses einige weitere Schritte ausgeführt.
    
    - Sie senden die Festplatte physisch an ein Microsoft-Rechenzentrum (die Versandadresse für das Microsoft-Rechenzentrum wird angezeigt, wenn der Importauftrag erstellt wird).
    
    - Nachdem die Festplatte bei Microsoft eingetroffen ist, laden Mitarbeiter des Rechenzentrums die PST-Dateien auf der Festplatte in den Azure-Speicherort für Ihre Organisation hoch. Wie bereits zuvor erläutert, werden Ihre PST-Dateien in einen Azure-Speicherbereich hochgeladen, der sich im selben regionalen Microsoft-Rechenzentrum wie Ihre Office 365-Organisation befindet.
    
      > [!NOTE]
      > Die PST-Dateien auf der Festplatte werden innerhalb von 7 bis 10 Werktagen nach dem Eintreffen der Festplatte in Azure hochgeladen. 
  
      Wie beim Netzwerkuploadprozess analysiert Office 365 dann die Daten in den PST-Dateien und gibt Ihnen die Möglichkeit, Filter festzulegen, mit denen gesteuert wird, welche Daten tatsächlich in die Postfächer importiert werden, die in der PST-Importzuordnungsdatei angegeben sind.
    
    - Microsoft liefert die Festplatte an Sie zurück. 
    
5. **Filterung der PST-Daten, die in Postfächer importiert werden sollen**: Nachdem der Importauftrag erstellt wurde (und nachdem die PST-Dateien aus einem Laufwerkversandauftrag in den Azure-Speicherbereich hochgeladen wurden), analysiert Office 365 die Daten in den PST-Dateien (gefahrlos und sicher), indem das Alter der Elemente und die verschiedenen Nachrichtentypen bestimmt werden, die in den PST-Dateien enthalten sind. Wenn die Analyse abgeschlossen ist und die Daten für den Import bereit sind, haben Sie die Möglichkeit, alle in den PST-Dateien enthaltenen Daten zu importieren oder die zu importierenden Daten einzuschränken, indem Sie Filter festlegen, mit denen gesteuert wird, welche Daten importiert werden. 
    
6. **Starten des PST-Importauftrags**: Nachdem der Importauftrag gestartet wurde, verwendet Office 365 die Informationen in der PST-Importzuordnungsdatei, um die PST-Dateien aus dem Azure-Speicherort in Benutzerpostfächer zu importieren. Statusinformationen zu dem Importauftrag (einschließlich Informationen zu jeder PST-Datei, die importiert wird) werden auf der Seite **Import** im Security & Compliance Center angezeigt. Wenn der Importauftrag abgeschlossen ist, wird sein Status auf **Abgeschlossen** festgelegt.
  
## <a name="why-import-email-data-to-office-365"></a>Warum sollten E-Mail-Daten in Office 365 importiert werden?

- Das Importieren von PST-Dateien in Benutzerpostfächer ist eine Methode, die E-Mails Ihrer Organisation in Office 365 zu migrieren.
    
- Sie können das Feature [Intelligenter Import](filter-data-when-importing-pst-files.md) zum Filtern der Elemente in PST-Dateien verwenden, die tatsächlich in die Zielpostfächer importiert werden sollen. Auf diese Weise können Sie den Datenimport einschränken, indem Sie Filter festlegen, die steuern, welche Daten importiert werden. 
    
- Das Importieren von E-Mail-Daten in Office 365 hilft Ihnen beim Erfüllen der Complianceanforderungen Ihrer Organisation, indem es Ihnen folgende Möglichkeiten gibt:
    
  - Aktivieren von [Archivpostfächern](enable-archive-mailboxes.md) und [unbegrenzter Archivierung](unlimited-archiving.md), um Benutzern zusätzlichen Postfachspeicherplatz zur Verfügung zu stellen. 
    
  - Kennzeichnen von Postfächern mit [Aufbewahrung für juristische Zwecke](https://go.microsoft.com/fwlink/?linkid=841243), um Inhalte aufzubewahren. 
    
  - Verwenden des [Tools für die Inhaltssuche](content-search.md) zum Durchsuchen von Postfachinhalten. 
    
  - Verwenden von [eDiscovery-Fällen](ediscovery-cases.md) zur Verwaltung juristischer Prüfungen in Ihrer Organisation. 
    
  - Verwenden von [Aufbewahrungsrichtlinien](retention-policies.md) im Security & Compliance Center, um zu steuern, wie lange Postfachinhalte aufbewahrt werden, und Löschen von Inhalten, nachdem der Aufbewahrungszeitraum abgelaufen ist. 

  - Verwenden von [Kommunikationscompliancerichtlinien](communication-compliance.md) zur Überprüfung von Nachrichten, um sicherzustellen, dass sie den Nachrichtenstandards entsprechen, und einen Klassifizierungstyp hinzuzufügen.
    
- Das Importieren von Daten in Office 365 schützt vor Datenverlust. E-Mail-Daten, die in Office 365 importiert werden, erben die Features für hohe Verfügbarkeit von Exchange Online.
    
- E-Mail-Daten in Office 365 stehen den Benutzern von allen Geräten aus zur Verfügung, da sie in der Cloud gespeichert sind.
    
## <a name="importing-sharepoint-data-to-office-365"></a>Importieren von SharePoint-Daten in Office 365

Sie können Dateien und Dokumente auch in SharePoint-Websites und OneDrive-Konten in Ihrer Office 365-Organisation importieren. Weitere Informationen finden Sie in den folgenden Artikeln:

- [Migrieren zu SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [Einführung in das SharePoint-Migrationstool](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [Migrieren zu SharePoint Online mithilfe von PowerShell](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [Migrieren von Dateifreigabe-Inhalten zu SharePoint Online mithilfe von Azure Data Box](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>Häufig gestellte Fragen zum Importieren von PST-Dateien in Office 365
  
Hier folgen einige häufig gestellte Fragen zum Massenimportvorgang von PST-Dateien in Office 365-Postfächer mithilfe des Office 365-Importdienstes. 
  
- [Verwenden des Netzwerkuploads zum Importieren von PST-Dateien](#using-network-upload-to-import-pst-files)
  
- [Verwenden des Laufwerkversands zum Importieren von PST-Dateien](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Verwenden des Netzwerkuploads zum Importieren von PST-Dateien

 **Welche Berechtigungen sind für das Erstellen von Importaufträgen im Office 365-Importdienst erforderlich?**
  
Ihnen muss die Rolle für den Postfachimport/-export in Exchange Online zugewiesen werden, damit Sie PST-Dateien in Office 365-Postfächer importieren können. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Alternativ können Sie eine neue Rollengruppe erstellen, dieser die Rolle für den Postfachimport/-export zuweisen und sich selbst oder andere Benutzer dann als Mitglied hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppe in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Darüber hinaus muss eine der folgenden Bedingungen erfüllt sein, um Importaufträge im Security & Compliance Center erstellen zu können:
  
- Ihnen muss in Exchange Online die Rolle „E-Mail-Empfänger“ zugewiesen sein. Standardmäßig wird diese Rolle den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen.
    
    Oder
    
- Sie müssen ein globaler Administrator innerhalb Ihrer Office 365-Organisation sein.
    
> [!TIP]
> Erwägen Sie, in Exchange Online eine neue Rollengruppe speziell zum Importieren von PST-Dateien nach Office 365 zu erstellen. Legen Sie für die neue Rollengruppe als mindestens erforderliche Berechtigungen zum Importieren von PST-Dateien die Rollen "Postfachimport/-export" und "E-Mail-Empfänger" fest, und fügen Sie anschließend Mitglieder hinzu. 
  
 **Wo ist der Netzwerkupload verfügbar?**
  
Der Netzwerkupload ist derzeit in den USA, Kanada, Brasilien, Großbritannien, Europa, Indien, Ostasien, Südostasien, Japan, der Republik Korea und Australien verfügbar. Der Netzwerkupload wird in Kürze in weiteren Regionen zur Verfügung gestellt.
  
 **Welche Preise ergeben sich für den Import von PST-Dateien über den Netzwerkupload?**
  
Using network upload to import PST files is free.
  
Dies bedeutet auch, dass aus dem Azure-Speicherbereich gelöschte PST-Dateien im Microsoft 365 Admin Center nicht mehr in der Dateiliste für einen abgeschlossenen Importauftrag angezeigt werden. Es kann zwar vorkommen, dass ältere Importaufträge noch auf der Seite **Importieren von Daten in Office 365** aufgelistet sind, die Liste der PST-Dateien könnte jedoch leer sein, wenn Sie die Details anzeigen. 
  
 **Welche Version des PST-Dateiformats wird für den Import in Office 365 unterstützt?**
  
Es gibt zwei Versionen des PST-Dateiformats: ANSI und Unicode. Wir empfehlen den Import von PST-Dateien im Unicode-Format. Allerdings können auch PST-Dateien im ANSI-Format (z. B. bei Sprachen mit Doppelbyte-Zeichensatz) in Office 365 importiert werden. Weitere Informationen zum Importieren von PST-Dateien im ANSI-Format finden Sie in Schritt 4 unter [Verwenden des Netzwerkuploads zum Importieren von PST-Dateien in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).
  
Darüber hinaus können PST-Dateien aus Outlook 2007 und neueren Versionen in Office 365 importiert werden.
  
 **Wie lange verbleiben meine PST-Dateien, nachdem ich sie in den Azure-Speicherbereich hochgeladen habe, in Azure, bevor sie gelöscht werden?**
  
Wenn Sie PST-Dateien mit der Netzwerkupload-Methode importieren, werden die Dateien in einen Azure-BLOB-Container namens **ingestiondata** hochgeladen. Wenn auf der Seite **Importieren** im Security & Compliance Center keine Importaufträge in Bearbeitung sind, werden alle PST-Dateien im Container **ingestiondata** in Azure 30 Tage nach Erstellung des letzten Importauftrags im Security & Compliance Center gelöscht. Daraus folgt, dass Sie innerhalb von 30 Tagen nach dem Hochladen von PST-Dateien nach Azure einen neuen Importauftrag im Security & Compliance Center erstellen müssen (wie in Schritt 5 in den Netzwerkupload-Anweisungen beschrieben). 
  
Dies bedeutet auch, dass aus dem Azure-Speicherbereich gelöschte PST-Dateien im Security & Compliance Center nicht mehr in der Dateiliste für einen abgeschlossenen Importauftrag angezeigt werden. Es kann zwar sein, dass auf der Seite **Importieren** im Security & Compliance Center ältere Importaufträge noch aufgeführt sind, die Liste der PST-Dateien könnte jedoch leer sein, wenn Sie die Details anzeigen. 
  
 **Wie lange dauert das Importieren einer PST-Datei in ein Postfach?**
  
Das hängt von der Kapazität des Netzwerks ab, aber normalerweise dauert es mehrere Stunden für jedes Terabyte (TB) an Daten, bis es in den Azure-Speicherbereich für Ihr Unternehmen hochgeladen wurde. Nachdem die PST-Dateien in den Azure-Speicherbereich kopiert wurden, wird eine PST-Datei mit einer Übertragungsrate von mindestens 24 GB pro Tag in ein Office 365-Postfach importiert. Wenn diese Rate nicht Ihren Anforderungen entspricht, sollten Sie ggf. andere Methoden zum Migrieren von E-Mail-Daten zu Office 365 in Betracht ziehen. Weitere Informationen finden Sie unter [Methoden zum Migrieren von mehreren E-Mail-Konten zu Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Wenn verschiedene PST-Dateien in unterschiedliche Zielpostfächer importiert werden, erfolgt der Importvorgang parallel, d. h. jedes PST-Postfach-Paar wird gleichzeitig importiert. Wenn mehrere PST-Dateien in dasselbe Postfach importiert werden, werden sie ebenfalls gleichzeitig importiert.
  
 **Gibt es eine Beschränkung der Nachrichtengröße beim Importieren von PST-Dateien?**
  
Ja. Wenn eine PST-Datei ein Postfachelement enthält, das größer als 150 MB ist, wird das Element beim Importvorgang übersprungen.
  
 **Bleiben die Eigenschaften der Nachrichten (z. B. Sende- oder Empfangsdatum, Empfängerliste und andere Eigenschaften) erhalten, wenn PST-Dateien in ein Office 365-Postfach importiert werden?**
  
Ja. Beim Importvorgang werden die Metadaten der ursprünglichen Nachricht nicht geändert.
  
 **Gibt es eine Beschränkung der Anzahl der Ebenen in einer Ordnerhierarchie für eine PST-Datei, die ich in ein Postfach importieren möchten?**
  
Ja. Sie können keine PST-Dateien mit 300 oder mehr Ebenen von geschachtelten Ordnern importieren.
  
 **Kann ich PST-Dateien über den Netzwerkupload in ein inaktives Postfach in Office 365 importieren?**
  
Ja, diese Funktion ist jetzt verfügbar.
  
 **Kann ich PST-Dateien über den Netzwerkupload in ein Onlinearchivpostfach in einer Exchange-Hybridbereitstellung importieren?**
  
Ja, diese Funktion ist jetzt verfügbar. 
  
 **Kann ich den Netzwerkupload zum Importieren von PST-Dateien in öffentliche Ordner in Exchange Online verwenden?**
  
Nein, Sie können keine PST-Dateien in öffentliche Ordner importieren.
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Verwenden des Laufwerkversands zum Importieren von PST-Dateien

 **Welche Berechtigungen sind für das Erstellen von Importaufträgen im Office 365-Importdienst erforderlich?**
  
Zum Importieren von PST-Dateien in Office 365-Postfächer muss Ihnen die Rolle „Postfachimport/-export“ zugewiesen sein. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Alternativ können Sie eine neue Rollengruppe erstellen, dieser die Rolle für den Postfachimport/-export zuweisen und sich selbst oder andere Benutzer dann als Mitglied hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppe in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Darüber hinaus muss eine der folgenden Bedingungen erfüllt sein, um Importaufträge im Security & Compliance Center erstellen zu können:
  
- Ihnen muss in Exchange Online die Rolle „E-Mail-Empfänger“ zugewiesen sein. Standardmäßig wird diese Rolle den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen.
    
    Oder
    
- Sie müssen ein globaler Administrator innerhalb Ihrer Office 365-Organisation sein.
    
> [!TIP]
> Erwägen Sie, in Exchange Online eine neue Rollengruppe speziell zum Importieren von PST-Dateien nach Office 365 zu erstellen. Legen Sie für die neue Rollengruppe als mindestens erforderliche Berechtigungen zum Importieren von PST-Dateien die Rollen "Postfachimport/-export" und "E-Mail-Empfänger" fest, und fügen Sie anschließend Mitglieder hinzu. 
  
 **Wo ist der Laufwerkversand verfügbar?**
  
Der Laufwerkversand ist derzeit in den USA, Kanada, Brasilien, Vereinigtem Königreich, Europa, Indien, Ostasien, Südostasien, Japan, Republik Korea und Australien verfügbar. Der Laufwerkversand wird in Kürze in weiteren Regionen zur Verfügung gestellt.
  
 **Welche kommerziellen Lizenzvereinbarungen unterstützen den Laufwerksversand?**
  
Der Laufwerkversand zum Importieren von PST-Dateien in Office 365 steht über ein Microsoft Enterprise Agreement (EA) zur Verfügung. Der Laufwerkversand steht nicht im Rahmen von Microsoft Products und Services Agreement (MPSA) zur Verfügung.
  
 **Was kostet die Verwendung des Laufwerkversands zum Importieren von PST-Dateien in Office 365?**
  
Die Kosten für den Laufwerksversand zum Importieren von PST-Dateien in Office 365-Postfächer betragen ca. 2 Euro pro GB an Daten. Wenn Sie z. B. eine Festplatte versenden, die 1.000 GB (1 TB) an PST-Dateien enthält, betragen die Kosten beispielsweise 2.000 Euro. Um die Importgebühren zu zahlen, können Sie mit einem Partner zusammenarbeiten. Informationen zum Suchen von Partnern finden Sie unter [Suchen nach Ihrem Office 365-Partner oder -Händler](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **Welche Festplattentypen werden für den Laufwerkversand unterstützt?**
  
Nur 2,5-Zoll-Festkörperlaufwerke (SSDs) oder interne 2,5-/3,5-Zoll-Festplatten (SATA II/III) werden für die Verwendung mit dem Office 365-Importdienst unterstützt. Sie können Festplatten bis zu 10 TB verwenden. Bei Importaufträgen wird nur das erste Datenvolume auf der Festplatte verarbeitet. Das Datenvolume muss mit NTFS formatiert sein. Beim Kopieren von Daten auf ein Festplattenlaufwerk kann der Anschluss direkt mithilfe eines 2,5-Zoll-SSD- oder eines 2,5- oder 3,5-Zoll-SATA II/III-Verbinders oder extern über einen externen 2,5-Zoll-SSD- oder einen 2,5- oder 3,5-Zoll-SATA II/III-USB-Adapter erfolgen.
  
> [!IMPORTANT]
> Externe Festplatten mit einem integrierten USB-Adapter werden vom Office 365-Importdienst nicht unterstützt. Darüber hinaus kann der Datenträger innerhalb des Gehäuses einer externen Festplatte nicht verwendet werden. Versenden Sie keine externen Festplatten. 
  
 **Wie viele Festplatten kann ich für einen einzelnen Importauftrag versenden?**
  
Sie können maximal 10 Festplatten für einen einzelnen Importauftrag versenden.
  
 **Wie lange dauert es nach dem Versand meiner Festplatten, bis sie im Microsoft-Rechenzentrum ankommen?**
  
Dies hängt von ein paar Dingen ab, z. B. von der Entfernung zum Microsoft-Rechenzentrum und der Art der Zustellung, die Sie zum Versenden Ihrer Festplatte verwendet haben (z. B. Lieferung am nächsten Tag, Lieferung in zwei Tagen oder Zustellung auf dem Landweg). Bei den meisten Zustelldiensten können Sie Sendungsverfolgungsnummern verwenden, um den Status der Lieferung nachzuverfolgen.
  
 **Wie lange dauert das Hochladen meiner PST-Dateien nach Azure, nachdem meine Festplatte im Microsoft Data Center eingetroffen ist?**
  
Nachdem Ihre Festplatte im Microsoft-Rechenzentrum eingetroffen ist, werden die PST-Dateien innerhalb von 7 bis 10 Werktagen in den Microsoft Azure-Speicherbereich für Ihre Organisation hochgeladen. Die PST-Dateien werden in einen Azure-BLOB-Container mit dem Namen `ingestiondata` hochgeladen. 
  
 **Wie lange dauert das Importieren einer PST-Datei in ein Postfach?**
  
Nachdem die PST-Dateien in den Azure-Speicherbereich hochgeladen wurden, werden die Daten in den PST-Dateien (auf gefahrlose und sichere Weise) von Office 365 analysiert, um das Alter der Elemente und die unterschiedlichen Nachrichtentypen zu bestimmen, die in den PST-Dateien enthalten sind. Nach Abschluss der Analyse können Sie alle in den PST-Dateien enthaltenen Daten importieren oder Filter festlegen, die steuern, welche Daten importiert werden sollen. Nachdem Sie den Importvorgang gestartet haben, wird eine PST-Datei mit einer Übertragungsrate von mindestens 24 GB pro Tag in ein Office 365-Postfach importiert. Wenn diese Rate nicht Ihren Anforderungen entspricht, sollten Sie ggf. andere Methoden zum Importieren von E-Mail-Daten in Office 365 in Betracht ziehen. Weitere Informationen finden Sie unter [Methoden zum Migrieren von mehreren E-Mail-Konten zu Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Wenn verschiedene PST-Dateien in unterschiedliche Zielpostfächer importiert werden, erfolgt der Importvorgang parallel, d. h. jedes PST-Postfach-Paar wird gleichzeitig importiert. Wenn mehrere PST-Dateien in dasselbe Postfach importiert werden, werden sie ebenfalls gleichzeitig importiert.
  
 **Wie lange verbleiben meine PST-Dateien, nachdem Microsoft sie in Azure hochgeladen hat, in Azure, bevor sie gelöscht werden?**
  
Alle PST-Dateien am Azure-Speicherort für Ihre Organisation (im BLOB-Container mit dem Namen `ingestiondata`) werden 30 Tage nach Erstellung des letzten Importauftrags auf der Seite **Importieren** im Security & Compliance Center gelöscht. 
  
Dies bedeutet auch, dass aus dem Azure-Speicherbereich gelöschte PST-Dateien im Security & Compliance Center nicht mehr in der Dateiliste für einen abgeschlossenen Importauftrag angezeigt werden. Es kann zwar sein, dass auf der Seite **Importieren** im Security & Compliance Center ältere Importaufträge noch aufgeführt sind, die Liste der PST-Dateien könnte jedoch leer sein, wenn Sie die Details anzeigen. 
  
 **Welche Version des PST-Dateiformats wird für den Import in Office 365 unterstützt?**
  
Es gibt zwei Versionen des PST-Dateiformats: ANSI und Unicode. Wir empfehlen den Import von PST-Dateien im Unicode-Format. Allerdings können auch PST-Dateien im ANSI-Format (z. B. bei Sprachen mit Doppelbyte-Zeichensatz) in Office 365 importiert werden. Weitere Informationen zum Importieren von PST-Dateien im ANSI-Format finden Sie in Schritt 3 unter [Verwenden des Laufwerkversands zum Importieren von PST-Dateien Ihrer Organisation in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Darüber hinaus können PST-Dateien aus Outlook 2007 und neueren Versionen in Office 365 importiert werden.
  
 **Gibt es eine Beschränkung der Nachrichtengröße beim Importieren von PST-Dateien?**
  
Ja. Wenn eine PST-Datei ein Postfachelement enthält, das größer als 150 MB ist, wird das Element beim Importvorgang übersprungen.
  
 **Bleiben die Eigenschaften der Nachrichten (z. B. Sende- oder Empfangsdatum, Empfängerliste und andere Eigenschaften) erhalten, wenn PST-Dateien in ein Office 365-Postfach importiert werden?**
  
Ja. Beim Importvorgang werden die Metadaten der ursprünglichen Nachricht nicht geändert.
  
 **Gibt es eine Beschränkung der Anzahl der Ebenen in einer Ordnerhierarchie für eine PST-Datei, die ich in ein Postfach importieren möchten?**
  
Ja. Sie können keine PST-Dateien mit 300 oder mehr Ebenen von geschachtelten Ordnern importieren.
  
 **Kann ich PST-Dateien über den Laufwerksversand in ein inaktives Postfach in Office 365 importieren?**
  
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
