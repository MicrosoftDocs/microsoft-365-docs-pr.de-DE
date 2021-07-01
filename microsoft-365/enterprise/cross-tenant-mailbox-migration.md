---
title: Mandantenübergreifende Postfachmigration
description: So verschieben Sie Postfächer zwischen Microsoft 365 oder Office 365 Mandanten.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 4541cd425a8f666f6f0b513dd18cb92c2d6c7c60
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230031"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Mandantenübergreifende Postfachmigration (Vorschau)

Wenn ein Exchange Online Mandant Postfächer in einen anderen Mandanten im selben Exchange Online Dienst verschieben musste, musste er sie zuvor vollständig an die lokale Bereitstellung auslagern und sie dann in einen neuen Mandanten integrieren. Mit dem neuen mandantenübergreifenden Postfachmigrationsfeature können Mandantenadministratoren in Quell- und Zielmandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben. Dadurch entgeht die Notwendigkeit, Postfächer zu off-board und zu integrieren.

In der Regel benötigen Sie bei Fusionen oder Veräusserungen die Möglichkeit, Benutzer und Inhalte in einen neuen Mandanten zu verschieben. Wenn der Zielmandantenadministrator die Verschiebung ausführt, wird dies als Pull-Verschiebung bezeichnet, ähnlich wie bei lokalen Migrationen zum Cloud-Onboarding.

Mandantenübergreifende Exchange Postfachverschiebungen werden von Mandantenadministratoren vollständig selbstverwendet und verwenden bekannte Schnittstellen, die in die größeren Workflows geschrieben werden können, die für den Übergang von Benutzern zu ihrer neuen Organisation erforderlich sind. Administratoren können das `New-MigrationBatch` Cmdlet verwenden, das über die Verwaltungsrolle "Postfächer verschieben" verfügbar ist, um mandantenübergreifende Verschiebungen auszuführen. Der Verschiebungsprozess umfasst Mandantenautorisierungsprüfungen während der Postfachsynchronisierung und -fertigstellung.

Benutzer, die migrieren, müssen im Zielmandanten Exchange Online System als MailUsers vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um mandantenübergreifende Verschiebungen zu ermöglichen. Bei Benutzern, die im Zielmandanten nicht ordnungsgemäß eingerichtet sind, schlägt das System fehl.

Wenn die Verschiebungen abgeschlossen sind, wird das Quellsystempostfach in MailUser konvertiert, und die targetAddress (in Exchange als ExternalEmailAddress angezeigt) wird mit der Routingadresse an den Zielmandanten gestempelt. Dieser Prozess verlässt den Legacy-MailUser im Quellmandanten und ermöglicht einen Zeitraum des Koexistenz- und E-Mail-Routings. Wenn Geschäftsprozesse dies zulassen, kann der Quellmandant die Quell-MailUser entfernen oder in einen E-Mail-Kontakt konvertieren.

Mandantenübergreifende Exchange Postfachmigrationen werden nur für Mandanten in Hybrid- oder Cloudumgebungen oder einer beliebigen Kombination der beiden unterstützt.

Dieser Artikel beschreibt den Prozess für mandantenübergreifende Postfachverschiebungen und enthält Anleitungen zum Vorbereiten von Quell- und Zielmandanten für die Inhaltsverschiebung.

## <a name="preparing-source-and-target-tenants"></a>Vorbereiten von Quell- und Zielmandanten

Das feature für die mandantenübergreifende Exchange Postfachmigration erfordert autorisierungs- und bereichsübergreifende Migrationen. Mithilfe der Azure Enterprise-Anwendungs- und Key Vault-Speicherlösungen können Mandantenadministratoren jetzt sowohl die Autorisierung als auch die Bereichsdefinition von Exchange Online Postfachmigrationen von einem Mandanten zu einem anderen verwalten. Mandantenübergreifende Postfachverschiebungen unterstützen ein Einladungs- und Zustimmungsmodell zum Einrichten einer Azure Active Directory (Azure AD)-Anwendung, die für die Authentifizierung zwischen einem Mandantenpaar verwendet wird. Zusätzliche Komponenten wie eine Organisationsbeziehung und ein Migrationsendpunkt sind ebenfalls erforderlich.

