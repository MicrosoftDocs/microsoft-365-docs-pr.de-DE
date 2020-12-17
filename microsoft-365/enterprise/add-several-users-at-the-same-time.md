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
ms.openlocfilehash: 71e1d1f9261fc58e9f49fac5050e07fd7b8839e3
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698267"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="98d2b-105">Gleichzeitiges Hinzufügen mehrerer Benutzer zu Microsoft 365-Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="98d2b-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="98d2b-106">Jede Person in Ihrem Team benötigt ein Benutzerkonto, bevor Sie sich anmelden und auf Microsoft 365-Dienste wie e-Mail und Office zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="98d2b-106">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office.</span></span> <span data-ttu-id="98d2b-107">Wenn das Team viele Personen umfasst, können Sie deren Konten aus einer Excel-Tabelle oder einer anderen, im CSV-Format gespeicherten, Datei gleichzeitig hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-107">If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format.</span></span> [<span data-ttu-id="98d2b-108">Was ist eine CSV-Datei?</span><span class="sxs-lookup"><span data-stu-id="98d2b-108">Not sure what CSV format is?</span></span>](add-several-users-at-the-same-time.md#__toc316652088)
  
> [!NOTE] 
> <span data-ttu-id="98d2b-109">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="98d2b-110">Hinzufügen mehrerer Benutzer im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="98d2b-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="98d2b-111">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an.</span><span class="sxs-lookup"><span data-stu-id="98d2b-111">Sign in to Microsoft 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="98d2b-112">Wählen Sie im Admin Center **Benutzer** \> **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="98d2b-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="98d2b-113">Wählen Sie **mehrere Benutzer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="98d2b-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="98d2b-114">Im Bereich **Mehrere Benutzer importieren** können Sie eine CSV-Beispieldatei mit oder ohne eingetragene Beispieldaten optional herunterladen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span> 
    
    <span data-ttu-id="98d2b-115">Das Arbeitsblatt muss **exakt dieselben Spaltenüberschriften** wie das Beispiel 1 enthalten (Benutzername, Vorname usw.).</span><span class="sxs-lookup"><span data-stu-id="98d2b-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="98d2b-116">Wenn Sie die Vorlage verwenden, öffnen Sie Sie in einem Text Bearbeitungstool wie Notepad, und ziehen Sie es vor, alle Daten in Zeile 1 allein zu lassen und nur Daten in Zeilen 2 und darunter einzugeben.</span><span class="sxs-lookup"><span data-stu-id="98d2b-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span> 
    
    <span data-ttu-id="98d2b-117">Darüber hinaus muss Ihre Tabelle für jeden Benutzer Werte für den Benutzernamen (wie "berend@contoso.com") und einen Anzeigenamen (wie "Berend Klein") enthalten.</span><span class="sxs-lookup"><span data-stu-id="98d2b-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span> 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="98d2b-118">Geben Sie in dem Feld einen Dateipfad ein, oder wählen Sie **Durchsuchen** aus, um zum Speicherort der CSV-Datei zu navigieren. Wählen Sie dann **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="98d2b-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="98d2b-p104">Wenn es Probleme mit der Datei gibt, wird eine entsprechende Meldung angezeigt. Sie können auch eine Protokolldatei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>
    
5. <span data-ttu-id="98d2b-121">Im Dialogfeld **Benutzeroptionen festlegen** können Sie den Anmeldestatus festlegen und die Produktlizenz auswählen, die allen Benutzern zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="98d2b-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span> 
    
