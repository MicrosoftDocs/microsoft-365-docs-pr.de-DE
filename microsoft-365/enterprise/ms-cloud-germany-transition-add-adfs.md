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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland

Diese Konfigurationsänderung kann jederzeit vor Beginn der Phase 4 angewendet werden.
Nach Abschluss von Phase 2 funktioniert die Konfigurationsänderung und Sie können sich bei Office 365 Global-Endpunkten wie `https://portal.office.com` anmelden. Wenn Sie die Konfigurationsänderung vor Phase 2 implementieren, funktionieren die globalen Office 365-Endpunkte _noch nicht_, aber die neue Vertrauensstellung der vertrauenden Partei ist weiterhin Teil Ihrer Active Directory-Verbunddienste(AD FS)-Konfiguration.

So migrieren Sie Ihre AD FS-Farm aus Microsoft Cloud Deutschland:

1. Sichern Sie Ihre AD FS-Einstellungen einschließlich FF Trust-Informationen mit [diesen Schritten](#backup). Geben Sie der Sicherungskopie den Namen **Microsoft Cloud Deutschland_Only**, um anzugeben, dass sie nur die Mandanteninformationen zu Microsoft Cloud Deutschland enthält.
2. Testen Sie die Wiederherstellung mithilfe der Sicherung „Microsoft Cloud Deutschland_Only“. Die AD FS-Farm sollte weiterhin nur als Microsoft Cloud Deutschland eingesetzt werden.

Führen Sie nach Abschluss und Testen der AD FS-Sicherung die folgenden Schritte aus, um Ihrer ADFS-Konfiguration eine neue Vertrauensstellung für vertrauende Parteien hinzuzufügen:

1. Öffnen Sie die AD FS-Verwaltungskonsole
2. Erweitern Sie im linken Bereich der ADFS-Verwaltungskonsole **ADFS**, dann **Vertrauensstellungen** und dann **Vertrauensstellungen für vertrauende Parteien**
3. Wählen Sie im rechten Bereich **Vertrauensstellung für vertrauende Partei hinzufügen...**
4. Wählen Sie auf der Seite **Willkommen** des Assistenten zum Hinzufügen von Vertrauensstellungen der vertrauenden Seite **Weiter** aus.
5. Wählen Sie auf der Seite **Datenquelle auswählen** die Option **Online oder in einem lokalen Netzwerk veröffentlichte Daten über die vertrauende Seite importieren** aus. Der Wert für **Adresse der Verbundmetadaten (Hostname oder URL)** muss auf `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` festgelegt sein. Klicken Sie dann auf **Weiter**.
6. Geben Sie auf der Seite **Datenquelle auswählen** den Anzeigenamen ein, z. B. **Microsoft Office 365 Identity Platform WorldWide**. Klicken Sie dann auf **Weiter**.
7. Wählen Sie auf der Seite des Assistenten **Mehrstufige Authentifizierung jetzt konfigurieren?** aus. Wählen Sie die entsprechende Auswahl entsprechend Ihren Authentifizierungsanforderungen aus. Wenn Sie sich an die Standardeinstellung halten, wählen Sie **Ich möchte derzeit keine Einstellungen für die Multi-Faktor-Authentifizierung für diese Vertrauensstellung der vertrauenden Partei konfigurieren**. Sie können diese Einstellung später ändern, wenn Sie möchten.
8. Klicken Sie in den **Ausstellungsautorisierungsregeln auswählen** auf **Alle Benutzer auf diese ausgewählte vertrauende Partei zugreifen lassen**, und klicken Sie auf **Weiter**
9. Klicken Sie auf der Seite **Bereit zum Hinzufügen von Vertrauensstellung** auf **Weiter**, um den Assistenten abzuschließen.
10. Klicken Sie auf der Seite **Fertig stellen** auf **Schließen**.

Durch Schließen des Assistenten wird die Vertrauensstellung der vertrauenden Partei mit den globalen Office 365-Diensten hergestellt. Es sind jedoch noch keine Ausstellungstransformationsregeln konfiguriert.

Sie können mit [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) die richtigen Ausstellungstransformationsregeln generieren. Die mit AD FS-Hilfe generierten Anspruchsregeln können entweder über die AD FS-Verwaltungskonsole oder mithilfe von PowerShell manuell hinzugefügt werden. Die AD FS-Hilfe generiert die erforderlichen PowerShell-Skripts, die ausgeführt werden müssen.  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. Führen Sie in AD FS-Hilfe **Ansprüche generieren** aus, und kopieren Sie das PowerShell-Anspruchtransformationsskript mithilfe der Option **Kopieren** in der rechten oberen Ecke des Skripts.
2. Öffnen Sie Ihren bevorzugten Texteditor und fügen Sie das PowerShell-Skript in ein neues Textfenster ein.
3. Fügen Sie die folgenden PowerShell-Zeilen ab Schritt 2 am Ende des eingefügten Skripts hinzu
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. Speichern Sie das PowerShell-Skript und führen Sie es aus.
5. Stellen Sie sicher, dass zwei Vertrauensstellungen der vertrauenden Partei vorhanden sind. Eine für die Microsoft Cloud Deutschland und eine für den Office 365 Global-Dienst.
6. Sichern Sie Ihre-Vertrauensstellungen mit [diesen Schritten](#backup). Speichern Sie die Datei unter dem Namen **FFAndWorldwide**.
7. Schließen Sie Ihre Backend-Migration ab und stellen Sie sicher, dass AD FS während des Migrationsprozesses noch funktioniert.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS-Notfallwiederherstellung (WID-Datenbank)

Wenn Sie die AD FS-Farm in einem Notfall wiederherstellen möchten, muss dazu das [AD FS Rapid Restore-Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) genutzt werden. Deshalb muss das Tool heruntergeladen und vor Beginn der Migration eine Sicherung erstellt und sicher gespeichert werden. In diesem Beispiel (TAT-Umgebungen) wurden die folgenden Befehle zum Sichern der Farm ausgeführt:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Sichern einer AD FS-Farm

1. Installieren Sie das AD FS Rapid Restore-Tool auf dem primären AD FS-Server.
2. Importieren Sie das Modul in einer PowerShell-Sitzung mit diesem Befehl.
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. Führen Sie den Befehl zum Sichern aus:
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. Speichern Sie die Sicherung sicher an einem bestimmten Ort.

### <a name="restore-an-ad-fs-farm"></a>Wiederherstellen einer AD FS-Farm

Wenn Ihre Farm vollständig fehlgeschlagen ist und es keine Möglichkeit zur Rückkehr zu der alten Farm gibt, führen Sie die folgenden Schritte aus. 

1. Verschieben Sie die zuvor generierte und gespeicherte Sicherung auf den neuen primären AD FS-Server.
2. Führen Sie den folgenden `Restore-ADFS`-PowerShell-Befehl aus. Importieren Sie vorher bei Bedarf das AD FS-SSL-Zertifikat.

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. Zeigen Sie auf den neuen AD FS-Servern auf Ihre neuen DNS-Einträge oder den Lastenausgleich.

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