Dieser Abschnitt enthält weder die spezifischen Schritte, die erforderlich sind, um die MailUser-Benutzerobjekte im Zielverzeichnis vorzubereiten, noch den Beispielbefehl zum Senden eines Migrationsbatches. Weitere Informationen finden Sie unter [Vorbereiten von Zielbenutzerobjekten für](#prepare-target-user-objects-for-migration) die Migration.

## <a name="prerequisites"></a>Voraussetzungen

Das Feature zum verschieben von mandantenübergreifenden Postfächern erfordert, dass [Azure Key Vault](/azure/key-vault/basic-concepts) eine mandantenpaarspezifische Azure-Anwendung zum sicheren Speichern und Zugreifen auf das Zertifikat/den geheimen Schlüssel zum Authentifizieren und Autorisieren der Postfachmigration von einem Mandanten zum anderen erstellt, wodurch alle Anforderungen zum Freigeben von Zertifikaten/geheimen Schlüsseln zwischen Mandanten entfernt werden.

Stellen Sie vor dem Start sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um Azure Key Vault, die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren. In der Regel verfügt der globale Administrator über die Berechtigung, alle Konfigurationsschritte auszuführen.

Darüber hinaus sind E-Mail-aktivierte Sicherheitsgruppen im Quellmandanten vor dem Ausführen des Setups erforderlich. Diese Gruppen werden verwendet, um die Liste der Postfächer zu beschränken, die vom Quellmandanten (oder manchmal auch als Ressourcenmandant bezeichnet) zum Zielmandanten verschoben werden können. Auf diese Weise kann der Quellmandantenadministrator den spezifischen Satz von Postfächern einschränken oder einschränken, die verschoben werden müssen, um zu verhindern, dass unbeabsichtigte Benutzer migriert werden. Geschachtelte Gruppen werden nicht unterstützt.

Sie müssen auch mit Ihrem vertrauenswürdigen Partnerunternehmen kommunizieren (mit dem Sie Postfächer verschieben), um deren Microsoft 365 Mandanten-ID zu erhalten. Diese Mandanten-ID wird im Feld "Organisationsbeziehung" `DomainName` verwendet.

Um die Mandanten-ID eines Abonnements abzurufen, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klicken Sie auf das Kopiersymbol für die Mandanten-ID-Eigenschaft, um sie in die Zwischenablage zu kopieren.

Hier sehen Sie, wie der Prozess funktioniert.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Mandantenvorbereitung für die Postfachmigration.":::

[Sehen Sie sich eine größere Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)an.

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
-->

### <a name="prepare-tenants"></a>Vorbereiten von Mandanten

Auf hoher Ebene werden beim Ausführen der Setupskripts die folgenden Konfigurationsaktionen ausgeführt.

Vorbereiten des Zielmandanten:

1. Wenn keine vorhandene Azure-Ressourcengruppe bereitgestellt wird, wird eine neue erstellt (SCRIPT).
2. Wenn kein vorhandener Key Vault bereitgestellt wird, wird ein neuer erstellt (SCRIPT).
3. Für die Office 365 Exchange Online Mailbox Migration Application (SCRIPT) wird eine neue Zugriffsrichtlinie erstellt.
4. Ein neues Zertifikat wird erstellt (oder ein vorhandenes, falls angegeben), um den geheimen Schlüssel für die Migrationsanwendung (SCRIPT) zu speichern.
5. Eine neue Azure AD-Anwendung wird erstellt (SCRIPT).
6. Das Zertifikat/geheimnis wird in die Migrationsanwendung (SCRIPT) hochgeladen.
7. Postfachmigrationsberechtigungen werden der Anwendung (SCRIPT) zugewiesen.
8. Das Bereitstellungsskript wird angehalten, bis der Zieladministrator seiner eigenen Anwendung (SCRIPT) zustimmt.
9. Der Zielmandantenadministrator stimmt den Berechtigungen zu, die der Anwendung erteilt werden (MANUAL).
10. Eine Organisationsbeziehung wird mit dem Zielmandanten (SCRIPT) erstellt.
11. Ein Migrationsendpunkt wird erstellt, um Postfächer an den Zielmandanten (SCRIPT) zu ziehen.

Vorbereiten des Quellmandanten:

1. Der Administrator des Quellmandanten akzeptiert die Zustimmung zur Postfachmigrationsanwendungseinladung vom Zielmandanten (MANUAL).
2. Der Administrator des Quellmandanten erstellt eine E-Mail-aktivierte Sicherheitsgruppe in ihrem Mandanten, die die Liste der Postfächer enthält, die von der Migrationsanwendung verschoben werden dürfen (MANUAL).
3. Es wird eine Organisationsbeziehung mit dem Zielmandanten erstellt, der angibt, dass die Postfachmigrationsanwendung für die OAuth-Überprüfung verwendet werden soll, um die Verschiebungsanforderung (SCRIPT) zu akzeptieren.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Schritt-für-Schritt-Anweisungen für den Zielmandantenadministrator

1. Laden Sie das Skript SetupCrossTenantRelationshipForTargetTenant.ps1 für das Setup des Zielmandanten aus dem [GitHub Repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview)herunter.
2. Speichern Sie das Skript (SetupCrossTenantRelationshipForTargetTenant.ps1) auf dem Computer, auf dem Sie das Skript ausführen.
3. Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Exchange Online Zielmandanten. Stellen Sie erneut sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um den Azure Key Vault-Speicher und das Azure Key Vault-Zertifikat, die Move Mailbox-Anwendung, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.
4. Ändern Sie das Dateiordnerverzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Ihrer Remote-PowerShell-Sitzung befindet.
5. Führen Sie das Skript mit den folgenden Parametern und Werten aus.

    | Parameter | Wert | Erforderlich oder optional
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Zielmandantendomäne, z. B. fabrikam \. onmicrosoft.com. | Erforderlich |
    | -ResourceTenantDomain                       | Quellmandantendomäne, \. z. B. contoso onmicrosoft.com. | Erforderlich |
    | -ResourceTenantAdminEmail                   | E-Mail-Adresse des Quellmandantenadministrators. Dies ist der Quellmandantenadministrator, der der Verwendung der Vom Zieladministrator gesendeten Postfachmigrationsanwendung zustimmt. Dies ist der Administrator, der die E-Mail-Einladung für die Anwendung erhält. | Erforderlich |
    | -ResourceTenantId                           | Quellmandanten-Organisations-ID (GUID). | Erforderlich |
    | -SubscriptionId                             | Das Azure-Abonnement, das zum Erstellen von Ressourcen verwendet werden soll. | Erforderlich |
    | -ResourceGroup                              | Name der Azure-Ressourcengruppe, die den Key Vault enthält oder enthalten wird. | Erforderlich |
    | -KeyVaultName                               | Azure Key Vault-Instanz, die Ihr Postfachmigrationsanwendungszertifikat/-geheimnis speichert. | Erforderlich |
    | -CertificateName                            | Zertifikatname beim Generieren oder Suchen nach Zertifikaten im Schlüsseltresor. | Erforderlich |
    | -CertificateSubject                         | Name des Azure Key Vault-Zertifikatantragstellers, z. B. CN=contoso_fabrikam. | Erforderlich |
    | -AzureResourceLocation                      | Der Speicherort der Azure-Ressourcengruppe und des Schlüsseltresors. | Erforderlich |
    | -ExistingApplicationId                      | E-Mail-Migrationsanwendung, die verwendet werden soll, wenn eine bereits erstellt wurde. | Optional |
    | -AzureAppPermissions                        | Die Berechtigungen, die für die Postfachmigrationsanwendung erforderlich sind, z. B. Exchange oder MSGraph (Exchange zum Verschieben von Postfächern, MSGraph für die Verwendung dieser Anwendung zum Senden einer Zustimmungslink-Einladung an den Ressourcenmandanten). | Erforderlich |
    | -UseAppAndCertGeneratedForSendingInvitation | Parameter für die Verwendung der Anwendung, die für die Migration erstellt wurde, um die Einladung zum Senden von Zustimmungslinks an den Administrator des Quellmandanten zu senden. Wenn dies nicht vorhanden ist, werden die Anmeldeinformationen des Zieladministrators aufgefordert, eine Verbindung mit dem Azure-Einladungs-Manager herzustellen und die Einladung als Zieladministrator zu senden. | Optional |
    | -KeyVaultAuditStorageAccountName            | Das Speicherkonto, in dem die Überwachungsprotokolle von Key Vault gespeichert werden. | Optional |
    | -KeyVaultAuditStorageResourceGroup          | Die Ressourcengruppe, die das Speicherkonto zum Speichern von Key Vault-Überwachungsprotokollen enthält. | Optional |
    ||||

    >[!Note]
    > Stellen Sie sicher, dass Sie das Azure AD PowerShell-Modul installiert haben, bevor Sie die Skripts ausführen. Installationsschritte finden Sie ![ hier. ](/powershell/azure/install-az-ps?view=azps-5.1.0)

6. Das Skript hält an und fordert Sie auf, die Exchange Postfachmigrationsanwendung zu akzeptieren oder zuzustimmen, die während dieses Prozesses erstellt wurde. Hier ein Beispiel.

    ```powershell
    PS C:\PowerShell\> # Note: the below User.Invite.All permission is optional, and will only be used to retrieve access token to send invitation email to source tenant
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureResourceLocation "Brazil Southeast" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - User.Invite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```

7. Eine URL wird in der Remote-PowerShell-Sitzung angezeigt. Kopieren Sie den Link, der für Die Zustimmung Ihres Mandanten bereitgestellt wurde, und fügen Sie ihn in einen Webbrowser ein.

8. Melden Sie sich mit Ihren Anmeldeinformationen für den globalen Administrator an. Wenn der folgende Bildschirm angezeigt wird, wählen Sie **"Annehmen"** aus.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogfeld &quot;Berechtigungen akzeptieren&quot;":::

9. Wechseln Sie zurück zur Remote-PowerShell-Sitzung, und drücken Sie die EINGABETASTE, um fortzufahren.

10. Das Skript konfiguriert die verbleibenden Setupobjekte. Hier ein Beispiel.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Das Setup des Zieladministrators ist jetzt abgeschlossen!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Schritt-für-Schritt-Anleitungen für den Administrator des Quellmandanten

1.  Melden Sie sich bei Ihrem Postfach als -ResourceTenantAdminEmail an, das vom Zieladministrator während der Einrichtung angegeben wurde. Suchen Sie die E-Mail-Einladung vom Zielmandanten, und wählen Sie dann die **Schaltfläche Erste Schritte** aus.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogfeld &quot;Sie wurden eingeladen&quot;":::

2. Wählen Sie **"Annehmen"** aus, um die Einladung anzunehmen.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialogfeld zum Akzeptieren von Berechtigungen":::

   > [!NOTE]
   > Wenn Sie diese E-Mail nicht erhalten oder nicht finden können, wurde dem Zielmandantenadministrator eine direkte URL bereitgestellt, die Ihnen zur Annahme der Einladung zur Verfügung gestellt werden kann. Die URL sollte sich in der Aufzeichnung der Remote-PowerShell-Sitzung des Zielmandantenadministrators befinden.

3. Erstellen Sie in der Microsoft 365 Admin Center oder einer Remote-PowerShell-Sitzung eine oder mehrere E-Mail-aktivierte Sicherheitsgruppen, um die Liste der Postfächer zu steuern, die vom Zielmandanten zum Abrufen (Verschieben) vom Quellmandanten zum Zielmandanten zugelassen sind. Sie müssen diese Gruppe nicht im Voraus auffüllen, aber mindestens eine Gruppe muss bereitgestellt werden, um die Setupschritte (Skript) auszuführen. Schachtelungsgruppen werden nicht unterstützt.

4. Laden Sie das Skript SetupCrossTenantRelationshipForResourceTenant.ps1 für das Setup des Quellmandanten aus dem GitHub-Repository herunter: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .

5. Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Quellmandanten mit Ihren Exchange Administratorberechtigungen. Globale Administratorberechtigungen sind nicht erforderlich, um den Quellmandanten zu konfigurieren, nur den Zielmandanten aufgrund des Erstellungsprozesses der Azure-Anwendung.

6. Ändern Sie das Verzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Ihrer Remote-PowerShell-Sitzung befindet.

7. Führen Sie das Skript mit den folgenden erforderlichen Parametern und Werten aus.

    | Parameter | Wert |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | E-Mail-aktivierte Sicherheitsgruppe, die vom Quellmandanten für die Identitäten/Postfächer erstellt wird, die sich im Bereich der Migration befinden. |
    | -ResourceTenantDomain | Domänenname des Quellmandanten, z. B. contoso \. onmicrosoft.com. |
    | -ApplicationId | Die Azure-Anwendungs-ID (GUID) der für die Migration verwendeten Anwendung. Anwendungs-ID, die über Ihr Azure-Portal (Azure AD, Enterprise Anwendungen, App-Name, Anwendungs-ID) verfügbar ist oder in Ihrer Einladungs-E-Mail enthalten ist.  |
    | -TargetTenantDomain | Zielmandantendomänenname, z. B. fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | Mandanten-ID des Zielmandanten. Beispielsweise die Azure AD-Mandanten-ID von contoso \. onmicrosoft.com Mandanten. |
    |||

    Hier ein Beispiel.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Das Setup des Quelladministrators ist jetzt abgeschlossen!

### <a name="verify-setup"></a>Überprüfen der Einrichtung

Stellen Sie sicher, dass die Organisationsbeziehungen in Quell- und Zielmandanten sowie der Migrationsendpunkt im Ziel erfolgreich erstellt wurden.

#### <a name="target-tenant"></a>Zielmandant

**Organisationsbeziehung**

Stellen Sie sicher, dass das Organisationsbeziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Hier ein Beispiel:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Migrationsendpunkt**

Stellen Sie sicher, dass das Migrationsendpunktobjekt mit diesem Befehl erstellt und konfiguriert wurde.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Hier ein Beispiel.

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Quellmandant

**Organisationsbeziehung**

Stellen Sie sicher, dass das Organisationsbeziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

Hier ein Beispiel.

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a>Überprüfen des Setupskripts

Wenn während der Konfiguration der Quell- oder Zielmandanten Fehler auftreten, können Sie das VerifySetup.ps1 Skript ausführen, das sich [auf GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) befindet, und die Ausgabe überprüfen.

Hier ist ein Beispiel für die Ausführung von VerifySetup.ps1 auf dem Zielmandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier ist ein Beispiel für VerifySetup.ps1 auf dem Quellmandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Verschieben von Postfächern zurück zur ursprünglichen Quelle

Wenn ein Postfach zurück zum ursprünglichen Quellmandanten verschoben werden muss, müssen die gleichen Schritte und Skripts sowohl in neuen Quell- als auch in neuen Zielmandanten ausgeführt werden. Das vorhandene Organization Relationship-Objekt wird aktualisiert oder angefügt, nicht neu erstellt.

## <a name="prepare-target-user-objects-for-migration"></a>Vorbereiten von Zielbenutzerobjekten für die Migration

Benutzer, die migrieren, müssen im Zielmandanten vorhanden sein und Exchange Online System (als MailUsers) mit bestimmten Attributen gekennzeichnet sein, um mandantenübergreifende Verschiebungen zu ermöglichen. Bei Benutzern, die im Zielmandanten nicht ordnungsgemäß eingerichtet sind, schlägt das System fehl. Im folgenden Abschnitt werden die MailUser-Objektanforderungen für den Zielmandanten beschrieben.

### <a name="prerequisites"></a>Voraussetzungen

Sie müssen sicherstellen, dass die folgenden Objekte und Attribute in der Zielorganisation festgelegt sind.

1. Für jedes Postfach, das aus einer Quellorganisation verschoben wird, müssen Sie ein MailUser-Objekt in der Zielorganisation bereitstellen:

   - Der Ziel-MailUser muss über diese Attribute aus dem Quellpostfach verfügen oder dem neuen User-Objekt zugewiesen sein:
      - ExchangeGUID (direkter Fluss von Quelle zu Ziel) – Die Postfach-GUID muss übereinstimmen. Der Verschiebungsprozess wird nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist.
      - ArchiveGUID (direkter Fluss von Quelle zu Ziel) – Die Archiv-GUID muss übereinstimmen. Der Verschiebungsprozess wird nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist. (Dies ist nur erforderlich, wenn das Quellpostfach archiviert ist).
      - LegacyExchangeDN (Flow as proxyAddress, "x500: <LegacyExchangeDN> ") – Der LegacyExchangeDN muss auf MailUser als x500 vorhanden sein: proxyAddress. Die Verschiebungsprozesse werden nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist.
      - UserPrincipalName – UPN richtet sich nach der NEUEN Identität oder dem Zielunternehmen des Benutzers (z. B. user@northwindtraders.onmicrosoft.com).
      - Primäre SMTPAddress – Primäre SMTP-Adresse richtet sich nach der NEUEN Firma des Benutzers (z. B. user@northwind.com).
      - TargetAddress/ExternalEmailAddress – MailUser verweist auf das aktuelle Postfach des Benutzers, das im Quellmandanten gehostet wird (z. B. user@contoso.onmicrosoft.com). Stellen Sie beim Zuweisen dieses Werts sicher, dass Sie PrimarySMTPAddress zugewiesen haben/sind, oder dieser Wert legt die PrimarySMTPAddress fest, was zu Verschiebungsfehlern führt.
      - Sie können keine älteren SMTP-Proxyadressen aus dem Quellpostfach zum MailUser-Ziel hinzufügen. Beispielsweise können Sie contoso.com auf dem MEU in fabrikam.onmicrosoft.com Mandantenobjekten nicht verwalten). Domänen sind nur einem Azure AD- oder Exchange Online-Mandanten zugeordnet.

     Beispiel **für ein** MailUser-Zielobjekt:

     | Attribut             | Wert                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     Beispiel für ein Quellpostfachobjekt: 

     | Attribut             | Wert                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Zusätzliche Attribute können bereits in Exchange Hybridrückschreiben enthalten sein. Wenn nicht, sollten sie eingeschlossen werden.
   - msExchBlockedSendersHash – Schreibt online sichere und blockierte Absenderdaten von Clients in lokales Active Directory zurück.
   - msExchSafeRecipientsHash – Schreibt online sichere und blockierte Absenderdaten von Clients in lokales Active Directory zurück.
   - msExchSafeSendersHash – Schreibt online sichere und blockierte Absenderdaten von Clients in lokales Active Directory zurück.

