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
ms.openlocfilehash: 237d47502d28ec43978cef2c16e049ac9e90d7b1
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040556"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Mandantenübergreifende Postfachmigration (Vorschau)

Wenn ein Exchange -Online-Mandant Postfächer in einen anderen Mandanten im gleichen Exchange Online-Dienst verschieben musste, musste er sie vollständig auf die lokale Version aus offboarden und dann in einen neuen Mandanten integrieren. Mit dem neuen feature für die mandantenübergreifende Postfachmigration können Mandantenadministratoren sowohl in Quell- als auch in Ziel-Mandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben. Dadurch müssen keine Off-Board- und Onboardingpostfächer mehr verwendet werden.

In der Regel benötigen Sie bei Fusionen oder Abgängen die Möglichkeit, Benutzer und Inhalte in einen neuen Mandanten zu verschieben. Wenn der Zieladministrator die Migration ausgeführt, wird dies als "Pull-Move" bezeichnet, ähnlich wie bei lokalen Migrationen mit Cloud-Onboarding-Migrationen.

Mandantenübergreifende Verschieben von Exchange-Postfächern werden von Mandantenadministratoren vollständig selbstverwendet und verwenden bekannte Schnittstellen, die in die größeren Workflows geskriptet werden können, die für den Übergang von Benutzern zu ihrer neuen Organisation erforderlich sind. Administratoren können das Über die Verwaltungsrolle "Postfächer verschieben" verfügbare `New-MigrationBatch` Cmdlet verwenden, um mandantenübergreifende Verschieben auszuführen. Der Verschiebevorgang umfasst Mandantenautorisierungsprüfungen während der Postfachsynchronisierung und -finalisierung. 
 
Benutzer, die migrieren, müssen im Exchange Online-Ziel-Mandantensystem als MailUsers vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um die mandantenübergreifenden Migrationen zu ermöglichen. Für Benutzer, die im Ziel mandanten nicht ordnungsgemäß eingerichtet sind, kann das System nicht ausgeführt werden.  

Nach Abschluss der Verschiebe wird das Quellsystempostfach in "MailUser" konvertiert, und die Zieladresse (in Exchange als "ExternalEmailAddress" angezeigt) wird mit der Routingadresse an den Ziel mandanten gestempelt. Bei diesem Prozess bleibt mailUser der Vorgängerzeit im Quell mandanten erhalten und ermöglicht eine Bestimmte Zeit der Koexistenz und des E-Mail-Routings. Wenn Geschäftsprozesse dies zulassen, kann der Quell mandant die Quelle "MailUser" entfernen oder in einen E-Mail-Kontakt konvertieren. 

Mandantenübergreifende Migrationen von Exchange-Postfächern werden nur für Mandanten in Hybrid- oder Cloudbereitstellungen oder in einer beliebigen Kombination der beiden Postfächer unterstützt.

Dieser Artikel beschreibt den Prozess für mandantenübergreifende Postfachver verschiebt und enthält Anleitungen zum Vorbereiten von Quell- und Ziel-Mandanten für die Inhaltsver verschieben.  

## <a name="preparing-source-and-target-tenants"></a>Vorbereiten von Quell- und Ziel mandanten

Das Feature für die mandantenübergreifende Migration von Exchange-Postfächern erfordert die Autorisierung und Dierung für mandantenübergreifende Migrationen. Mithilfe der Azure Enterprise-Anwendungs- und Key Vault-Speicherlösungen können Mandantenadministratoren jetzt sowohl die Autorisierung als auch die Scoping von Exchange Online-Postfachmigrationen von einem Mandanten zu einem anderen verwalten. Mandantenübergreifende Postfachbewegungen unterstützen ein Einladungs- und Zustimmungsmodell zum Einrichten einer Azure Active Directory (Azure AD)-Anwendung, die für die Authentifizierung zwischen einem Mandantenpaar verwendet wird. Zusätzliche Komponenten wie eine Organisationsbeziehung und ein Migrationsendpunkt sind ebenfalls erforderlich.

Dieser Abschnitt enthält weder die spezifischen Schritte, die zum Vorbereiten der MailUser-Benutzerobjekte im Zielverzeichnis erforderlich sind, noch den Beispielbefehl zum Übermitteln eines Migrationsbatches. Informationen hierzu finden Sie unter "Vorbereiten [von Zielbenutzerobjekten für](#prepare-target-user-objects-for-migration) die Migration".

## <a name="prerequisites"></a>Voraussetzungen

Das feature für die mandantenübergreifende Postfachver verschieben erfordert [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) eine mandantenpaarspezifische Azure-Anwendung, um das Zertifikat/den geheimen Schlüssel sicher zu speichern und darauf zu zugreifen, das verwendet wird, um die Postfachmigration von einem Mandanten zum anderen zu authentifizieren und zu autorisieren, und alle Anforderungen für die Freigabe von Zertifikaten/Geheimnissen zwischen Mandanten zu entfernen. 

Bevor Sie beginnen, stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um Azure Key Vault, die Move Mailbox-Anwendung, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren. In der Regel verfügt der globale Administrator über die Berechtigung, alle Konfigurationsschritte durchzuführen.

Darüber hinaus sind E-Mail-aktivierte Sicherheitsgruppen im Quell mandanten erforderlich, bevor Setup ausgeführt wird. Diese Gruppen werden verwendet, um die Liste der Postfächer zu bereichern, die vom Quell-Mandanten (oder manchmal auch als Ressourcen-Mandant bezeichnet) zum Ziel mandanten verschoben werden können. Dadurch kann der Quell-Mandanten-Administrator die bestimmte Gruppe von Postfächern einschränken oder einschränken, die verschoben werden müssen, um zu verhindern, dass unbeabsichtigte Benutzer migriert werden. Geschachtelte Gruppen werden nicht unterstützt.

