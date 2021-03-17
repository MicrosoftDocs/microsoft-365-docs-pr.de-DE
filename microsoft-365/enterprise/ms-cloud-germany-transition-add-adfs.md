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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838413"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD FS-Migrationsschritte für die Migration von Microsoft Cloud Deutschland

Diese Konfigurationsänderung muss immer angewendet werden, bevor Phase 2 beginnt.
Sobald Phase 2 abgeschlossen ist, funktioniert die Konfigurationsänderung, und Sie können sich über globale Office 365-Endpunkte wie `https://portal.office.com` anmelden. Wenn Sie die Konfigurationsänderung vor Phase 2 implementieren, funktionieren die globalen Office 365-Endpunkte _noch nicht_, aber die neue Vertrauensstellung der vertrauenden Partei ist weiterhin Teil Ihrer Active Directory-Verbunddienste(AD FS)-Konfiguration.

Kunden, die die Verbundauthentifizierung mit Active Directory Federation Services (AD FS) verwenden, sollten während der Migration keine Änderungen an Aussteller-URIs vornehmen, die für alle Authentifizierungen mit lokalen Active Directory Domain Services (AD DS) verwendet werden. Das Ändern von Aussteller-URIs führt zu Authentifizierungsfehlern für Benutzer in der Domäne. Aussteller-URIs können direkt in AD FS geändert werden oder wenn eine Domäne von _verwaltet_ zu _Verbund_ oder umgekehrt konvertiert wird. Es wird empfohlen, keine Verbunddomäne im migrierten Azure AD-Mandanten hinzuzufügen, zu entfernen oder zu konvertieren. Aussteller-URIs können nach Abschluss der Migration geändert werden.

Führen Sie die folgenden Schritte aus, um Ihre AD FS-Farm auf die Migration aus Microsoft Cloud Deutschland vorzubereiten:

1. Sichern Sie Ihre AD FS-Einstellungen, einschließlich der vorhandenen Microsoft Cloud Deutschland Relying Party-Vertrauensstellung, mit [den folgenden Schritten.](#backup) Benennen Sie die **Sicherung MicrosoftCloudDeutschlandOnly,** um anzugeben, dass sie nur die Microsoft Cloud Deutschland-Mandanteninformationen hat.

   > [!NOTE]
   > Die Sicherung enthält nicht nur die vorhandene Office 365 Relying Party Trust für Microsoft Cloud Deutschland, sondern auch alle anderen vertrauenden Parteienvertrauensstellungen, die in der entsprechenden AD FS-Farm vorhanden sind.

2. Testen Sie die Wiederherstellung mithilfe der MicrosoftCloudDeutschlandOnly-Sicherung. Die AD #A0 sollte weiterhin nur als Microsoft Cloud Deutschland funktionieren.

Führen Sie nach Abschluss und Testen der AD FS-Sicherung die folgenden Schritte aus, um Ihrer ADFS-Konfiguration eine neue Vertrauensstellung für vertrauende Parteien hinzuzufügen:

1. Öffnen Sie die AD FS-Verwaltungskonsole.

2. Navigieren Sie im linken Bereich der ADFS-Verwaltungskonsole zum Menü **Vertrauen der vertrauenden** Seite.

3. Wählen Sie im rechten Bereich **Vertrauensstellung für vertrauende Partei hinzufügen...**

4. Wählen **Sie auf** der **Willkommensseite des** Assistenten Vertrauen vertrauende Seite hinzufügen die Option Start aus.

5. Wählen Sie auf der Seite **Datenquelle auswählen** die Option **Online oder in einem lokalen Netzwerk veröffentlichte Daten über die vertrauende Seite importieren** aus. Der Wert für **Adresse der Verbundmetadaten (Hostname oder URL)** muss auf `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` festgelegt sein. Klicken Sie auf **Weiter**.

6. Geben Sie auf der Seite **Anzeigename** angeben den Anzeigenamen ein, z. B. **Microsoft Office 365 Identity Platform WorldWide**. Klicken Sie auf **Weiter**.

7. Wenn Sie ADFS in Windows Server 2012, wählen Sie auf der Assistentenseite Mehrstufige Authentifizierung jetzt **konfigurieren?** die entsprechende Auswahl entsprechend Ihren Authentifizierungsanforderungen aus. Wenn Sie sich an die Standardeinstellung halten, wählen Sie **Ich möchte derzeit keine Einstellungen für die Multi-Faktor-Authentifizierung für diese Vertrauensstellung der vertrauenden Partei konfigurieren**. Sie können diese Einstellung später ändern, wenn Sie möchten.

8. For AD FS 2012: On the **Choose Issuance Authorization Rules,** keep Permit all users to access **this relying party** selected and click **Next**.

8. Für AD FS 2016 und AD FS 2019: Wählen Sie auf der Seite Zugriffssteuerungsrichtlinie auswählen die entsprechende Zugriffssteuerungsrichtlinie aus, und klicken Sie auf **Weiter**.  Wenn keine ausgewählt ist, funktioniert die Vertrauensstellung der vertrauenden **Partei NICHT.**

9. Klicken Sie auf der Seite **Bereit zum Hinzufügen von Vertrauensstellung** auf **Weiter**, um den Assistenten abzuschließen.

10. Klicken Sie auf der Seite **Fertig stellen** auf **Schließen**.

Durch Schließen des Assistenten wird die Vertrauen vertrauende Partei mit dem globalen Office 365-Dienst eingerichtet. Es sind jedoch noch keine Ausstellungstransformationsregeln konfiguriert.

Sie können mit [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) die richtigen Ausstellungstransformationsregeln generieren. Die mit AD FS-Hilfe generierten Anspruchsregeln können entweder über die AD FS-Verwaltungskonsole oder mithilfe von PowerShell manuell hinzugefügt werden. Die AD FS-Hilfe generiert die erforderlichen PowerShell-Skripts, die ausgeführt werden müssen.  

> [!NOTE]
> [Die AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) generiert die standardmäßigen Ausgabetransformationsregeln, die mit dem Produkt versandt werden. Wenn jedoch benutzerdefinierte Ausgabetransformationsregeln in der Microsoft Cloud Deutschland Relying Party Trust (z. B. benutzerdefinierte Aussteller-URIs, nicht standardmäßig unveränderliche IDs oder andere Anpassungen) installiert sind, müssen die von der AD FS-Hilfe generierten Regeln so geändert werden, dass sie der benutzerdefinierten Logik entsprechen, die derzeit für die Vertrauen vertrauende Microsoft Cloud Deutschland-Vertrauensstellung gilt. Wenn diese Anpassungen nicht in die über die [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)generierten Regeln integriert sind, funktioniert  die Authentifizierung für **Microsoft Office 365 Identity Platform WorldWide** höchstwahrscheinlich nicht für Ihre Verbundidentitäten.

1. Führen **Sie In** der AD FS-Hilfe Generieren von Ansprüchen [aus,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) und kopieren Sie das PowerShell-Skript mithilfe der **Option Kopieren** in der rechten oberen Ecke des Skripts.

2. Führen Sie die in der [AD FS-Hilfe](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) beschriebenen Schritte aus, um das PowerShell-Skript in Ihrer AD FS-Farm auszuführen, um die globale Vertrauen vertrauende Partei zu generieren.

3. Stellen Sie sicher, dass zwei Vertrauen vertrauende Parteien vorhanden sind. eine für Microsoft Cloud Deutschland und eine für den globalen Office 365-Dienst. Der folgende Befehl kann für die Überprüfung verwendet werden. Es sollten zwei Zeilen und die entsprechenden Namen und Bezeichner zurückgegeben werden.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. Sichern Sie Ihre vollständige Migrationskonfiguration, einschließlich der vertrauenden Seitenvertrauensstellungen, mithilfe [dieser Schritte.](#backup) Speichern Sie es mit dem Namen **MicrosoftCloudDeutschlandAndWorldwide**.

5. Überprüfen Sie während der Migration ihres Mandanten regelmäßig, ob die AD FS-Authentifizierung mit Microsoft Cloud Deutschland und Microsoft Global Cloud in den verschiedenen unterstützten Migrationsschritten funktioniert.


## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS-Notfallwiederherstellung (WID-Datenbank)

Wenn Sie die AD FS-Farm in einem Notfall wiederherstellen möchten, muss dazu das [AD FS Rapid Restore-Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) genutzt werden. Deshalb muss das Tool heruntergeladen und vor Beginn der Migration eine Sicherung erstellt und sicher gespeichert werden. In diesem Beispiel wurden die folgenden Befehle ausgeführt, um eine Farm zu sichern, die in einer WID-Datenbank ausgeführt wird:

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
