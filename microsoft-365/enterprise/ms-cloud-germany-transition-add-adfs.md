---
title: AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: Active Directory-Migrationsschritte für die Verbunddienste (AD FS) für die Migration von Microsoft Cloud Deutschland.'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688665"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="9af1b-103">AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="9af1b-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="9af1b-104">So migrieren Sie Ihre Active Directory Verbunddienste-Farm (AD FS) von Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="9af1b-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="9af1b-105">Sichern Sie Ihre AD FS-Einstellungen einschließlich FF Trust Info mit [diesen Schritten](#backup).</span><span class="sxs-lookup"><span data-stu-id="9af1b-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="9af1b-106">Nennen Sie die **Microsoft Cloud-Deutschland_Only** für die Sicherung, um anzugeben, dass nur die Microsoft Cloud Deutschland-Mandanten Info angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9af1b-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="9af1b-107">Testen der Wiederherstellung mit der Microsoft-Cloud Deutschland_Only Sicherung sollte die AD FS-Farm nur weiterhin als Microsoft Cloud Deutschland ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9af1b-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="9af1b-108">Erstellen Sie eine neue Vertrauensstellung der vertrauenden Seite von **AD FS > Office 365-Diensten**.</span><span class="sxs-lookup"><span data-stu-id="9af1b-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="9af1b-109">Wählen Sie in **Vertrauensstellungen** der vertrauenden Seite in der AD FS-Verwaltungskonsole die Option Vertrauensstellung der vertrauenden **Seite hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="9af1b-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="9af1b-110">Klicken Sie auf der **Willkommens** Seite des Assistenten zum Hinzufügen von Vertrauensstellungen der vertrauenden Seite auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="9af1b-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="9af1b-111">Wählen Sie auf der Seite **Datenquelleauswählen** die Option **Daten über die vertrauende Seite, die Online veröffentlicht wurde oder in einem lokalen Netzwerk importieren** aus.</span><span class="sxs-lookup"><span data-stu-id="9af1b-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="9af1b-112">Die **Adresse der Verbundmetadaten (Hostname oder URL)** ist auf festgelegt `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="9af1b-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="9af1b-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9af1b-113">Click **Next**.</span></span>
7. <span data-ttu-id="9af1b-114">Geben Sie auf der Seite **Datenquelleauswählen** den Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="9af1b-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="9af1b-115">Microsoft empfiehlt **Microsoft Office 365-Identitäts Plattform weltweit**.</span><span class="sxs-lookup"><span data-stu-id="9af1b-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="9af1b-116">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9af1b-116">Click **Next**.</span></span>
8. <span data-ttu-id="9af1b-117">Klicken Sie auf der Seite **mehrstufige Authentifizierung jetzt konfigurieren?** auf **weiter** , **Wählen Sie Ausstellungs Autorisierungsregeln** und **zum Hinzufügen von Vertrauensstellungsseiten vorbereiten** aus.</span><span class="sxs-lookup"><span data-stu-id="9af1b-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="9af1b-118">Klicken Sie auf der Seite **Fertig stellen** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="9af1b-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="9af1b-119">Wenn Sie den Assistenten schließen, wird die Vertrauensstellung der vertrauenden Seite für die Office 365 Dienste-eSTS eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="9af1b-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="9af1b-120">Es werden jedoch keine Regeln für die Veröffentlichungs Transformation erstellt.</span><span class="sxs-lookup"><span data-stu-id="9af1b-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="9af1b-121">Sie können die [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) verwenden, um die richtigen Regeln zur Veröffentlichungs Transformation zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9af1b-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="9af1b-122">Die generierten Anspruchsregeln, die mit der AD FS-Hilfe erstellt wurden, können entweder manuell über die AD FS-Verwaltungskonsole oder mit PowerShell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9af1b-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="9af1b-123">In der AD FS-Hilfe werden die erforderlichen PowerShell-Skripts generiert, die ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9af1b-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="9af1b-124">Führen Sie **Generate Claims** on AD FS help aus, und kopieren Sie das PowerShell-Anspruchs Transformationsskript mithilfe der **Copy** -Option in der rechten oberen Ecke des Skripts.</span><span class="sxs-lookup"><span data-stu-id="9af1b-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="9af1b-125">Fügen Sie die generierte PowerShell in Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9af1b-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="9af1b-126">Führen Sie das abgeschlossene Skript aus.</span><span class="sxs-lookup"><span data-stu-id="9af1b-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="9af1b-127">Stellen Sie sicher, dass zwei Vertrauensstellungen der vertrauenden Seite vorhanden sind. einer für weltweit und einer für BF.</span><span class="sxs-lookup"><span data-stu-id="9af1b-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="9af1b-128">Sichern Sie Ihre Vertrauensstellungen mit [den folgenden Schritten](#backup).</span><span class="sxs-lookup"><span data-stu-id="9af1b-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="9af1b-129">Speichern Sie Sie mit dem Namen **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="9af1b-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="9af1b-130">Schließen Sie die Back-End-Migration ab, und stellen Sie sicher, dass AD FS während des Migrationsprozesses weiterhin funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9af1b-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="9af1b-131">AD FS-Notfallwiederherstellung (WID-Datenbank)</span><span class="sxs-lookup"><span data-stu-id="9af1b-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="9af1b-132">Um die AD FS-Farm in einem Disaster [AD FS-Tool für die schnelle Wiederherstellung](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) wiederherzustellen, muss die Anwendung genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="9af1b-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="9af1b-133">Daher muss das Tool heruntergeladen werden, und vor dem Beginn der Migration muss eine Sicherung erstellt und sicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9af1b-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="9af1b-134">In diesem Beispiel (Tat Environments) wurden die folgenden Befehle ausgeführt, um die Farm zu sichern:</span><span class="sxs-lookup"><span data-stu-id="9af1b-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="9af1b-135">Sichern einer AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="9af1b-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="9af1b-136">Installieren Sie das AD FS Rapid Restore-Tool auf dem primären AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="9af1b-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="9af1b-137">Importieren Sie das Modul in eine PowerShell-Sitzung mit diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="9af1b-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="9af1b-138">Führen Sie den Befehl Backup aus:</span><span class="sxs-lookup"><span data-stu-id="9af1b-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="9af1b-139">Speichern Sie die Sicherung sicher an einem gewünschten Ziel.</span><span class="sxs-lookup"><span data-stu-id="9af1b-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="9af1b-140">Wiederherstellen einer AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="9af1b-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="9af1b-141">Wenn die Farm vollständig ausgefallen ist und keine Möglichkeit besteht, zur alten Farm zurückzukehren, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="9af1b-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="9af1b-142">Verschiebt die zuvor generierte und gespeicherte Sicherung auf den neuen primären AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="9af1b-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="9af1b-143">Führen Sie den folgenden `Restore-ADFS` PowerShell-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="9af1b-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="9af1b-144">Falls erforderlich, importieren Sie das AD FS-SSL-Zertifikat vorab.</span><span class="sxs-lookup"><span data-stu-id="9af1b-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="9af1b-145">Richten Sie Ihre neuen DNS-Einträge oder den Lastenausgleich auf die neuen AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="9af1b-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="9af1b-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9af1b-146">More information</span></span>

