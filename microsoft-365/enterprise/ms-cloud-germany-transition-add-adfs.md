---
title: AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland
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
description: 'Zusammenfassung: AD FS-Migrationsschritte (Active Directory Federation Services, Active Directory-Verbunddienste) für die Migration von Microsoft Cloud Deutschland.'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688665"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="692aa-103">AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="692aa-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="692aa-104">So migrieren Sie Ihre AD FS-Farm (Active Directory Federation Services, Active Directory-Verbunddienste) aus Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="692aa-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="692aa-105">Sichern Sie Ihre AD FS-Einstellungen einschließlich FF Trust-Informationen mit [diesen Schritten](#backup).</span><span class="sxs-lookup"><span data-stu-id="692aa-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="692aa-106">Geben Sie der Sicherungskopie den Namen **Microsoft Cloud Deutschland_Only**, um anzugeben, dass sie nur die Mandanteninformationen zu Microsoft Cloud Deutschland enthält.</span><span class="sxs-lookup"><span data-stu-id="692aa-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="692aa-107">Testen Sie die Wiederherstellung mithilfe der Sicherung „Microsoft Cloud Deutschland_Only“. Die AD FS-Farm sollte weiterhin nur als Microsoft Cloud Deutschland eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="692aa-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="692aa-108">Erstellen Sie aus **AD FS > Office 365-Dienste** eine neue Vertrauensstellung der vertrauenden Seite.</span><span class="sxs-lookup"><span data-stu-id="692aa-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="692aa-109">Wählen Sie in der AD FS-Verwaltungskonsole in **Vertrauensstellung der vertrauenden Seite** die Option **Vertrauensstellung der vertrauenden Seite hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="692aa-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="692aa-110">Wählen Sie auf der Seite **Willkommen** des Assistenten zum Hinzufügen von Vertrauensstellungen der vertrauenden Seite **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="692aa-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="692aa-111">Wählen Sie auf der Seite **Datenquelle auswählen** die Option **Online oder in einem lokalen Netzwerk veröffentlichte Daten über die vertrauende Seite importieren** aus.</span><span class="sxs-lookup"><span data-stu-id="692aa-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="692aa-112">Der Wert für **Adresse der Verbundmetadaten (Hostname oder URL)** wird auf `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="692aa-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="692aa-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="692aa-113">Click **Next**.</span></span>
7. <span data-ttu-id="692aa-114">Geben Sie auf der Seite **Datenquelle auswählen** den Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="692aa-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="692aa-115">Microsoft empfiehlt **Microsoft Office 365 Identity Platform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="692aa-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="692aa-116">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="692aa-116">Click **Next**.</span></span>
8. <span data-ttu-id="692aa-117">Klicken Sie auf den Seiten **Mehrstufige Authentifizierung jetzt konfigurieren?**, **Ausstellungsautorisierungsregeln auswählen** und **Bereit zum Hinzufügen der Vertrauensstellung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="692aa-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="692aa-118">Klicken Sie auf der Seite **Fertig stellen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="692aa-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="692aa-119">Durch Schließen des Assistenten wird die Vertrauensstellung der vertrauenden Seite zum ESTS der Office 365-Dienste eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="692aa-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="692aa-120">Es werden jedoch keine Ausstellungstransformationsregeln eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="692aa-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="692aa-121">Sie können mit [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) die richtigen Ausstellungstransformationsregeln generieren.</span><span class="sxs-lookup"><span data-stu-id="692aa-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="692aa-122">Die mit AD FS-Hilfe generierten Anspruchsregeln können entweder über die AD FS-Verwaltungskonsole oder mithilfe von PowerShell manuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="692aa-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="692aa-123">AD FS-Hilfe generiert die erforderlichen PowerShell-Skripts, die ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="692aa-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="692aa-124">Führen Sie in AD FS-Hilfe **Ansprüche generieren** aus, und kopieren Sie das PowerShell-Anspruchtransformationsskript mithilfe der Option **Kopieren** in der rechten oberen Ecke des Skripts.</span><span class="sxs-lookup"><span data-stu-id="692aa-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="692aa-125">Fügen Sie die generierte PowerShell in Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="692aa-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="692aa-126">Führen Sie das abgeschlossene Skript aus.</span><span class="sxs-lookup"><span data-stu-id="692aa-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="692aa-127">Überprüfen Sie, ob zwei Vertrauensstellungen der vertrauenden Seite vorhanden sind – eine für „weltweit“ und eine für „BF“.</span><span class="sxs-lookup"><span data-stu-id="692aa-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="692aa-128">Sichern Sie Ihre-Vertrauensstellungen mit [diesen Schritten](#backup).</span><span class="sxs-lookup"><span data-stu-id="692aa-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="692aa-129">Speichern Sie die Datei unter dem Namen **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="692aa-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="692aa-130">Schließen Sie Ihre Back-End-Migration ab, und stellen Sie sicher, dass AD FS während des Migrationsvorgangs weiterhin funktioniert.</span><span class="sxs-lookup"><span data-stu-id="692aa-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="692aa-131">AD FS-Notfallwiederherstellung (WID-Datenbank)</span><span class="sxs-lookup"><span data-stu-id="692aa-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="692aa-132">Wenn Sie die AD FS-Farm in einem Notfall wiederherstellen möchten, muss dazu das [AD FS Rapid Restore-Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="692aa-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="692aa-133">Deshalb muss das Tool heruntergeladen und vor Beginn der Migration eine Sicherung erstellt und sicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="692aa-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="692aa-134">In diesem Beispiel (TAT-Umgebungen) wurden die folgenden Befehle zum Sichern der Farm ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="692aa-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="692aa-135">Sichern einer AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="692aa-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="692aa-136">Installieren Sie das AD FS Rapid Restore-Tool auf dem primären AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="692aa-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="692aa-137">Importieren Sie das Modul in einer PowerShell-Sitzung mit diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="692aa-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="692aa-138">Führen Sie den Befehl zum Sichern aus:</span><span class="sxs-lookup"><span data-stu-id="692aa-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="692aa-139">Speichern Sie die Sicherung sicher an einem bestimmten Ort.</span><span class="sxs-lookup"><span data-stu-id="692aa-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="692aa-140">Wiederherstellen einer AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="692aa-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="692aa-141">Wenn Ihre Farm vollständig fehlgeschlagen ist und es keine Möglichkeit zur Rückkehr zu der alten Farm gibt, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="692aa-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="692aa-142">Verschieben Sie die zuvor generierte und gespeicherte Sicherung auf den neuen primären AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="692aa-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="692aa-143">Führen Sie den folgenden `Restore-ADFS`-PowerShell-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="692aa-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="692aa-144">Importieren Sie vorher bei Bedarf das AD FS-SSL-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="692aa-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="692aa-145">Zeigen Sie auf den neuen AD FS-Servern auf Ihre neuen DNS-Einträge oder den Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="692aa-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="692aa-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="692aa-146">More information</span></span>

<span data-ttu-id="692aa-147">Erste Schritte:</span><span class="sxs-lookup"><span data-stu-id="692aa-147">Getting started:</span></span>

- [<span data-ttu-id="692aa-148">Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen</span><span class="sxs-lookup"><span data-stu-id="692aa-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="692aa-149">Hilfe zur Microsoft Cloud Deutschland-Migration Assistance</span><span class="sxs-lookup"><span data-stu-id="692aa-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="692aa-150">So können Sie sich für die Migration anmelden</span><span class="sxs-lookup"><span data-stu-id="692aa-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="692aa-151">Kundenerfahrung während der Migration</span><span class="sxs-lookup"><span data-stu-id="692aa-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="692aa-152">Der Weg durch die Umstellung:</span><span class="sxs-lookup"><span data-stu-id="692aa-152">Moving through the transition:</span></span>

- [<span data-ttu-id="692aa-153">Phasen, Aktionen und Auswirkungen der Migration</span><span class="sxs-lookup"><span data-stu-id="692aa-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="692aa-154">Zusätzliche Vorarbeit</span><span class="sxs-lookup"><span data-stu-id="692aa-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="692aa-155">Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="692aa-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="692aa-156">Cloud-Apps:</span><span class="sxs-lookup"><span data-stu-id="692aa-156">Cloud apps:</span></span>

- [<span data-ttu-id="692aa-157">Informationen zum Dynamics 365-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="692aa-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="692aa-158">Informationen zum Power BI-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="692aa-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="692aa-159">Erste Schritte mit dem Upgrade von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="692aa-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
