---
title: Gleichzeitiges Hinzufügen mehrerer Benutzer zu Microsoft 365-Administratorhilfe
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: 'In diesem Artikel erfahren Sie, wie Sie Microsoft 365 for Business mehrere Benutzer aus einer Liste in einer Tabellenkalkulation oder einer anderen CSV-formatierten Datei hinzufügen. Sehen Sie sich ein Video auf YouTube an, in dem das Hinzufügen von Konten zu Microsoft 365 erläutert wird. Am Ende dieses Prozesses verfügt jeder Benutzer mit einem Konto über ein Microsoft 365-Postfach. '
ms.openlocfilehash: c75f16233a85f48be44082ba3ec9ffb82ef18ff9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690904"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>Gleichzeitiges Hinzufügen mehrerer Benutzer zu Microsoft 365-Administratorhilfe

Jede Person in Ihrem Team benötigt ein Benutzerkonto, bevor Sie sich anmelden und auf Microsoft 365-Dienste wie e-Mail und Office zugreifen kann. Wenn das Team viele Personen umfasst, können Sie deren Konten aus einer Excel-Tabelle oder einer anderen, im CSV-Format gespeicherten, Datei gleichzeitig hinzufügen. [Was ist eine CSV-Datei?](add-several-users-at-the-same-time.md#__toc316652088)
  
> [!NOTE] 
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>Hinzufügen mehrerer Benutzer im Microsoft 365 Admin Center

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an. 
    
2. Wählen Sie im Admin Center **Benutzer** \> **Aktive Benutzer** aus.

3. Wählen Sie **mehrere Benutzer hinzufügen**aus.

4. Im Bereich **Mehrere Benutzer importieren** können Sie eine CSV-Beispieldatei mit oder ohne eingetragene Beispieldaten optional herunterladen. 
    
    Ihre Tabelle muss **dieselben Spaltenüberschriften** wie die Beispieltabelle enthalten ("Benutzername", "Vorname" usw.). Wenn Sie die Vorlage verwenden, öffnen Sie sie in einem Textbearbeitungstool, z. B. Editor. Sie sollten nach Möglichkeit alle Daten in Zeile 1 beibehalten und Daten nur in Zeile 2 und die Zeilen darunter eingeben. 
    
    Darüber hinaus muss Ihre Tabelle für jeden Benutzer Werte für den Benutzernamen (wie "berend@contoso.com") und einen Anzeigenamen (wie "Berend Klein") enthalten. 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-9821,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-9822,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-9823,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-9824,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-9825,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. Geben Sie in dem Feld einen Dateipfad ein, oder wählen Sie **Durchsuchen** aus, um zum Speicherort der CSV-Datei zu navigieren. Wählen Sie dann **Überprüfen** aus.
  
    Wenn es Probleme mit der Datei gibt, wird eine entsprechende Meldung angezeigt. Sie können auch eine Protokolldatei herunterladen.
    
5. Im Dialogfeld **Benutzeroptionen festlegen** können Sie den Anmeldestatus festlegen und die Produktlizenz auswählen, die allen Benutzern zugewiesen werden soll. 
    
6. Im Dialogfeld **Ergebnisse anzeigen** können Sie auswählen, ob die Ergebnisse an Sie selbst oder an andere Benutzer (Kennwörter im Nur-Text-Format) gesendet werden sollen. Außerdem können Sie sehen, wie viele Benutzer erstellt wurden und ob Sie weitere Lizenzen erwerben müssen, um sie einigen der neuen Benutzer zuzuweisen. 

## <a name="next-steps"></a>Nächste Schritte
<a name="bk_preview"> </a>

- Da diese Personen nun über Konten verfügen, müssen Sie [Microsoft 365 oder Office 2016 auf einem PC oder Mac herunterladen und installieren oder neu installieren](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658). Jede Person in Ihrem Team kann Microsoft 365 auf bis zu fünf PCs oder Macs installieren. 
    
- Jede Person kann auch [Office-Apps und e-Mail auf einem mobilen Gerät](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) auf bis zu 5 Tablets und 5 Telefonen wie iPhones, iPads und Android-Telefone und-Tablets einrichten. Hiermit können Office-Dateien von praktisch überall aus bearbeitet werden. 
    
    Eine End-to-End-Liste der Setupschritte finden Sie unter [Einrichten von Microsoft 365 for Business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) . 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>Weitere Informationen zum Hinzufügen von Benutzern zu Microsoft 365
<a name="bk_preview"> </a>

### <a name="not-sure-what-csv-format-is"></a>Was ist eine CSV-Datei?
<a name="__toc316652088"> </a>

Eine CSV-Datei ist eine Datei mit durch Kommas getrennten Werten. Sie können eine Datei wie diese mit einem beliebigen Text-Editor oder Tabellenkalkulationsprogramm wie beispielsweise Excel erstellen oder bearbeiten.
  
Sie können [diese Beispieltabelle](https://www.microsoft.com/download/details.aspx?id=45485) als Ausgangspunkt herunterladen. Beachten Sie, dass Microsoft 365 Spaltenüberschriften in der ersten Zeile erfordert, damit Sie nicht durch eine andere ersetzen. 
  
Speichern Sie die Datei unter einem neuen Namen, und geben Sie das Format "CSV" an.
  
![Ein Bild, das zeigt, wie eine Datei in Excel im CSV-Format gespeichert wird](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
Beim Speichern der Datei werden Sie wahrscheinlich darüber informiert, dass einige Features in Ihrer Arbeitsmappe verloren gehen, wenn Sie die Datei im CSV-Format speichern. Dies geht in Ordnung. Klicken Sie auf **Ja**, um den Vorgang fortzusetzen. 
  
![Eine Abbildung der Eingabeaufforderung, die in Excel möglicherweise angezeigt wird und fragt, ob Sie die Datei tatsächlich im CSV-Format speichern möchten](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>Tipps zum Formatieren Ihrer Tabelle
<a name="__toc314595848"> </a>

- **Benötige ich dieselben Spaltenüberschriften wie in der Beispieltabelle?** Ja. Die erste Zeile der Beispieltabelle enthält die Spaltenüberschriften. Diese Überschriften sind erforderlich. Erstellen Sie für jeden Benutzer, den Sie Microsoft 365 hinzufügen möchten, eine Zeile unter der Überschrift. Wenn Sie Spaltenüberschriften hinzufügen, ändern oder löschen, kann Microsoft 365 möglicherweise keine Benutzer anhand der Informationen in der Datei erstellen. 
    
- **Was kann ich tun, wenn ich nicht über alle Informationen verfüge, die bei jedem Benutzer erforderlich sind?** Der Benutzername und der Anzeigename sind unbedingt erforderlich; Sie können keinen neuen Benutzer ohne diese Angaben hinzufügen. Falls Ihnen einige der anderen Informationen fehlen, wie beispielsweise das Fax, können Sie ein Leerzeichen plus das von Ihnen verwendete Trennzeichen eingeben und so festlegen, dass das Feld leer bleiben soll. 
    
- **Wie klein oder groß kann die Kalkulationstabelle sein?** Das Arbeitsblatt muss mindestens zwei Zeilen aufweisen. One is for the column headings (the user data column label) and one for the user. You cannot have more than 251 rows. If you need to import more than 250 users, you can create more than one spreadsheet. 
    
- **Welche Sprachen kann ich verwenden?** Wenn Sie Ihre Kalkulationstabelle erstellen, können Sie Benutzerdaten Spaltenbeschriftungen in einer beliebigen Sprache oder in beliebigen Zeichen eingeben, aber Sie dürfen die Reihenfolge der Beschriftungen nicht ändern, wie im Beispiel gezeigt. You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format. 
    
- **Was geschieht, wenn ich Benutzer aus verschiedenen Ländern oder Regionen hinzufüge?** Erstellen Sie eine separate Tabelle für jeden Bereich. Sie müssen den Assistenten "Massenhinzufügung von Benutzern" mit jeder Tabelle schrittweise durchlaufen. Geben Sie dabei einen einzigen Standort für alle Benutzer an, die in der Datei, mit der Sie arbeiten, enthalten sind. 
    
- **Bestehen Beschränkungen bei der Anzahl der Zeichen, die ich verwenden kann?** Die folgende Tabelle zeigt die Beschriftungen für Benutzerdatenspalten sowie die maximale Zeichenanzahl für jedes Element der Beispieltabelle. 
    
|**Beschriftung für Benutzerdatenspalte**|**Maximale Zeichenanzahl**|
|:-----|:-----|
|Benutzername (erforderlich)  <br/> |79 einschließlich des @-Zeichens im Format Name@Domain. \<extension\> . Der Alias des Benutzers darf 50 Zeichen nicht überschreiten, und der Domänenname darf 48 Zeichen nicht überschreiten.  <br/> |
|Vorname  <br/> |64  <br/> |
|Nachname  <br/> |64  <br/> |
|Anzeigename (erforderlich)  <br/> |256  <br/> |
|Position  <br/> |64  <br/> |
|Abteilung  <br/> |64  <br/> |
|Büronummer  <br/> |128  <br/> |
|Rufnummer  <br/> |64  <br/> |
|Mobiltelefon  <br/> |64  <br/> |
|Fax  <br/> |64  <br/> |
|Adresse  <br/> |1023  <br/> |
|Ort  <br/> |128  <br/> |
|Bundesland oder Kanton  <br/> |128  <br/> |
|PLZ  <br/> |40  <br/> |
|Land oder Region  <br/> |128  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>Gibt es weiterhin Probleme beim Hinzufügen von Benutzern zu Microsoft 365?

- **Überprüfen Sie sorgfältig, ob die Tabelle richtig formatiert wurde.** Überprüfen Sie, ob die Spaltenüberschriften mit den Überschriften in der Beispieldatei übereinstimmen. Vergewissern Sie sich, dass Sie die Regeln für die maximale Zeichenanzahl eingehalten haben und dass jedes Feld durch ein Trennzeichen getrennt ist. 
    
- **Wenn die neuen Benutzer in Microsoft 365 nicht sofort angezeigt werden, warten Sie einige Minuten.** Es kann eine Weile dauern, bis Änderungen in allen Diensten in Microsoft 365 durchlaufen werden. 
    
## <a name="related-articles"></a>Verwandte Artikel

[Hinzufügen von Benutzern einzeln oder in Massen zu Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users)