<span data-ttu-id="9af1b-147">Erste Schritte:</span><span class="sxs-lookup"><span data-stu-id="9af1b-147">Getting started:</span></span>

- [<span data-ttu-id="9af1b-148">Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums</span><span class="sxs-lookup"><span data-stu-id="9af1b-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="9af1b-149">Hilfe zur Microsoft Cloud Deutschland-Migration Assistance</span><span class="sxs-lookup"><span data-stu-id="9af1b-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="9af1b-150">So können Sie sich für die Migration anmelden</span><span class="sxs-lookup"><span data-stu-id="9af1b-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="9af1b-151">Kundenerfahrung während der Migration</span><span class="sxs-lookup"><span data-stu-id="9af1b-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="9af1b-152">Navigieren durch den Übergang:</span><span class="sxs-lookup"><span data-stu-id="9af1b-152">Moving through the transition:</span></span>

- [<span data-ttu-id="9af1b-153">Phasen, Aktionen und Auswirkungen der Migration</span><span class="sxs-lookup"><span data-stu-id="9af1b-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="9af1b-154">Zusätzliche vorab Arbeit</span><span class="sxs-lookup"><span data-stu-id="9af1b-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="9af1b-155">Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="9af1b-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="9af1b-156">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="9af1b-156">Cloud apps:</span></span>

- [<span data-ttu-id="9af1b-157">Informationen zum Dynamics 365-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="9af1b-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="9af1b-158">Informationen zum Power BI-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="9af1b-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="9af1b-159">Erste Schritte mit dem Upgrade von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9af1b-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
