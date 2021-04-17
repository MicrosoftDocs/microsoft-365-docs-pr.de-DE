---
title: Mandantenübergreifende Postfachmigration
description: So verschieben Sie Postfächer zwischen Microsoft 365- oder Office 365-Mandanten.
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
ms.openlocfilehash: d52a0ca4a2dc9b799a32f70962416ffe190e16db
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876187"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Mandantenübergreifende Postfachmigration (Vorschau)

Wenn ein Exchange Online-Mandant Postfächer in einen anderen Mandanten im gleichen Exchange Online-Dienst verschieben musste, müssten sie diese vollständig in den lokalen Dienst verschieben und dann in einen neuen Mandanten integrieren. Mit dem neuen mandantenübergreifenden Migrationsfeature können Mandantenadministratoren sowohl in Quell- als auch in Ziel mandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben. Dadurch wird die Notwendigkeit von Off-Board- und Onboardpostfächern entfernt.

In der Regel benötigen Sie bei Fusionen oder Übernahmen die Möglichkeit, Benutzer und Inhalte in einen neuen Mandanten zu verschieben. Wenn der Ziel-Mandant-Administrator die Migration ausgeführt hat, wird dies als Pull-Move bezeichnet, ähnlich wie bei lokalen Migrationen mit Cloud-Onboarding.

Mandantenübergreifende Exchange-Postfachbewegungen werden von Mandantenadministratoren vollständig self-serviced ausgeführt. Dabei werden bekannte Schnittstellen verwendet, die in die größeren Workflows geschrieben werden können, die zum Übergang von Benutzern in ihre neue Organisation erforderlich sind. Administratoren können das Über die Verwaltungsrolle Postfächer verschieben verfügbare `New-MigrationBatch` Cmdlet verwenden, um mandantenübergreifende Verschieben auszuführen. Der Verschiebenprozess umfasst Mandantenautorisierungsüberprüfungen während der Postfachsynchronisierung und -finalisierung. 
 
Die Migration von Benutzern muss im Exchange Online-Ziel-Mandantensystem als MailUsers vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um mandantenübergreifende Bewegungen zu ermöglichen. Für Benutzer, die im Ziel-Mandanten nicht ordnungsgemäß eingerichtet sind, wird beim System ein Fehler ausgeführt.  

Wenn die Verschieben abgeschlossen sind, wird das Quellsystempostfach in MailUser konvertiert, und die targetAddress (in Exchange als ExternalEmailAddress angezeigt) wird mit der Routingadresse an den Ziel-Mandanten gestempelt. Bei diesem Prozess bleibt das legacy MailUser im Quell-Mandant und ermöglicht eine Zeit der Koexistenz und des E-Mail-Routings. Wenn Geschäftsprozesse dies zulassen, kann der Quell-Mandant die Quelle MailUser entfernen oder in einen E-Mail-Kontakt konvertieren. 

Mandantenübergreifende Exchange-Postfachmigrationen werden nur für Mandanten in Hybrid- oder Cloud- oder einer beliebigen Kombination der beiden Unterstützt.

In diesem Artikel wird der Prozess für mandantenübergreifende Postfachbewegungen beschrieben und Anleitungen zum Vorbereiten von Quell- und Ziel mandanten für die Inhaltsver verschieben.  

## <a name="preparing-source-and-target-tenants"></a>Vorbereiten von Quell- und Ziel-Mandanten

Das Mandantenübergreifende Exchange-Postfachmigrationsfeature erfordert autorisierungs- und scoping für mandantenübergreifende Migrationen. Mithilfe der Azure Enterprise-Anwendung und der Key Vault-Speicherlösungen können Mandantenadministratoren jetzt sowohl die Autorisierung als auch das Scoping von Exchange Online-Postfachmigrationen von einem Mandanten zum anderen verwalten. Mandantenübergreifende Postfachbewegungen unterstützen ein Einladungs- und Zustimmungsmodell zum Einrichten einer Azure Active Directory (Azure AD)-Anwendung, die für die Authentifizierung zwischen einem Mandantenpaar verwendet wird. Zusätzliche Komponenten wie eine Organisationsbeziehung und ein Migrationsendpunkt sind ebenfalls erforderlich.

