---
title: Verwenden von PowerShell zum Ausführen einer IMAP-Migration zu Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Erfahren Sie, wie Sie PowerShell verwenden, um eine Internet Mail Access Protocol (IMAP)-Migration zu Microsoft 365 durchzuführen.
ms.openlocfilehash: fbfc0340e80ce70aa8a706d89a4d27729b91535b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924768"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="0eb09-103">Verwenden von PowerShell zum Ausführen einer IMAP-Migration zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0eb09-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="0eb09-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0eb09-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0eb09-105">Im Rahmen der Bereitstellung von Microsoft 365 können Sie den Inhalt von Benutzerpostfächern von einem ImAP-E-Mail-Dienst (Internet Mail Access Protocol) zu Microsoft 365 migrieren.</span><span class="sxs-lookup"><span data-stu-id="0eb09-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="0eb09-106">Dieser Artikel führt Sie durch die Aufgaben für eine IMAP-Migration mithilfe von Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0eb09-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0eb09-107">Sie können auch die Exchange-Verwaltungskonsole zum Durchführen einer IMAP-Migration verwenden.</span><span class="sxs-lookup"><span data-stu-id="0eb09-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="0eb09-108">Weitere [Informationen finden Sie unter Migrate your IMAP mailboxes](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="0eb09-108">See [Migrate your IMAP mailboxes](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0eb09-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="0eb09-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="0eb09-110">Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 2 bis 5 Minuten, um einen Migrationsbatch zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="0eb09-111">Nach dem Start der Migration variiert die Dauer der Migration abhängig von der Anzahl von Postfächern in dem Batch, der Größe der einzelnen Postfächer und Ihrer verfügbaren Netzkapazität.</span><span class="sxs-lookup"><span data-stu-id="0eb09-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="0eb09-112">Weitere Informationen zu anderen Faktoren, die sich auf die Dauer der Migration von Postfächern zu Microsoft 365 [auswirken,](/Exchange/mailbox-migration/office-365-migration-best-practices)finden Sie unter Migration Performance .</span><span class="sxs-lookup"><span data-stu-id="0eb09-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>
  
<span data-ttu-id="0eb09-p104">Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Berechtigungen, die Sie benötigen, finden Sie unter dem Eintrag „Migration" in einer Tabelle im Thema [Empfängerberechtigungen](/exchange/recipients-permissions-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="0eb09-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>
  
<span data-ttu-id="0eb09-p105">Um die Exchange Online-PowerShell-Cmdlets zu verwenden, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell Sitzung importieren. Finden Sie Anweisungen unter[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShelll](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0eb09-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>
  
<span data-ttu-id="0eb09-117">Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="0eb09-117">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
  
<span data-ttu-id="0eb09-118">Folgende Einschränkungen gelten für IMAP-Migrationen:</span><span class="sxs-lookup"><span data-stu-id="0eb09-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="0eb09-p106">Nur Elemente aus dem Posteingang oder anderen E-Mail-Ordnern eines Benutzers können migriert werden. Sie können keine Kontakte, Kalenderelemente oder Aufgaben migrieren.</span><span class="sxs-lookup"><span data-stu-id="0eb09-p106">Only items in a user's inbox or other mail folders can be migrated. You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="0eb09-121">Maximal 500.000 Elemente können aus dem Postfach eines Benutzers migriert werden.</span><span class="sxs-lookup"><span data-stu-id="0eb09-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="0eb09-122">Die maximale Nachrichtengröße, die migriert werden kann, beträgt 35 MB.</span><span class="sxs-lookup"><span data-stu-id="0eb09-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="0eb09-123">Migrationsschritte</span><span class="sxs-lookup"><span data-stu-id="0eb09-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="0eb09-124">Schritt 1: IMAP-Migration vorbereiten</span><span class="sxs-lookup"><span data-stu-id="0eb09-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="0eb09-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb09-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="0eb09-126">**Wenn Sie über eine Domäne für Ihre IMAP-Organisation verfügen, fügen Sie sie als akzeptierte Domäne Ihrer Microsoft 365-Organisation hinzu.**</span><span class="sxs-lookup"><span data-stu-id="0eb09-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="0eb09-127">Wenn Sie dieselbe Domäne verwenden möchten, die Sie bereits für Ihre Microsoft 365-Postfächer besitzen, müssen Sie sie zunächst als akzeptierte Domäne zu Microsoft 365 hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="0eb09-128">Nachdem Sie sie hinzugefügt haben, können Sie Ihre Benutzer in Microsoft 365 erstellen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="0eb09-129">Weitere Informationen finden Sie unter[Verify your domain](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="0eb09-129">For more information, see[Verify your domain](../admin/setup/add-domain.md).</span></span>
    
- <span data-ttu-id="0eb09-130">**Fügen Sie jeden Benutzer zu Microsoft 365 hinzu, damit er über ein Postfach verfügen kann.**</span><span class="sxs-lookup"><span data-stu-id="0eb09-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="0eb09-131">Anweisungen finden Sie unter[Hinzufügen von Benutzern zu Microsoft 365 Business](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="0eb09-131">For instructions, see[Add users to Microsoft 365 for business](../admin/add-users/add-users.md).</span></span>
    
- <span data-ttu-id="0eb09-p109">**Abrufen des FQDN des IMAP-Servers**. Sie müssen den vollqualifizierten Domänennamen (FQDN, auch als vollständiger Computername bezeichnet) des IMAP-Servers angeben, von dem Sie Postfachdaten migrieren möchten, wenn Sie einen IMAP-Migrationsendpunkt erstellen. Verwenden Sie einen IMAP-Client oder den Ping-Befehl, um sicherzustellen, dass Sie mit dem FQDN über das Internet mit dem IMAP-Server kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="0eb09-p109">**Obtain the FQDN of the IMAP server**. You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint. Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="0eb09-p110">**Konfigurieren der Firewall zum Zulassen von IMAP-Verbindungen**. Sie müssen unter Umständen Ports in der Firewall der Organisation öffnen, in der sich der IMAP-Server befindet, damit Netzwerkdatenverkehr, der während der Migration aus dem Microsoft-Datencenter stammt, in die Organisation gelangen darf, in der sich der IMAP-Server befindet. Eine Liste der IP-Adressen, die von Microsoft-Datencentern verwendet werden, finden Sie unter [Ausgehende IP-Adressen](./urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="0eb09-p110">**Configure the firewall to allow IMAP connections**. You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server. For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](./urls-and-ip-address-ranges.md).</span></span>
    
- <span data-ttu-id="0eb09-p111">**Zuweisen der Administratorkontoberechtigungen für den Zugriff auf Postfächer in der IMAP-Organisation**. Wenn Sie Administratoranmeldeinformationen in der CSV-Datei verwenden, muss das verwendete Konto die erforderlichen Berechtigungen für den Zugriff auf die lokalen Postfächer besitzen. Die für den Zugriff auf Benutzerpostfächer erforderlichen Berechtigungen werden durch den jeweiligen IMAP-Server bestimmt.</span><span class="sxs-lookup"><span data-stu-id="0eb09-p111">**Assign the administrator account permissions to access mailboxes in your IMAP organization**. If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes. The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="0eb09-p112">**Um die Exchange Online-PowerShell-Cmdlets zu verwenden**, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell-Sitzung importieren. Anweisungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0eb09-p112">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>
    
    <span data-ttu-id="0eb09-143">Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="0eb09-143">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
    
- <span data-ttu-id="0eb09-p113">**Überprüfen, ob Sie mit Ihrem IMAP-Server eine Verbindung herstellen können**. Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Einstellungen für die Verbindung mit Ihrem IMAP-Server zu testen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-p113">**Verify that you can connect to your IMAP server**. Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="0eb09-146">Normalerweise wird für den **Port** -Parameter der Wert 143 für unverschlüsselte oder TLS-Verbindungen (Transport Layer Security) verwendet und der Wert 993 für SSL-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="0eb09-147">Schritt 2: CSV-Datei für einen IMAP-Migrationsbatch erstellen</span><span class="sxs-lookup"><span data-stu-id="0eb09-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="0eb09-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb09-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="0eb09-p114">Identifizieren Sie die Gruppe der Benutzer, deren Postfächer Sie in einem IMAP-Migrationsbatch migrieren möchten. Jede Zeile in der CSV-Datei enthält Informationen, die zum Herstellen einer Verbindung mit einem Postfach im IMAP-Messaging-System erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0eb09-p114">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch. Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="0eb09-151">Die folgenden Attribute sind für jeden Benutzer erforderlich:</span><span class="sxs-lookup"><span data-stu-id="0eb09-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="0eb09-152">**EmailAddress** gibt die Benutzer-ID für das Microsoft 365-Postfach des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="0eb09-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="0eb09-153">**UserName** gibt den Anmeldenamen für das Konto an, das für den Zugriff auf das Postfach auf dem IMAP-Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0eb09-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="0eb09-154">**Password** gibt das Kennwort für das Konto in der Spalte UserName **UserName** an.</span><span class="sxs-lookup"><span data-stu-id="0eb09-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="0eb09-p115">Das folgende Beispiel zeigt das Format der CSV-Datei. In diesem Beispiel werden drei Postfächer migriert:</span><span class="sxs-lookup"><span data-stu-id="0eb09-p115">Here's an example of the format for the CSV file. In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="0eb09-157">Für das Attribut **UserName** können Sie zusätzlich zum Benutzernamen die Anmeldeinformationen eines Kontos verwenden, dem die erforderlichen Berechtigungen für den Zugriff auf Postfächer auf dem IMAP-Server zugewiesen wurden. Es folgen einige spezielle Formate, die für einige IMAP-Server verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0eb09-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="0eb09-158">**Microsoft Exchange**</span><span class="sxs-lookup"><span data-stu-id="0eb09-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="0eb09-159">Wenn Sie E-Mails aus der IMAP-Implementierung für Microsoft Exchange migrieren, verwenden Sie das Format **Domain/Admin_UserName/User_UserName** für das **UserName** -Attribut in der CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="0eb09-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="0eb09-160">Angenommen, Sie migrieren die E-Mails für die Benutzer Terry Adams, Ann Beebe und Paul Cannon von Exchange.</span><span class="sxs-lookup"><span data-stu-id="0eb09-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="0eb09-161">Sie haben ein E-Mail-Administratorkonto, wobei der Benutzername **mailadmin** und das Kennwort **P \@ ssw0rd ist.**</span><span class="sxs-lookup"><span data-stu-id="0eb09-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P\@ssw0rd**.</span></span> <span data-ttu-id="0eb09-162">Die CSV-Datei würde dann folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="0eb09-162">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="0eb09-163">**Dovecot**</span><span class="sxs-lookup"><span data-stu-id="0eb09-163">**Dovecot:**</span></span>
  
<span data-ttu-id="0eb09-164">Verwenden Sie für IMAP-Server wie Dovecot-IMAP-Server, die Simple Authentication and Security Layer (SASL) unterstützen, das Format **User_UserName\*Admin_UserName**, wobei das Sternchen ( \* ) ein konfigurierbares Trennzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="0eb09-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="0eb09-165">Angenommen, Sie migrieren die E-Mails dieser Benutzer von einem Dovecot-IMAP-Server mit den Administratoranmeldeinformationen **mailadmin** und **P \@ ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="0eb09-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P\@ssw0rd**.</span></span> <span data-ttu-id="0eb09-166">Die CSV-Datei würde dann folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="0eb09-166">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="0eb09-167">**Mirapoint**</span><span class="sxs-lookup"><span data-stu-id="0eb09-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="0eb09-168">Wenn Sie E-Mails von Mirapoint Message Server migrieren, verwenden Sie das Format **#user \@ Domäne#Admin_UserName#** für die Administratoranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-168">If you're migrating email from Mirapoint Message Server, use the format **#user\@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="0eb09-169">Zum Migrieren von E-Mails von Mirapoint mit den Administratoranmeldeinformationen **mailadmin** und **P \@ ssw0rd** würde Ihre CSV-Datei wie dies aussehen:</span><span class="sxs-lookup"><span data-stu-id="0eb09-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P\@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="0eb09-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="0eb09-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="0eb09-171">Einige Quell-E-Mail-Systeme, z. B. Courier IMAP, unterstützen die Verwendung von Postfachadministratoranmeldeinformationen zum Migrieren von Postfächern zu Microsoft 365 nicht.</span><span class="sxs-lookup"><span data-stu-id="0eb09-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="0eb09-172">Stattdessen können Sie Ihr E-Mail-Quellsystem für die Verwendung virtueller freigegebener Ordner einrichten.</span><span class="sxs-lookup"><span data-stu-id="0eb09-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="0eb09-173">Mithilfe der virtuellen freigegebenen Ordner können Sie die Postfach-Administratoranmeldeinformationen verwenden, um auf Benutzerpostfächer im E-Mail-Quellsystem zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="0eb09-174">Weitere Informationen zum Konfigurieren von virtuellen freigegebenen Ordnern für Courier IMAP finden Sie unter [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span><span class="sxs-lookup"><span data-stu-id="0eb09-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="0eb09-p120">Um Postfächer zu migrieren, nachdem Sie auf dem E-Mail-Quellsystem virtuelle freigegebene Ordner eingerichtet haben, müssen Sie das optionale Attribut **UserRoot** in die Migrationsdatei einfügen. Dieses Attribut gibt das Verzeichnis an, in dem die einzelnen Benutzerpostfächer in der Struktur der virtuellen freigegebenen Ordner im E-Mail-Quellsystem gespeichert sind. Der Pfad zu Terrys Postfach lautet beispielsweise „/users/terry.adams".</span><span class="sxs-lookup"><span data-stu-id="0eb09-p120">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file. This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system. For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="0eb09-178">Beispiel für eine CSV-Datei, die das Attribut **UserRoot** enthält:</span><span class="sxs-lookup"><span data-stu-id="0eb09-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="0eb09-179">Schritt 3: IMAP-Migrationsendpunkt erstellen</span><span class="sxs-lookup"><span data-stu-id="0eb09-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="0eb09-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb09-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="0eb09-181">Um E-Mails erfolgreich zu migrieren, muss Microsoft 365 eine Verbindung mit dem Quell-E-Mail-System herstellen und mit diesem kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="0eb09-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="0eb09-182">Zu diesem Zwecke verwendet Microsoft 365 einen Migrationsendpunkt.</span><span class="sxs-lookup"><span data-stu-id="0eb09-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="0eb09-183">Der Migrationsendpunkt definiert außerdem die Anzahl der Postfächer, die gleichzeitig migriert werden, sowie die Anzahl der Postfächer, die gleichzeitig während einer inkrementellen Synchronisierung synchronisiert werden, die alle 24 Stunden auftritt.</span><span class="sxs-lookup"><span data-stu-id="0eb09-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="0eb09-184">Um einen Migrationsendpunkt für die IMAP-Migration zu erstellen, [stellen Sie zunächst eine Verbindung mit Exchange Online her](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0eb09-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> 
  
<span data-ttu-id="0eb09-185">Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="0eb09-185">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
  
<span data-ttu-id="0eb09-186">Zum Erstellen eines IMAP-Migrationsendpunkts namens „IMAPEndpoint“ in Exchange Online PowerShell, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0eb09-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="0eb09-p122">Sie können auch Parameter zum Angeben gleichzeitiger Migrationen, gleichzeitiger inkrementeller Migrationen und des zu verwendenden Ports hinzufügen. Der folgende Exchange Online PowerShell-Befehl erstellt einen IMAP-Migrationsendpunkt namens „IMAPEndpoint", der 50 gleichzeitige Migrationen und bis zu 25 gleichzeitige inkrementelle Synchronisierungen unterstützt. Darüber hinaus wird der Endpunkt für die Verwendung von Port 143 für die TLS-Verschlüsselung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0eb09-p122">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use. The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations. It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="0eb09-190">Weitere Informationen zu den **New-MigrationEndpoint** -Cmdlets finden Sie unter [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).</span><span class="sxs-lookup"><span data-stu-id="0eb09-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="0eb09-191">Stellen Sie die Funktion sicher</span><span class="sxs-lookup"><span data-stu-id="0eb09-191">Verify it worked</span></span>

<span data-ttu-id="0eb09-192">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen über den „IMAPEndpoint“ anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0eb09-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="0eb09-193">Schritt 4: Erstellen und Starten eines IMAP-Migrationsbatches</span><span class="sxs-lookup"><span data-stu-id="0eb09-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="0eb09-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb09-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="0eb09-p123">Sie können das [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch)-Cmdlet verwenden, um einen Migrationsbatch für eine IMAP-Migration zu erstellen. Sie können einen Migrationsbatch erstellen und automatisch durch Einschließen des  _AutoStart_-Parameters starten. Alternativ können Sie den Migrationsbatch erstellen und danach mithilfe des [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch)-Cmdlets starten.</span><span class="sxs-lookup"><span data-stu-id="0eb09-p123">You can use the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet to create a migration batch for an IMAP migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) cmdlet.</span></span>
  
<span data-ttu-id="0eb09-198">Der folgende Exchange Online PowerShell-Befehl startet automatisch den Migrationsbatch namens „IMAPBatch1“ mit den IMAP-Endpunkt namens „IMAPEndpoint“:</span><span class="sxs-lookup"><span data-stu-id="0eb09-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="0eb09-199">Stellen Sie die Funktion sicher</span><span class="sxs-lookup"><span data-stu-id="0eb09-199">Verify it worked</span></span>

<span data-ttu-id="0eb09-200">Führen Sie das [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)-Cmdlet aus, um Informationen zu „IMAPBatch1" anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0eb09-200">Run the [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="0eb09-201">Sie können auch überprüfen, ob der Batch gestartet wurde, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="0eb09-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="0eb09-202">Schritt 5: Route your email to Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0eb09-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="0eb09-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb09-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="0eb09-204">E-Mail-Systeme verwenden einen als MX-Eintrag bezeichneten DNS-Eintrag, um zu ermitteln, wohin E-Mails gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="0eb09-205">Während der E-Mail-Migration hat Ihr MX-Eintrag auf Ihr Quell-E-Mail-System verwiesen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="0eb09-206">Nachdem die E-Mail-Migration zu Microsoft 365 abgeschlossen ist, ist es an der Zeit, Ihren MX-Eintrag auf Microsoft 365 zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="0eb09-207">Dadurch wird sichergestellt, dass E-Mails an Ihre Microsoft 365-Postfächer zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0eb09-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="0eb09-208">Durch Verschieben des MX-Eintrags können Sie auch Ihr altes E-Mail-System deaktivieren, wenn Sie bereit sind.</span><span class="sxs-lookup"><span data-stu-id="0eb09-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="0eb09-209">Für viele DNS-Anbieter gibt es bestimmte Anweisungen zum Ändern des MX-Eintrags.</span><span class="sxs-lookup"><span data-stu-id="0eb09-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="0eb09-210">Wenn Ihr DNS-Anbieter nicht enthalten ist oder wenn Sie allgemeine Anweisungen erhalten möchten, finden Sie entsprechende Informationen unter [Erstellen und Konfigurieren eines DNS-Eintrags für Office 365](https://go.microsoft.com/fwlink/?LinkId=397449).</span><span class="sxs-lookup"><span data-stu-id="0eb09-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="0eb09-p126">Es kann bis zu 72 Stunden dauern, bis die E-Mail-Systeme der Kunden und Partnern den geänderten MX-Eintrag erkennen. Warten Sie mindestens 72 Stunden, bevor Sie mit dem nächsten Schritt fortfahren: Schritt 6: IMAP-Migrationsbatch löschen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-p126">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="0eb09-213">Schritt 6: IMAP-Migrationsbatch löschen</span><span class="sxs-lookup"><span data-stu-id="0eb09-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="0eb09-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb09-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="0eb09-215">Nachdem Sie den MX-Eintrag geändert und überprüft haben, ob alle E-Mails an Microsoft 365-Postfächer geroutet werden, benachrichtigen Sie die Benutzer, dass ihre E-Mails an Microsoft 365 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0eb09-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="0eb09-216">Danach können Sie den IMAP-Migrationsbatch löschen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="0eb09-217">Überprüfen Sie Folgendes, bevor Sie den Migrationsbatch löschen.</span><span class="sxs-lookup"><span data-stu-id="0eb09-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="0eb09-218">Alle Benutzer verwenden Microsoft 365-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="0eb09-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="0eb09-219">Nachdem der Batch gelöscht wurde, werden E-Mails, die an Postfächer in der lokalen Exchange Server gesendet werden, nicht in die entsprechenden Microsoft 365-Postfächer kopiert.</span><span class="sxs-lookup"><span data-stu-id="0eb09-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="0eb09-220">Microsoft 365-Postfächer wurden mindestens einmal synchronisiert, nachdem E-Mails direkt an sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="0eb09-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="0eb09-221">Stellen Sie dazu sicher, dass der Wert im Feld Letzte Synchronisierungszeit für den Migrationsbatch aktueller ist als der Wert, als E-Mails direkt an Microsoft 365-Postfächer geroutet wurden.</span><span class="sxs-lookup"><span data-stu-id="0eb09-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="0eb09-222">Führen Sie den folgenden Befehl aus, um den Migrationsbatch „IMAPBatch1“ in Exchange Online PowerShell zu löschen:
</span><span class="sxs-lookup"><span data-stu-id="0eb09-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="0eb09-223">Weitere Informationen zu dem **Remove-MigrationBatch** -Cmdlet finden Sie unter [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).</span><span class="sxs-lookup"><span data-stu-id="0eb09-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="0eb09-224">Stellen Sie die Funktion sicher</span><span class="sxs-lookup"><span data-stu-id="0eb09-224">Verify it worked</span></span>

<span data-ttu-id="0eb09-225">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen über den "IMAPBatch1" anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0eb09-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="0eb09-226">Der Befehl gibt entweder den Migrationsbatch mit dem Status **Removing** zurück oder einen Fehler, der besagt, dass der Migrationsbatch nicht gefunden werden konnte, was bestätigt, dass er gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="0eb09-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="0eb09-227">Weitere Informationen zu den **Get-MigrationBatch** -Cmdlets finden Sie unter [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span><span class="sxs-lookup"><span data-stu-id="0eb09-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0eb09-228">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0eb09-228">See also</span></span>

[<span data-ttu-id="0eb09-229">Problembehandlung der IMAP-Migration</span><span class="sxs-lookup"><span data-stu-id="0eb09-229">IMAP Migration Troubleshooter</span></span>](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)