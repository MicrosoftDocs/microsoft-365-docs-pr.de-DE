---
title: Massenimport externer Kontakte in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Erfahren Sie, wie Administratoren Exchange Online PowerShell und eine CSV-Datei zum Massenimport externer Kontakte in die globale Adressliste verwenden können.
ms.openlocfilehash: b6f7c430cef13985a679abf42a2f91d9605bf556
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596262"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Massenimport externer Kontakte in Exchange Online

**Dieser Artikel richtet sich an Administratoren. Versuchen Sie, Kontakte in Ihr eigenes Postfach zu importieren? Siehe [Importieren von Kontakten in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
Verfügt Ihr Unternehmen über viele vorhandene Geschäftskontakte, die Sie in Exchange Online in das freigegebene Adressbuch einbeziehen möchten (auch als globale Adressliste bezeichnet)? Möchten Sie externe Kontakte als Mitglieder von Verteilergruppen hinzufügen, so wie Sie es mit Benutzern in Ihrem Unternehmen tun können? Wenn dies der Fall ist, können Sie mit Exchange Online PowerShell und einer CSV-Datei (durch trennzeichengetrennte Werte) externe Kontakte in Exchange Online Massenimportieren. Es handelt sich um einen dreistufigen Prozess:
  
[Schritt 1: Erstellen einer CSV-Datei, die Informationen zu den externen Kontakten enthält](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Schritt 2: Erstellen der externen Kontakte mit PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Schritt 3: Hinzufügen von Informationen zu den Eigenschaften der externen Kontakte](#step-3-add-information-to-the-properties-of-the-external-contacts)

Nachdem Sie diese Schritte zum Importieren von Kontakten ausgeführt haben, können Sie diese zusätzlichen Aufgaben ausführen:
  
- [Hinzufügen weiterer externer Kontakte](#add-more-external-contacts)
  
- [Ausblenden externer Kontakte aus dem freigegebenen Adressbuch](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Schritt 1: Erstellen einer CSV-Datei, die Informationen zu den externen Kontakten enthält

Der erste Schritt besteht darin, eine CSV-Datei zu erstellen, die Informationen zu jedem externen Kontakt enthält, den Sie in Exchange Online importieren möchten. 
  
1. Kopieren Sie den folgenden Text in eine Textdatei im Editor, und speichern Sie ihn auf dem Desktop als CSV-Datei unter Verwendung des Datei namens Suffixes ". csv"; Beispiel: ExternalContacts. CSV.
    
    > [!TIP]
    > Wenn Ihre Sprache Sonderzeichen enthält (wie **å**, **ä**und **ö** auf Schwedisch), speichern Sie die CSV-Datei mit UTF-8 oder einer anderen Unicode-Codierung, wenn Sie die Datei im Editor speichern. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    In der ersten Zeile oder Kopfzeile der CSV-Datei werden die Eigenschaften von Kontakten aufgelistet, die beim Importieren in Exchange Online verwendet werden können. Jeder Eigenschaften Name wird durch ein Komma getrennt. Jede Zeile unter der Kopfzeile stellt die Eigenschaftswerte zum Importieren eines einzelnen externen Kontakts dar. 
    
    > [!NOTE]
    > Dieser Text enthält Beispieldaten, die Sie löschen können. Löschen oder ändern Sie jedoch nicht die erste Zeile (Kopfzeile). Sie enthält alle Eigenschaften für die externen Kontakte. 
  
2. Öffnen Sie die CSV-Datei in Microsoft Excel, um die CSV-Datei zu bearbeiten, da es viel einfacher ist, Excel zum Bearbeiten der CSV-Datei zu verwenden.
    
3. Erstellen Sie eine Zeile für jeden Kontakt, den Sie in Exchange Online importieren möchten. Füllen Sie so viele Zellen wie möglich. Diese Informationen werden für jeden Kontakt im freigegebenen Adressbuch angezeigt. 
    
    > [!IMPORTANT]
    >  Die folgenden Eigenschaften (bei denen es sich um die ersten vier Elemente in der Kopfzeile handelt) sind erforderlich, um einen externen Kontakt zu erstellen, der in der CSV-Datei aufgefüllt werden muss: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. Mit dem PowerShell-Befehl, den Sie in Schritt 2 ausführen, werden die Werte für diese Eigenschaften zum Erstellen der Kontakte verwendet. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Schritt 2: Erstellen der externen Kontakte mit PowerShell

Der nächste Schritt besteht darin, die CSV-Datei zu verwenden, die Sie in Schritt 1 und PowerShell erstellt haben, um Massenimport der in der CSV-Datei aufgeführten externen Kontakte in Exchange Online durchführen zu können. 
  
1.  Verbinden Sie PowerShell mit Ihrer Exchange Online Organisation. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Achten Sie darauf, den Benutzernamen und das Kennwort für Ihr Office 365 globales Administratorkonto zu verwenden, wenn Sie eine Verbindung mit Exchange Online PowerShell herstellen. 
    
2. Nachdem Sie PowerShell mit Exchange Online verbunden haben, wechseln Sie zu dem Desktop Ordner, in dem Sie die CSV-Datei in Schritt 1 gespeichert haben. zum Beispiel `C:\Users\Administrator\desktop`.
    
3. Führen Sie den folgenden Befehl aus, um die externen Kontakte zu erstellen:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Es kann eine Weile dauern, bis die neuen Kontakte erstellt werden, je nachdem, wie viele importiert werden. Wenn der Befehl ausgeführt wird, zeigt PowerShell eine Liste der neuen Kontakte an, die erstellt wurden. 
    
4. Um die neuen externen Kontakte anzuzeigen, wechseln Sie zur Exchange-Verwaltungskonsole (EAC), und klicken Sie dann auf **Empfänger** \> **Kontakte**. 
    
    > [!TIP]
    > Anweisungen zum Herstellen einer Verbindung mit der Exchange-Verwaltungskonsole finden Sie unter [Exchange Admin Center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197). 
  
5. Klicken Sie bei Bedarf auf **Aktualisieren** , um die Liste zu aktualisieren und die importierten externen Kontakte anzuzeigen. 
    
    Die importierten Kontakte werden im freigegebenen Adressbuch in Outlook und Outlook im Internet angezeigt.
    
    > [!NOTE]
    > Sie können die Kontakte auch im Microsoft 365 Admin Center anzeigen, indem Sie zu **Benutzer** \> **Kontakte**wechseln. 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Schritt 3: Hinzufügen von Informationen zu den Eigenschaften der externen Kontakte

Nachdem Sie den Befehl in Schritt 2 ausgeführt haben, werden die externen Kontakte erstellt, Sie enthalten jedoch keine Kontakt-oder Organisationsinformationen, also die Informationen aus den meisten Zellen in der CSV-Datei. Dies liegt daran, dass beim Erstellen neuer externer Kontakte nur die erforderlichen Eigenschaften aufgefüllt werden. Machen Sie sich keine Sorgen, wenn Sie nicht alle Informationen in der CSV-Datei aufgefüllt haben. Wenn er nicht vorhanden ist, wird er nicht hinzugefügt.
  
1.  Verbinden Sie PowerShell mit Ihrer Exchange Online Organisation. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Wechseln Sie zum Desktop Ordner, in dem Sie die CSV-Datei in Schritt 1 gespeichert haben; Beispiel: `C:\Users\Administrator\desktop`.
    
3. Führen Sie die folgenden beiden Befehle aus, um die anderen Eigenschaften aus der CSV-Datei zu den externen Kontakten hinzuzufügen, die Sie in Schritt 2 erstellt haben.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Der Parameter _Manager_ ist möglicherweise problematisch. Wenn die Zelle in der CSV-Datei leer ist, wird eine Fehlermeldung angezeigt, und dem Kontakt werden keine der Eigenschaftsinformationen hinzugefügt. Wenn Sie keinen Vorgesetzten angeben müssen, löschen ` -Manager $_.Manager ` Sie einfach den vorherigen PowerShell-Befehl. 
  
    Auch hier kann es eine Weile dauern, bis die Kontakte aktualisiert werden, je nachdem, wie viele Sie in Schritt 1 importiert haben. 
    
4. So stellen Sie sicher, dass die Eigenschaften den Kontakten hinzugefügt wurden: 
    
1. Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.
    
2. Klicken Sie auf einen Kontakt, **** ![und klicken Sie](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) dann auf Bearbeitungssymbol bearbeiten, um die Eigenschaften des Kontakts anzuzeigen. 
    
Das ist alles. Benutzer können die Kontakte und die zusätzlichen Informationen im Adressbuch Outlook und Outlook im Internet anzeigen.
  
## <a name="add-more-external-contacts"></a>Hinzufügen weiterer externer Kontakte

Sie können die Schritte 1 bis Schritt 3 wiederholen, um neue externe Kontakte in Exchange Online hinzuzufügen. Sie oder Benutzer in Ihrem Unternehmen können einfach eine neue Zeile in der CSV-Datei für den neuen Kontakt hinzufügen. Anschließend können Sie die PowerShell-Befehle aus Schritt 2 und Schritt 3 ausführen, um Informationen zu erstellen und zu den neuen Kontakten hinzuzufügen.
  
> [!NOTE]
> Wenn Sie den Befehl zum Erstellen neuer Kontakte ausführen, erhalten Sie möglicherweise eine Fehlermeldung, dass die zuvor erstellten Kontakte bereits vorhanden sind. Jeder neue Kontakt, der der CSV-Datei hinzugefügt wurde, wird jedoch erstellt. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Ausblenden externer Kontakte aus dem freigegebenen Adressbuch>

Einige Unternehmen können externe Kontakte nur verwenden, damit Sie als Mitglieder von Verteilergruppen hinzugefügt werden können. In diesem Szenario möchten Sie möglicherweise externe Kontakte aus dem freigegebenen Adressbuch ausblenden. Dazu gehen Sie so vor:
  
1.  Verbinden Sie PowerShell mit Ihrer Exchange Online Organisation. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Führen Sie den folgenden Befehl aus, um einen einzelnen externen Kontakt auszublenden.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Um beispielsweise Pilar Pinilla aus dem freigegebenen Adressbuch auszublenden, führen Sie den folgenden Befehl aus:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Um alle externen Kontakte aus dem freigegebenen Adressbuch auszublenden, führen Sie den folgenden Befehl aus:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Nachdem Sie diese ausgeblendet haben, werden externe Kontakte nicht im freigegebenen Adressbuch angezeigt, Sie können Sie jedoch dennoch als Mitglieder einer Verteilergruppe hinzufügen.