Dieser Abschnitt enthält weder die spezifischen Schritte, die zum Vorbereiten der MailUser-Benutzerobjekte im Zielverzeichnis erforderlich sind, noch den Beispielbefehl zum Übermitteln eines Migrationsbatches. Weitere Informationen [finden Sie unter Prepare target user objects for migration.](#prepare-target-user-objects-for-migration)

## <a name="prerequisites"></a>Voraussetzungen

Das mandantenübergreifende Postfach verschieben-Feature [erfordert,](/azure/key-vault/basic-concepts) dass Azure Key Vault eine mandantenpaarspezifische Azure-Anwendung zum sicheren Speichern und Zugreifen auf das Zertifikat/den geheimen Schlüssel einrichten kann, das zum Authentifizieren und Autorisieren der Postfachmigration von einem Mandanten zum anderen verwendet wird. Dabei werden alle Anforderungen zum Freigeben von Zertifikaten/Geheimschlüsseln zwischen Mandanten entfernt. 

Stellen Sie vor dem Start sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um Azure Key Vault, Die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren. In der Regel verfügt der globale Administrator über die Berechtigung zum Ausführen aller Konfigurationsschritte.

Darüber hinaus sind E-Mail-aktivierte Sicherheitsgruppen im Quell-Mandant vor dem Ausführen des Setups erforderlich. Diese Gruppen werden verwendet, um die Liste der Postfächer, die vom Quell-Mandanten (oder manchmal auch als Ressourcen-Mandant bezeichnet) zum Ziel-Mandanten verschoben werden können, zu bereichern. Auf diese Weise kann der Quell-Mandant-Administrator die bestimmte Gruppe von Postfächern einschränken oder beschränken, die verschoben werden müssen, um zu verhindern, dass unbeabsichtigte Benutzer migriert werden. Geschachtelte Gruppen werden nicht unterstützt.

Sie müssen auch mit Ihrem vertrauenswürdigen Partnerunternehmen kommunizieren (mit dem Sie Postfächer verschieben), um ihre Microsoft 365-Mandanten-ID zu erhalten. Diese Mandanten-ID wird im Feld Organisationsbeziehung `DomainName` verwendet.

Um die Mandanten-ID eines Abonnements zu erhalten, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klicken Sie auf das Kopiersymbol für die Tenant ID-Eigenschaft, um sie in die Zwischenablage zu kopieren.

Hier sehen Sie, wie der Prozess funktioniert.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Mandantenvorbereitung für die Postfachmigration.":::

[Sehen Sie sich eine größere Version dieses Bilds an.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Vorbereiten von Mandanten

Auf einer hohen Ebene werden die folgenden Konfigurationsaktionen beim Ausführen der Setupskripts ausgeführt.

Bereiten Sie den Ziel mandanten vor:

1. Wenn keine vorhandene Azure-Ressourcengruppe bereitgestellt wird, wird ein neues (SCRIPT) erstellt.
2. Wenn kein vorhandener Schlüsseltresor bereitgestellt wird, wird ein neues (SCRIPT) erstellt.
3. Für die Office 365 Exchange Online Mailbox Migration Application (SCRIPT) wird eine neue Zugriffsrichtlinie erstellt.
4. Ein neues Zertifikat wird erstellt (oder vorhanden, falls angegeben), um das Geheimnis der Migrationsanwendung (SCRIPT) zu halten.
5. Eine neue Azure AD-Anwendung wird erstellt (SCRIPT).
6. Das Zertifikat/der geheime Schlüssel wird in die Migrationsanwendung (SCRIPT) hochgeladen.
7. Berechtigungen für die Postfachmigration werden der Anwendung (SCRIPT) zugewiesen.
8. Das Bereitstellungsskript hält an, bis der Zieladministrator der eigenen Anwendung (SCRIPT) zuwilligt.
9. Der Ziel-Mandant-Administrator ist mit den Berechtigungen einverstanden, die der Anwendung erteilt werden (MANUAL).
10. Eine Organisationsbeziehung wird zum Ziel-Mandant (SCRIPT) erstellt.
11. Ein Migrationsendpunkt wird erstellt, um Postfächer an den Ziel mandanten (SCRIPT) zu ziehen.

Bereiten Sie den Quell-Mandanten vor:

1. Der Quell-Mandant-Administrator akzeptiert die Zustimmung zur Einladung der Postfachmigrationsanwendung vom Ziel-Mandanten (MANUAL).
2. Der Quell-Mandantenadministrator erstellt eine E-Mail-aktivierte Sicherheitsgruppe in ihrem Mandanten, die die Liste der Postfächer enthält, die von der Migrationsanwendung verschoben werden dürfen (MANUAL).
3. Es wird eine Organisationsbeziehung mit dem Ziel-Mandanten erstellt, der an die Postfachmigrationsanwendung annimmt, die für die OAuth-Überprüfung verwendet werden soll, um die Verschiebenanforderung (SCRIPT) zu akzeptieren.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Schritt-für-Schritt-Anweisungen für den Ziel-Mandantenadministrator

1. Laden Sie SetupCrossTenantRelationshipForTargetTenant.ps1 Skript für das Ziel-Mandanten-Setup aus dem [GitHub-Repository herunter.](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 
2. Speichern Sie das Skript (SetupCrossTenantRelationshipForTargetTenant.ps1) auf dem Computer, von dem Sie das Skript ausführen.
3. Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Exchange Online-Ziel-Mandanten. Stellen Sie erneut sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um den Azure Key Vault-Speicher und -Zertifikat, die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.
4. Ändern Sie das Verzeichnis des Dateiordners in den Skriptspeicherort, oder überprüfen Sie, ob das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Der Remote-PowerShell-Sitzung befindet.
5. Führen Sie das Skript mit den folgenden Parametern und Werten aus.

    | Parameter | Wert | Erforderlich oder Optional
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Ziel-Mandantendomäne, z. B. fabrikam \. onmicrosoft.com. | Erforderlich |
    | -ResourceTenantDomain                       | Quell-Mandantendomäne, z. B. contoso \. onmicrosoft.com. | Erforderlich |
    | -ResourceTenantAdminEmail                   | E-Mail-Adresse des Quell-Mandantenadministrators. Dies ist der Quell-Mandantenadministrator, der der Verwendung der Vom Zieladministrator gesendeten Postfachmigrationsanwendung zuwilligt. Dies ist der Administrator, der die E-Mail-Einladung für die Anwendung erhält. | Erforderlich |
    | -ResourceTenantId                           | GuiD (Source Tenant Organization ID). | Erforderlich |
    | -SubscriptionId                             | Das Zum Erstellen von Ressourcen zu verwendende Azure-Abonnement. | Erforderlich |
    | -ResourceGroup                              | Azure-Ressourcengruppenname, der den Schlüsseltresor enthält oder enthält. | Erforderlich |
    | -KeyVaultName                               | Azure Key Vault-Instanz, in der Ihr Zertifikat/geheimer Postfachmigrationsanwendung gespeichert wird. | Erforderlich |
    | -CertificateName                            | Zertifikatname beim Generieren oder Suchen nach Zertifikaten im Schlüsseltresor. | Erforderlich |
    | -CertificateSubject                         | Name des Azure Key Vault-Zertifikatsubjekts, z. B. CN=contoso_fabrikam. | Erforderlich |
    | -ExistingApplicationId                      | E-Mail-Migrationsanwendung, die verwendet werden soll, wenn sie bereits erstellt wurde. | Optional |
    | -AzureAppPermissions                        | Die erforderlichen Berechtigungen für die Postfachmigrationsanwendung, z. B. Exchange oder MSGraph (Exchange zum Verschieben von Postfächern, MSGraph für die Verwendung dieser Anwendung zum Senden einer Einladung zum Zustimmungslink an den Ressourcen-Mandanten). | Erforderlich |
    | -UseAppAndCertGeneratedForSendingInvitation | Parameter für die Verwendung der Anwendung, die für die Migration zum Senden einer Einladung zum Zustimmungslink an den Quell-Mandantenadministrator erstellt wurde. Wenn dies nicht vorhanden ist, werden die Anmeldeinformationen des Zieladministrators aufgefordert, eine Verbindung mit dem Azure-Einladungs-Manager herzustellen und die Einladung als Zieladministrator zu senden. | Optional |
    | -KeyVaultAuditStorageAccountName            | Das Speicherkonto, in dem die Überwachungsprotokolle von Key Vault gespeichert werden. | Optional |
    | -KeyVaultAuditStorageResourceGroup          | Die Ressourcengruppe, die das Speicherkonto zum Speichern von Key Vault-Überwachungsprotokollen enthält. | Optional |
    ||||

    >[!Note]
    > Stellen Sie sicher, dass Sie das Azure AD PowerShell-Modul installiert haben, bevor Sie die Skripts ausführen. Installationsschritte ![ ](/powershell/azure/install-az-ps?view=azps-5.1.0) finden Sie hier.

6. Das Skript hält an und bittet Sie, die während dieses Vorgangs erstellte Exchange-Postfachmigrationsanwendung zu akzeptieren oder zu akzeptieren. Hier ein Beispiel.

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. In der Remote-PowerShell-Sitzung wird eine URL angezeigt. Kopieren Sie den Link, der für Ihre Mandanten zustimmung bereitgestellt wurde, und fügen Sie ihn in einen Webbrowser ein.

8. Melden Sie sich mit Ihren Anmeldeinformationen für den globalen Administrator an. Wenn der folgende Bildschirm angezeigt wird, wählen Sie **Akzeptieren aus.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogfeld Berechtigungen akzeptieren":::

9. Wechseln Sie zurück zur Remote-PowerShell-Sitzung, und fahren Sie mit enter fort.

10. Das Skript konfiguriert die verbleibenden Setupobjekte. Hier ein Beispiel.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Das Setup des Zieladministrators ist nun abgeschlossen!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Schritt-für-Schritt-Anweisungen für den Quell-Mandantenadministrator

1.  Melden Sie sich bei Ihrem Postfach als -ResourceTenantAdminEmail an, das vom Zieladministrator während des Setups angegeben wurde. Suchen Sie die E-Mail-Einladung vom Ziel-Mandanten, und wählen Sie dann die Schaltfläche **Erste Schritte** aus.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogfeld &quot;Eingeladen&quot;":::

2. Wählen **Sie Annehmen** aus, um die Einladung zu akzeptieren.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialogfeld zum Akzeptieren von Berechtigungen":::

   > [!NOTE]
   > Wenn Sie diese E-Mail nicht erhalten oder nicht finden können, wurde dem Zielmandantadministrator eine direkte URL bereitgestellt, die Sie erhalten können, um die Einladung zu akzeptieren. Die URL sollte in der Aufzeichnung der Remote-PowerShell-Sitzung des Ziel-Mandantenadministrators enthalten sein.

3. Erstellen Sie im Microsoft 365 Admin Center oder in einer Remote-PowerShell-Sitzung eine oder mehrere E-Mail-aktivierte Sicherheitsgruppen, um die Liste der Postfächer zu steuern, die der Ziel-Mandant vom Quell-Mandant zum Ziel mandanten ziehen (verschieben) darf. Sie müssen diese Gruppe nicht im Voraus auffüllen, aber es muss mindestens eine Gruppe bereitgestellt werden, um die Setupschritte (Skript) ausführen zu können. Schachtelgruppen werden nicht unterstützt. 

4. Laden Sie SetupCrossTenantRelationshipForResourceTenant.ps1 Skript für das Setup des Quell-Mandanten aus dem GitHub-Repository herunter: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) . 

5. Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Quell-Mandanten mit Ihren Exchange-Administratorberechtigungen. Globale Administratorberechtigungen sind nicht erforderlich, um den Quell-Mandanten zu konfigurieren, sondern nur den Ziel-Mandanten aufgrund des Erstellungsprozesses der Azure-Anwendung.

6. Ändern Sie das Verzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Der Remote-PowerShell-Sitzung befindet.

7. Führen Sie das Skript mit den folgenden erforderlichen Parametern und Werten aus.

    | Parameter | Wert |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | E-Mail-aktivierte Sicherheitsgruppe, die vom Quell-Mandant für die Identitäten/Postfächer erstellt wurde, die sich im Bereich der Migration befinden. |
    | -ResourceTenantDomain | Quell-Mandantendomänenname, z. B. contoso \. onmicrosoft.com. |
    | -ApplicationId | Azure-Anwendungs-ID (GUID) der Anwendung, die für die Migration verwendet wird. Anwendungs-ID, die über Ihr Azure-Portal (Azure AD, Unternehmensanwendungen, App-Name, Anwendungs-ID) oder in Ihrer Einladungs-E-Mail enthalten ist.  |
    | -TargetTenantDomain | Ziel-Mandantendomänenname, z. B. fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | Mandanten-ID des Ziel-Mandanten. Beispielsweise ist die Azure AD-Mandanten-ID von contoso \. onmicrosoft.com Mandanten. |
    |||

    Hier ein Beispiel.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Das Setup des Quelladministrators ist nun abgeschlossen!

### <a name="verify-setup"></a>Überprüfen des Setups

Stellen Sie sicher, dass die Organisationsbeziehungen in Quell- und Ziel mandanten und Migrationsendpunkt im Ziel erfolgreich erstellt wurden.

#### <a name="target-tenant"></a>Ziel-Mandant

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

#### <a name="source-tenant"></a>Quell-Mandant

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

Wenn Bei der Konfiguration der Quell- oder Ziel-Mandanten Fehler auftreten, können Sie das Skript VerifySetup.ps1 [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ausführen und die Ausgabe überprüfen.

Im Folgenden finden Sie ein Beispiel für die Ausführung VerifySetup.ps1 für den Ziel-Mandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Im Folgenden finden Sie ein Beispiel für VerifySetup.ps1 für den Quell-Mandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Verschieben von Postfächern zurück zur ursprünglichen Quelle

Wenn ein Postfach zurück zum ursprünglichen Quell-Mandant verschoben werden muss, müssen die gleichen Schritte und Skripts sowohl in neuen Quell- als auch in neuen Ziel-Mandanten ausgeführt werden. Das vorhandene Organisationsbeziehungsobjekt wird aktualisiert oder angefügt, nicht neu erstellt.

## <a name="prepare-target-user-objects-for-migration"></a>Vorbereiten von Zielbenutzerobjekten für die Migration

Die Migration von Benutzern muss im Ziel mandanten- und Exchange Online-System (als MailUsers) vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um mandantenübergreifende Bewegungen zu ermöglichen. Für Benutzer, die im Ziel-Mandanten nicht ordnungsgemäß eingerichtet sind, wird beim System ein Fehler ausgeführt. Im folgenden Abschnitt werden die MailUser-Objektanforderungen für den Ziel mandanten beschrieben.

### <a name="prerequisites"></a>Voraussetzungen
  
Sie müssen sicherstellen, dass die folgenden Objekte und Attribute in der Zielorganisation festgelegt sind.  

1. Für alle Postfächer, die aus einer Quellorganisation verschoben werden, müssen Sie ein MailUser-Objekt in der Zielorganisation bereitstellen: 

   - Ziel-MailUser muss über die folgenden Attribute aus dem Quellpostfach verfügen oder dem neuen User-Objekt zugewiesen sein:
      - ExchangeGUID (direkter Fluss von Quelle zu Ziel) – Die Postfach-GUID muss übereinstimmen. Der Verschiebevorgang wird nicht fortgesetzt, wenn dies für das Zielobjekt nicht vorhanden ist. 
      - ArchiveGUID (direkter Fluss von Quelle zu Ziel) – Die Guid des Archivs muss übereinstimmen. Der Verschiebevorgang wird nicht fortgesetzt, wenn dies für das Zielobjekt nicht vorhanden ist. (Dies ist nur erforderlich, wenn das Quellpostfach Archive aktiviert ist). 
      - LegacyExchangeDN (flow as proxyAddress, "x500: ") – Der <LegacyExchangeDN> LegacyExchangeDN muss auf ziel-MailUser als x500: proxyAddress vorhanden sein. Die Verschiebeprozesse werden nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist. 
      - UserPrincipalName – UPN richtet sich an der NEUEN Identität oder dem Zielunternehmen des Benutzers aus (z. B. user@northwindtraders.onmicrosoft.com). 
      - Primäre SMTPAddress– Primäre SMTP-Adresse richtet sich nach dem NEUEN Unternehmen des Benutzers aus (z. B. user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser referenziert das aktuelle Postfach des Benutzers, das im Quell-Mandant gehostet wird (z. B. user@contoso.onmicrosoft.com). Stellen Sie beim Zuweisen dieses Werts sicher, dass Sie auch PrimarySMTPAddress zugewiesen haben bzw. zuweisen, oder dieser Wert gibt den PrimarySMTPAddress-Wert an, der zu Verschiebefehlern führen wird. 
      - Sie können keine älteren SMTP-Proxyadressen aus dem Quellpostfach zu Ziel-MailUser hinzufügen. Sie können z. B. keine contoso.com für die MEU in fabrikam.onmicrosoft.com Mandantenobjekten verwalten). Domänen sind nur einem Azure AD- oder Exchange Online-Mandanten zugeordnet.
 
     Beispiel **für ein** MailUser-Zielobjekt:
 
     | Attribut             | Wert                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | Laran                                                                                                                    |
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

     Beispiel **für das** Quellpostfachobjekt:

     | Attribut             | Wert                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | Laran                                                                    |
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

   - Zusätzliche Attribute sind möglicherweise bereits in der Exchange-Hybrid-Rückschreiben enthalten. Andern falls nicht, sollten sie eingeschlossen werden. 
   - msExchBlockedSendersHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.
   - msExchSafeRecipientsHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.
   - msExchSafeSendersHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.

2. Wenn sich das Quellpostfach auf LitigationHold befindet und die Größe des Quellpostfachs "Wiederherstellbare Elemente" größer als die Standardgröße der Datenbank (30 GB) ist, wird das Verschieben nicht fortgesetzt, da das Zielkontingent kleiner als die Größe des Quellpostfachs ist. Sie können das MailUser-Zielobjekt so aktualisieren, dass die ELC-Postfachflags von der Quellumgebung zum Ziel verschoben werden. Dadurch wird das Zielsystem ausgelöst, um das Kontingent von MailUser auf 100 GB zu erweitern, sodass der Wechsel zum Ziel ermöglicht wird. Diese Anweisungen funktionieren nur für Hybrididentität mit Azure AD Connect, da die Befehle zum Stempeln der ELC-Flags nicht für Mandantenadministratoren verfügbar gemacht werden.

    >[!Note]
    > BEISPIEL – AS IS, NO WARRANTY<br/>Dieses Skript setzt eine Verbindung mit dem Quellpostfach (um Quellwerte zu erhalten) und dem lokalen Active Directory-Ziel (zum Stempeln des ADUser-Objekts) voraus. Wenn für die Quelle ein Rechtsstreit oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto ein.  Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Nicht hybride Ziel-Mandanten können das Kontingent für den Ordner "Wiederherstellbare Elemente" für die MailUsers vor der Migration ändern, indem Sie den folgenden Befehl ausführen, um das Litigation Hold für das MailUser-Objekt zu aktivieren und das Kontingent auf 100 GB zu erhöhen: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Beachten Sie, dass dies für Mandanten in Hybrid nicht funktioniert.

4. Benutzer in der Zielorganisation müssen mit entsprechenden Exchange Online-Abonnements lizenziert werden, die für die Organisation gelten. Sie können eine Lizenz vor dem Verschieben eines Postfachs anwenden, aber nur, wenn das Ziel-MailUser ordnungsgemäß mit ExchangeGUID und Proxyadressen eingerichtet ist. Das Anwenden einer Lizenz vor dem Anwenden der ExchangeGUID führt zu einem neuen Postfach, das in der Zielorganisation bereitgestellt wird. 

    > [!Note]
    > Wenn Sie eine Lizenz auf ein Mailbox- oder MailUser-Objekt anwenden, werden alle SMTP-Typproxyaddresses bereinigunget, um sicherzustellen, dass nur überprüfte Domänen im Exchange EmailAddresses-Array enthalten sind. 

5. Sie müssen sicherstellen, dass das Ziel-MailUser-Ziel keine vorherige ExchangeGuid-Version hat, die nicht mit der ExchangeGuid-Quelle übereinstimmen kann. Dies kann auftreten, wenn die Ziel-MEU zuvor für Exchange Online lizenziert und ein Postfach bereitgestellt wurde. Wenn das Ziel-MailUser zuvor für exchangeGuid lizenziert wurde oder über eine ExchangeGuid verfügte, die nicht mit der ExchangeGuid-Quelle übereinstimmen, müssen Sie eine Bereinigung der Cloud-MEU durchführen. Für diese Cloud-MEUs können Sie `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` ausführen.  

    > [!Caution]
    > Dieser Vorgang ist unwiderruflich. Wenn das Objekt über ein softDeleted-Postfach verfügt, kann es nach diesem Zeitpunkt nicht wiederhergestellt werden. Nach dem Löschen können Sie jedoch das richtige ExchangeGuid-Objekt mit dem Zielobjekt synchronisieren, und MRS verbindet das Quellpostfach mit dem neu erstellten Zielpostfach. (Referenz-EHLO-Blog zum neuen Parameter.)  

    Suchen Sie Objekte, die zuvor Postfächer waren, mithilfe dieses Befehls.

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

    Löschen Sie das soft-deleted-Postfach mit diesem Befehl.

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

Mandantenübergreifende Exchange-Postfachmigrationen werden als Migrationsbatches übermittelt, die vom Ziel mandanten initiiert wurden. Dies ähnelt der Art und Weise, wie Migrationsbatches beim Einsteigen bei der Migration von lokalen Exchange zu Microsoft 365 funktionieren. 

### <a name="create-migration-batches"></a>Erstellen von Migrationsbatches

Im Folgenden finden Sie ein Beispiel für ein Migrationsbatch-Cmdlet zum Starten von Bewegungen.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Die E-Mail-Adresse in der CSV-Datei muss die im Ziel-Mandant angegebene Adresse sein, nicht der Quell-Mandant.

Die Migrationsbatchübermittlung wird auch vom neuen Exchange Admin Center unterstützt, wenn die mandantenübergreifende Option ausgewählt wird.

#### <a name="update-on-premises-mailusers"></a>Aktualisieren von lokalen MailUsers

Sobald das Postfach von Quelle zu Ziel verschoben wird, sollten Sie sicherstellen, dass die lokalen E-Mail-Benutzer, sowohl Source als auch Target, mit dem neuen targetAddress aktualisiert werden. In den Beispielen ist die targetDeliveryDomain, die in der Bewegung verwendet wird, **contoso.onmicrosoft.com**. Aktualisieren Sie die E-Mail-Benutzer mit dieser targetAddress.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Müssen wir RemoteMailboxen nach dem Verschieben lokal in der Quelle aktualisieren?**

Ja, Sie sollten die targetAddress (RemoteRoutingAddress/ExternalEmailAddress) der lokalen Quellbenutzer aktualisieren, wenn das Quell-Mandantenpostfach in den Ziel mandanten verschoben wird.  Während das E-Mail-Routing den Empfehlungen für mehrere E-Mail-Benutzer mit unterschiedlichen targetAddresses folgen kann, müssen Frei/Gebucht-Suchen für E-Mail-Benutzer auf den Speicherort des Postfachbenutzers zielen. Frei/Gebucht-Suchen verfolgen nicht mehrere Umleitungen. 

**Migrieren Teams-Besprechungen mandantenübergreifende?**  

Die Besprechungen werden jedoch von der Teams-Besprechungs-URL nicht aktualisiert, wenn elemente mandantenübergreifende Migriert werden. Da die URL im Ziel-Mandant ungültig ist, müssen Sie die Teams-Besprechungen entfernen und neu erstellen.

**Migriert der Inhalt des Teams-Chatordners mandantenübergreifende Inhalte?**  

Nein, der Inhalt des Teams-Chatordners wird nicht mandantenübergreifende migriert.  

**Wie kann ich nur mandantenübergreifende Und nicht meine Onboarding- und Off-Boarding-Bewegungen sehen?**

Verwenden Sie den `-flags` Parameter. Hier ein Beispiel.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Können Sie Beispielskripts zum Kopieren von Attributen bereitstellen, die in Tests verwendet werden?**

> [!Note]
> BEISPIEL – AS IS, NO WARRANTY<br/>Dieses Skript setzt eine Verbindung mit dem Quellpostfach (zum Abspeichern von Quellwerten) und den lokalen Active Directory-Domänendiensten (zum Stempeln des ADUser-Objekts) voraus. Wenn für die Quelle ein Rechtsstreit oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto ein.  Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.

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
**Wie greifen wir auf Outlook an Tag 1 zu, nachdem das Verwendungspostfach verschoben wurde?**

Da nur ein Mandant eine Domäne besitzen kann, wird die frühere primäre SMTPAddress dem Benutzer im Ziel-Mandant nicht zugeordnet, wenn die Postfach verschieben abgeschlossen ist. nur die Domänen, die dem neuen Mandanten zugeordnet sind. Outlook verwendet den neuen BENUTZER-UPN, um sich beim Dienst zu authentifizieren, und das Outlook-Profil erwartet, dass das primäre SMTPAddress-Legacy für das Postfach im Zielsystem zu finden ist. Da sich die Legacyadresse nicht im Zielsystem befindet, wird im Outlook-Profil keine Verbindung hergestellt, um das neu verschobene Postfach zu finden. 

Für diese anfängliche Bereitstellung müssen Benutzer ihr Profil mit dem neuen UPN, der primären SMTP-Adresse und dem erneuten Synchronisieren von OST-Inhalten neu erstellen. 

> [!Note]
> Planen Sie entsprechend, während Sie Ihre Benutzer für den Abschluss batchen. Sie müssen die Netzwerkauslastung und -kapazität berücksichtigen, wenn Outlook-Clientprofile erstellt und nachfolgende OST- und OAB-Dateien auf Clients heruntergeladen werden. 
 
**In welchen Exchange-Rollen muss ich Mitglied sein, um eine mandantenübergreifende Bewegung einrichten oder abschließen zu können?**
 
Es gibt eine Matrix von Rollen, die auf der Annahme delegierter Aufgaben beim Ausführen einer Postfach verschieben basieren. Derzeit sind zwei Rollen erforderlich:  

- Die erste Rolle ist eine einmal durchgeführte Einrichtungsaufgabe, die die Autorisierung des Verschiebens von Inhalten in Oder aus Ihrer Mandanten-/Organisationsgrenze etabliert. Da das Verschieben von Daten aus Ihrem Organisationssteuerelement für alle Unternehmen ein entscheidendes Problem ist, haben wir uns mit der höchsten zugewiesenen Rolle des Organisationsadministrators (OrgAdmin) entschieden. Diese Rolle muss eine neue OrganizationRelationship ändern oder einrichten, die die -MailboxMoveCapability mit der Remoteorganisation definiert. Nur orgAdmin kann die Einstellung MailboxMoveCapability ändern, während andere Attribute des OrganizationRelationhip vom Verbundfreigabeadministrator verwaltet werden können. 
 
- Die Rolle der Ausführung der tatsächlichen Verschiebebefehle kann an eine Funktion auf niedrigerer Ebene delegiert werden. Der Rolle des Verschiebens von Postfächern wird die Möglichkeit zugewiesen, Postfächer mithilfe des Parameters in oder aus der Organisation zu `-RemoteTenant` verschieben.  

**Wie wird gezielt die SMTP-Adresse für targetAddress (TargetDeliveryDomain) für das konvertierte Postfach (in Die MailUser-Konvertierung) ausgewählt?**
 
Exchange-Postfach verschiebt mithilfe von MRS die targetAddress für das ursprüngliche Quellpostfach beim Konvertieren in ein MailUser-Objekt durch Abgleichen einer E-Mail-Adresse (proxyAddress) für das Zielobjekt. Der Prozess übernimmt den -TargetDeliveryDomain-Wert, der an den Befehl move übergeben wurde, und sucht dann auf der Zielseite nach einem übereinstimmenden Proxy für diese Domäne. Wenn eine Übereinstimmung gefunden wird, wird die übereinstimmende proxyAddress verwendet, um das ExternalEmailAddress (targetAddress) für das konvertierte Postfachobjekt (jetzt MailUser) zu setzen.
 
**Wie werden Postfachberechtigungen übergangen?**

Postfachberechtigungen umfassen Senden im Auftrag von und Postfachzugriff: 

- Send On Behalf Of (AD:publicDelegates) speichert den DN von Empfängern mit Zugriff auf das Postfach eines Benutzers als Stellvertretung. Dieser Wert wird in Active Directory gespeichert und wird derzeit nicht als Teil des Postfachübergangs verschoben. Wenn für das Quellpostfach publicDelegates festgelegt ist, müssen Sie die öffentlichenDelegates für das Zielpostfach erneut aufrüsten, sobald die Konvertierung "MEU in Mailbox" in der Zielumgebung abgeschlossen ist, indem Sie `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` ausführen. 
 
- Postfachberechtigungen, die im Postfach gespeichert sind, werden mit dem Postfach verschoben, wenn sowohl der Prinzipal als auch der Stellvertreter in das Zielsystem verschoben werden. Beispielsweise wird dem Benutzer TestUser_7 vollzugriff auf die Postfachdatenbank TestUser_8 Mandanten SourceCompany.onmicrosoft.com. Nachdem die Postfach verschieben abgeschlossen TargetCompany.onmicrosoft.com, werden die gleichen Berechtigungen im Zielverzeichnis eingerichtet. Beispiele, *die Get-MailboxPermission* für TestUser_7 quell- und ziel mandanten verwenden, sind unten dargestellt. Exchange-Cmdlets wird quell- und zielpräfixiert. 
 
Hier sehen Sie ein Beispiel für die Ausgabe der Postfachberechtigung vor einer Bewegung. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Hier sehen Sie ein Beispiel für die Ausgabe der Postfachberechtigung nach dem Verschieben. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Mandantenübergreifende Postfach- und Kalenderberechtigungen werden NICHT unterstützt. Sie müssen Prinzipale und Stellvertretung in konsolidierten Verschiebebatches organisieren, damit diese verbundenen Postfächer gleichzeitig vom Quell-Mandanten umgewechselt werden. 

**Welcher X500-Proxy sollte den Ziel-MailUser-Proxyadressen hinzugefügt werden, um die Migration zu ermöglichen?**  

Für die mandantenübergreifende Postfachmigration muss der LegacyExchangeDN-Wert des Quellpostfachobjekts als x500-E-Mail-Adresse für das MailUser-Zielobjekt gestempelt werden.  

Beispiel:  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> Zusätzlich zu diesem X500-Proxy müssen Sie alle X500-Proxys aus dem Postfach in der Quelle in das Postfach im Ziel kopieren.  

**Wo beginne ich mit der Problembehandlung, wenn Bewegungen nicht funktionieren?**  

Starten Sie, indem Sie VerifySetup.ps1 Skript auf [GitHub ausführen](https://github.com/microsoft/cross-tenant/releases/tag/Preview) und die Ausgabe überprüfen.

Im Folgenden finden Sie ein Beispiel für die Ausführung VerifySetup.ps1 für den Ziel-Mandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier ist ein eExample zum Ausführen von VerifySetup.ps1 für den Quell-Mandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**Kann der Quell- und Ziel-Mandant denselben Domänennamen verwenden?**  

Nein. Die Quell- und Ziel-Mandantendomänennamen müssen eindeutig sein. Beispielsweise eine Quelldomäne von contoso.com und die Zieldomäne von fourthcoffee.com.

**Werden freigegebene Postfächer verschoben und funktionieren weiterhin?**

Ja, wir behalten jedoch nur die Speicherberechtigungen wie in den folgenden Artikeln beschrieben bei:

- [Microsoft Docs | Verwalten von Berechtigungen für Empfänger in Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft Support | Erteilen von Exchange- und Outlook-Postfachberechtigungen in Office 365](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Ist Azure Key Vault erforderlich und wann werden Transaktionen ausgeführt?**  

Ja, ein Azure-Abonnement ist erforderlich, um Key Vault zum Speichern des Zertifikats zum Autorisieren der Migration zu verwenden. Im Gegensatz zu Onboardingmigrationen, die den Benutzernamen & kennwort für die Authentifizierung bei der Quelle verwenden, verwenden mandantenübergreifende Postfachmigrationen OAuth und dieses Zertifikat als Geheim-/Anmeldeinformationen. Der Zugriff auf den Schlüsseltresor muss während aller Postfachmigrationen beibehalten werden, da am Anfang und am Ende der Migration einmal darauf zugegriffen wird, sowie einmal alle 24 Stunden während inkrementeller Synchronisierungszeiten. Details zur AKV-Kostenkalkulation finden Sie [hier]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).  

**Gibt es Empfehlungen für Batches?**  

Nicht mehr als 2.000 Postfächer pro Batch. Es wird dringend empfohlen, Batches zwei Wochen vor dem Fälligkeitsdatum zu übermitteln, da während der Synchronisierung keine Auswirkungen auf die Endbenutzer zu sehen sind. Wenn Sie Anleitungen für Postfächer über 50.000 benötigen, können Sie sich an die Engineering Feedback Distribution List unter crosstenantmigrationpreview@service.microsoft.com.

**Was passiert, wenn ich die Dienstverschlüsselung mit dem Kundenschlüssel verwende?**

Das Postfach wird vor dem Verschieben entschlüsselt. Stellen Sie sicher, dass der Kundenschlüssel im Ziel-Mandant konfiguriert ist, wenn er weiterhin erforderlich ist. Weitere [Informationen](../compliance/customer-key-overview.md) finden Sie hier.  

**Wie ist die geschätzte Migrationszeit?**

Um Die Migration zu planen, [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) enthält die hier gezeigte Tabelle die Richtlinien, wann Massenpostfachmigrationen oder einzelne Migrationen abgeschlossen werden sollen. Diese Schätzungen basieren auf einer Datenanalyse früherer Kundenmigrationen. Da jede Umgebung eindeutig ist, kann die genaue Migrationsgeschwindigkeit variieren.  

Denken Sie daran, dass sich dieses Feature derzeit in der Vorschau befindet und die SLA und alle anwendbaren ServiceLevels während des Vorschaustatus dieses Features nicht auf Leistungs- oder Verfügbarkeitsprobleme angewendet werden.

## <a name="known-issues"></a>Bekannte Probleme  

-  **Problem: Automatisch erweiterte Archive können nicht migriert werden.** Das mandantenübergreifende Migrationsfeature unterstützt Migrationen des primären Und Archivpostfachs für einen bestimmten Benutzer. Wenn der Benutzer in der Quelle jedoch über ein automatisch erweitertes Archiv verfügt , d. h. mehr als ein Archivpostfach, kann das Feature die zusätzlichen Archive nicht migrieren und sollte fehlschlagen.

- **Problem: Cloud MailUsers mit nicht im Besitz des SmtpproxysAddress Block MRS verschiebt hintergrund.** Beim Erstellen von MailUser-Ziel-Mandantenobjekten müssen Sie sicherstellen, dass alle SMTP-Proxyadressen zur Ziel mandantenorganisation gehören. Wenn ein SMTP-proxyAddress für den Ziel-E-Mail-Benutzer vorhanden ist, der nicht zum lokalen Mandanten gehört, wird die Konvertierung von MailUser in Mailbox verhindert. Dies liegt an der Zusicherung, dass Postfachobjekte nur E-Mails von Domänen senden können, für die der Mandant autorisierend ist (vom Mandanten beanspruchte Domänen): 

   - Wenn Sie Benutzer lokal mit Azure AD Connect synchronisieren, stellen Sie lokale MailUser-Objekte mit ExternalEmailAddress bereit, die auf den Quell mandanten verweisen, in dem das Postfach vorhanden ist (laran@contoso.onmicrosoft.com), und Sie stempeln die PrimarySMTPAddress als Domäne, die sich im Ziel mandanten befindet (Lara.Newton@northwind.com). Diese Werte werden mit dem Mandanten synchronisiert, und ein entsprechender E-Mail-Benutzer ist bereitgestellt und für die Migration bereit. Hier wird ein Beispielobjekt gezeigt.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Die *contoso.onmicrosoft.com* adresse *ist nicht* im EmailAddresses /proxyAddresses-Array vorhanden.

- **Problem: MailUser-Objekte mit "externen" primären SMTP-Adressen werden geändert/auf "interne" vom Unternehmen beanspruchte Domänen zurückgesetzt**

   MailUser-Objekte sind Zeiger auf nicht lokale Postfächer. Bei mandantenübergreifenden Postfachmigrationen verwenden wir MailUser-Objekte, um entweder das Quellpostfach (aus Sicht der Zielorganisation) oder das Zielpostfach (aus der Perspektive der Quellorganisation) zu repräsentieren. Die MailUsers verfügen über eine ExternalEmailAddress (targetAddress), die auf die SMTP-Adresse des tatsächlichen Postfachs (ProxyTest@fabrikam.onmicrosoft.com) und der primärenSMTP-Adresse verweist, die die angezeigte SMTP-Adresse des Postfachbenutzers im Verzeichnis darstellt. Einige Organisationen entscheiden sich dafür, die primäre SMTP-Adresse als externe SMTP-Adresse und nicht als Adresse im Besitz des lokalen Mandanten (z. B. fabrikam.com anstatt als contoso.com).  Nachdem jedoch ein Exchange-Dienstplanobjekt über Lizenzierungsvorgänge auf das MailUser-Objekt angewendet wurde, wird die primäre SMTP-Adresse so geändert, dass sie von der lokalen Organisation (contoso.com) überprüft wird. Es gibt zwei mögliche Gründe:
   
   - Wenn ein Exchange-Dienstplan auf einen MailUser angewendet wird, beginnt der Azure AD-Prozess, die Proxybereinigung zu erzwingen, um sicherzustellen, dass die lokale Organisation keine E-Mails, Spoof- oder E-Mails von einem anderen Mandanten senden kann. Jede SMTP-Adresse für ein Empfängerobjekt mit diesen Dienstplänen wird entfernt, wenn die Adresse nicht von der lokalen Organisation überprüft wird. Wie im Beispiel wird die Fabikam.com-Domäne nicht vom contoso.onmicrosoft.com-Mandanten überprüft, sodass die Fabrikam.com entfernt wird. Wenn Sie diese externe Domäne auf MailUser beibehalten möchten, entweder vor der Migration oder nach der Migration, müssen Sie Ihre Migrationsprozesse so ändern, dass Lizenzen nach Abschluss des Verschiebens oder vor dem Verschieben gestreift werden, um sicherzustellen, dass die Benutzer das erwartete externe Branding angewendet haben. Sie müssen sicherstellen, dass das Postfachobjekt ordnungsgemäß lizenziert ist, um keinen Einfluss auf den E-Mail-Dienst zu haben.<br/><br/>Hier wird ein Beispielskript zum Entfernen der Dienstpläne für einen MailUser im Contoso.onmicrosoft.com mandanten angezeigt.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Die Ergebnisse der zugewiesenen ServicePlans werden hier angezeigt.

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
 
       PrimarySMTPAddress des Benutzers wird nicht mehr gestrubbt. Die fabrikam.com befindet sich nicht im Besitz des contoso.onmicrosoft.com Mandanten und bleibt als primäre SMTP-Adresse im Verzeichnis erhalten.

       Hier ein Beispiel.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Wenn msExchRemoteRecipientType auf 8 (DeprovisionMailbox) festgelegt ist, werden für lokale MailUser, die zum Zielmandanten migriert werden, von der Proxybereinigungslogik in Azure nicht besitzereigene Domänen entfernt und der primäreSMTP auf eine eigene Domäne zurückgesetzt. Durch Löschen von msExchRemoteRecipientType im lokalen MailUser wird die Proxybereinigungslogik nicht mehr angewendet. <br/><br>Nachfolgend finden Sie den vollständigen Satz möglicher Dienstpläne, die Exchange Online enthalten.

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
   | Einblicke von MyAnalytics                           |
   | Erweiterte Microsoft 365-Überwachung                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (Vollversion)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender für Office 365 (Plan 1)    |
   | Microsoft Defender für Office 365 (Plan 2)    |
   | Office 365 Privileged Access Management           |
   | Premium-Verschlüsselung in Office 365                  |
