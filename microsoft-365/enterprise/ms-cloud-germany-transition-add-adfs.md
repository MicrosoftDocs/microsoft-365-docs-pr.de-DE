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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland

So migrieren Sie Ihre Active Directory Verbunddienste-Farm (AD FS) von Microsoft Cloud Deutschland:

1. Sichern Sie Ihre AD FS-Einstellungen einschließlich FF Trust Info mit [diesen Schritten](#backup). Nennen Sie die **Microsoft Cloud-Deutschland_Only** für die Sicherung, um anzugeben, dass nur die Microsoft Cloud Deutschland-Mandanten Info angezeigt wird.
2. Testen der Wiederherstellung mit der Microsoft-Cloud Deutschland_Only Sicherung sollte die AD FS-Farm nur weiterhin als Microsoft Cloud Deutschland ausgeführt werden.
3. Erstellen Sie eine neue Vertrauensstellung der vertrauenden Seite von **AD FS > Office 365-Diensten**.
4. Wählen Sie in **Vertrauensstellungen** der vertrauenden Seite in der AD FS-Verwaltungskonsole die Option Vertrauensstellung der vertrauenden **Seite hinzufügen** aus.
5. Klicken Sie auf der **Willkommens** Seite des Assistenten zum Hinzufügen von Vertrauensstellungen der vertrauenden Seite auf **weiter** .
6. Wählen Sie auf der Seite **Datenquelleauswählen** die Option **Daten über die vertrauende Seite, die Online veröffentlicht wurde oder in einem lokalen Netzwerk importieren** aus. Die **Adresse der Verbundmetadaten (Hostname oder URL)** ist auf festgelegt `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Klicken Sie auf **Weiter**.
7. Geben Sie auf der Seite **Datenquelleauswählen** den Anzeigenamen ein. Microsoft empfiehlt **Microsoft Office 365-Identitäts Plattform weltweit**. Klicken Sie auf **Weiter**.
8. Klicken Sie auf der Seite **mehrstufige Authentifizierung jetzt konfigurieren?** auf **weiter** , **Wählen Sie Ausstellungs Autorisierungsregeln** und **zum Hinzufügen von Vertrauensstellungsseiten vorbereiten** aus.
9. Klicken Sie auf der Seite **Fertig stellen** auf **Schließen** .

Wenn Sie den Assistenten schließen, wird die Vertrauensstellung der vertrauenden Seite für die Office 365 Dienste-eSTS eingerichtet. Es werden jedoch keine Regeln für die Veröffentlichungs Transformation erstellt.

Sie können die [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) verwenden, um die richtigen Regeln zur Veröffentlichungs Transformation zu generieren. Die generierten Anspruchsregeln, die mit der AD FS-Hilfe erstellt wurden, können entweder manuell über die AD FS-Verwaltungskonsole oder mit PowerShell hinzugefügt werden. In der AD FS-Hilfe werden die erforderlichen PowerShell-Skripts generiert, die ausgeführt werden müssen.  

1. Führen Sie **Generate Claims** on AD FS help aus, und kopieren Sie das PowerShell-Anspruchs Transformationsskript mithilfe der **Copy** -Option in der rechten oberen Ecke des Skripts.
2. Fügen Sie die generierte PowerShell in Folgendes ein:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Führen Sie das abgeschlossene Skript aus.
4.  Stellen Sie sicher, dass zwei Vertrauensstellungen der vertrauenden Seite vorhanden sind. einer für weltweit und einer für BF.
5.  Sichern Sie Ihre Vertrauensstellungen mit [den folgenden Schritten](#backup). Speichern Sie Sie mit dem Namen **FFAndWorldwide**.
6.  Schließen Sie die Back-End-Migration ab, und stellen Sie sicher, dass AD FS während des Migrationsprozesses weiterhin funktioniert.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS-Notfallwiederherstellung (WID-Datenbank)

Um die AD FS-Farm in einem Disaster [AD FS-Tool für die schnelle Wiederherstellung](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) wiederherzustellen, muss die Anwendung genutzt werden. Daher muss das Tool heruntergeladen werden, und vor dem Beginn der Migration muss eine Sicherung erstellt und sicher gespeichert werden. In diesem Beispiel (Tat Environments) wurden die folgenden Befehle ausgeführt, um die Farm zu sichern:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Sichern einer AD FS-Farm

1. Installieren Sie das AD FS Rapid Restore-Tool auf dem primären AD FS-Server.
2. Importieren Sie das Modul in eine PowerShell-Sitzung mit diesem Befehl.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. Führen Sie den Befehl Backup aus:

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. Speichern Sie die Sicherung sicher an einem gewünschten Ziel. 

### <a name="restore-an-ad-fs-farm"></a>Wiederherstellen einer AD FS-Farm

Wenn die Farm vollständig ausgefallen ist und keine Möglichkeit besteht, zur alten Farm zurückzukehren, gehen Sie wie folgt vor. 

1. Verschiebt die zuvor generierte und gespeicherte Sicherung auf den neuen primären AD FS-Server.
2. Führen Sie den folgenden `Restore-ADFS` PowerShell-Befehl aus. Falls erforderlich, importieren Sie das AD FS-SSL-Zertifikat vorab.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Richten Sie Ihre neuen DNS-Einträge oder den Lastenausgleich auf die neuen AD FS-Server.

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Navigieren durch den Übergang:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche vorab Arbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