2. Wenn sich das Quellpostfach auf LitigationHold befindet und die Größe des Quellpostfachs "Wiederherstellbare Elemente" größer als der Datenbankstandard (30 GB) ist, werden Verschiebungen nicht fortgesetzt, da das Zielkontingent kleiner als die Größe des Quellpostfachs ist. Sie können das MailUser-Zielobjekt so aktualisieren, dass die ELC-Postfachflags von der Quellumgebung auf das Ziel übertragen werden. Dadurch wird das Zielsystem veranlasst, das Kontingent der MailUser auf 100 GB zu erweitern, wodurch die Verschiebung zum Ziel ermöglicht wird. Diese Anweisungen funktionieren nur für hybride Identitäten, die Azure AD Verbinden ausführen, da die Befehle zum Stempeln der ELC-Flags für Mandantenadministratoren nicht verfügbar gemacht werden.

    >[!Note]
    > BEISPIEL – WIE BESEHEN KEINE GARANTIE<br/>Dieses Skript geht von einer Verbindung mit dem Quellpostfach (zum Abrufen von Quellwerten) und dem lokalen Ziel-Active Directory (zum Stempeln des ADUser-Objekts) aus. Wenn für die Quelle rechtsstreitigkeiten oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto fest.  Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.

    ```powershell
    $ELCValue = 0
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}}
    ```

