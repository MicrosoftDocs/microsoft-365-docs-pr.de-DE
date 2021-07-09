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
ms.openlocfilehash: c8e784c8e582185b4bdebc0cb359cc4c19503d1a
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339610"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland

Diese Konfigurationsänderung muss zu einem beliebigen Zeitpunkt vor dem Start von Phase 2 vorgenommen werden.
Sobald Phase 2 abgeschlossen ist, funktioniert die Konfigurationsänderung und Sie können sich bei Office 365 Global-Endpunkten wie `https://admin.microsoft.com` anmelden. Wenn Sie die Konfigurationsänderung vor Phase 2 implementieren, funktionieren die globalen Office 365-Endpunkte _noch nicht_, aber die neue Vertrauensstellung der vertrauenden Partei ist weiterhin Teil Ihrer Active Directory-Verbunddienste(AD FS)-Konfiguration.

Kunden, die Verbundauthentifizierung mit Active Directory-Verbunddienste (AD FS) verwenden, sollten während der Migration keine Änderungen an Aussteller-URIs vornehmen, die für alle Authentifizierungen mit lokalen Active Directory Domain Services (AD DS) verwendet werden. Das Ändern von Aussteller-URIs führt zu Authentifizierungsfehlern für Benutzer in der Domäne. Aussteller-URIs können direkt in AD FS geändert werden oder wenn eine Domäne von _verwaltet_ zu _Verbund_ oder umgekehrt konvertiert wird. Wir empfehlen, dass Sie keine Verbunddomäne im migrierten Azure AD-Mandanten hinzufügen, entfernen oder konvertieren. Aussteller-URIs können geändert werden, nachdem die Migration vollständig abgeschlossen ist.

Um Ihre AD FS-Farm für die Migration aus der Microsoft Cloud Deutschland vorzubereiten, führen Sie die folgenden Schritte durch:

1. Sichern Sie Ihre AD FS-Einstellungen, einschließlich der bestehenden Vertrauensstellung der vertrauenden Partei von Microsoft Cloud Deutschland, mit [diesen Schritten](#backup). Nennen Sie das Backup **MicrosoftCloudDeutschlandOnly**, um anzugeben, dass sie nur die Microsoft Cloud Deutschland-Mieterinformationen enthält.

   > [!NOTE]
   > Das Backup wird nicht nur die bestehende Office 365 Vertrauensstellung der vertrauenden Partei für die Microsoft Cloud Deutschland enthalten, sondern auch alle anderen Vertrauensstellungen für vertrauende Parteien, die auf der jeweiligen AD FS-Farm vorhanden sind.

2. Testen Sie die Wiederherstellung mit dem MicrosoftCloudDeutschlandOnly-Backup. Die AD FS-Farm sollte weiterhin nur als Microsoft Cloud Deutschland betrieben werden.

Führen Sie nach Abschluss und Testen der AD FS-Sicherung die folgenden Schritte aus, um Ihrer ADFS-Konfiguration eine neue Vertrauensstellung für vertrauende Parteien hinzuzufügen:

1. Öffnen Sie die AD FS-Verwaltungskonsole.

2. Navigieren Sie im linken Bereich der ADFS-Verwaltungskonsole zum Menü **Vertrauensstellungen für vertrauende Parteien**.

3. Wählen Sie im rechten Bereich **Vertrauensstellung der vertrauenden Partei hinzufügen...**

4. Wählen Sie **Start** auf der Seite **Willkommen** des Assistenten zum Hinzufügen von Vertrauensstellung der vertrauenden Partei.

5. Wählen Sie auf der Seite **Datenquelle auswählen** die Option **Online oder in einem lokalen Netzwerk veröffentlichte Daten über die vertrauende Seite importieren** aus. Der Wert für **Adresse der Verbundmetadaten (Hostname oder URL)** muss auf `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` festgelegt sein. Klicken Sie auf **Weiter**.

6. Geben Sie auf der Seite **Anzeigename angeben** den Anzeigenamen ein, z. B. **Microsoft Office 365-Identitätsplatform WorldWide**. Klicken Sie auf **Weiter**.

7. Wenn Sie ADFS in Windows Server 2012 verwenden, wählen Sie auf der Assistentenseite **Jetzt die Multi-Faktor-Authentifizierung konfigurieren?** die entsprechende Auswahl entsprechend Ihren Authentifizierungsanforderungen. Wenn Sie sich an die Standardeinstellung halten, wählen Sie **Ich möchte derzeit keine Einstellungen für die Multi-Faktor-Authentifizierung für diese Vertrauensstellung der vertrauenden Partei konfigurieren**. Sie können diese Einstellung später ändern, wenn Sie möchten.

8. Für AD FS 2012: Lassen Sie im Dialogfeld **Ausgaberegeln auswählen** die Option **Allen Benutzern den Zugriff auf diese vertrauende Partei** erlauben ausgewählt und klicken Sie auf **Weiter**.

9. Für AD FS 2016 und AD FS 2019: Wählen Sie auf der Seite **Zugriffskontrollrichtlinie auswählen** die entsprechende Zugriffssteuerungsrichtlinie aus und klicken Sie auf **Weiter**. Wenn keine ausgewählt wird, funktioniert die Vertrauensstellung der vertrauenden Partei **NICHT**.

10. Klicken Sie auf der Seite **Bereit zum Hinzufügen von Vertrauensstellung** auf **Weiter**, um den Assistenten abzuschließen.

11. Klicken Sie auf der Seite **Fertig stellen** auf **Schließen**.

Durch das Schließen des Assistenten wird die Vertrauensstellung der vertrauenden Partei mit dem Office 365 Global-Dienst eingerichtet. Es sind jedoch noch keine Ausstellungstransformationsregeln konfiguriert.

Sie können mit [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) die richtigen Ausstellungstransformationsregeln generieren. Die mit AD FS-Hilfe generierten Anspruchsregeln können entweder über die AD FS-Verwaltungskonsole oder mithilfe von PowerShell manuell hinzugefügt werden. Die AD FS-Hilfe generiert die erforderlichen PowerShell-Skripts, die ausgeführt werden müssen.  

> [!NOTE]
> [Die AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) generiert die Standardregeln für die Ausgabetransformation, die mit dem Produkt geliefert werden. Wenn jedoch benutzerdefinierte Regeln für die Ausgabetransformation in der Microsoft Cloud Deutschland Vertrauensstellung der vertrauenden Partei vorhanden sind (z. B. benutzerdefinierte Aussteller-URIs, nicht standardmäßige unveränderliche IDs oder andere Anpassungen), müssen die von der AD FS-Hilfe generierten Regeln so geändert werden, dass sie zur benutzerdefinierten Logik passen, die derzeit für die Microsoft Cloud Deutschland Vertrauensstellung der vertrauenden Partei vorhanden ist. Wenn diese Anpassungen nicht in die über die [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) generierten Regeln integriert sind, wird die Authentifizierung bei **Microsoft Office 365-Identitätsplattform WorldWide** höchstwahrscheinlich **nicht** für Ihre föderierten Identitäten funktionieren.

1. Führen Sie **Ansprüche generieren** in [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) aus und kopieren Sie das PowerShell-Skript über die Option **Kopieren** in der rechten oberen Ecke des Skripts.

2. Führen Sie die in der [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) beschriebenen Schritte aus, um das PowerShell-Skript in Ihrer AD FS-Farm auszuführen, um den globalen Relying Party Trust zu erzeugen. Ersetzen Sie vor dem Ausführen des Skripts die folgenden Codezeilen im generierten Skript, wie nachstehend beschrieben:

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. Stellen Sie sicher, dass zwei Vertrauensstellungen der vertrauenden Parteien vorhanden sind. Eine für die Microsoft Cloud Deutschland und eine für den Office 365 Global-Dienst. Der folgende Befehl kann für die Prüfung verwendet werden. Er sollte zwei Zeilen und die jeweiligen Namen und Bezeichner zurücksenden.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. Sichern Sie Ihre vollständige Migrationskonfiguration, einschließlich beider Vertrauensstellungen der vertrauenden Parteien, mit den [folgenden Schritten](#backup). Speichern Sie es unter dem Namen **MicrosoftCloudDeutschlandUndWeltweit**.

5. Während sich Ihr Mandant in der Migration befindet, überprüfen Sie regelmäßig, ob die AD FS-Authentifizierung mit Microsoft Cloud Deutschland und Microsoft Global Cloud in den verschiedenen unterstützten Migrationsschritten funktioniert.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS-Notfallwiederherstellung (WID-Datenbank)

Wenn Sie die AD FS-Farm in einem Notfall wiederherstellen möchten, muss dazu das [AD FS Rapid Restore-Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) genutzt werden. Deshalb muss das Tool heruntergeladen und vor Beginn der Migration eine Sicherung erstellt und sicher gespeichert werden. In diesem Beispiel wurden die folgenden Befehle ausgeführt, um eine Farm zu sichern, die auf einer WID-Datenbank läuft:

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

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)