Sie müssen auch mit Ihrem vertrauenswürdigen Partnerunternehmen kommunizieren (mit dem Sie Postfächer verschieben), um die Microsoft 365-Mandanten-ID zu erhalten. Diese Mandanten-ID wird im Feld "Organisationsbeziehung" `DomainName` verwendet.

Um die Mandanten-ID eines Abonnements zu erhalten, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klicken Sie auf das Kopiersymbol für die Mandanten-ID-Eigenschaft, um sie in die Zwischenablage zu kopieren.

Hier sehen Sie, wie der Prozess funktioniert.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Mandantenvorbereitung für die Postfachmigration.":::

[Sehen Sie sich eine größere Version dieses Bilds an.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Vorbereiten von Mandanten

Auf hoher Ebene werden die folgenden Konfigurationsaktionen beim Ausführen der Setupskripts ausgeführt.

Bereiten Sie den Ziel mandanten vor:

1. Wenn keine vorhandene Azure-Ressourcengruppe bereitgestellt wird, wird ein neues (SCRIPT) erstellt.
2. Wenn kein vorhandener Key Vault bereitgestellt wird, wird ein neues (SCRIPT) erstellt.
3. Für die Office 365 Exchange Online-Postfachmigrationsanwendung (SCRIPT) wird eine neue Zugriffsrichtlinie erstellt.
4. Es wird ein neues Zertifikat erstellt (oder ein vorhandenes, falls angegeben), das den geheimen Schlüssel für die Migrationsanwendung (SCRIPT) enthält.
5. Eine neue Azure AD-Anwendung wird erstellt (SCRIPT).
6. Das Zertifikat/der geheime Schlüssel wird in die Migrationsanwendung (SCRIPT) hochgeladen.
7. Berechtigungen für die Postfachmigration werden der Anwendung (SCRIPT) zugewiesen.
8. Das Bereitstellungsskript wird angehalten, bis der Zieladministrator der eigenen Anwendung (SCRIPT) zuwilligt.
9. Der Zieladministrator des Mandanten ist mit den berechtigungen einverstanden, die der Anwendung erteilt werden (MANUAL).
10. Es wird eine Organisationsbeziehung mit dem Ziel mandanten (SCRIPT) erstellt.
11. Ein Migrationsendpunkt wird erstellt, um Postfächer an den Ziel mandanten (SCRIPT) zu ziehen.

Bereiten Sie den Quell mandanten vor:

1. Der Quell-Mandanten-Administrator akzeptiert die Zustimmung zur Einladung der Postfachmigrationsanwendung vom Ziel-Mandanten (MANUAL).
2. Der Quell-Mandantenadministrator erstellt eine E-Mail-aktivierte Sicherheitsgruppe in ihrem Mandanten, die die Liste der Postfächer enthält, die von der Migrationsanwendung verschoben werden dürfen (MANUAL).
3. Es wird eine Organisationsbeziehung mit dem Ziel mandanten erstellt, in der angegeben wird, dass die Postfachmigrationsanwendung für die OAuth-Überprüfung verwendet werden soll, um die Verschiebenanforderung (SCRIPT) zu akzeptieren.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Schritt-für-Schritt-Anleitungen für den Zieladministrator des Mandanten

1. Laden Sie das SetupCrossTenantRelationshipForTargetTenant.ps1 für das Setup des Ziel mandanten aus dem [GitHub-Repository herunter.](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 
2. Speichern Sie das Skript (SetupCrossTenantRelationshipForTargetTenant.ps1) auf dem Computer, von dem aus Sie das Skript ausführen.
3. Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Exchange Online-Ziel-Mandanten. Stellen Sie erneut sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um den Azure Key Vault-Speicher und das Zertifikat, die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.
4. Ändern Sie das Dateiordnerverzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Ihrer Remote-PowerShell-Sitzung befindet.
5. Führen Sie das Skript mit den folgenden Parametern und Werten aus.

    | Parameter | Wert | Erforderlich oder optional
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Ziel-Mandantendomäne, z. B. \. contoso-onmicrosoft.com. | Erforderlich |
    | -ResourceTenantDomain                       | Quell-Mandantendomäne, z. B. fabrikam \. onmicrosoft.com. | Erforderlich |
    | -ResourceTenantAdminEmail                   | Die E-Mail-Adresse des Quell-Mandantenadministrators. Dies ist der Quell-Mandantenadministrator, der der Verwendung der vom Zieladministrator gesendeten Postfachmigrationsanwendung zuwilligt. Dies ist der Administrator, der die E-Mail-Einladung für die Anwendung erhält. | Erforderlich |
    | -ResourceTenantId                           | Quell-Mandantenorganisations-ID (GUID). | Erforderlich |
    | -SubscriptionId                             | Das Azure-Abonnement, das zum Erstellen von Ressourcen verwendet werden soll. | Erforderlich |
    | -ResourceGroup                              | Azure-Ressourcengruppenname, der den Key Vault enthält oder enthalten wird. | Erforderlich |
    | -KeyVaultName                               | Azure Key Vault-Instanz, in der das Zertifikat/der geheime Schlüssel der Postfachmigrationsanwendung gespeichert wird. | Erforderlich |
    | -CertificateName                            | Zertifikatname beim Generieren oder Suchen nach Zertifikaten im Schlüsseltresor. | Erforderlich |
    | -CertificateSubject                         | Azure Key Vault-Zertifikat-Subject-Name, z. B. CN=contoso_fabrikam. | Erforderlich |
    | -ExistingApplicationId                      | E-Mail-Migrationsanwendung, die verwendet werden soll, wenn bereits eine erstellt wurde. | Optional |
    | -AzureAppPermissions                        | Die Berechtigungen, die für die Postfachmigrationsanwendung erforderlich sind, z. B. Exchange oder MSGraph (Exchange zum Verschieben von Postfächern, MSGraph für die Verwendung dieser Anwendung zum Senden einer Einladung zum Zustimmungslink an den Ressourcen-Mandanten). | Erforderlich |
    | -UseAppAndCertGeneratedForSendingInvitation | Parameter für die Verwendung der Anwendung, die für die Migration zum Senden einer Einladung zum Zustimmungslink an den Quell-Mandantenadministrator erstellt wurde. Wenn nicht angegeben, werden die Anmeldeinformationen des Zieladministrators aufgefordert, eine Verbindung mit dem Azure-Einladungs-Manager herzustellen und die Einladung als Zieladministrator zu senden. | Optional |
    | -KeyVaultAuditStorageAccountName            | Das Speicherkonto, in dem die Überwachungsprotokolle von Key Vault gespeichert werden. | Optional |
    | -KeyVaultAuditStorageResourceGroup          | Die Ressourcengruppe, die das Speicherkonto zum Speichern von Key Vault-Überwachungsprotokollen enthält. | Optional |
    ||||

    >[!Note]
    > Stellen Sie sicher, dass Sie das Azure AD -PowerShell-Modul installiert haben, bevor Sie die Skripts ausführen. Installationsschritte ![ finden ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) Sie hier.

6. Das Skript hält an und fordert Sie auf, die während dieses Vorgangs erstellte Exchange-Postfachmigrationsanwendung zu akzeptieren oder ihr zuzuwilligen. Hier ein Beispiel.

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

7. In der Remote-PowerShell-Sitzung wird eine URL angezeigt. Kopieren Sie den Link, der für Ihre Mandantengewilligung bereitgestellt wurde, und fügen Sie ihn in einen Webbrowser ein.

8. Melden Sie sich mit Ihren globalen Administratoranmeldeinformationen an. Wenn der folgende Bildschirm angezeigt wird, wählen Sie **"Annehmen" aus.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogfeld &quot;Berechtigungen akzeptieren&quot;":::

9. Wechseln Sie zurück zur Remote-PowerShell-Sitzung, und geben Sie die EINGABETASTE ein, um den Vorgang fortzufahren.

10. Das Skript konfiguriert die verbleibenden Setupobjekte. Hier ein Beispiel.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Die Einrichtung des Zieladministrators ist nun abgeschlossen!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Schritt-für-Schritt-Anleitungen für den Quell-Mandanten-Administrator

1.  Melden Sie sich bei Ihrem Postfach als "-ResourceTenantAdminEmail" an, das vom Zieladministrator während des Setups angegeben wurde. Suchen Sie die E-Mail-Einladung vom Ziel-Mandanten, und wählen Sie dann die Schaltfläche **"Erste Schritte"** aus.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogfeld &quot;Eingeladen&quot;":::

2. Wählen Sie **"Annehmen"** aus, um die Einladung zu akzeptieren.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialogfeld zum Akzeptieren von Berechtigungen":::

   > [!NOTE]
   > Wenn Sie diese E-Mail nicht erhalten oder nicht finden können, wurde dem Zielmandantadministrator eine direkte URL bereitgestellt, die Ihnen zum Annehmen der Einladung zur Verfügung gestellt werden kann. Die URL sollte in der Aufzeichnung der Remote-PowerShell-Sitzung des Ziel-Mandantenadministrators enthalten sein.

3. Erstellen Sie im Microsoft 365 Admin Center oder in einer Remote-PowerShell-Sitzung eine oder mehrere E-Mail-aktivierte Sicherheitsgruppen, um die Liste der Postfächer zu steuern, die der Ziel mandant vom Quell mandanten zum Ziel mandanten ziehen (verschieben) darf. Sie müssen diese Gruppe nicht im Voraus auffüllen, aber es muss mindestens eine Gruppe bereitgestellt werden, um die Setupschritte (Skript) auszuführen. Schachtelgruppen werden nicht unterstützt. 

4. Laden Sie das SetupCrossTenantRelationshipForResourceTenant.ps1 für das Quell-Mandanten-Setup aus dem GitHub-Repository hier herunter: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) . 

5. Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Quell mandanten mit Ihren Exchange-Administratorberechtigungen. Globale Administratorberechtigungen sind aufgrund des Erstellungsprozesses der Azure-Anwendung nicht erforderlich, um den Quell-Mandanten zu konfigurieren, sondern nur den Ziel-Mandanten.

6. Ändern Sie das Verzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Ihrer Remote-PowerShell-Sitzung befindet.

7. Führen Sie das Skript mit den folgenden erforderlichen Parametern und Werten aus.

    | Parameter | Wert |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | E-Mail-aktivierte Sicherheitsgruppe, die vom Quell mandanten für die Identitäten/Postfächer erstellt wurde, die sich im Bereich der Migration befinden. |
    | -ResourceTenantDomain | Quelldomänenname des Mandanten, z. B. fabrikam \. onmicrosoft.com. |
    | -ApplicationId | Azure-Anwendungs-ID (GUID) der Anwendung, die für die Migration verwendet wird. Die Anwendungs-ID ist über Ihr Azure-Portal verfügbar (Azure AD, Enterprise-Anwendungen, App-Name, Anwendungs-ID) oder in Ihrer Einladungs-E-Mail enthalten.  |
    | -TargetTenantDomain | Zieldomänenname des Mandanten, z. B. Contoso \. onmicrosoft.com. |
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

#### <a name="target-tenant"></a>Ziel mandant

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

#### <a name="source-tenant"></a>Quell mandant

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

Wenn während der Konfiguration der Quell- oder Ziel-Mandanten Fehler angezeigt werden, können Sie das Skript VerifySetup.ps1 [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ausführen und die Ausgabe überprüfen.

Hier ist ein Beispiel für die Ausführung VerifySetup.ps1 für den Ziel-Mandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier ist ein Beispiel für VerifySetup.ps1 für den Quell-Mandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Verschieben von Postfächern zurück zur ursprünglichen Quelle

Wenn ein Postfach zurück zum ursprünglichen Quell mandanten verschoben werden muss, müssen die gleichen Schritte und Skripts sowohl in neuen Quell- als auch in neuen Ziel-Mandanten ausgeführt werden. Das vorhandene Organisationsbeziehungsobjekt wird aktualisiert oder angefügt, nicht neu erstellt.

## <a name="prepare-target-user-objects-for-migration"></a>Vorbereiten von Zielbenutzerobjekten für die Migration

Benutzer, die migrieren, müssen im Ziel mandanten- und Exchange Online-System (als MailUsers) vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um die mandantenübergreifenden Migrationen zu ermöglichen. Bei Benutzern, die im Ziel mandanten nicht ordnungsgemäß eingerichtet sind, kann das System nicht ausgeführt werden. Im folgenden Abschnitt werden die Anforderungen des MailUser-Objekts für den Ziel mandanten beschrieben.

### <a name="prerequisites"></a>Voraussetzungen
  
Sie müssen sicherstellen, dass die folgenden Objekte und Attribute in der Zielorganisation festgelegt sind.  

1. Für alle Postfächer, die aus einer Quellorganisation verschoben werden, müssen Sie ein MailUser -Objekt in der Zielorganisation bereitstellen: 

   - Das Ziel-MailUser-Objekt muss über die folgenden Attribute aus dem Quellpostfach verfügen oder dem neuen Benutzerobjekt zugewiesen sein:
      - ExchangeGUID (direkter Fluss von Quelle zu Ziel) – Die Postfach-GUID muss übereinstimmen. Der Verschiebevorgang wird nicht fortgesetzt, wenn dies für das Zielobjekt nicht vorhanden ist. 
      - ArchiveGUID (direkter Fluss von Quelle zu Ziel) – Die Archiv-GUID muss übereinstimmen. Der Verschiebevorgang wird nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist. (Dies ist nur erforderlich, wenn das Quellpostfach "Archiv" aktiviert ist. 
      - LegacyExchangeDN (flow as proxyAddress, "x500: <LegacyExchangeDN> ") – Der LegacyExchangeDN muss im Ziel-MailUser als x500 vorhanden sein: proxyAddress. Die Verschiebeprozesse werden nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist. 
      - UserPrincipalName – UPN richtet sich nach der neuen Identität oder dem Zielunternehmen des Benutzers (z. B. user@northwindtraders.onmicrosoft.com). 
      - Primäre SMTPAddress – Primäre SMTP-Adresse wird an der neuen Firma des Benutzers ausgerichtet (z. B. user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser referenziert das aktuelle Postfach des Benutzers, das im Quell mandanten gehostet wird (z. B. user@contoso.onmicrosoft.com). Stellen Sie beim Zuweisen dieses Werts sicher, dass Sie auch "PrimarySMTPAddress" zugewiesen haben/sind, oder legen Sie mit diesem Wert "PrimarySMTPAddress" fest, was zu Verschiebenfehlern führen kann. 
      - Sie können keine legacy-SMTP-Proxyadressen aus dem Quellpostfach zu Ziel-MailUser hinzufügen. Sie können z. B. keine contoso.com für die E-Fabrikam.onmicrosoft.com Mandantenobjekte verwalten). Domänen sind nur einem Azure AD- oder Exchange Online-Mandanten zugeordnet.
 
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

     Beispiel für ein Quellpostfachobjekt: 

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

   - Zusätzliche Attribute sind möglicherweise bereits in der Exchange-Hybrid-Rückschreiben enthalten. Wenn nicht, sollten sie eingeschlossen werden. 
   - msExchBlockedSendersHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.
   - msExchSafeRecipientsHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.
   - msExchSafeSendersHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.

2. Wenn sich das Quellpostfach auf LitigationHold befindet und die Größe des Quellpostfachs "Wiederherstellbare Elemente" größer als der Standardwert für die Datenbank (30 GB) ist, wird das Verschieben nicht fortgesetzt, da das Zielkontingent kleiner als die Größe des Quellpostfachs ist. Sie können das Ziel-MailUser-Objekt so aktualisieren, dass die ElC-Postfachflags von der Quellumgebung auf das Ziel umgestellt werden, wodurch das Zielsystem das Kontingent von MailUser auf 100 GB erweitert und die Umstellung auf das Ziel ermöglicht. Diese Anweisungen funktionieren nur für hybride Identitäten mit Azure AD Connect, da die Befehle zum Stempeln der ELC-Flags für Mandantenadministratoren nicht verfügbar gemacht werden.

    >[!Note]
    > BEISPIEL – WIE BESS, KEINE GARANTIE<br/>Dieses Skript setzt eine Verbindung mit dem Quellpostfach (zum Erhalten von Quellwerten) und dem lokalen Active Directory des Ziels (zum Stempeln des ADUser-Objekts) voraus. Wenn für die Quelle ein Rechtsstreit oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto ein.  Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Nicht-hybride Ziel-Mandanten können das Kontingent für den Ordner "Wiederherstellbare Elemente" für die MailUsers vor der Migration ändern, indem Sie den folgenden Befehl ausführen, um das Rechtsstreitigkeiten für das MailUser -Objekt zu aktivieren und das Kontingent auf 100 GB zu `Set-MailUser -EnableLitigationHoldForMigration $TRUE` erhöhen: Beachten Sie, dass dies bei Mandanten in hybriden Hybridbereitstellungen nicht funktioniert.

4. Benutzer in der Zielorganisation müssen mit entsprechenden Exchange Online-Abonnements lizenziert werden, die für die Organisation gelten. Sie können eine Lizenz vor dem Verschieben eines Postfachs anwenden, aber nur, wenn das Ziel-MailUser-Postfach ordnungsgemäß mit ExchangeGUID und Proxyadressen eingerichtet ist. Das Anwenden einer Lizenz vor dem Anwenden der ExchangeGUID führt zu einem neuen Postfach, das in der Zielorganisation bereitgestellt wird. 

    > [!Note]
    > Wenn Sie eine Lizenz auf ein Postfach- oder ein MailUser -Objekt anwenden, werden alle PROXYAddresses des Typs SMTP entfernt, um sicherzustellen, dass nur überprüfte Domänen im Exchange EmailAddresses-Array enthalten sind. 

5. Sie müssen sicherstellen, dass das Ziel-MailUser-Konto keine vorherige ExchangeGuid hat, die nicht mit der ExchangeGuid-Quelle übereinstimmen. Dies kann vorkommen, wenn der Ziel-E-Mail-Benutzer zuvor für Exchange Online lizenziert und ein Postfach bereitgestellt hat. Wenn das Ziel-MailUser zuvor für eine ExchangeGuid lizenziert wurde oder über eine ExchangeGuid verfügte, die nicht der ExchangeGuid-Quelle entsprechen, müssen Sie eine Bereinigung der Cloud-MEU durchführen. Für diese Cloud-MEUs können Sie `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` ausführen.  

    > [!Caution]
    > Dieser Vorgang ist unwiderruflich. Wenn das Objekt über ein "softDeleted"-Postfach verfügt, kann es nach diesem Zeitpunkt nicht wiederhergestellt werden. Nach dem Löschen können Sie jedoch die richtige ExchangeGuid mit dem Zielobjekt synchronisieren, und der Postfachpostfachserver verbindet das Quellpostfach mit dem neu erstellten Zielpostfach. (Referenzieren Sie den EHLO-Blog zum neuen Parameter.)  

    Suchen Sie objekte, die zuvor Postfächer waren, indem Sie diesen Befehl verwenden.

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

Mandantenübergreifende Migrationen von Exchange-Postfächern werden als Migrationsbatches übermittelt, die vom Ziel mandanten initiiert werden. Dies ähnelt der Art und Weise, in der Migrationsbatches beim Migrieren von lokalen Exchange zu Microsoft 365 funktionieren. 

### <a name="create-migration-batches"></a>Erstellen von Migrationsbatches

Hier ist ein Beispiel für ein Migrationsbatch-Cmdlet zum Starten von Verschiebebewegungen.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Die E-Mail-Adresse in der CSV-Datei muss die im Ziel-Mandanten angegebene Adresse sein, nicht der Quell-Mandant.

Die Migrationsbatchübermittlung wird auch vom neuen Exchange Admin Center unterstützt, wenn Sie die option für mandantenübergreifende Migration auswählen.

#### <a name="update-on-premises-mailusers"></a>Aktualisieren von lokalen MailUsers

Sobald das Postfach von der Quelle zum Ziel verschoben wird, sollten Sie sicherstellen, dass die lokalen E-Mail-Benutzer( Quelle und Ziel) mit der neuen targetAddress aktualisiert werden. In den Beispielen ist die targetDeliveryDomain, die beim Verschieben verwendet wird, **contoso.onmicrosoft.com.** Aktualisieren Sie die E-Mail-Benutzer mit dieser targetAddress.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Müssen wir RemoteMailboxes nach dem Verschieben lokal in der Quelle aktualisieren?**

Ja, Sie sollten die targetAddress (RemoteRoutingAddress/ExternalEmailAddress) der lokalen Quellbenutzer aktualisieren, wenn das Quellpostfach des Mandanten zum Ziel mandanten verschoben wird.  Während das E-Mail-Routing den Empfehlungen für mehrere E-Mail-Benutzer mit unterschiedlichen TargetAddresses folgen kann, MÜSSEN Frei/Gebucht-Suchen für E-Mail-Benutzer auf den Standort des Postfachbenutzers zielen. Frei/Gebucht-Lookups verfolgen nicht mehrere Umleitungen. 

**Werden die Inhalte des Teams-Chatordners mandantenübergreifende migriert?**  

Nein, der Inhalt des Teams-Chatordners wird nicht mandantenübergreifende migriert.  

**Wie kann ich nur Bewegungen sehen, bei der es sich um mandantenübergreifende Bewegungen handelt, nicht um meine Onboarding- und Offboard-Moves?**

Verwenden Sie den `-flags` Parameter. Hier ein Beispiel.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Können Sie Beispielskripts zum Kopieren von Attributen bereitstellen, die beim Testen verwendet werden?**

> [!Note]
> BEISPIEL – WIE BESS, KEINE GARANTIE<br/>Dieses Skript geht von einer Verbindung mit dem Quellpostfach (zum Erhalten von Quellwerten) und den lokalen Active Directory-Zieldomänendiensten (zum Stempeln des ADUser-Objekts) aus. Wenn für die Quelle ein Rechtsstreit oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto ein.  Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**Wie greifen wir auf Outlook an Tag 1 zu, nachdem das Verwendungspostfach verschoben wurde?**

Da nur ein Mandant eine Domäne besitzen kann, wird die frühere primäre #A0 nach Abschluss der Postfach verschieben nicht dem Benutzer im Ziel mandanten zugeordnet. nur die Domänen, die dem neuen Mandanten zugeordnet sind. Outlook verwendet den neuen UPN der Benutzer für die Authentifizierung beim Dienst, und das Outlook-Profil erwartet, dass die primäre SMTPAddress der Vor-Version so zu finden ist, dass sie dem Postfach im Zielsystem zu entsprechen. Da sich die Legacyadresse nicht im Zielsystem befindet, wird vom Outlookprofil keine Verbindung hergestellt, um das neu verschobene Postfach zu finden. 

Bei dieser anfänglichen Bereitstellung müssen Benutzer ihr Profil mit ihrem neuen UPN, der primären SMTP-Adresse, neu erstellen und die Ost-Inhalte erneut synchronisieren. 

> [!Note]
> Planen Sie entsprechend, während Sie die Benutzer für den Abschluss in einem Batch stapeln. Sie müssen die Netzwerkauslastung und Kapazität berücksichtigen, wenn Outlook-Clientprofile erstellt und nachfolgende OST- und OAB-Dateien auf Clients heruntergeladen werden. 
 
**Bei welchen Rollen für die rollenübergreifende Exchange-ROLLEN-Übergreifende Aktivierung muss ich Mitglied sein, um eine mandantenübergreifende Bewegung einrichten oder abschließen zu können?**
 
Es gibt eine Matrix von Rollen, die auf der Annahme delegierter Aufgaben beim Ausführen einer Postfach verschieben basiert. Derzeit sind zwei Rollen erforderlich:  

- Die erste Rolle ist eine einmal durchgeführte Einrichtungsaufgabe, die die Autorisierung für das Verschieben von Inhalten in Oder von Ihrer Mandanten-/Organisationsgrenze ein- oder ausdingt. Da das Verschieben von Daten aus der Kontrolle Ihrer Organisation für alle Unternehmen ein entscheidendes Problem ist, haben wir uns für die höchste zugewiesene Rolle des Organisationsadministrators (OrgAdmin) entschieden. Diese Rolle muss eine neue OrganizationRelationship ändern oder einrichten, die "-MailboxMoveCapability" mit der Remoteorganisation definiert. Nur das OrgAdmin kann die Einstellung "MailboxMoveCapability" ändern, während andere Attribute für "OrganizationRelationhip" vom Verbundfreigabeadministrator verwaltet werden können. 
 
- Die Rolle der Ausführung der tatsächlichen Verschiebebefehle kann an eine Funktion auf niedrigerer Ebene delegiert werden. Der Rolle des Verschiebens von Postfächern wird die Funktion zum Verschieben von Postfächern in oder aus der Organisation mithilfe des Parameters `-RemoteTenant` zugewiesen.  

**Wie wird die für targetAddress (TargetDeliveryDomain) ausgewählte SMTP-Adresse für das konvertierte Postfach (in die MailUser-Konvertierung) ausgewählt?**
 
Exchange-Postfach-Verschieben mithilfe von MRS erstellen die targetAddress für das ursprüngliche Quellpostfach, wenn sie in ein MailUser konvertiert werden, indem eine E-Mail-Adresse (proxyAddress) für das Zielobjekt gefunden wird. Der Prozess verwendet den an den Verschiebebefehl übergebenen Wert "-TargetDeliveryDomain" und sucht dann auf der Zielseite nach einem übereinstimmenden Proxy für diese Domäne. Wenn wir eine Übereinstimmung finden, wird die übereinstimmende proxyAddress verwendet, um die ExternalEmailAddress (targetAddress) für das konvertierte Postfachobjekt (jetzt MailUser) festgelegt.
 
**Wie werden Postfachberechtigungen übergangen?**

Zu den Postfachberechtigungen gehören "Senden im Auftrag von" und "Postfachzugriff": 

- "Senden im Auftrag von" (AD:publicDelegates) speichert den DN von Empfängern mit Zugriff auf das Postfach eines Benutzers als Stellvertretung. Dieser Wert wird in Active Directory gespeichert und wird derzeit nicht als Teil des Postfachübergangs verschoben. Wenn für das Quellpostfach "publicDelegates" festgelegt ist, müssen Sie die publicDelegates für das Zielpostfach neu ausgestalten, sobald die Konvertierung von E-Mail in Postfach in der Zielumgebung abgeschlossen ist, indem Sie die Ausführung `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` ausführen. 
 
- Postfachberechtigungen, die im Postfach gespeichert sind, werden mit dem Postfach verschoben, wenn sowohl der Prinzipal als auch die Stellvertretung in das Zielsystem verschoben werden. Beispielsweise erhält der Benutzer TestUser_7 Zugriff auf das Postfach, TestUser_8 in der Mandantendatenbank SourceCompany.onmicrosoft.com. Nachdem die Postfachspeicherung abgeschlossen TargetCompany.onmicrosoft.com, werden die gleichen Berechtigungen im Zielverzeichnis eingerichtet. Beispiele für *die Verwendung von Get-MailboxPermission* TestUser_7 sowohl in Quell- als auch in Ziel-Mandanten sind unten aufgeführt. Exchange-Cmdlets wird entsprechend das Präfix "Quelle" und "Ziel" vorangestellt. 
 
Hier ist ein Beispiel für die Ausgabe der Postfachberechtigung vor einer Bewegung. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Hier ist ein Beispiel für die Ausgabe der Postfachberechtigung nach dem Verschieben. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Mandantenübergreifende Postfach- und Kalenderberechtigungen werden NICHT unterstützt. Sie müssen Prinzipale und Stellvertretung in konsolidierten Verschiebebatches organisieren, damit diese verbundenen Postfächer gleichzeitig vom Quell mandanten übertragen werden. 

**Welcher X500-Proxy sollte den MailUser-Zielproxyadressen hinzugefügt werden, um die Migration zu ermöglichen?**  

Für die mandantenübergreifende Postfachmigration muss der LegacyExchangeDN-Wert des Quellpostfachobjekts als x500-E-Mail-Adresse im Ziel-MailUser-Objekt gestempelt werden.  

Beispiel:  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> Zusätzlich zu diesem X500-Proxy müssen Sie alle X500-Proxys aus dem Postfach in der Quelle in das Postfach im Ziel kopieren.  

**Wo beginne ich mit der Problembehandlung, wenn Dies nicht funktioniert?**  

Beginnen Sie, indem Sie VerifySetup.ps1 Skript auf [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ausführen und die Ausgabe überprüfen.

Hier ist ein Beispiel für die Ausführung VerifySetup.ps1 für den Ziel-Mandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier sehen Sie eine eExample zum Ausführen VerifySetup.ps1 für den Quell-Mandanten:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**Kann der Quell- und Ziel mandant denselben Domänennamen verwenden?**  

Nein. Die Quell- und Zieldomänendomänennamen des Mandanten müssen eindeutig sein. Beispielsweise eine Quelldomäne von contoso.com und die Zieldomäne des fourthcoffee.com.

**Werden freigegebene Postfächer verschoben und funktionieren sie weiterhin?**

Ja, wir behalten jedoch nur die Speicherberechtigungen, wie in den folgenden Artikeln beschrieben:

- [Microsoft Docs | Verwalten von Berechtigungen für Empfänger in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft Support | So erteilen Sie Exchange- und Outlook-Postfachberechtigungen in Office 365 de dedicated](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Ist Azure Key Vault erforderlich und wann werden Transaktionen ausgeführt?**  

Ja, ein Azure-Abonnement ist erforderlich, um Key Vault zum Speichern des Zertifikats zum Autorisieren der Migration zu verwenden. Im Gegensatz zu Onboardingmigrationen, bei denen der Benutzername & Kennwort für die Authentifizierung bei der Quelle verwendet wird, verwenden mandantenübergreifende Postfachmigrationen OAuth und dieses Zertifikat als schlüssel-/anmeldeinformationen. Der Zugriff auf den Key Vault muss während aller Postfachmigrationen beibehalten werden, da zu Beginn und nach dem Ende der Migration einmal darauf zugegriffen wird, sowie einmal alle 24 Stunden während inkrementeller Synchronisierungszeiten. Details zu den Kosten für AKV finden Sie [hier.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)  

**Gibt es Empfehlungen für Batches?**  

Überschreiten Sie nicht mehr als 2.000 Postfächer pro Batch. Es wird dringend empfohlen, Batches zwei Wochen vor dem Synchronisierungsdatum zu übermitteln, da es während der Synchronisierung keine Auswirkungen auf die Endbenutzer gibt. Wenn Sie Anleitungen für Postfachmengen über 50.000 benötigen, können Sie sich an die Engineering Feedback Distribution List unter crosstenantmigrationpreview@service.microsoft.com.

**Was passiert, wenn ich die Dienstverschlüsselung mit Customer Key verwende?**

Das Postfach wird vor dem Verschieben entschlüsselt. Stellen Sie sicher, dass der Kundenschlüssel im Ziel mandanten konfiguriert ist, wenn er weiterhin erforderlich ist. Weitere [Informationen finden](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) Sie hier.  

**Wie sieht die geschätzte Migrationszeit aus?**

Zur Unterstützung der Planung der [](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) Migration enthält die hier aufgeführte Tabelle die Richtlinien, wann Massenmigrationen von Postfächern oder einzelne Migrationen durchgeführt werden sollten. Diese Schätzungen basieren auf einer Datenanalyse vorheriger Kundenmigrationen. Da jede Umgebung einzigartig ist, kann die genaue Migrationsgeschwindigkeit variieren.  

Denken Sie daran, dass sich dieses Feature derzeit in der Vorschau befindet und die SLA und alle anwendbaren Servicelevels während des Vorschaustatus dieses Features nicht auf Leistungs- oder Verfügbarkeitsprobleme angewendet werden.

## <a name="known-issues"></a>Bekannte Probleme  

-  **Problem: Automatisch erweiterte Archive können nicht migriert werden.** Die mandantenübergreifende Migrationsfunktion unterstützt Migrationen des primären Postfachs und Archivpostfachs für einen bestimmten Benutzer. Wenn der Benutzer in der Quelle jedoch über ein automatisch erweitertes Archiv verfügt , d. h. mehrere Archivpostfächer, kann das Feature die zusätzlichen Archive nicht migrieren und sollte fehlschlagen.

- **Problem: Cloud MailUsers mit nicht im Besitz von "smtp proxyAddress"-Block-MRS verschiebt den Hintergrund.** Beim Erstellen von Ziel-Mandanten-MailUser-Objekten müssen Sie sicherstellen, dass alle SMTP-Proxyadressen zur Ziel mandantenorganisation gehören. Wenn für den Ziel-E-Mail-Benutzer, der nicht zum lokalen Mandanten gehört, eine SMTP-Proxyadresse vorhanden ist, wird die Konvertierung von MailUser in Mailbox verhindert. Dies liegt an unserer Zusicherung, dass Postfachobjekte nur E-Mails von Domänen senden können, für die der Mandant autorisierend ist (vom Mandanten beanspruchte Domänen): 

   - Wenn Sie Benutzer lokal mithilfe von Azure AD Connect synchronisieren, stellen Sie lokale "MailUser"-Objekte mit "ExternalEmailAddress" bereit, die auf den Quell-Mandanten zeigen, in dem das Postfach vorhanden ist (laran@contoso.onmicrosoft.com), und stempeln "PrimarySMTPAddress" als Domäne, die sich im Ziel mandanten (Lara.Newton@northwind.com) befindet. Diese Werte werden mit dem Mandanten synchronisiert, und ein entsprechender E-Mail-Benutzer ist bereitgestellt und für die Migration bereit. Hier wird ein Beispielobjekt gezeigt.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Die *contoso.onmicrosoft.com* Adresse *ist im* Array "EmailAddresses/proxyAddresses" nicht vorhanden.

- **Problem: MailUser-Objekte mit "externen" primären SMTP-Adressen werden geändert/auf "interne" vom Unternehmen beanspruchte Domänen zurückgesetzt**

   MailUser -Objekte sind Zeiger auf nicht lokale Postfächer. Bei mandantenübergreifenden Postfachmigrationen verwenden wir MailUser-Objekte, um entweder das Quellpostfach (aus der Perspektive der Zielorganisation) oder das Zielpostfach (aus der Perspektive der Quellorganisation) zu repräsentieren. Die MailUsers verfügen über eine ExternalEmailAddress (targetAddress), die auf die smtp-Adresse des tatsächlichen Postfachs (ProxyTest@fabrikam.onmicrosoft.com) und die primäreSMTP-Adresse verweist, die die angezeigte SMTP-Adresse des Postfachbenutzers im Verzeichnis darstellt. Einige Organisationen entscheiden sich dafür, die primäre SMTP-Adresse als externe SMTP-Adresse und nicht als Adresse im Besitz des lokalen Mandanten (z. B. fabrikam.com anstelle von contoso.com) angezeigt zu contoso.com.  Nachdem jedoch ein Objekt des Exchange-Dienstplans über Lizenzierungsvorgänge auf MailUser angewendet wurde, wird die primäre SMTP-Adresse geändert, um sie als von der lokalen Organisation überprüfte Domäne (contoso.com). Es gibt zwei mögliche Gründe:
   
   - Wenn ein beliebiger Exchange-Dienstplan auf ein MailUser angewendet wird, beginnt der Azure AD-Prozess, proxy scrubbing zu erzwingen, um sicherzustellen, dass die lokale Organisation keine E-Mails, Spoofing oder E-Mails von einem anderen Mandanten senden kann. Alle SMTP-Adressen für ein Empfängerobjekt mit diesen Dienstplänen werden entfernt, wenn die Adresse nicht von der lokalen Organisation überprüft wird. Wie im Beispiel wird die Fabikam.com Domäne nicht vom contoso.onmicrosoft.com-Mandanten überprüft, sodass das Scrubbing diese fabrikam.com entfernt. Wenn Sie diese externe Domäne in MailUser beibehalten möchten, entweder vor der Migration oder nach der Migration, müssen Sie Ihre Migrationsprozesse so ändern, dass Lizenzen nach Abschluss der Migration oder vor dem Verschieben entfernen werden, um sicherzustellen, dass die Benutzer das erwartete externe Branding angewendet haben. Sie müssen sicherstellen, dass das Postfachobjekt ordnungsgemäß lizenziert ist, um keinen Einfluss auf den E-Mail-Dienst zu haben.<br/><br/>Hier wird ein Beispielskript zum Entfernen der Dienstpläne für einen MailUser im Contoso.onmicrosoft.com A0 gezeigt.

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
 
       Die PrimarySMTPAddress des Benutzers wird nicht mehr bereinigungsbereinigung. Die fabrikam.com befindet sich nicht im Besitz des contoso.onmicrosoft.com Mandanten und wird als primäre SMTP-Adresse beibehalten, die im Verzeichnis angezeigt wird.

       Hier ein Beispiel.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Wenn "msExchRemoteRecipientType" auf "8" (DeprovisionMailbox) festgelegt ist, entfernt die Proxybereinigungslogik in Azure für lokale MailUser, die zum Zielmandanten migriert werden, nicht gehostete Domänen und setzt den primarySMTP auf eine Domäne im Besitz zurück. Durch Löschen von "msExchRemoteRecipientType" im lokalen MailUser gilt die Proxybereinigungslogik nicht mehr. <br/><br>Im Folgenden finden Sie den vollständigen Satz möglicher Servicepläne, die Exchange Online enthalten.

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
   | Exchange Online Inactive User Add-on              |
   | Exchange Online-Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Plan 1                            |
   | Exchange Online-POP                               |
   | Exchange Online Protection                        |
   | Informationsbarrieren                              |
   | Information Protection für Office 365 – Premium   |
   | Information Protection für Office 365 – Standard  |
   | Einblicke von MyAnalytics                           |
   | Microsoft 365 Advanced Auditing                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (Vollversion)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender für Office 365 (Plan 1)    |
   | Microsoft Defender für Office 365 (Plan 2)    |
   | Office 365 Privileged Access Management           |
   | Premiumverschlüsselung in Office 365                  |
    