3. Nicht hybride Zielmandanten können das Kontingent im Ordner "Wiederherstellbare Elemente" für die MailUsers vor der Migration ändern, indem sie den folgenden Befehl ausführen, um das Beweissicherungsverfahren für das MailUser-Objekt zu aktivieren und das Kontingent auf 100 GB zu erhöhen: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Beachten Sie, dass dies für Mandanten in hybriden Umgebungen nicht funktioniert.

4. Benutzer in der Zielorganisation müssen mit entsprechenden Exchange Online Abonnements lizenziert werden, die für die Organisation gelten. Sie können eine Lizenz vor einer Postfachverlagerung anwenden, aber NUR, wenn das Ziel-MailUser ordnungsgemäß mit ExchangeGUID- und Proxyadressen eingerichtet ist. Das Anwenden einer Lizenz vor der Anwendung von ExchangeGUID führt zu einem neuen Postfach, das in der Zielorganisation bereitgestellt wird.

    > [!Note]
    > Wenn Sie eine Lizenz auf ein Postfach- oder MailUser-Objekt anwenden, werden alle PROXYAddresses des SMTP-Typs bereinigt, um sicherzustellen, dass nur überprüfte Domänen im Exchange EmailAddresses-Array enthalten sind.

5. Sie müssen sicherstellen, dass das Ziel-MailUser keine vorherige ExchangeGuid-Datei aufweist, die nicht mit der ExchangeGuid-Quelle übereinstimmt. Dies kann vorkommen, wenn das Ziel-MEU zuvor für Exchange Online lizenziert und ein Postfach bereitgestellt wurde. Wenn das Ziel-MailUser zuvor für ExchangeGuid lizenziert wurde oder über ein ExchangeGuid verfügt, das nicht mit der ExchangeGuid-Quelle übereinstimmt, müssen Sie eine Bereinigung der Cloud-MEU durchführen. Für diese Cloud-MEUs können Sie `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` ausführen.

    > [!Caution]
    > Dieser Vorgang ist unumkehrbar. Wenn das Objekt über ein "softDeleted"-Postfach verfügt, kann es nach diesem Punkt nicht wiederhergestellt werden. Nach dem Löschen können Sie jedoch die richtige ExchangeGuid mit dem Zielobjekt synchronisieren, und MRS verbindet das Quellpostfach mit dem neu erstellten Zielpostfach. (Verweisen Sie auf den EHLO-Blog zum neuen Parameter.)

    Suchen Sie objekte, bei denen es sich zuvor um Postfächer handelte, mit diesem Befehl.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    Hier ein Beispiel.

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails
    ----       ---------------------------- ------------- --------------------
    John       UserMailbox                  MailUser      MailUser
    ```

    Löschen Sie das vorläufig gelöschte Postfach mit diesem Befehl.

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    Hier ein Beispiel.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm
    Are you sure you want to perform this action?
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.
    Do you want to continue?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y
    ```

