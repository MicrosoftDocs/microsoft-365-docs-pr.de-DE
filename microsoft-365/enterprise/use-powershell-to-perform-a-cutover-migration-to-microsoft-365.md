---
title: Verwenden von PowerShell zum Ausführen einer Übernahmemigration zu Microsoft 365
ms.author: sirkkuw
author: sirkkuw
manager: laurawi
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
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von PowerShell die Inhalte aus einem Quell-e-Mail-System auf einmal durch Ausführen einer Cutover-Migration zu Microsoft 365 migrieren.
ms.openlocfilehash: 74e7791c4292598e4717e56af25e39b3c8208108
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948196"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="df4df-103">Verwenden von PowerShell zum Ausführen einer Übernahmemigration zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="df4df-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="df4df-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="df4df-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="df4df-105">Sie können die Inhalte von Benutzerpostfächern aus einem Quell-e-Mail-System auf einmal mithilfe einer Cutover-Migration zu Microsoft 365 migrieren.</span><span class="sxs-lookup"><span data-stu-id="df4df-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="df4df-106">Dieser Artikel führt Sie durch die Aufgaben für eine E-Mail-Übernahmemigration mithilfe von Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df4df-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span>

<span data-ttu-id="df4df-107">Durch die Überprüfung des Themas, [was Sie über eine Cutover-e-Mail-Migration zu Microsoft 365 wissen müssen](https://go.microsoft.com/fwlink/p/?LinkId=536688), erhalten Sie einen Überblick über den Migrationsprozess.</span><span class="sxs-lookup"><span data-stu-id="df4df-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), you can get an overview of the migration process.</span></span> <span data-ttu-id="df4df-108">Wenn Sie mit dem Inhalt dieses Artikels vertraut sind, verwenden Sie die Informationen, um Postfächer von einem E-Mail-System zu einem anderen zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="df4df-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="df4df-109">Sie können auch die Exchange-Verwaltungskonsole zum Durchführen einer Übernahmemigration verwenden.</span><span class="sxs-lookup"><span data-stu-id="df4df-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="df4df-110">Weitere Informationen finden Sie unter [Durchführen einer Cutover Migration von e-Mails zu Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).</span><span class="sxs-lookup"><span data-stu-id="df4df-110">See [Perform a cutover migration of email to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="df4df-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="df4df-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="df4df-112">Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 2 bis 5 Minuten, um einen Migrationsbatch zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df4df-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="df4df-113">Nach dem Start der Migration variiert die Dauer der Migration abhängig von der Anzahl von Postfächern in dem Batch, der Größe der einzelnen Postfächer und Ihrer verfügbaren Netzkapazität.</span><span class="sxs-lookup"><span data-stu-id="df4df-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="df4df-114">Informationen zu anderen Faktoren, die sich auf die Dauer der Migration von Postfächern zu Microsoft 365 auswirken, finden Sie unter [Migrationsleistung](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span><span class="sxs-lookup"><span data-stu-id="df4df-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>

<span data-ttu-id="df4df-p105">Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Berechtigungen, die Sie benötigen, finden Sie unter dem Eintrag „Migration" in einer Tabelle im Thema [Empfängerberechtigungen](https://go.microsoft.com/fwlink/p/?LinkId=534105).</span><span class="sxs-lookup"><span data-stu-id="df4df-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>

<span data-ttu-id="df4df-p106">Um die Exchange Online-PowerShell-Cmdlets zu verwenden, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell Sitzung importieren. Finden Sie Anweisungen unter[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShelll](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="df4df-p106">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>

<span data-ttu-id="df4df-119">Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="df4df-119">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="df4df-120">Migrationsschritte</span><span class="sxs-lookup"><span data-stu-id="df4df-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="df4df-121">Schritt 1: Übernahmemigration vorbereiten</span><span class="sxs-lookup"><span data-stu-id="df4df-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="df4df-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="df4df-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="df4df-123">**Fügen Sie Ihre lokale Exchange-Organisation als akzeptierte Domäne Ihrer Microsoft 365-Organisation hinzu.**</span><span class="sxs-lookup"><span data-stu-id="df4df-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="df4df-124">Der Migrationsdienst verwendet die SMTP-Adresse Ihrer lokalen Postfächer, um die Microsoft Online Services-Benutzer-ID und die e-Mail-Adresse für die neuen Microsoft 365-Postfächer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df4df-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="df4df-125">Die Migration schlägt fehl, wenn es sich bei Ihrer Exchange-Domäne nicht um eine akzeptierte Domäne oder die primäre Domäne Ihrer Microsoft 365-Organisation handelt.</span><span class="sxs-lookup"><span data-stu-id="df4df-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="df4df-126">Weitere Informationen finden Sie unter [Überprüfen Ihrer Domäne](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span><span class="sxs-lookup"><span data-stu-id="df4df-126">For more information, see [Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>

- <span data-ttu-id="df4df-p108">**Konfigurieren von Outlook Anywhere auf dem lokalen Exchange-Server** Der E-Mail-Migrationsdienst verwendet RPC über HTTP oder Outlook Anywhere, um eine Verbindung mit dem lokalen Exchange-Server herzustellen. Informationen zum Einrichten von Outlook Anywhere für Exchange 2010, Exchange 2007 und Exchange 2003 finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="df4df-p108">**Configure Outlook Anywhere on your on-premises Exchange server.** The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server. For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>

  - [<span data-ttu-id="df4df-130">Exchange 2010: Aktivieren von Outlook Anywhere</span><span class="sxs-lookup"><span data-stu-id="df4df-130">Exchange 2010: Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=187249)

  - [<span data-ttu-id="df4df-131">Exchange 2007: Aktivieren von Outlook Anywhere</span><span class="sxs-lookup"><span data-stu-id="df4df-131">Exchange 2007: How to Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=167210)

  - [<span data-ttu-id="df4df-132">Exchange 2003: Bereitstellungsszenarien für RPC über HTTP</span><span class="sxs-lookup"><span data-stu-id="df4df-132">Exchange 2003: Deployment Scenarios for RPC over HTTP</span></span>](https://go.microsoft.com/fwlink/?LinkID=73657)

  - [<span data-ttu-id="df4df-133">Konfigurieren von Outlook Anywhere mit Exchange 2003</span><span class="sxs-lookup"><span data-stu-id="df4df-133">How to Configure Outlook Anywhere with Exchange 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=167209)

    > [!IMPORTANT]
    > <span data-ttu-id="df4df-p109">Die Outlook Anywhere-Konfiguration muss mit einem Zertifikat einer vertrauenswürdigen Zertifizierungsstelle konfiguriert werden. Outlook Anywhere kann nicht mit einem selbstsignierten Zertifikat konfiguriert werden. Weitere Informationen finden Sie unter [Konfigurieren von SSL für Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span><span class="sxs-lookup"><span data-stu-id="df4df-p109">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA). It can't be configured with a self-signed certificate. For more information, see [How to Configure SSL for Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span></span>

- <span data-ttu-id="df4df-p110">**Sicherstellen, dass mit Outlook Anywhere eine Verbindung mit der Exchange-Organisation hergestellt werden kann** Sie können eine der folgenden Methoden verwenden, um die Verbindungseinstellungen zu testen:</span><span class="sxs-lookup"><span data-stu-id="df4df-p110">**Verify that you can connect to your Exchange organization using Outlook Anywhere.** Try one of these methods to test your connection settings:</span></span>

  - <span data-ttu-id="df4df-139">Verwenden Sie Microsoft Outlook von außerhalb Ihre Firmennetzwerks, um eine Verbindung mit Ihrem lokalen Exchange-Postfach herzustellen.</span><span class="sxs-lookup"><span data-stu-id="df4df-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

  - <span data-ttu-id="df4df-p111">Verwenden Sie die Microsoft [Exchange-Remoteverbindungsuntersuchung](https://www.testexchangeconnectivity.com/) zum Testen der Verbindungseinstellungen. Verwenden Sie die Outlook Anywhere- (RPC über HTTP)- oder Outlook-AutoErmittlungs-Tests.</span><span class="sxs-lookup"><span data-stu-id="df4df-p111">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings. Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

  - <span data-ttu-id="df4df-142">Führen Sie die folgenden Befehle in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="df4df-142">Run the following commands in Exchange Online PowerShell.</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="df4df-143">**Zuweisen der erforderlichen Berechtigungen für das lokale Benutzerkonto für den Zugriff auf Postfächer in der Exchange-Organisation**</span><span class="sxs-lookup"><span data-stu-id="df4df-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="df4df-144">Das lokale Benutzerkonto, das Sie zum Herstellen einer Verbindung mit Ihrer lokalen Exchange-Organisation (auch als Migrations Administrator bezeichnet) verwenden, muss über die erforderlichen Berechtigungen für den Zugriff auf die lokalen Postfächer verfügen, die Sie zu Microsoft 365 migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="df4df-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="df4df-145">Dieses Benutzerkonto wird zur Erstellung eines Migrationsendpunkts zu Ihrer lokalen Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="df4df-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>

    <span data-ttu-id="df4df-p113">Die folgende Liste zeigt die Administratorrechte an, die erforderlich sind, um Postfächer mithilfe einer Übernahmemigration zu migrieren. Es gibt drei mögliche Optionen.</span><span class="sxs-lookup"><span data-stu-id="df4df-p113">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration. There are three possible options.</span></span>

  - <span data-ttu-id="df4df-148">Der Migrationsadministrator muss Mitglied der Gruppe **Domänen-Admins** in Active Directory in der lokalen Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="df4df-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="df4df-149">oder -</span><span class="sxs-lookup"><span data-stu-id="df4df-149">Or</span></span>

  - <span data-ttu-id="df4df-150">Dem Migrationsadministrator muss die Berechtigung **FullAccess** für jedes lokale Postfach zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="df4df-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>

    <span data-ttu-id="df4df-151">oder -</span><span class="sxs-lookup"><span data-stu-id="df4df-151">Or</span></span>

  - <span data-ttu-id="df4df-152">Dem Migrationsadministrator muss die Berechtigung **Receive As** für die lokale Postfachdatenbank zugewiesen werden, in der die Benutzerpostfächer gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="df4df-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>

- <span data-ttu-id="df4df-p114">**Deaktivieren von Unified Messaging** Wenn die zu migrierenden lokalen Postfächer für Unified Messaging (UM) aktiviert sind, müssen Sie vor der Migration UM in den Postfächern deaktivieren. Nach Abschluss der Migration können Sie UM dann für die Postfächer wieder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="df4df-p114">**Disable Unified Messaging.** If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them. You can then enable UM on the mailboxes after the migration is complete.</span></span>

- <span data-ttu-id="df4df-156">**Sicherheitsgruppen und Stellvertretungen** Der e-Mail-Migrationsdienst kann nicht erkennen, ob lokale Active Directory Gruppen Sicherheitsgruppen sind oder nicht, sodass migrierte Gruppen nicht als Sicherheitsgruppen in Microsoft 365 bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="df4df-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="df4df-157">Wenn Sie Sicherheitsgruppen in Ihrem Microsoft 365-Mandanten haben möchten, müssen Sie zuerst eine leere e-Mail-aktivierte Sicherheitsgruppe in Ihrem Microsoft 365-Mandanten vorsehen, bevor Sie die Cutover-Migration starten.</span><span class="sxs-lookup"><span data-stu-id="df4df-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="df4df-158">Zudem werden bei dieser Migrationsmethode nur Postfächer, E-Mail-Benutzer, E-Mail-Kontakte und E-Mail-aktivierte Gruppen verschoben.</span><span class="sxs-lookup"><span data-stu-id="df4df-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="df4df-159">Wenn ein anderes Active Directory-Objekt, wie beispielsweise ein Benutzer, der nicht zu Microsoft 365 migriert wird, als Manager oder Stellvertreter für ein migriertes Objekt zugewiesen wird, müssen Sie vor der Migration aus dem Objekt entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="df4df-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>

### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="df4df-160">Schritt 2: Migrationsendpunkt erstellen</span><span class="sxs-lookup"><span data-stu-id="df4df-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="df4df-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="df4df-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="df4df-162">Um e-Mails erfolgreich zu migrieren, muss Microsoft 365 eine Verbindung herstellen und mit dem Quell-e-Mail-System kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="df4df-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="df4df-163">Zu diesem Zwecke verwendet Microsoft 365 einen Migrations Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="df4df-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="df4df-164">Um einen Outlook Anywhere-Migrationsendpunkt für die Übernahmemigration zu erstellen, [stellen Sie zunächst eine Verbindung mit Exchange Online her](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="df4df-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span>

<span data-ttu-id="df4df-165">Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="df4df-165">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>

<span data-ttu-id="df4df-166">Führen Sie die folgenden Befehle in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="df4df-166">Run the following commands in Exchange Online PowerShell:</span></span>

```powershell
$Credentials = Get-Credential
```

<span data-ttu-id="df4df-167">Dabei wird das Cmdlet [Test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) verwendet, um die Einstellungen für die Verbindung mit dem lokalen Exchange-Server abzurufen und zu testen. Anschließend werden diese Verbindungseinstellungen zum Erstellen des Migrationsendpunkts verwendet.</span><span class="sxs-lookup"><span data-stu-id="df4df-167">The example uses the [Test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="df4df-p117">Beim Cmdlet **New-MigrationEndpoint** können Sie mit der Option **-TargetDatabase** eine von dem Dienst zu verwendende Datenbank angeben. Andernfalls wird nach dem Zufallsprinzip eine Datenbank aus dem Active Directory-Verbunddienste (AD FS) 2.0-Standort zugewiesen, in dem sich das Verwaltungspostfach befindet.</span><span class="sxs-lookup"><span data-stu-id="df4df-p117">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="df4df-170">Stellen Sie die Funktion sicher</span><span class="sxs-lookup"><span data-stu-id="df4df-170">Verify it worked</span></span>

<span data-ttu-id="df4df-171">Führen Sie den folgenden Befehl zum Anzeigen von Informationen zum Migrationsendpunkt „CutoverEndpoint“ in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="df4df-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="df4df-172">Schritt 3: Übernahmemigrationsbatch erstellen</span><span class="sxs-lookup"><span data-stu-id="df4df-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="df4df-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="df4df-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="df4df-p118">Sie können das **New-MigrationBatch** -Cmdlet in Exchange Online PowerShell verwenden, um einen Migrationsbatch für eine Übernahmemigration zu erstellen. Sie können einen Migrationsbatch erstellen und diesen automatisch starten, indem Sie den _AutoStart_-Parameter verwenden. Alternativ können Sie den Migrationsbatch erstellen und später mithilfe des **Start-MigrationBatch** -Cmdlets manuell starten. In diesem Beispiel wird ein Migrationsbatch namens „CutoverBatch" erstellt und der im vorherigen Schritt erstellte Migrationsendpunkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="df4df-p118">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="df4df-p119">In diesem Beispiel wird auch ein Migrationsbatch namens „CutoverBatch" erstellt und verwendet den Migrationsendpunkt, der im vorherigen Schritt erstellt wurde. Da der Parameter  _AutoStart_ nicht verwendet wird, muss der Migrationsbatch manuell im Migrationsdashboard gestartet werden oder mithilfe des **Start-MigrationBatch** -Cmdlets . Wie bereits erwähnt, kann immer nur ein Übernahmemigrationsbatch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="df4df-p119">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="df4df-181">Stellen Sie die Funktion sicher</span><span class="sxs-lookup"><span data-stu-id="df4df-181">Verify it worked</span></span>

<span data-ttu-id="df4df-182">Um zu überprüfen, ob Sie erfolgreich einen Migrationsbatch für eine Übernahmemigration erstellt haben, führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen zum neuen Migrationsbatch anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="df4df-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="df4df-183">Schritt 4: Übernahmemigrationsbatch starten</span><span class="sxs-lookup"><span data-stu-id="df4df-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="df4df-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="df4df-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="df4df-p120">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um den Migrationsbatch zu starten. Dadurch wird ein Migrationsbatch namens „CutoverBatch“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="df4df-p120">To start the migration batch in Exchange Online PowerShell, run the following command. This will create a migration batch called "CutoverBatch".</span></span>

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="df4df-187">Stellen Sie die Funktion sicher</span><span class="sxs-lookup"><span data-stu-id="df4df-187">Verify it worked</span></span>

<span data-ttu-id="df4df-p121">Wenn ein Migrationsbatch erfolgreich gestartet wurde, lautet sein Status im Migrationsdashboard Synchronisierung. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob ein Migrationsbatch erfolgreich mithilfe von Exchange Online PowerShell gestartet wurde:</span><span class="sxs-lookup"><span data-stu-id="df4df-p121">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing. To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="df4df-190">Schritt 5: weiterleiten Ihrer e-Mail an Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="df4df-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="df4df-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="df4df-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="df4df-192">E-Mail-Systeme verwenden einen als MX-Eintrag bezeichneten DNS-Eintrag, um zu ermitteln, wohin E-Mails gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="df4df-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="df4df-193">Während der E-Mail-Migration hat Ihr MX-Eintrag auf Ihr Quell-E-Mail-System verwiesen.</span><span class="sxs-lookup"><span data-stu-id="df4df-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="df4df-194">Nachdem die e-Mail-Migration zu Microsoft 365 abgeschlossen ist, ist es an der Zeit, Ihren MX-Eintrag auf Microsoft 365 zu richten.</span><span class="sxs-lookup"><span data-stu-id="df4df-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="df4df-195">Dadurch kann sichergestellt werden, dass e-Mails an Ihre Microsoft 365-Postfächer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="df4df-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="df4df-196">Wenn Sie den MX-Eintrag verschieben, können Sie auch Ihr altes e-Mail-System ausschalten, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="df4df-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span>

<span data-ttu-id="df4df-197">Für viele DNS-Anbieter gibt es bestimmte Anweisungen zum Ändern des MX-Eintrags.</span><span class="sxs-lookup"><span data-stu-id="df4df-197">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="df4df-198">Für den Fall, dass Ihr DNS-Anbieter nicht aufgeführt ist oder Sie eine Vorstellung von den allgemeinen Anweisungen erhalten möchten, werden auch [allgemeine Anweisungen für MX-Einträge](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="df4df-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) are provided as well.</span></span>

<span data-ttu-id="df4df-p124">Es kann bis zu 72 Stunden dauern, bis die E-Mail-Systeme der Kunden und Partnern den geänderten MX-Eintrag erkennen. Warten Sie mindestens 72 Stunden, bevor Sie mit dem nächsten Schritt fortfahren: [Schritt 6: Übernahmemigrationsbatch löschen](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span><span class="sxs-lookup"><span data-stu-id="df4df-p124">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span>

### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="df4df-201">Schritt 6: Übernahmemigrationsbatch löschen</span><span class="sxs-lookup"><span data-stu-id="df4df-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="df4df-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="df4df-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="df4df-203">Nachdem Sie den MX-Eintrag geändert und sichergestellt haben, dass alle e-Mails an Microsoft 365-Postfächer weitergeleitet werden, Benachrichtigen Sie die Benutzer, dass Ihre e-Mail-Nachrichten an Microsoft 365 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="df4df-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="df4df-204">Danach können Sie den Übernahmemigrationsbatch löschen.</span><span class="sxs-lookup"><span data-stu-id="df4df-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="df4df-205">Überprüfen Sie Folgendes, bevor Sie den Migrationsbatch löschen.</span><span class="sxs-lookup"><span data-stu-id="df4df-205">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="df4df-206">Alle Benutzer verwenden Microsoft 365-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="df4df-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="df4df-207">Nach dem Löschen des Batches werden e-Mails, die an Postfächer im lokalen Exchange Server gesendet werden, nicht in die entsprechenden Microsoft 365-Postfächer kopiert.</span><span class="sxs-lookup"><span data-stu-id="df4df-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="df4df-208">Microsoft 365-Postfächer wurden mindestens einmal synchronisiert, nachdem e-Mails direkt an Sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="df4df-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="df4df-209">Stellen Sie dazu sicher, dass der Wert im Feld zuletzt synchronisierte Zeit für den Migrationsbatch aktueller ist als die Weiterleitung von e-Mails direkt an Microsoft 365-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="df4df-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="df4df-210">Führen Sie den folgenden Befehl aus, um den Migrationsbatch „CutoverBatch“ in Exchange Online PowerShell zu löschen:</span><span class="sxs-lookup"><span data-stu-id="df4df-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="df4df-211">Abschnitt 7: Zuweisen von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="df4df-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="df4df-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="df4df-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="df4df-213">**Aktivieren Sie Microsoft 365-Benutzerkonten für die migrierten Konten durch Zuweisen von Lizenzen.**</span><span class="sxs-lookup"><span data-stu-id="df4df-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="df4df-214">Wenn Sie keine Lizenz zuweisen, wird das Postfach nach Ablauf der Kulanzzeit (30 Tage) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="df4df-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="df4df-215">Informationen zum Zuweisen einer Lizenz im Microsoft 365 Admin Center finden Sie unter [zuweisen oder](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)Aufheben der Zuweisung von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="df4df-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="df4df-216">Schritt 8: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="df4df-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="df4df-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="df4df-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="df4df-218">**Erstellen Sie einen AutoErmittlung-DNS-Eintrag, damit Benutzer problemlos auf ihre Postfächer zugreifen können.**</span><span class="sxs-lookup"><span data-stu-id="df4df-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="df4df-219">Nachdem alle lokalen Postfächer zu Microsoft 365 migriert wurden, können Sie einen Auto Ermittlungs-DNS-Eintrag für Ihre Microsoft 365-Organisation konfigurieren, um Benutzern die einfache Verbindung mit ihren neuen Microsoft 365-Postfächern mit Outlook und mobilen Clients zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="df4df-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="df4df-220">In diesem neuen DNS-Eintrag für die AutoErmittlung muss derselbe Namespace verwendet werden, den Sie für Ihre Microsoft 365-Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="df4df-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="df4df-221">Wenn der Namespace für die Cloud-basierte Organisation beispielsweise "cloud.contoso.com" lautet, müssen Sie den DNS-Datensatz "autodiscover.cloud.contoso.com" für die AutoErmittlung erstellen.</span><span class="sxs-lookup"><span data-stu-id="df4df-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="df4df-222">Wenn Sie Ihre Exchange Server beibehalten, sollten Sie auch sicherstellen, dass der AutoErmittlungs-DNS-CNAME-Eintrag sowohl im internen als auch im externen DNS nach der Migration auf Microsoft 365 verweist, damit der Outlook-Client eine Verbindung mit dem richtigen Postfach herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="df4df-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="df4df-223">In Exchange 2007, Exchange 2010 und Exchange 2013 sollten Sie auch  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` auf `Null` festlegen.</span><span class="sxs-lookup"><span data-stu-id="df4df-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span>

    <span data-ttu-id="df4df-224">Microsoft 365 verwendet einen CNAME-Eintrag, um den AutoErmittlungsdienst für Outlook und Mobile Clients zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="df4df-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="df4df-225">Der CNAME-Eintrag für die AutoErmittlung muss folgende Informationen enthalten:</span><span class="sxs-lookup"><span data-stu-id="df4df-225">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="df4df-226">**Alias:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="df4df-226">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="df4df-227">**Ziel:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df4df-227">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="df4df-228">Weitere Informationen finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span><span class="sxs-lookup"><span data-stu-id="df4df-228">For more information, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span></span>

- <span data-ttu-id="df4df-229">**Nehmen Sie lokale Exchange-Server außer Betrieb.**</span><span class="sxs-lookup"><span data-stu-id="df4df-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="df4df-230">Nachdem Sie sichergestellt haben, dass alle e-Mails direkt an die Microsoft 365-Postfächer weitergeleitet werden und Sie Ihre lokale e-Mail-Organisation nicht mehr warten müssen oder nicht die Implementierung einer Lösung für einmaliges Anmelden (Single Sign-on, SSO) planen möchten, können Sie Exchange von ihren Servern deinstallieren und Ihre lokale Exchange-Organisation entfernen.</span><span class="sxs-lookup"><span data-stu-id="df4df-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="df4df-231">Weitere Informationen erhalten Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="df4df-231">For more information, see the following:</span></span>

  - [<span data-ttu-id="df4df-232">Ändern oder Entfernen von Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="df4df-232">Modify or Remove Exchange 2010</span></span>](https://go.microsoft.com/fwlink/?LinkId=217936)

  - [<span data-ttu-id="df4df-233">Entfernen einer Exchange 2007-Organisation</span><span class="sxs-lookup"><span data-stu-id="df4df-233">How to Remove an Exchange 2007 Organization</span></span>](https://go.microsoft.com/fwlink/?LinkID=100485)

  - [<span data-ttu-id="df4df-234">Deinstallieren von Exchange Server 2003</span><span class="sxs-lookup"><span data-stu-id="df4df-234">How to Uninstall Exchange Server 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=56561)


