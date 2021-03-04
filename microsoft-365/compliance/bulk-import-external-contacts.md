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
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="985a1-103">Massenimport externer Kontakte nach Exchange Online</span><span class="sxs-lookup"><span data-stu-id="985a1-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="985a1-104">**Dieser Artikel ist für Administratoren vorgesehen. Versuchen Sie, Kontakte in Ihr eigenes Postfach zu importieren? Siehe [Importieren von Kontakten in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="985a1-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="985a1-105">Verfügt Ihr Unternehmen über viele vorhandene Geschäftskontakte, die Sie in das freigegebene Adressbuch (auch als globale Adressliste bezeichnet) in Exchange Online eingeben möchten?</span><span class="sxs-lookup"><span data-stu-id="985a1-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="985a1-106">Möchten Sie externe Kontakte als Mitglieder von Verteilergruppen hinzufügen, wie dies mit Benutzern innerhalb Ihres Unternehmens möglich ist?</span><span class="sxs-lookup"><span data-stu-id="985a1-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="985a1-107">Wenn ja, können Sie Exchange Online PowerShell und eine CSV-Datei (durch Kommas getrennt) zum Massenimport externer Kontakte in Exchange Online verwenden.</span><span class="sxs-lookup"><span data-stu-id="985a1-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="985a1-108">Es ist ein Drei-Schritt-Prozess:</span><span class="sxs-lookup"><span data-stu-id="985a1-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="985a1-109">Schritt 1: Erstellen einer CSV-Datei, die Informationen zu den externen Kontakten enthält</span><span class="sxs-lookup"><span data-stu-id="985a1-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="985a1-110">Schritt 2: Erstellen der externen Kontakte mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="985a1-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="985a1-111">Schritt 3: Hinzufügen von Informationen zu den Eigenschaften der externen Kontakte</span><span class="sxs-lookup"><span data-stu-id="985a1-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="985a1-112">Nachdem Sie die folgenden Schritte zum Importieren von Kontakten ausgeführt haben, können Sie die folgenden zusätzlichen Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="985a1-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="985a1-113">Hinzufügen von weiteren externen Kontakten</span><span class="sxs-lookup"><span data-stu-id="985a1-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="985a1-114">Ausblenden externer Kontakte aus dem freigegebenen Adressbuch</span><span class="sxs-lookup"><span data-stu-id="985a1-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="985a1-115">Schritt 1: Erstellen einer CSV-Datei, die Informationen zu den externen Kontakten enthält</span><span class="sxs-lookup"><span data-stu-id="985a1-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="985a1-116">Der erste Schritt besteht im Erstellen einer CSV-Datei, die Informationen zu jedem externen Kontakt enthält, den Sie in Exchange Online importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="985a1-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="985a1-117">Kopieren Sie den folgenden Text in eine Textdatei in NotePad, und speichern Sie ihn auf Ihrem Desktop als ExternalContacts.csv mit dem Dateinamensuffix CSV; Beispiel: ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="985a1-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="985a1-118">Wenn Ihre Sprache Sonderzeichen enthält (z. B. **å**, **ä** und **ö** auf Schwedisch), speichern Sie die #A0 mit UTF-8 oder einer anderen #A1 beim Speichern der Datei in NotePad.</span><span class="sxs-lookup"><span data-stu-id="985a1-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="985a1-119">In der ersten Zeile oder Kopfzeile der CSV-Datei sind die Eigenschaften von Kontakten aufgeführt, die beim Importieren in Exchange Online verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="985a1-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="985a1-120">Jeder Eigenschaftenname wird durch ein Komma getrennt.</span><span class="sxs-lookup"><span data-stu-id="985a1-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="985a1-121">Jede Zeile unter der Kopfzeile stellt die Eigenschaftswerte zum Importieren eines einzelnen externen Kontakts dar.</span><span class="sxs-lookup"><span data-stu-id="985a1-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="985a1-122">Dieser Text enthält Beispieldaten, die Sie löschen können.</span><span class="sxs-lookup"><span data-stu-id="985a1-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="985a1-123">Löschen oder ändern Sie jedoch nicht die erste Zeile (Kopfzeile).</span><span class="sxs-lookup"><span data-stu-id="985a1-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="985a1-124">Es enthält alle Eigenschaften für die externen Kontakte.</span><span class="sxs-lookup"><span data-stu-id="985a1-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="985a1-125">Öffnen Sie die CSV-Datei in Microsoft Excel, um die CSV-Datei zu bearbeiten, da es viel einfacher ist, Excel zum Bearbeiten der CSV-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="985a1-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="985a1-126">Erstellen Sie eine Zeile für jeden Kontakt, den Sie in Exchange Online importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="985a1-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="985a1-127">Füllen Sie so viele Zellen wie möglich auf.</span><span class="sxs-lookup"><span data-stu-id="985a1-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="985a1-128">Diese Informationen werden im freigegebenen Adressbuch für jeden Kontakt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="985a1-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="985a1-129">Die folgenden Eigenschaften (die ersten vier Elemente in der Kopfzeile) sind zum Erstellen eines externen Kontakts erforderlich und müssen in der CSV-Datei aufgefüllt werden: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span><span class="sxs-lookup"><span data-stu-id="985a1-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="985a1-130">Der in Schritt 2 ausgeführte PowerShell-Befehl verwendet die Werte für diese Eigenschaften, um die Kontakte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="985a1-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="985a1-131">Schritt 2: Erstellen der externen Kontakte mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="985a1-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="985a1-132">Im nächsten Schritt verwenden Sie die in Schritt 1 und PowerShell erstellte CSV-Datei, um die in der CSV-Datei aufgeführten externen Kontakte massenimportiert in Exchange Online zu importieren.</span><span class="sxs-lookup"><span data-stu-id="985a1-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="985a1-133">Verbinden Sie PowerShell mit Ihrer Exchange Online-Organisation.</span><span class="sxs-lookup"><span data-stu-id="985a1-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="985a1-134">Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="985a1-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="985a1-135">Achten Sie darauf, den Benutzernamen und das Kennwort für Ihr globales Administratorkonto zu verwenden, wenn Sie eine Verbindung mit Exchange Online PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="985a1-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="985a1-136">Nachdem Sie PowerShell mit Exchange Online hergestellt haben, wechseln Sie zum Desktopordner, in dem Sie die #A0 in Schritt 1 gespeichert haben. beispiel: `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="985a1-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="985a1-137">Führen Sie den folgenden Befehl aus, um die externen Kontakte zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="985a1-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="985a1-138">Es kann eine Weile dauern, bis die neuen Kontakte erstellt werden, je nachdem, wie viele Sie importieren.</span><span class="sxs-lookup"><span data-stu-id="985a1-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="985a1-139">Wenn der Befehl ausgeführt wurde, zeigt PowerShell eine Liste der neuen Kontakte an, die erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="985a1-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="985a1-140">Wechseln Sie zum Anzeigen der neuen externen Kontakte zum Exchange Admin  Center (EAC), und klicken Sie dann auf \> **EmpfängerKontakte**.</span><span class="sxs-lookup"><span data-stu-id="985a1-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="985a1-141">Anweisungen zum Herstellen einer Verbindung mit der EAC finden Sie unter [Exchange Admin Center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span><span class="sxs-lookup"><span data-stu-id="985a1-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="985a1-142">Klicken Sie bei Bedarf auf **Aktualisieren,** um die Liste zu aktualisieren und die importierten externen Kontakte zu sehen.</span><span class="sxs-lookup"><span data-stu-id="985a1-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="985a1-143">Die importierten Kontakte werden im freigegebenen Adressbuch in Outlook und Outlook im Web angezeigt.</span><span class="sxs-lookup"><span data-stu-id="985a1-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="985a1-144">Sie können die Kontakte auch im Microsoft 365  Admin Center anzeigen, indem Sie zu \> **Benutzerkontakte gehen.**</span><span class="sxs-lookup"><span data-stu-id="985a1-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="985a1-145">Schritt 3: Hinzufügen von Informationen zu den Eigenschaften der externen Kontakte</span><span class="sxs-lookup"><span data-stu-id="985a1-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="985a1-146">Nachdem Sie den Befehl in Schritt 2 ausgeführt haben, werden die externen Kontakte erstellt, enthalten jedoch keine Kontakt- oder Organisationsinformationen, d. h. die Informationen aus den meisten Zellen in der CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="985a1-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="985a1-147">Dies liegt daran, dass beim Erstellen neuer externer Kontakte nur die erforderlichen Eigenschaften aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="985a1-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="985a1-148">Machen Sie sich keine Sorgen, wenn nicht alle Informationen in der CSV-Datei aufgefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="985a1-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="985a1-149">Wenn sie nicht da ist, wird sie nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="985a1-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="985a1-150">Verbinden Sie PowerShell mit Ihrer Exchange Online-Organisation.</span><span class="sxs-lookup"><span data-stu-id="985a1-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="985a1-151">Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="985a1-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="985a1-152">Wechseln Sie zum Desktopordner, in dem Sie die #A0 in Schritt 1 gespeichert haben. Beispiel: `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="985a1-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="985a1-153">Führen Sie die folgenden beiden Befehle aus, um die anderen Eigenschaften aus der CSV-Datei den externen Kontakten hinzuzufügen, die Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="985a1-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="985a1-154">Der  _Parameter Manager_ kann problematisch sein.</span><span class="sxs-lookup"><span data-stu-id="985a1-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="985a1-155">Wenn die Zelle in der CSV-Datei leer ist, wird ein Fehler angezeigt, und dem Kontakt werden keine Eigenschaftsinformationen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="985a1-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="985a1-156">Wenn Sie keinen Vorgesetzten angeben müssen, löschen Sie einfach aus dem vorherigen  ` -Manager $_.Manager ` PowerShell-Befehl.</span><span class="sxs-lookup"><span data-stu-id="985a1-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="985a1-157">Auch hier kann es eine Weile dauern, bis die Kontakte aktualisiert werden, je nachdem, wie viele Sie in Schritt 1 importiert haben.</span><span class="sxs-lookup"><span data-stu-id="985a1-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="985a1-158">So überprüfen Sie, ob die Eigenschaften den Kontakten hinzugefügt wurden:</span><span class="sxs-lookup"><span data-stu-id="985a1-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="985a1-159">Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="985a1-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="985a1-160">Klicken Sie auf einen Kontakt, und klicken Sie dann auf **Bearbeiten** ![ (Symbol), ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) um die Eigenschaften des Kontakts anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="985a1-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="985a1-161">Das ist alles.</span><span class="sxs-lookup"><span data-stu-id="985a1-161">That's it!</span></span> <span data-ttu-id="985a1-162">Benutzer können die Kontakte und die zusätzlichen Informationen im Adressbuch Outlook und Outlook im Web sehen.</span><span class="sxs-lookup"><span data-stu-id="985a1-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="985a1-163">Hinzufügen von weiteren externen Kontakten</span><span class="sxs-lookup"><span data-stu-id="985a1-163">Add more external contacts</span></span>

<span data-ttu-id="985a1-164">Sie können die Schritte 1 bis Schritt 3 wiederholen, um neue externe Kontakte in Exchange Online hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="985a1-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="985a1-165">Sie oder Benutzer in Ihrem Unternehmen können einfach eine neue Zeile in der CSV-Datei für den neuen Kontakt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="985a1-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="985a1-166">Anschließend können Sie die PowerShell-Befehle aus Schritt 2 und Schritt 3 ausführen, um Informationen zu den neuen Kontakten zu erstellen und hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="985a1-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="985a1-167">Wenn Sie den Befehl zum Erstellen neuer Kontakte ausführen, wird möglicherweise eine Fehlermeldung angezeigt, dass die zuvor erstellten Kontakte bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="985a1-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="985a1-168">Es wird jedoch jeder neue Kontakt erstellt, der der CSV-Datei hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="985a1-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="985a1-169">Ausblenden externer Kontakte aus dem freigegebenen Adressbuch></span><span class="sxs-lookup"><span data-stu-id="985a1-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="985a1-170">Einige Unternehmen verwenden möglicherweise nur externe Kontakte, damit sie als Mitglieder von Verteilergruppen hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="985a1-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="985a1-171">In diesem Szenario möchten sie möglicherweise externe Kontakte aus dem freigegebenen Adressbuch ausblenden.</span><span class="sxs-lookup"><span data-stu-id="985a1-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="985a1-172">Dazu gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="985a1-172">Here's how:</span></span>
  
1.  <span data-ttu-id="985a1-173">Verbinden Sie PowerShell mit Ihrer Exchange Online-Organisation.</span><span class="sxs-lookup"><span data-stu-id="985a1-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="985a1-174">Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="985a1-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="985a1-175">Führen Sie den folgenden Befehl aus, um einen einzelnen externen Kontakt auszublenden.</span><span class="sxs-lookup"><span data-stu-id="985a1-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="985a1-176">Führen Sie beispielsweise den folgenden Befehl aus, um Pilar Pinilla aus dem freigegebenen Adressbuch auszublenden:</span><span class="sxs-lookup"><span data-stu-id="985a1-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="985a1-177">Führen Sie den folgenden Befehl aus, um alle externen Kontakte aus dem freigegebenen Adressbuch auszublenden:</span><span class="sxs-lookup"><span data-stu-id="985a1-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="985a1-178">Nachdem Sie sie ausgeblendet haben, werden externe Kontakte nicht im freigegebenen Adressbuch angezeigt, Sie können sie jedoch weiterhin als Mitglieder einer Verteilergruppe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="985a1-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
