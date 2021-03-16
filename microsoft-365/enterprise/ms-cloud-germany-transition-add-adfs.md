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
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727467"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="5b895-103">AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="5b895-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="5b895-104">Diese Konfigurationsänderung kann jederzeit vor Beginn der Phase 4 angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b895-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="5b895-105">Nach Abschluss von Phase 2 funktioniert die Konfigurationsänderung und Sie können sich bei Office 365 Global-Endpunkten wie `https://portal.office.com` anmelden.</span><span class="sxs-lookup"><span data-stu-id="5b895-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="5b895-106">Wenn Sie die Konfigurationsänderung vor Phase 2 implementieren, funktionieren die globalen Office 365-Endpunkte _noch nicht_, aber die neue Vertrauensstellung der vertrauenden Partei ist weiterhin Teil Ihrer Active Directory-Verbunddienste(AD FS)-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5b895-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="5b895-107">So migrieren Sie Ihre AD FS-Farm aus Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="5b895-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="5b895-108">Sichern Sie Ihre AD FS-Einstellungen einschließlich FF Trust-Informationen mit [diesen Schritten](#backup).</span><span class="sxs-lookup"><span data-stu-id="5b895-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="5b895-109">Geben Sie der Sicherungskopie den Namen **Microsoft Cloud Deutschland_Only**, um anzugeben, dass sie nur die Mandanteninformationen zu Microsoft Cloud Deutschland enthält.</span><span class="sxs-lookup"><span data-stu-id="5b895-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="5b895-110">Testen Sie die Wiederherstellung mithilfe der Sicherung „Microsoft Cloud Deutschland_Only“. Die AD FS-Farm sollte weiterhin nur als Microsoft Cloud Deutschland eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5b895-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="5b895-111">Führen Sie nach Abschluss und Testen der AD FS-Sicherung die folgenden Schritte aus, um Ihrer ADFS-Konfiguration eine neue Vertrauensstellung für vertrauende Parteien hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="5b895-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="5b895-112">Öffnen Sie die AD FS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="5b895-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="5b895-113">Erweitern Sie im linken Bereich der ADFS-Verwaltungskonsole **ADFS**, dann **Vertrauensstellungen** und dann **Vertrauensstellungen für vertrauende Parteien**</span><span class="sxs-lookup"><span data-stu-id="5b895-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="5b895-114">Wählen Sie im rechten Bereich **Vertrauensstellung für vertrauende Partei hinzufügen...**</span><span class="sxs-lookup"><span data-stu-id="5b895-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="5b895-115">Wählen Sie auf der Seite **Willkommen** des Assistenten zum Hinzufügen von Vertrauensstellungen der vertrauenden Seite **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5b895-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="5b895-116">Wählen Sie auf der Seite **Datenquelle auswählen** die Option **Online oder in einem lokalen Netzwerk veröffentlichte Daten über die vertrauende Seite importieren** aus.</span><span class="sxs-lookup"><span data-stu-id="5b895-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="5b895-117">Der Wert für **Adresse der Verbundmetadaten (Hostname oder URL)** muss auf `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="5b895-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="5b895-118">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5b895-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="5b895-119">Geben Sie auf der Seite **Datenquelle auswählen** den Anzeigenamen ein, z. B. **Microsoft Office 365 Identity Platform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="5b895-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="5b895-120">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5b895-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="5b895-121">Wählen Sie auf der Seite des Assistenten **Mehrstufige Authentifizierung jetzt konfigurieren?** aus. Wählen Sie die entsprechende Auswahl entsprechend Ihren Authentifizierungsanforderungen aus.</span><span class="sxs-lookup"><span data-stu-id="5b895-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="5b895-122">Wenn Sie sich an die Standardeinstellung halten, wählen Sie **Ich möchte derzeit keine Einstellungen für die Multi-Faktor-Authentifizierung für diese Vertrauensstellung der vertrauenden Partei konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="5b895-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="5b895-123">Sie können diese Einstellung später ändern, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="5b895-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="5b895-124">Klicken Sie in den **Ausstellungsautorisierungsregeln auswählen** auf **Alle Benutzer auf diese ausgewählte vertrauende Partei zugreifen lassen**, und klicken Sie auf **Weiter**</span><span class="sxs-lookup"><span data-stu-id="5b895-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="5b895-125">Klicken Sie auf der Seite **Bereit zum Hinzufügen von Vertrauensstellung** auf **Weiter**, um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5b895-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="5b895-126">Klicken Sie auf der Seite **Fertig stellen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="5b895-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="5b895-127">Durch Schließen des Assistenten wird die Vertrauensstellung der vertrauenden Partei mit den globalen Office 365-Diensten hergestellt.</span><span class="sxs-lookup"><span data-stu-id="5b895-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="5b895-128">Es sind jedoch noch keine Ausstellungstransformationsregeln konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5b895-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="5b895-129">Sie können mit [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) die richtigen Ausstellungstransformationsregeln generieren.</span><span class="sxs-lookup"><span data-stu-id="5b895-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="5b895-130">Die mit AD FS-Hilfe generierten Anspruchsregeln können entweder über die AD FS-Verwaltungskonsole oder mithilfe von PowerShell manuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5b895-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="5b895-131">Die AD FS-Hilfe generiert die erforderlichen PowerShell-Skripts, die ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5b895-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="5b895-132">Führen Sie in AD FS-Hilfe **Ansprüche generieren** aus, und kopieren Sie das PowerShell-Anspruchtransformationsskript mithilfe der Option **Kopieren** in der rechten oberen Ecke des Skripts.</span><span class="sxs-lookup"><span data-stu-id="5b895-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="5b895-133">Öffnen Sie Ihren bevorzugten Texteditor und fügen Sie das PowerShell-Skript in ein neues Textfenster ein.</span><span class="sxs-lookup"><span data-stu-id="5b895-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="5b895-134">Fügen Sie die folgenden PowerShell-Zeilen ab Schritt 2 am Ende des eingefügten Skripts hinzu</span><span class="sxs-lookup"><span data-stu-id="5b895-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="5b895-135">Speichern Sie das PowerShell-Skript und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="5b895-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="5b895-136">Stellen Sie sicher, dass zwei Vertrauensstellungen der vertrauenden Partei vorhanden sind. Eine für die Microsoft Cloud Deutschland und eine für den Office 365 Global-Dienst.</span><span class="sxs-lookup"><span data-stu-id="5b895-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="5b895-137">Sichern Sie Ihre-Vertrauensstellungen mit [diesen Schritten](#backup).</span><span class="sxs-lookup"><span data-stu-id="5b895-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="5b895-138">Speichern Sie die Datei unter dem Namen **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="5b895-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="5b895-139">Schließen Sie Ihre Backend-Migration ab und stellen Sie sicher, dass AD FS während des Migrationsprozesses noch funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5b895-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="5b895-140">AD FS-Notfallwiederherstellung (WID-Datenbank)</span><span class="sxs-lookup"><span data-stu-id="5b895-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="5b895-141">Wenn Sie die AD FS-Farm in einem Notfall wiederherstellen möchten, muss dazu das [AD FS Rapid Restore-Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="5b895-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="5b895-142">Deshalb muss das Tool heruntergeladen und vor Beginn der Migration eine Sicherung erstellt und sicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5b895-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="5b895-143">In diesem Beispiel (TAT-Umgebungen) wurden die folgenden Befehle zum Sichern der Farm ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b895-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="5b895-144">Sichern einer AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="5b895-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="5b895-145">Installieren Sie das AD FS Rapid Restore-Tool auf dem primären AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="5b895-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="5b895-146">Importieren Sie das Modul in einer PowerShell-Sitzung mit diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="5b895-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="5b895-147">Führen Sie den Befehl zum Sichern aus:</span><span class="sxs-lookup"><span data-stu-id="5b895-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="5b895-148">Speichern Sie die Sicherung sicher an einem bestimmten Ort.</span><span class="sxs-lookup"><span data-stu-id="5b895-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="5b895-149">Wiederherstellen einer AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="5b895-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="5b895-150">Wenn Ihre Farm vollständig fehlgeschlagen ist und es keine Möglichkeit zur Rückkehr zu der alten Farm gibt, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="5b895-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="5b895-151">Verschieben Sie die zuvor generierte und gespeicherte Sicherung auf den neuen primären AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="5b895-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="5b895-152">Führen Sie den folgenden `Restore-ADFS`-PowerShell-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="5b895-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="5b895-153">Importieren Sie vorher bei Bedarf das AD FS-SSL-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="5b895-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="5b895-154">Zeigen Sie auf den neuen AD FS-Servern auf Ihre neuen DNS-Einträge oder den Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="5b895-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="5b895-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b895-155">More information</span></span>

<span data-ttu-id="5b895-156">Erste Schritte:</span><span class="sxs-lookup"><span data-stu-id="5b895-156">Getting started:</span></span>

- [<span data-ttu-id="5b895-157">Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen</span><span class="sxs-lookup"><span data-stu-id="5b895-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="5b895-158">Hilfe zur Microsoft Cloud Deutschland-Migration Assistance</span><span class="sxs-lookup"><span data-stu-id="5b895-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="5b895-159">So können Sie sich für die Migration anmelden</span><span class="sxs-lookup"><span data-stu-id="5b895-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="5b895-160">Kundenerfahrung während der Migration</span><span class="sxs-lookup"><span data-stu-id="5b895-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="5b895-161">Der Weg durch die Umstellung:</span><span class="sxs-lookup"><span data-stu-id="5b895-161">Moving through the transition:</span></span>

- [<span data-ttu-id="5b895-162">Phasen, Aktionen und Auswirkungen der Migration</span><span class="sxs-lookup"><span data-stu-id="5b895-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="5b895-163">Zusätzliche Vorarbeit</span><span class="sxs-lookup"><span data-stu-id="5b895-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="5b895-164">Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="5b895-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="5b895-165">Cloud-Apps:</span><span class="sxs-lookup"><span data-stu-id="5b895-165">Cloud apps:</span></span>

- [<span data-ttu-id="5b895-166">Informationen zum Dynamics 365-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="5b895-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="5b895-167">Informationen zum Power BI-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="5b895-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="5b895-168">Erste Schritte mit dem Upgrade von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b895-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