## <a name="perform-mailbox-migrations"></a>Durchführen von Postfachmigrationen

Mandantenübergreifende Exchange Postfachmigrationen werden als Migrationsbatches übermittelt, die vom Zielmandanten initiiert werden. Dies ähnelt der Art und Weise, wie Migrationsbatches beim Onboarding von Exchange lokalen zu Microsoft 365 funktionieren.

### <a name="create-migration-batches"></a>Erstellen von Migrationsbatches

Nachfolgend sehen Sie ein Beispiel für ein Cmdlet für migrationsbatches Cmdlet zum Starten von Verschiebungen.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Die E-Mail-Adresse in der CSV-Datei muss die im Zielmandanten und nicht im Quellmandanten angegebene Adresse sein.

Die Batchübermittlung für die Migration wird auch vom neuen Exchange Admin Center unterstützt, wenn Sie die mandantenübergreifende Option auswählen.

#### <a name="update-on-premises-mailusers"></a>Aktualisieren von lokalen MailUsers

Sobald das Postfach von der Quelle zum Ziel wechselt, sollten Sie sicherstellen, dass die lokalen E-Mail-Benutzer (Quelle und Ziel) mit der neuen targetAddress aktualisiert werden. In den Beispielen ist die targetDeliveryDomain, die bei der Verschiebung verwendet **wird, contoso.onmicrosoft.com**. Aktualisieren Sie die E-Mail-Benutzer mit dieser targetAddress.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Müssen RemoteMailboxes nach dem Verschieben lokal in der Quelle aktualisiert werden?**

Ja, Sie sollten die targetAddress (RemoteRoutingAddress/ExternalEmailAddress) der lokalen Quellbenutzer aktualisieren, wenn das Quellmandantenpostfach zum Zielmandanten verschoben wird.  Während das E-Mail-Routing den Empfehlungen für mehrere E-Mail-Benutzer mit unterschiedlichen TargetAddresses folgen kann, MÜSSEN Frei/Gebucht-Nachschlagevorgänge für E-Mail-Benutzer auf den Speicherort des Postfachbenutzers abzielen. Frei/Gebucht-Nachschlagevorgänge verfolgen nicht mehrere Umleitungen.

**Migrieren Teams Besprechungen mandantenübergreifend?**

Die Besprechungen werden jedoch verschoben, aber die Teams Besprechungs-URL wird nicht aktualisiert, wenn Elemente mandantenübergreifend migriert werden. Da die URL im Zielmandanten ungültig ist, müssen Sie die Teams Besprechungen entfernen und neu erstellen.

**Werden die Inhalte des Teams Chatordners mandantenübergreifend migriert?**

Nein, der inhalt des Teams Chatordners wird nicht mandantenübergreifend migriert.

**Wie kann ich nur Verschiebungen sehen, bei denen es sich um mandantenübergreifende Verschiebungen handelt, nicht um meine Onboarding- und Offboard-Verschiebungen?**

Verwenden Sie den `-flags` Parameter. Hier ein Beispiel.

```powershell
Get-MoveRequest -Flags "CrossTenant"
```

**Können Sie Beispielskripts zum Kopieren von Attributen bereitstellen, die beim Testen verwendet werden?**

> [!Note]
> BEISPIEL – WIE BESEHEN KEINE GARANTIE<br/>Dieses Skript geht von einer Verbindung mit dem Quellpostfach (zum Abrufen von Quellwerten) und dem lokalen Active Directory Domain Services-Ziel (zum Stempeln des ADUser-Objekts) aus. Wenn für die Quelle rechtsstreitigkeiten oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto fest.  Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.

```powershell
#Dumps out the test mailboxes from SourceTenant
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit"
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

#################################################################
#Copy the file $outfile to the desktop of the target on-premises
#then run the below to create MEU in Target
#################################################################
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

#################################################################
# On AADSync machine, run AADSync
#################################################################
Start-ADSyncSyncCycle

#AADSync and FWDSync will create the target MEUs in the Target tenant
```
**Wie greifen wir am 1. Tag nach dem Verschieben des Verwendungspostfachs auf Outlook zu?**