6. <span data-ttu-id="98d2b-122">Im Dialogfeld **Ergebnisse anzeigen** können Sie auswählen, ob die Ergebnisse an Sie selbst oder an andere Benutzer (Kennwörter im Nur-Text-Format) gesendet werden sollen. Außerdem können Sie sehen, wie viele Benutzer erstellt wurden und ob Sie weitere Lizenzen erwerben müssen, um sie einigen der neuen Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="98d2b-123">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="98d2b-123">Next steps</span></span>
<span data-ttu-id="98d2b-124"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="98d2b-124"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="98d2b-125">Da diese Personen nun über Konten verfügen, müssen Sie [Microsoft 365 oder Office 2016 auf einem PC oder Mac herunterladen und installieren oder neu installieren](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span><span class="sxs-lookup"><span data-stu-id="98d2b-125">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="98d2b-126">Jede Person in Ihrem Team kann Microsoft 365 auf bis zu fünf PCs oder Macs installieren.</span><span class="sxs-lookup"><span data-stu-id="98d2b-126">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span> 
    
- <span data-ttu-id="98d2b-127">Jede Person kann auch [Office-Apps und e-Mail auf einem mobilen Gerät](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) auf bis zu 5 Tablets und 5 Telefonen wie iPhones, iPads und Android-Telefone und-Tablets einrichten.</span><span class="sxs-lookup"><span data-stu-id="98d2b-127">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="98d2b-128">Hiermit können Office-Dateien von praktisch überall aus bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="98d2b-128">This way they can edit Office files from anywhere.</span></span> 
    
    <span data-ttu-id="98d2b-129">Eine End-to-End-Liste der Setupschritte finden Sie unter [Einrichten von Microsoft 365 for Business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) .</span><span class="sxs-lookup"><span data-stu-id="98d2b-129">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span> 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="98d2b-130">Weitere Informationen zum Hinzufügen von Benutzern zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="98d2b-130">More information about how to add users to Microsoft 365</span></span>
<span data-ttu-id="98d2b-131"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="98d2b-131"><a name="bk_preview"> </a></span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="98d2b-132">Was ist eine CSV-Datei?</span><span class="sxs-lookup"><span data-stu-id="98d2b-132">Not sure what CSV format is?</span></span>
<span data-ttu-id="98d2b-133"><a name="__toc316652088"> </a></span><span class="sxs-lookup"><span data-stu-id="98d2b-133"><a name="__toc316652088"> </a></span></span>

<span data-ttu-id="98d2b-p107">Eine CSV-Datei ist eine Datei mit durch Kommas getrennten Werten. Sie können eine Datei wie diese mit einem beliebigen Text-Editor oder Tabellenkalkulationsprogramm wie beispielsweise Excel erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="98d2b-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="98d2b-136">Sie können [diese Beispieltabelle](https://www.microsoft.com/download/details.aspx?id=45485) als Ausgangspunkt herunterladen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-136">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="98d2b-137">Beachten Sie, dass Microsoft 365 Spaltenüberschriften in der ersten Zeile erfordert, damit Sie nicht durch eine andere ersetzen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-137">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="98d2b-138">Speichern Sie die Datei unter einem neuen Namen, und geben Sie das Format "CSV" an.</span><span class="sxs-lookup"><span data-stu-id="98d2b-138">Save the file with a new name, and specify CSV format.</span></span>
  
![Ein Bild, das zeigt, wie eine Datei in Excel im CSV-Format gespeichert wird](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="98d2b-p109">Beim Speichern der Datei werden Sie wahrscheinlich darüber informiert, dass einige Features in Ihrer Arbeitsmappe verloren gehen, wenn Sie die Datei im CSV-Format speichern. Dies geht in Ordnung. Klicken Sie auf **Ja**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-p109">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span> 
  
![Eine Abbildung der Eingabeaufforderung, die in Excel möglicherweise angezeigt wird und fragt, ob Sie die Datei tatsächlich im CSV-Format speichern möchten](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="98d2b-144">Tipps zum Formatieren Ihrer Tabelle</span><span class="sxs-lookup"><span data-stu-id="98d2b-144">Tips for formatting your spreadsheet</span></span>
<span data-ttu-id="98d2b-145"><a name="__toc314595848"> </a></span><span class="sxs-lookup"><span data-stu-id="98d2b-145"><a name="__toc314595848"> </a></span></span>

- <span data-ttu-id="98d2b-146">**Benötige ich dieselben Spaltenüberschriften wie in der Beispieltabelle?**</span><span class="sxs-lookup"><span data-stu-id="98d2b-146">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="98d2b-147">Ja.</span><span class="sxs-lookup"><span data-stu-id="98d2b-147">Yes.</span></span> <span data-ttu-id="98d2b-148">Die erste Zeile der Beispieltabelle enthält die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="98d2b-148">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="98d2b-149">Diese Überschriften sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98d2b-149">These headings are required.</span></span> <span data-ttu-id="98d2b-150">Erstellen Sie für jeden Benutzer, den Sie Microsoft 365 hinzufügen möchten, eine Zeile unter der Überschrift.</span><span class="sxs-lookup"><span data-stu-id="98d2b-150">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="98d2b-151">Wenn Sie Spaltenüberschriften hinzufügen, ändern oder löschen, kann Microsoft 365 möglicherweise keine Benutzer anhand der Informationen in der Datei erstellen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-151">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span> 
    
- <span data-ttu-id="98d2b-p111">**Was kann ich tun, wenn ich nicht über alle Informationen verfüge, die bei jedem Benutzer erforderlich sind?** Der Benutzername und der Anzeigename sind unbedingt erforderlich; Sie können keinen neuen Benutzer ohne diese Angaben hinzufügen. Falls Ihnen einige der anderen Informationen fehlen, wie beispielsweise das Fax, können Sie ein Leerzeichen plus das von Ihnen verwendete Trennzeichen eingeben und so festlegen, dass das Feld leer bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="98d2b-p111">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span> 
    
- <span data-ttu-id="98d2b-155">**Wie klein oder groß kann die Kalkulationstabelle sein?**</span><span class="sxs-lookup"><span data-stu-id="98d2b-155">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="98d2b-156">Das Arbeitsblatt muss mindestens zwei Zeilen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="98d2b-156">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="98d2b-157">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="98d2b-157">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="98d2b-158">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="98d2b-158">You cannot have more than 251 rows.</span></span> <span data-ttu-id="98d2b-159">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="98d2b-159">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span> 
    
- <span data-ttu-id="98d2b-160">**Welche Sprachen kann ich verwenden?**</span><span class="sxs-lookup"><span data-stu-id="98d2b-160">**What languages can I use?**</span></span> <span data-ttu-id="98d2b-161">Wenn Sie Ihre Kalkulationstabelle erstellen, können Sie Benutzerdaten Spaltenbeschriftungen in einer beliebigen Sprache oder in beliebigen Zeichen eingeben, aber Sie dürfen die Reihenfolge der Beschriftungen nicht ändern, wie im Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="98d2b-161">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="98d2b-162">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span><span class="sxs-lookup"><span data-stu-id="98d2b-162">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span> 
    
- <span data-ttu-id="98d2b-p114">**Was geschieht, wenn ich Benutzer aus verschiedenen Ländern oder Regionen hinzufüge?** Erstellen Sie eine separate Tabelle für jeden Bereich. Sie müssen den Assistenten "Massenhinzufügung von Benutzern" mit jeder Tabelle schrittweise durchlaufen. Geben Sie dabei einen einzigen Standort für alle Benutzer an, die in der Datei, mit der Sie arbeiten, enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="98d2b-p114">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span> 
    
- <span data-ttu-id="98d2b-p115">**Bestehen Beschränkungen bei der Anzahl der Zeichen, die ich verwenden kann?** Die folgende Tabelle zeigt die Beschriftungen für Benutzerdatenspalten sowie die maximale Zeichenanzahl für jedes Element der Beispieltabelle.</span><span class="sxs-lookup"><span data-stu-id="98d2b-p115">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span> 
    
|<span data-ttu-id="98d2b-168">**Beschriftung für Benutzerdatenspalte**</span><span class="sxs-lookup"><span data-stu-id="98d2b-168">**User data column label**</span></span>|<span data-ttu-id="98d2b-169">**Maximale Zeichenanzahl**</span><span class="sxs-lookup"><span data-stu-id="98d2b-169">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98d2b-170">Benutzername (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="98d2b-170">User Name (Required)</span></span>  <br/> |<span data-ttu-id="98d2b-171">79 einschließlich des @-Zeichens im Format Name@Domain. \<extension\> .</span><span class="sxs-lookup"><span data-stu-id="98d2b-171">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="98d2b-172">Der Alias des Benutzers darf 50 Zeichen nicht überschreiten, und der Domänenname darf 48 Zeichen nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="98d2b-172">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="98d2b-173">Vorname</span><span class="sxs-lookup"><span data-stu-id="98d2b-173">First Name</span></span>  <br/> |<span data-ttu-id="98d2b-174">64</span><span class="sxs-lookup"><span data-stu-id="98d2b-174">64</span></span>  <br/> |
|<span data-ttu-id="98d2b-175">Nachname</span><span class="sxs-lookup"><span data-stu-id="98d2b-175">Last Name</span></span>  <br/> |<span data-ttu-id="98d2b-176">64</span><span class="sxs-lookup"><span data-stu-id="98d2b-176">64</span></span>  <br/> |
|<span data-ttu-id="98d2b-177">Anzeigename (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="98d2b-177">Display Name (required)</span></span>  <br/> |<span data-ttu-id="98d2b-178">256</span><span class="sxs-lookup"><span data-stu-id="98d2b-178">256</span></span>  <br/> |
|<span data-ttu-id="98d2b-179">Position</span><span class="sxs-lookup"><span data-stu-id="98d2b-179">Job Title</span></span>  <br/> |<span data-ttu-id="98d2b-180">64</span><span class="sxs-lookup"><span data-stu-id="98d2b-180">64</span></span>  <br/> |
|<span data-ttu-id="98d2b-181">Abteilung</span><span class="sxs-lookup"><span data-stu-id="98d2b-181">Department</span></span>  <br/> |<span data-ttu-id="98d2b-182">64</span><span class="sxs-lookup"><span data-stu-id="98d2b-182">64</span></span>  <br/> |
|<span data-ttu-id="98d2b-183">Büronummer</span><span class="sxs-lookup"><span data-stu-id="98d2b-183">Office Number</span></span>  <br/> |<span data-ttu-id="98d2b-184">128</span><span class="sxs-lookup"><span data-stu-id="98d2b-184">128</span></span>  <br/> |
|<span data-ttu-id="98d2b-185">Rufnummer</span><span class="sxs-lookup"><span data-stu-id="98d2b-185">Office Phone</span></span>  <br/> |<span data-ttu-id="98d2b-186">64</span><span class="sxs-lookup"><span data-stu-id="98d2b-186">64</span></span>  <br/> |
|<span data-ttu-id="98d2b-187">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="98d2b-187">Mobile Phone</span></span>  <br/> |<span data-ttu-id="98d2b-188">64</span><span class="sxs-lookup"><span data-stu-id="98d2b-188">64</span></span>  <br/> |
|<span data-ttu-id="98d2b-189">Fax</span><span class="sxs-lookup"><span data-stu-id="98d2b-189">Fax</span></span>  <br/> |<span data-ttu-id="98d2b-190">64</span><span class="sxs-lookup"><span data-stu-id="98d2b-190">64</span></span>  <br/> |
|<span data-ttu-id="98d2b-191">Adresse</span><span class="sxs-lookup"><span data-stu-id="98d2b-191">Address</span></span>  <br/> |<span data-ttu-id="98d2b-192">1023</span><span class="sxs-lookup"><span data-stu-id="98d2b-192">1023</span></span>  <br/> |
|<span data-ttu-id="98d2b-193">Ort</span><span class="sxs-lookup"><span data-stu-id="98d2b-193">City</span></span>  <br/> |<span data-ttu-id="98d2b-194">128</span><span class="sxs-lookup"><span data-stu-id="98d2b-194">128</span></span>  <br/> |
|<span data-ttu-id="98d2b-195">Bundesland oder Kanton</span><span class="sxs-lookup"><span data-stu-id="98d2b-195">State or Province</span></span>  <br/> |<span data-ttu-id="98d2b-196">128</span><span class="sxs-lookup"><span data-stu-id="98d2b-196">128</span></span>  <br/> |
|<span data-ttu-id="98d2b-197">PLZ</span><span class="sxs-lookup"><span data-stu-id="98d2b-197">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="98d2b-198">40</span><span class="sxs-lookup"><span data-stu-id="98d2b-198">40</span></span>  <br/> |
|<span data-ttu-id="98d2b-199">Land oder Region</span><span class="sxs-lookup"><span data-stu-id="98d2b-199">Country or Region</span></span>  <br/> |<span data-ttu-id="98d2b-200">128</span><span class="sxs-lookup"><span data-stu-id="98d2b-200">128</span></span>  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="98d2b-201">Gibt es weiterhin Probleme beim Hinzufügen von Benutzern zu Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="98d2b-201">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="98d2b-p117">**Überprüfen Sie sorgfältig, ob die Tabelle richtig formatiert wurde.** Überprüfen Sie, ob die Spaltenüberschriften mit den Überschriften in der Beispieldatei übereinstimmen. Vergewissern Sie sich, dass Sie die Regeln für die maximale Zeichenanzahl eingehalten haben und dass jedes Feld durch ein Trennzeichen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="98d2b-p117">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span> 
    
- <span data-ttu-id="98d2b-205">**Wenn die neuen Benutzer in Microsoft 365 nicht sofort angezeigt werden, warten Sie einige Minuten.**</span><span class="sxs-lookup"><span data-stu-id="98d2b-205">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="98d2b-206">Es kann eine Weile dauern, bis Änderungen in allen Diensten in Microsoft 365 durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="98d2b-206">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 
    
## <a name="related-articles"></a><span data-ttu-id="98d2b-207">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="98d2b-207">Related articles</span></span>

[<span data-ttu-id="98d2b-208">Hinzufügen von Benutzern einzeln oder in Massen zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="98d2b-208">Add users individually or in bulk to Microsoft 365</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)




