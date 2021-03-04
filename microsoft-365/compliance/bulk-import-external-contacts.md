---
title: Massenimport externer Kontakte nach Exchange Online
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
ms.openlocfilehash: 475afc3b0622c404b50ebe5549bb5be85af80c5e
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423252"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Massenimport externer Kontakte nach Exchange Online

**Dieser Artikel ist für Administratoren vorgesehen. Versuchen Sie, Kontakte in Ihr eigenes Postfach zu importieren? Siehe [Importieren von Kontakten in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
Verfügt Ihr Unternehmen über viele vorhandene Geschäftskontakte, die Sie in das freigegebene Adressbuch (auch als globale Adressliste bezeichnet) in Exchange Online eingeben möchten? Möchten Sie externe Kontakte als Mitglieder von Verteilergruppen hinzufügen, wie dies mit Benutzern innerhalb Ihres Unternehmens möglich ist? Wenn ja, können Sie Exchange Online PowerShell und eine CSV-Datei (durch Kommas getrennt) zum Massenimport externer Kontakte in Exchange Online verwenden. Es ist ein Drei-Schritt-Prozess:
  
[Schritt 1: Erstellen einer CSV-Datei, die Informationen zu den externen Kontakten enthält](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Schritt 2: Erstellen der externen Kontakte mit PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Schritt 3: Hinzufügen von Informationen zu den Eigenschaften der externen Kontakte](#step-3-add-information-to-the-properties-of-the-external-contacts)

Nachdem Sie die folgenden Schritte zum Importieren von Kontakten ausgeführt haben, können Sie die folgenden zusätzlichen Aufgaben ausführen:
  
- [Hinzufügen von weiteren externen Kontakten](#add-more-external-contacts)
  
- [Ausblenden externer Kontakte aus dem freigegebenen Adressbuch](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Schritt 1: Erstellen einer CSV-Datei, die Informationen zu den externen Kontakten enthält

Der erste Schritt besteht im Erstellen einer CSV-Datei, die Informationen zu jedem externen Kontakt enthält, den Sie in Exchange Online importieren möchten. 
  
1. Kopieren Sie den folgenden Text in eine Textdatei in NotePad, und speichern Sie ihn auf Ihrem Desktop als ExternalContacts.csv mit dem Dateinamensuffix CSV; Beispiel: ExternalContacts.csv.
    
    > [!TIP]
    > Wenn Ihre Sprache Sonderzeichen enthält (z. B. **å**, **ä** und **ö** auf Schwedisch), speichern Sie die #A0 mit UTF-8 oder einer anderen #A1 beim Speichern der Datei in NotePad. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    In der ersten Zeile oder Kopfzeile der CSV-Datei sind die Eigenschaften von Kontakten aufgeführt, die beim Importieren in Exchange Online verwendet werden können. Jeder Eigenschaftenname wird durch ein Komma getrennt. Jede Zeile unter der Kopfzeile stellt die Eigenschaftswerte zum Importieren eines einzelnen externen Kontakts dar. 
    
    > [!NOTE]
    > Dieser Text enthält Beispieldaten, die Sie löschen können. Löschen oder ändern Sie jedoch nicht die erste Zeile (Kopfzeile). Es enthält alle Eigenschaften für die externen Kontakte. 
  
2. Öffnen Sie die CSV-Datei in Microsoft Excel, um die CSV-Datei zu bearbeiten, da es viel einfacher ist, Excel zum Bearbeiten der CSV-Datei zu verwenden.
    
3. Erstellen Sie eine Zeile für jeden Kontakt, den Sie in Exchange Online importieren möchten. Füllen Sie so viele Zellen wie möglich auf. Diese Informationen werden im freigegebenen Adressbuch für jeden Kontakt angezeigt. 
    
    > [!IMPORTANT]
    >  Die folgenden Eigenschaften (die ersten vier Elemente in der Kopfzeile) sind zum Erstellen eines externen Kontakts erforderlich und müssen in der CSV-Datei aufgefüllt werden: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. Der in Schritt 2 ausgeführte PowerShell-Befehl verwendet die Werte für diese Eigenschaften, um die Kontakte zu erstellen. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Schritt 2: Erstellen der externen Kontakte mit PowerShell

Im nächsten Schritt verwenden Sie die in Schritt 1 und PowerShell erstellte CSV-Datei, um die in der CSV-Datei aufgeführten externen Kontakte massenimportiert in Exchange Online zu importieren. 
  
1.  Verbinden Sie PowerShell mit Ihrer Exchange Online-Organisation. Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Achten Sie darauf, den Benutzernamen und das Kennwort für Ihr globales Administratorkonto zu verwenden, wenn Sie eine Verbindung mit Exchange Online PowerShell herstellen. 
    
2. Nachdem Sie PowerShell mit Exchange Online hergestellt haben, wechseln Sie zum Desktopordner, in dem Sie die #A0 in Schritt 1 gespeichert haben. beispiel: `C:\Users\Administrator\desktop` .
    
3. Führen Sie den folgenden Befehl aus, um die externen Kontakte zu erstellen:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Es kann eine Weile dauern, bis die neuen Kontakte erstellt werden, je nachdem, wie viele Sie importieren. Wenn der Befehl ausgeführt wurde, zeigt PowerShell eine Liste der neuen Kontakte an, die erstellt wurden. 
    
4. Wechseln Sie zum Anzeigen der neuen externen Kontakte zum Exchange Admin  Center (EAC), und klicken Sie dann auf \> **EmpfängerKontakte**. 
    
    > [!TIP]
    > Anweisungen zum Herstellen einer Verbindung mit der EAC finden Sie unter [Exchange Admin Center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197). 
  
5. Klicken Sie bei Bedarf auf **Aktualisieren,** um die Liste zu aktualisieren und die importierten externen Kontakte zu sehen. 
    
    Die importierten Kontakte werden im freigegebenen Adressbuch in Outlook und Outlook im Web angezeigt.
    
    > [!NOTE]
    > Sie können die Kontakte auch im Microsoft 365  Admin Center anzeigen, indem Sie zu \> **Benutzerkontakte gehen.** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Schritt 3: Hinzufügen von Informationen zu den Eigenschaften der externen Kontakte

Nachdem Sie den Befehl in Schritt 2 ausgeführt haben, werden die externen Kontakte erstellt, enthalten jedoch keine Kontakt- oder Organisationsinformationen, d. h. die Informationen aus den meisten Zellen in der CSV-Datei. Dies liegt daran, dass beim Erstellen neuer externer Kontakte nur die erforderlichen Eigenschaften aufgefüllt werden. Machen Sie sich keine Sorgen, wenn nicht alle Informationen in der CSV-Datei aufgefüllt sind. Wenn sie nicht da ist, wird sie nicht hinzugefügt.
  
1.  Verbinden Sie PowerShell mit Ihrer Exchange Online-Organisation. Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Wechseln Sie zum Desktopordner, in dem Sie die #A0 in Schritt 1 gespeichert haben. Beispiel: `C:\Users\Administrator\desktop` .
    
3. Führen Sie die folgenden beiden Befehle aus, um die anderen Eigenschaften aus der CSV-Datei den externen Kontakten hinzuzufügen, die Sie in Schritt 2 erstellt haben.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Der  _Parameter Manager_ kann problematisch sein. Wenn die Zelle in der CSV-Datei leer ist, wird ein Fehler angezeigt, und dem Kontakt werden keine Eigenschaftsinformationen hinzugefügt. Wenn Sie keinen Vorgesetzten angeben müssen, löschen Sie einfach aus dem vorherigen  ` -Manager $_.Manager ` PowerShell-Befehl. 
  
    Auch hier kann es eine Weile dauern, bis die Kontakte aktualisiert werden, je nachdem, wie viele Sie in Schritt 1 importiert haben. 
    
4. So überprüfen Sie, ob die Eigenschaften den Kontakten hinzugefügt wurden: 
    
1. Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.
    
2. Klicken Sie auf einen Kontakt, und klicken Sie dann auf **Bearbeiten** ![ (Symbol), ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) um die Eigenschaften des Kontakts anzeigen zu können. 
    
Das ist alles. Benutzer können die Kontakte und die zusätzlichen Informationen im Adressbuch Outlook und Outlook im Web sehen.
  
## <a name="add-more-external-contacts"></a>Hinzufügen von weiteren externen Kontakten

Sie können die Schritte 1 bis Schritt 3 wiederholen, um neue externe Kontakte in Exchange Online hinzuzufügen. Sie oder Benutzer in Ihrem Unternehmen können einfach eine neue Zeile in der CSV-Datei für den neuen Kontakt hinzufügen. Anschließend können Sie die PowerShell-Befehle aus Schritt 2 und Schritt 3 ausführen, um Informationen zu den neuen Kontakten zu erstellen und hinzuzufügen.
  
> [!NOTE]
> Wenn Sie den Befehl zum Erstellen neuer Kontakte ausführen, wird möglicherweise eine Fehlermeldung angezeigt, dass die zuvor erstellten Kontakte bereits vorhanden sind. Es wird jedoch jeder neue Kontakt erstellt, der der CSV-Datei hinzugefügt wurde. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Ausblenden externer Kontakte aus dem freigegebenen Adressbuch>

Einige Unternehmen verwenden möglicherweise nur externe Kontakte, damit sie als Mitglieder von Verteilergruppen hinzugefügt werden können. In diesem Szenario möchten sie möglicherweise externe Kontakte aus dem freigegebenen Adressbuch ausblenden. Dazu gehen Sie so vor:
  
1.  Verbinden Sie PowerShell mit Ihrer Exchange Online-Organisation. Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Führen Sie den folgenden Befehl aus, um einen einzelnen externen Kontakt auszublenden.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Führen Sie beispielsweise den folgenden Befehl aus, um Pilar Pinilla aus dem freigegebenen Adressbuch auszublenden:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Führen Sie den folgenden Befehl aus, um alle externen Kontakte aus dem freigegebenen Adressbuch auszublenden:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Nachdem Sie sie ausgeblendet haben, werden externe Kontakte nicht im freigegebenen Adressbuch angezeigt, Sie können sie jedoch weiterhin als Mitglieder einer Verteilergruppe hinzufügen.