Da nur ein Mandant eine Domäne besitzen kann, wird die frühere primäre SMTPAddress dem Benutzer im Zielmandanten nicht zugeordnet, wenn die Postfach-Verschiebung abgeschlossen ist. nur die Domänen, die dem neuen Mandanten zugeordnet sind. Outlook verwendet den neuen BENUTZER-UPN, um sich beim Dienst zu authentifizieren, und das Outlook-Profil erwartet, dass die primäre SMTPAddress der Vorversion gefunden wird, die dem Postfach im Zielsystem entspricht. Da sich die Legacyadresse nicht im Zielsystem befindet, stellt das Outlook-Profil keine Verbindung her, um das neu verschobene Postfach zu finden.

Für diese anfängliche Bereitstellung müssen Benutzer ihr Profil mit dem neuen UPN, der primären SMTP-Adresse und dem erneuten Synchronisieren von OST-Inhalten neu erstellen.

> [!Note]
> Planen Sie entsprechend, wenn Sie Ihre Benutzer für den Abschluss batchen. Sie müssen die Netzwerkauslastung und -kapazität berücksichtigen, wenn Outlook Clientprofile erstellt und nachfolgende OST- und OAB-Dateien auf Clients heruntergeladen werden.

**In welchen Exchange RBAC-Rollen muss ich Mitglied sein, um eine mandantenübergreifende Verschiebung einzurichten oder abzuschließen?**

Es gibt eine Matrix von Rollen, die auf der Annahme delegierter Aufgaben beim Ausführen einer Postfach-Verschiebung basiert. Derzeit sind zwei Rollen erforderlich:

- Die erste Rolle ist für eine einmalige Einrichtungsaufgabe, die die Autorisierung zum Verschieben von Inhalten in oder aus Ihrer Mandanten-/Organisationsgrenze festlegt. Da das Verschieben von Daten aus Ihrer Organisatorischen Kontrolle für alle Unternehmen ein wichtiges Problem ist, haben wir uns für die höchste zugewiesene Rolle des Organisationsadministrators (OrgAdmin) entschieden. Diese Rolle muss eine neue OrganizationRelationship ändern oder einrichten, die die -MailboxMoveCapability mit der Remoteorganisation definiert. Nur der OrgAdmin kann die MailboxMoveCapability-Einstellung ändern, während andere Attribute in OrganizationRelationhip vom Verbundfreigabeadministrator verwaltet werden können.

- Die Rolle der Ausführung der tatsächlichen Verschiebungsbefehle kann an eine Funktion auf niedrigerer Ebene delegiert werden. Der Rolle des Verschiebens von Postfächern wird die Funktion zum Verschieben von Postfächern in oder aus der Organisation mithilfe des `-RemoteTenant` Parameters zugewiesen.

**Wie wird die SMTP-Adresse als Ziel für targetAddress (TargetDeliveryDomain) im konvertierten Postfach (in MailUser-Konvertierung) ausgewählt?**

Exchange Postfach wird mithilfe von MRS verschoben, indem die targetAddress für das ursprüngliche Quellpostfach beim Konvertieren in ein MailUser erstellt wird, indem eine E-Mail-Adresse (proxyAddress) für das Zielobjekt zugeordnet wird. Der Prozess verwendet den Wert "-TargetDeliveryDomain", der an den Verschiebungsbefehl übergeben wird, und sucht dann auf der Zielseite nach einem übereinstimmenden Proxy für diese Domäne. Wenn eine Übereinstimmung gefunden wird, wird die übereinstimmende proxyAddress verwendet, um die ExternalEmailAddress (targetAddress) für das konvertierte Postfachobjekt (jetzt MailUser) festzulegen.

**Wie werden Postfachberechtigungen übertragen?**

Postfachberechtigungen umfassen "Senden im Auftrag von" und "Postfachzugriff":

- Send On Behalf Of (AD:publicDelegates) speichert den DN von Empfängern mit Zugriff auf das Postfach eines Benutzers als Stellvertretung. Dieser Wert wird in Active Directory gespeichert und wird derzeit nicht als Teil des Postfachübergangs verschoben. Wenn für das Quellpostfach publicDelegates festgelegt sind, müssen Sie die publicDelegates für das Zielpostfach neu erstellen, sobald die MEU-in-Postfach-Konvertierung in der Zielumgebung abgeschlossen ist, indem Sie `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` ausführen.

- Postfachberechtigungen, die im Postfach gespeichert sind, werden mit dem Postfach verschoben, wenn sowohl der Prinzipal als auch der Stellvertreter in das Zielsystem verschoben werden. Beispielsweise wird dem Benutzer TestUser_7 FullAccess für das Postfach gewährt, TestUser_8 im Mandanten-SourceCompany.onmicrosoft.com. Nachdem die Postfach-Verschiebung in TargetCompany.onmicrosoft.com abgeschlossen ist, werden die gleichen Berechtigungen im Zielverzeichnis eingerichtet. Beispiele für die Verwendung von *"Get-MailboxPermission"* für TestUser_7 in Quell- und Zielmandanten finden Sie unten. Exchange Cmdlets wird das Präfix "Quelle" und "Ziel" entsprechend vorangestellt.

Hier ist ein Beispiel für die Ausgabe der Postfachberechtigung vor einer Verschiebung.

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Hier ist ein Beispiel für die Ausgabe der Postfachberechtigung nach der Verschiebung.

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```

> [!Note]
> Mandantenübergreifende Postfach- und Kalenderberechtigungen werden NICHT unterstützt. Sie müssen Prinzipale und Stellvertretungen in konsolidierten Verschiebungsbatches organisieren, damit diese verbundenen Postfächer gleichzeitig vom Quellmandanten übertragen werden.

**Welcher X500-Proxy sollte den MailUser-Zielproxyadressen hinzugefügt werden, um die Migration zu ermöglichen?**

Für die mandantenübergreifende Postfachmigration muss der LegacyExchangeDN-Wert des Quellpostfachobjekts als x500-E-Mail-Adresse im MailUser-Zielobjekt gestempelt werden.

Beispiel:
```powershell
LegacyExchangeDN value on source mailbox is:
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara

