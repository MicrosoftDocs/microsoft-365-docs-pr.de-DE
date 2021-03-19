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
ms.openlocfilehash: 852fc8f93158d7b6080f1add5a05e7367539f889
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838413"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="f5d98-103">AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="f5d98-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="f5d98-104">Diese Konfigurationsänderung muss zu einem beliebigen Zeitpunkt vor dem Start von Phase 2 vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="f5d98-105">Sobald Phase 2 abgeschlossen ist, funktioniert die Konfigurationsänderung und Sie können sich bei Office 365 Global-Endpunkten wie `https://portal.office.com` anmelden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="f5d98-106">Wenn Sie die Konfigurationsänderung vor Phase 2 implementieren, funktionieren die globalen Office 365-Endpunkte _noch nicht_, aber die neue Vertrauensstellung der vertrauenden Partei ist weiterhin Teil Ihrer Active Directory-Verbunddienste(AD FS)-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f5d98-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="f5d98-107">Kunden, die Verbundauthentifizierung mit Active Directory-Verbunddienste (AD FS) verwenden, sollten während der Migration keine Änderungen an Aussteller-URIs vornehmen, die für alle Authentifizierungen mit lokalen Active Directory Domain Services (AD DS) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="f5d98-108">Das Ändern von Aussteller-URIs führt zu Authentifizierungsfehlern für Benutzer in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="f5d98-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="f5d98-109">Aussteller-URIs können direkt in AD FS geändert werden oder wenn eine Domäne von _verwaltet_ zu _Verbund_ oder umgekehrt konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="f5d98-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="f5d98-110">Wir empfehlen, dass Sie keine Verbunddomäne im migrierten Azure AD-Mandanten hinzufügen, entfernen oder konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f5d98-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="f5d98-111">Aussteller-URIs können geändert werden, nachdem die Migration vollständig abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f5d98-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="f5d98-112">Um Ihre AD FS-Farm für die Migration aus der Microsoft Cloud Deutschland vorzubereiten, führen Sie die folgenden Schritte durch:</span><span class="sxs-lookup"><span data-stu-id="f5d98-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="f5d98-113">Sichern Sie Ihre AD FS-Einstellungen, einschließlich der bestehenden Vertrauensstellung der vertrauenden Partei von Microsoft Cloud Deutschland, mit [diesen Schritten](#backup).</span><span class="sxs-lookup"><span data-stu-id="f5d98-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="f5d98-114">Nennen Sie das Backup **MicrosoftCloudDeutschlandOnly**, um anzugeben, dass sie nur die Microsoft Cloud Deutschland-Mieterinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="f5d98-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f5d98-115">Das Backup wird nicht nur die bestehende Office 365 Vertrauensstellung der vertrauenden Partei für die Microsoft Cloud Deutschland enthalten, sondern auch alle anderen Vertrauensstellungen für vertrauende Parteien, die auf der jeweiligen AD FS-Farm vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f5d98-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="f5d98-116">Testen Sie die Wiederherstellung mit dem MicrosoftCloudDeutschlandOnly-Backup. Die AD FS-Farm sollte weiterhin nur als Microsoft Cloud Deutschland betrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="f5d98-117">Führen Sie nach Abschluss und Testen der AD FS-Sicherung die folgenden Schritte aus, um Ihrer ADFS-Konfiguration eine neue Vertrauensstellung für vertrauende Parteien hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f5d98-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="f5d98-118">Öffnen Sie die AD FS-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="f5d98-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="f5d98-119">Navigieren Sie im linken Bereich der ADFS-Verwaltungskonsole zum Menü **Vertrauensstellungen für vertrauende Parteien**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="f5d98-120">Wählen Sie im rechten Bereich **Vertrauensstellung der vertrauenden Partei hinzufügen...**</span><span class="sxs-lookup"><span data-stu-id="f5d98-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="f5d98-121">Wählen Sie **Start** auf der Seite **Willkommen** des Assistenten zum Hinzufügen von Vertrauensstellung der vertrauenden Partei.</span><span class="sxs-lookup"><span data-stu-id="f5d98-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="f5d98-122">Wählen Sie auf der Seite **Datenquelle auswählen** die Option **Online oder in einem lokalen Netzwerk veröffentlichte Daten über die vertrauende Seite importieren** aus.</span><span class="sxs-lookup"><span data-stu-id="f5d98-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="f5d98-123">Der Wert für **Adresse der Verbundmetadaten (Hostname oder URL)** muss auf `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="f5d98-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="f5d98-124">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-124">Click **Next**.</span></span>

6. <span data-ttu-id="f5d98-125">Geben Sie auf der Seite **Anzeigename angeben** den Anzeigenamen ein, z. B. **Microsoft Office 365-Identitätsplatform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="f5d98-126">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-126">Click **Next**.</span></span>

7. <span data-ttu-id="f5d98-127">Wenn Sie ADFS in Windows Server 2012 verwenden, wählen Sie auf der Assistentenseite **Jetzt die Multi-Faktor-Authentifizierung konfigurieren?** die entsprechende Auswahl entsprechend Ihren Authentifizierungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="f5d98-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="f5d98-128">Wenn Sie sich an die Standardeinstellung halten, wählen Sie **Ich möchte derzeit keine Einstellungen für die Multi-Faktor-Authentifizierung für diese Vertrauensstellung der vertrauenden Partei konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="f5d98-129">Sie können diese Einstellung später ändern, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="f5d98-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="f5d98-130">Für AD FS 2012: Lassen Sie im Dialogfeld **Ausgaberegeln auswählen** die Option **Allen Benutzern den Zugriff auf diese vertrauende Partei** erlauben ausgewählt und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

8. <span data-ttu-id="f5d98-131">Für AD FS 2016 und AD FS 2019: Wählen Sie auf der Seite **Zugriffskontrollrichtlinie auswählen** die entsprechende Zugriffssteuerungsrichtlinie aus und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="f5d98-132">Wenn keine ausgewählt wird, funktioniert die Vertrauensstellung der vertrauenden Partei **NICHT**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

9. <span data-ttu-id="f5d98-133">Klicken Sie auf der Seite **Bereit zum Hinzufügen von Vertrauensstellung** auf **Weiter**, um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f5d98-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

10. <span data-ttu-id="f5d98-134">Klicken Sie auf der Seite **Fertig stellen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="f5d98-135">Durch das Schließen des Assistenten wird die Vertrauensstellung der vertrauenden Partei mit dem Office 365 Global-Dienst eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="f5d98-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="f5d98-136">Es sind jedoch noch keine Ausstellungstransformationsregeln konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f5d98-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="f5d98-137">Sie können mit [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) die richtigen Ausstellungstransformationsregeln generieren.</span><span class="sxs-lookup"><span data-stu-id="f5d98-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="f5d98-138">Die mit AD FS-Hilfe generierten Anspruchsregeln können entweder über die AD FS-Verwaltungskonsole oder mithilfe von PowerShell manuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="f5d98-139">Die AD FS-Hilfe generiert die erforderlichen PowerShell-Skripts, die ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f5d98-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="f5d98-140">[Die AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) generiert die Standardregeln für die Ausgabetransformation, die mit dem Produkt geliefert werden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="f5d98-141">Wenn jedoch benutzerdefinierte Regeln für die Ausgabetransformation in der Microsoft Cloud Deutschland Vertrauensstellung der vertrauenden Partei vorhanden sind (z. B. benutzerdefinierte Aussteller-URIs, nicht standardmäßige unveränderliche IDs oder andere Anpassungen), müssen die von der AD FS-Hilfe generierten Regeln so geändert werden, dass sie zur benutzerdefinierten Logik passen, die derzeit für die Microsoft Cloud Deutschland Vertrauensstellung der vertrauenden Partei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f5d98-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="f5d98-142">Wenn diese Anpassungen nicht in die über die [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) generierten Regeln integriert sind, wird die Authentifizierung bei **Microsoft Office 365-Identitätsplattform WorldWide** höchstwahrscheinlich **nicht** für Ihre föderierten Identitäten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f5d98-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="f5d98-143">Führen Sie **Ansprüche generieren** in [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) aus und kopieren Sie das PowerShell-Skript über die Option **Kopieren** in der rechten oberen Ecke des Skripts.</span><span class="sxs-lookup"><span data-stu-id="f5d98-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="f5d98-144">Führen Sie die in der [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) beschriebenen Schritte aus, um das PowerShell-Skript in Ihrer AD FS-Farm auszuführen, um den globalen Relying Party Trust zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="f5d98-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span>

3. <span data-ttu-id="f5d98-145">Stellen Sie sicher, dass zwei Vertrauensstellungen der vertrauenden Parteien vorhanden sind. Eine für die Microsoft Cloud Deutschland und eine für den Office 365 Global-Dienst.</span><span class="sxs-lookup"><span data-stu-id="f5d98-145">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="f5d98-146">Der folgende Befehl kann für die Prüfung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-146">The following command can be leveraged for the check.</span></span> <span data-ttu-id="f5d98-147">Er sollte zwei Zeilen und die jeweiligen Namen und Bezeichner zurücksenden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-147">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="f5d98-148">Sichern Sie Ihre vollständige Migrationskonfiguration, einschließlich beider Vertrauensstellungen der vertrauenden Parteien, mit den [folgenden Schritten](#backup).</span><span class="sxs-lookup"><span data-stu-id="f5d98-148">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="f5d98-149">Speichern Sie es unter dem Namen **MicrosoftCloudDeutschlandUndWeltweit**.</span><span class="sxs-lookup"><span data-stu-id="f5d98-149">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="f5d98-150">Während sich Ihr Mandant in der Migration befindet, überprüfen Sie regelmäßig, ob die AD FS-Authentifizierung mit Microsoft Cloud Deutschland und Microsoft Global Cloud in den verschiedenen unterstützten Migrationsschritten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f5d98-150">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>


## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="f5d98-151">AD FS-Notfallwiederherstellung (WID-Datenbank)</span><span class="sxs-lookup"><span data-stu-id="f5d98-151">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="f5d98-152">Wenn Sie die AD FS-Farm in einem Notfall wiederherstellen möchten, muss dazu das [AD FS Rapid Restore-Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-152">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="f5d98-153">Deshalb muss das Tool heruntergeladen und vor Beginn der Migration eine Sicherung erstellt und sicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f5d98-153">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="f5d98-154">In diesem Beispiel wurden die folgenden Befehle ausgeführt, um eine Farm zu sichern, die auf einer WID-Datenbank läuft:</span><span class="sxs-lookup"><span data-stu-id="f5d98-154">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="f5d98-155">Sichern einer AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="f5d98-155">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="f5d98-156">Installieren Sie das AD FS Rapid Restore-Tool auf dem primären AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="f5d98-156">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="f5d98-157">Importieren Sie das Modul in einer PowerShell-Sitzung mit diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="f5d98-157">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="f5d98-158">Führen Sie den Befehl zum Sichern aus:</span><span class="sxs-lookup"><span data-stu-id="f5d98-158">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="f5d98-159">Speichern Sie die Sicherung sicher an einem bestimmten Ort.</span><span class="sxs-lookup"><span data-stu-id="f5d98-159">Store the backup safely on a desired destination.</span></span>


### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="f5d98-160">Wiederherstellen einer AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="f5d98-160">Restore an AD FS Farm</span></span>

<span data-ttu-id="f5d98-161">Wenn Ihre Farm vollständig fehlgeschlagen ist und es keine Möglichkeit zur Rückkehr zu der alten Farm gibt, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="f5d98-161">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="f5d98-162">Verschieben Sie die zuvor generierte und gespeicherte Sicherung auf den neuen primären AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="f5d98-162">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="f5d98-163">Führen Sie den folgenden `Restore-ADFS`-PowerShell-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f5d98-163">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="f5d98-164">Importieren Sie vorher bei Bedarf das AD FS-SSL-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="f5d98-164">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="f5d98-165">Zeigen Sie auf den neuen AD FS-Servern auf Ihre neuen DNS-Einträge oder den Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="f5d98-165">Point your new DNS records or load balancer to the new AD FS servers.</span></span>


## <a name="more-information"></a><span data-ttu-id="f5d98-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5d98-166">More information</span></span>

<span data-ttu-id="f5d98-167">Erste Schritte:</span><span class="sxs-lookup"><span data-stu-id="f5d98-167">Getting started:</span></span>

- [<span data-ttu-id="f5d98-168">Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen</span><span class="sxs-lookup"><span data-stu-id="f5d98-168">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="f5d98-169">Hilfe zur Microsoft Cloud Deutschland-Migration Assistance</span><span class="sxs-lookup"><span data-stu-id="f5d98-169">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="f5d98-170">So können Sie sich für die Migration anmelden</span><span class="sxs-lookup"><span data-stu-id="f5d98-170">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="f5d98-171">Kundenerfahrung während der Migration</span><span class="sxs-lookup"><span data-stu-id="f5d98-171">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="f5d98-172">Der Weg durch die Umstellung:</span><span class="sxs-lookup"><span data-stu-id="f5d98-172">Moving through the transition:</span></span>

- [<span data-ttu-id="f5d98-173">Phasen, Aktionen und Auswirkungen der Migration</span><span class="sxs-lookup"><span data-stu-id="f5d98-173">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="f5d98-174">Zusätzliche Vorarbeit</span><span class="sxs-lookup"><span data-stu-id="f5d98-174">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="f5d98-175">Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="f5d98-175">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="f5d98-176">Cloud-Apps:</span><span class="sxs-lookup"><span data-stu-id="f5d98-176">Cloud apps:</span></span>

- [<span data-ttu-id="f5d98-177">Informationen zum Dynamics 365-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="f5d98-177">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="f5d98-178">Informationen zum Power BI-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="f5d98-178">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="f5d98-179">Erste Schritte mit dem Upgrade von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5d98-179">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