so the x500 email address to be added to target MailUser object would be:
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara
```

> [!Note]
> Zusätzlich zu diesem X500-Proxy müssen Sie alle X500-Proxys aus dem Postfach in der Quelle in das Postfach im Ziel kopieren.

**Wo beginne ich mit der Problembehandlung, wenn Verschiebungen nicht funktionieren?**

Führen Sie zunächst das VerifySetup.ps1 Skript [aus,](https://github.com/microsoft/cross-tenant/releases/tag/Preview) das sich in GitHub befindet, und überprüfen Sie die Ausgabe.

Hier ist ein Beispiel für die Ausführung von VerifySetup.ps1 auf dem Zielmandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier ist ein eExample zum Ausführen von VerifySetup.ps1 auf dem Quellmandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**Kann der Quell- und Zielmandant denselben Domänennamen verwenden?**

Nein. Die Quell- und Zielmandantendomänennamen müssen eindeutig sein. Beispielsweise eine Quelldomäne von contoso.com und die Zieldomäne von fourthcoffee.com.

**Werden freigegebene Postfächer verschoben und funktionieren weiterhin?**

Ja, wir behalten jedoch nur die Speicherberechtigungen, wie in diesen Artikeln beschrieben:

- [Microsoft Docs | Verwalten von Berechtigungen für Empfänger in Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft Support | So erteilen Sie Exchange und Outlook Postfachberechtigungen in Office 365 dedizierten](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Ist Azure Key Vault erforderlich und wann werden Transaktionen ausgeführt?**

Ja, ein Azure-Abonnement ist erforderlich, um Key Vault zum Speichern des Zertifikats zum Autorisieren der Migration zu verwenden. Im Gegensatz zum Onboarding von Migrationen, bei denen Benutzername & Kennwort für die Authentifizierung bei der Quelle verwendet wird, verwenden mandantenübergreifende Postfachmigrationen OAuth und dieses Zertifikat als Geheimnis/Anmeldeinformationen. Der Zugriff auf den Key Vault muss während aller Postfachmigrationen aufrechterhalten werden, da er einmal am Anfang und nach Ende der Migration sowie einmal alle 24 Stunden während inkrementeller Synchronisierungszeiten aufgerufen wird. Details zur AKV-Kostenkalkulation finden Sie [hier.](https://azure.microsoft.com/en-us/pricing/details/key-vault/)

**Haben Sie Empfehlungen für Batches?**

2.000 Postfächer pro Batch nicht überschreiten. Es wird dringend empfohlen, Batches zwei Wochen vor dem Übernahmedatum zu übermitteln, da es während der Synchronisierung keine Auswirkungen auf die Endbenutzer gibt. Wenn Sie Anleitungen für Postfächer mit mehr als 50.000 Postfächern benötigen, können Sie sich an die Engineering Feedback Distribution List unter crosstenantmigrationpreview@service.microsoft.com wenden.

**Was geschieht, wenn ich die Dienstverschlüsselung mit Customer Key verwende?**

Das Postfach wird vor dem Verschieben entschlüsselt. Stellen Sie sicher, dass der Kundenschlüssel im Zielmandanten konfiguriert ist, wenn er noch erforderlich ist. Weitere Informationen finden Sie [hier.](../compliance/customer-key-overview.md)

**Wie lautet die geschätzte Migrationszeit?**

Um Sie bei der Planung Ihrer Migration zu unterstützen, enthält die [hier](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) aufgeführte Tabelle die Richtlinien dazu, wann Massenmigrationen von Postfächern oder einzelne Migrationen zu erwarten sind. Diese Schätzungen basieren auf einer Datenanalyse vorheriger Kundenmigrationen. Da jede Umgebung einzigartig ist, kann ihre genaue Migrationsgeschwindigkeit variieren.

Denken Sie daran, dass sich dieses Feature derzeit in der Vorschau befindet und die SLA und alle anwendbaren ServiceLevels während des Vorschaustatus dieses Features nicht auf Leistungs- oder Verfügbarkeitsprobleme angewendet werden.

## <a name="known-issues"></a>Bekannte Probleme

-  **Problem: Automatisch erweiterte Archive können nicht migriert werden.** Die mandantenübergreifende Migrationsfunktion unterstützt Migrationen des primären Postfachs und des Archivpostfachs für einen bestimmten Benutzer. Wenn der Benutzer in der Quelle jedoch über ein automatisch erweitertes Archiv verfügt , d. h. mehrere Archivpostfächer, kann das Feature die zusätzlichen Archive nicht migrieren und sollte fehlschlagen.

- **Problem: Cloud-MailUsers mit nicht-owned smtp proxyAddress block MRS moves background.** Beim Erstellen von MailUser-Zielmandantenobjekten müssen Sie sicherstellen, dass alle SMTP-Proxyadressen zur Zielmandantenorganisation gehören. Wenn eine SMTP-Proxyadresse für den E-Mail-Zielbenutzer vorhanden ist, der nicht zum lokalen Mandanten gehört, wird die Konvertierung von MailUser in Postfach verhindert. Dies ist aufgrund unserer Zusicherung, dass Postfachobjekte nur E-Mails von Domänen senden können, für die der Mandant autoritativ ist (vom Mandanten beanspruchte Domänen):

   - Wenn Sie Benutzer lokal mithilfe von Azure AD Verbinden synchronisieren, stellen Sie lokale MailUser-Objekte mit ExternalEmailAddress bereit, die auf den Quellmandanten zeigen, in dem das Postfach vorhanden ist (laran@contoso.onmicrosoft.com), und Sie stempeln die PrimarySMTPAddress als Domäne, die sich im Zielmandanten (Lara.Newton@northwind.com) befindet. Diese Werte werden mit dem Mandanten synchronisiert, und ein entsprechender E-Mail-Benutzer wird bereitgestellt und für die Migration bereit. Hier ist ein Beispielobjekt dargestellt.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses
     ExternalEmailAddress               EmailAddresses
     --------------------               --------------
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com}
     ```

   > [!Note]
   > Die *contoso.onmicrosoft.com* Adresse ist im Array EmailAddresses/proxyAddresses *nicht* vorhanden.

- **Problem: MailUser-Objekte mit "externen" primären SMTP-Adressen werden geändert/auf "interne" vom Unternehmen beanspruchte Domänen zurückgesetzt.**

   MailUser-Objekte sind Zeiger auf nicht lokale Postfächer. Bei mandantenübergreifenden Postfachmigrationen verwenden wir MailUser-Objekte, um entweder das Quellpostfach (aus Sicht der Zielorganisation) oder das Zielpostfach (aus Sicht der Quellorganisation) darzustellen. Die MailUsers verfügen über eine ExternalEmailAddress (targetAddress), die auf die SMTP-Adresse des tatsächlichen Postfachs (ProxyTest@fabrikam.onmicrosoft.com) und die primarySMTP-Adresse verweist, die die angezeigte SMTP-Adresse des Postfachbenutzers im Verzeichnis darstellt. Einige Organisationen entscheiden sich dafür, die primäre SMTP-Adresse als externe SMTP-Adresse anzuzeigen, nicht als Adresse, die dem lokalen Mandanten gehört/bestätigt wird (z. B. fabrikam.com statt als contoso.com).  Sobald jedoch ein Exchange Dienstplanobjekt über Lizenzierungsvorgänge auf mailUser angewendet wird, wird die primäre SMTP-Adresse so geändert, dass sie von der lokalen Organisation überprüft wird (contoso.com). Es gibt zwei mögliche Gründe:

   - Wenn ein Exchange Serviceplan auf einen MailUser angewendet wird, wird im Azure AD-Prozess das Proxy-Scrubbing erzwungen, um sicherzustellen, dass die lokale Organisation keine E-Mails von einem anderen Mandanten senden kann. Alle SMTP-Adressen in einem Empfängerobjekt mit diesen Serviceplänen werden entfernt, wenn die Adresse von der lokalen Organisation nicht überprüft wird. Wie im Beispiel wird die Fabikam.com Domäne nicht vom contoso.onmicrosoft.com Mandanten überprüft, sodass das Scrubbing diese domäne entfernt fabrikam.com. Wenn Sie diese externe Domäne auf MailUser beibehalten möchten, entweder vor der Migration oder nach der Migration, müssen Sie Ihre Migrationsprozesse ändern, um Lizenzen nach Abschluss der Verschiebung oder vor der Verschiebung zu entfernen, um sicherzustellen, dass die Benutzer das erwartete externe Branding angewendet haben. Sie müssen sicherstellen, dass das Postfachobjekt ordnungsgemäß lizenziert ist, um keinen Einfluss auf den E-Mail-Dienst zu haben.<br/><br/>Hier sehen Sie ein Beispielskript zum Entfernen der Dienstpläne für einen MailUser im Contoso.onmicrosoft.com Mandanten.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION"
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo
    ```

       Hier werden ergebnisse in der Gruppe der zugewiesenen ServicePlans angezeigt.

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending
    ServicePlan           ProvisioningStatus
    -----------           ------------------
    ATP_ENTERPRISE        PendingProvisioning
    MICROSOFT_SEARCH      PendingProvisioning
    INTUNE_O365           PendingActivation
    PAM_ENTERPRISE        Disabled
    EXCHANGE_ANALYTICS    Disabled
    EQUIVIO_ANALYTICS     Disabled
    THREAT_INTELLIGENCE   Disabled
    LOCKBOX_ENTERPRISE    Disabled
    PREMIUM_ENCRYPTION    Disabled
    EXCHANGE_S_ENTERPRISE Disabled
    INFORMATION_BARRIERS  Disabled
    MYANALYTICS_P2        Disabled
    MIP_S_CLP1            Disabled
    MIP_S_CLP2            Disabled
    ADALLOM_S_O365        PendingInput
    RMS_S_ENTERPRISE      Success
    YAMMER_ENTERPRISE     Success
    PROJECTWORKMANAGEMENT Success
    BI_AZURE_P2           Success
    WHITEBOARD_PLAN3      Success
    SHAREPOINTENTERPRISE  Success
    SHAREPOINTWAC         Success
    KAIZALA_STANDALONE    Success
    OFFICESUBSCRIPTION    Success
    MCOSTANDARD           Success
    Deskless              Success
    STREAM_O365_E5        Success
    FLOW_O365_P3          Success
    POWERAPPS_O365_P3     Success
    TEAMS1                Success
    MCOEV                 Success
    MCOMEETADV            Success
    BPOS_S_TODO_3         Success
    FORMS_PLAN_E5         Success
    SWAY                  Success

    ```

       Die PrimarySMTPAddress des Benutzers wird nicht mehr bereinigt. Die fabrikam.com Domäne gehört nicht dem contoso.onmicrosoft.com Mandanten und bleibt als primäre SMTP-Adresse im Verzeichnis erhalten.

       Hier ein Beispiel.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress
    ------------------        -------------------------               --------------------
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com
    ```

   - Wenn msExchRemoteRecipientType auf 8 (DeprovisionMailbox) festgelegt ist, entfernt die Proxy-Scrubbinglogik in Azure für lokale MailUser, die zum Zielmandanten migriert werden, nicht zugewiesene Domänen und setzt primarySMTP auf eine eigene Domäne zurück. Durch Löschen von msExchRemoteRecipientType im lokalen MailUser wird die Proxy-Scrub-Logik nicht mehr angewendet. <br/><br>Nachfolgend finden Sie den vollständigen Satz möglicher Servicepläne, die Exchange Online enthalten.

   | Name                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery Storage (500 GB)               |
   | Kunden-Lockbox                                  |
   | Verhinderung von Datenverlust                              |
   | Exchange Enterprise CAL Services (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (Plan 1)                          |
   | Exchange Online (Plan 2)                          |
   | Exchange Online-Archivierung für Exchange Online     |
   | Exchange Online-Archivierung für Exchange Server     |
   | Exchange Online Inaktives Benutzer-Add-On              |
   | Exchange Online-Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Plan 1                            |
   | Exchange Online-POP                               |
   | Exchange Online Protection                        |
   | Informationsbarrieren                              |
   | Information Protection für Office 365 – Premium   |
   | Information Protection für Office 365 – Standard  |
   | Insights von MyAnalytics                           |
   | Microsoft 365 Erweiterte Überwachung                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (Vollversion)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender für Office 365 (Plan 1)    |
   | Microsoft Defender für Office 365 (Plan 2)    |
   | Office 365 Privileged Access Management           |
   | Premium Verschlüsselung in Office 365                  |
