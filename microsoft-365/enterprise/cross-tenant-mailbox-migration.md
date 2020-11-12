---
title: Mandantenübergreifende Postfachmigration
description: Verschieben von Postfächern zwischen Microsoft 365-oder Office 365-Mandanten.
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
ms.openlocfilehash: a2065ac324acd0a4d5980bceb97f9f6b8ad73058
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002245"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Mandantenübergreifende Postfachmigration (Vorschau)

Wenn ein Exchange Online-Mandant zuvor zum Verschieben von Postfächern in einen anderen Mandanten in demselben Exchange Online Dienst benötigt wurde, müsste er diese vollständig lokal extern und dann an einen neuen Mandanten an Bord bringen. Mit dem neuen Feature für die Mandantenübergreifende Postfachmigration können mandantenadministratoren in den Quell-und Zielmandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in Ihren lokalen Systemen verschieben. Dadurch wird die Notwendigkeit, extern und Onboard-Postfächer zu entfernen.

Bei Fusionen oder Veräußerungen benötigen Sie häufig die Möglichkeit, Benutzer und Inhalte in einen neuen Mandanten zu verlagern. Wenn der Zielmandanten Administrator den Umzug ausführt, wird er als Pull-Umzug bezeichnet, ähnlich wie bei Onboarding-Migrationen vor Ort und Cloud.

Mandantenübergreifende Exchange-Postfachverschiebungen werden von mandantenadministratoren vollständig selbst gewartet, wobei bekannte Schnittstellen verwendet werden, die in die größeren Workflows geschrieben werden können, die für den Übergang von Benutzern zu ihrer neuen Organisation benötigt werden. Administratoren können das `New-MigrationBatch` Cmdlet verwenden, das über die Verwaltungsrolle "Postfächer verschieben" zur Verfügung steht, um Mandantenübergreifende Verschiebungen auszuführen. Der Verschiebevorgang umfasst Mandanten Autorisierungsüberprüfungen während der Postfachsynchronisierung und-Fertigstellung. 
 
Benutzer, die migriert werden, müssen im Zielmandanten Exchange Online System als MailUser vorhanden sein, die mit bestimmten Attributen markiert sind, um die mandantenübergreifenden Verschiebungen zu ermöglichen. Das System führt keine Verschiebungen für Benutzer aus, die nicht ordnungsgemäß im Zielmandanten eingerichtet sind. 

Wenn die Verschiebungen abgeschlossen sind, wird das Quellsystem Postfach in MailUser konvertiert, und die targetAddress (als ExternalEmailAddress in Exchange angezeigt) wird mit der Routingadresse an den Zielmandanten gestempelt. Bei diesem Prozess bleibt die Legacy-MailUser im Quellmandanten und ermöglicht eine gewisse Zeit der Koexistenz und des e-Mail-Routings. Wenn Geschäftsprozesse dies zulassen, entfernt der Quellmandant möglicherweise die Quell-MailUser oder wandelt sie in einen e-Mail-Kontakt um. 

Mandantenübergreifende Exchange-Postfachmigrationen werden nur in Hybrid-oder Cloud-Umgebungen oder in einer beliebigen Kombination aus beiden unterstützt.

In diesem Artikel wird der Prozess für Mandantenübergreifende Postfachverschiebungen beschrieben, und es werden Anleitungen zum Vorbereiten von Quell-und Zielmandanten für die Inhaltsverschiebung bereitgestellt. 

## <a name="preparing-source-and-target-tenants"></a>Vorbereiten von Quell-und Zielmandanten

Das Feature für die Mandantenübergreifende Exchange-Postfachmigration erfordert Autorisierung und Scoping für Mandantenübergreifende Migrationen. Mithilfe der Azure Enterprise-Anwendung und Schlüsselspeicher Lösungen für Vault können mandantenadministratoren nun die Autorisierung und das Scoping von Exchange Online Postfachmigrationen von einem Mandanten auf einen anderen verwalten. Mandantenübergreifende Postfachverschiebungen unterstützen ein Einladungs-und Zustimmungs Modell zum Einrichten einer Azure Active Directory (Azure AD)-Anwendung, die für die Authentifizierung zwischen einem Mandanten paar verwendet wird. Zusätzliche Komponenten wie eine Organisationsbeziehung und ein Migrations Endpunkt sind ebenfalls erforderlich.

In diesem Abschnitt werden nicht die erforderlichen Schritte zum Vorbereiten der MailUser-Benutzerobjekte im Zielverzeichnis sowie der Beispielbefehl zum Übermitteln eines Migrationsbatches berücksichtigt. Informationen hierzu finden Sie unter [Vorbereiten von Zielbenutzer Objekten für die Migration](#prepare-target-user-objects-for-migration) .

## <a name="prerequisites"></a>Voraussetzungen

Das Feature für die Mandantenübergreifende Post Fach Verlagerung erfordert [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) , um eine mandantenspezifische Azure-Anwendung einzurichten, mit der sicher gespeichert und auf das Zertifikat/das Geheimnis zugegriffen werden kann, das zur Authentifizierung und Autorisierung der Postfachmigration von einem Mandanten zum anderen verwendet wird, sodass alle Anforderungen zum Freigeben von Zertifikaten/Schlüsseln zwischen Mandanten entfernt werden 

Stellen Sie vor dem Starten sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um Azure Key Vault, Post Fachanwendung, Exo-Migrations Endpunkt und die Exo-Organisationsbeziehung zu konfigurieren. Normalerweise verfügt der globale Administrator über die Berechtigung zum Ausführen aller Konfigurationsschritte.

Darüber hinaus sind e-Mail-aktivierte Sicherheitsgruppen im Quellmandanten vor der Ausführung von Setup erforderlich. Diese Gruppen werden verwendet, um die Liste der Postfächer zu belegen, die von einem Mandanten (oder auch als Ressource bezeichnet) in den Zielmandanten verschoben werden können. Dadurch kann der Quellmandanten-Administrator die zu verschiebenden spezifischen Sätze von Postfächern einschränken oder auf den Bereich beschränken, wodurch verhindert werden kann, dass unbeabsichtigte Benutzer migriert werden müssen. Geschachtelte Gruppen werden nicht unterstützt.

Sie müssen auch mit Ihrer vertrauenswürdigen Partnerfirma (mit der Sie Postfächer verschieben werden) kommunizieren, um Ihre Microsoft 365-Mandanten-ID zu erhalten. Diese Mandanten-ID wird im Feld Organisationsbeziehung verwendet `DomainName` .

Um die Mandanten-ID eines Abonnements zu erhalten, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klicken Sie auf das Symbol Kopieren für die Mandanten-ID-Eigenschaft, um es in die Zwischenablage zu kopieren.

Hier erfahren Sie, wie der Prozess funktioniert.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Mandanten Vorbereitung für die Postfachmigration.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).
--> 

### <a name="prepare-tenants"></a>Vorbereiten von Mandanten

Auf einer hohen Ebene erfolgen die folgenden Konfigurationsaktionen beim Ausführen der Setupskripts.

Vorbereiten des Zielmandanten:

1. Wenn keine vorhandene Azure-Ressourcengruppe bereitgestellt wird, wird ein neues erstellt (Skript).
2. Wenn kein vorhandener schlüsseltresor bereitgestellt wird, wird ein neues Schlüsseldepot erstellt (Skript).
3. Für die Office 365 Exchange Online Post Fach Migrationsanwendung (Script) wird eine neue Zugriffsrichtlinie erstellt.
4. Ein neues Zertifikat wird (falls angegeben) erstellt (oder vorhanden), um das Geheimnis für die Migrationsanwendung (Skript) zu halten.
5. Eine neue Azure AD Anwendung wird erstellt (Skript).
6. Das Zertifikat/der geheime Schlüssel wird in die Migrationsanwendung (Skript) hochgeladen.
7. Der Anwendung werden Berechtigungen für die Postfachmigration (Skript) zugewiesen.
8. Das Bereitstellungsskript wird angehalten, bis der Zieladministrator ihrer eigenen Anwendung (Skript) zustimmt.
9. Der Zielmandanten Administrator stimmt den Berechtigungen zu, die der Anwendung erteilt wurden (manuell).
10. Eine Organisationsbeziehung wird mit dem Zielmandanten (Skript) erstellt.
11. Ein Migrations Endpunkt wird erstellt, um Postfächer an den Zielmandanten (Skript) zu ziehen.

Vorbereiten des Quellmandanten:

1. Der Quellmandanten Administrator akzeptiert die Zustimmung zur Post Fach Migrations-Anwendungseinladung vom Zielmandanten (Manual).
2. Der Quellmandanten Administrator erstellt eine e-Mail-aktivierte Sicherheitsgruppe in Ihrem Mandanten, die die Liste der Postfächer enthält, die von der Migrationsanwendung verschoben werden dürfen (manuell).
3. Eine Organisationsbeziehung wird mit dem Zielmandanten erstellt, der angibt, dass die Post Fach Migrationsanwendung für die OAuth-Überprüfung verwendet werden soll, um die Verschiebe Anforderung (Skript) zu akzeptieren.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Schritt-für-Schritt-Anweisungen für den Zielmandanten Administrator

1. Laden Sie das SetupCrossTenantRelationshipForTargetTenant.ps1-Skript für das Setup des Zielmandanten aus dem [GitHub-Repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview)herunter. 
2. Speichern Sie das Skript (SetupCrossTenantRelationshipForTargetTenant.ps1) auf dem Computer, auf dem das Skript ausgeführt wird.
3. Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Exchange Online Zielmandanten. Stellen Sie auch in diesem Fall sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um die Azure Key Vault-Speicherung und das Zertifikat, die Post Fachanwendung, den Exo-Migrations Endpunkt und die Exo-Organisationsbeziehung zu konfigurieren.
4. Ändern Sie das Datei Ordner Verzeichnis in den Skript Speicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in der Remote-PowerShell-Sitzung befindet.
5. Führen Sie das Skript mit den folgenden Parametern und Werten aus.

    | Parameter | Wert | Erforderlich oder optional
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | Quellmandanten Domäne, beispielsweise Fabrikam \. onmicrosoft.com. | Erforderlich |
    | -ResourceTenantAdminEmail                   | Die e-Mail-Adresse des Quellmandanten-Administrators. Dies ist der Quellmandanten Administrator, der der Verwendung der Post Fach Migrationsanwendung zustimmt, die vom Zieladministrator gesendet wird. Dies ist der Administrator, der die e-Mail-Einladung für die Anwendung erhalten wird. | Erforderlich |
    | -TargetTenantDomain                         | Zielmandanten Domäne, wie Contoso \. onmicrosoft.com. | Erforderlich |
    | -ResourceTenantId                           | Quellmandanten-Organisations-ID (GUID). | Erforderlich |
    | -Abonnement-Nr                             | Das Azure-Abonnement, das zum Erstellen von Ressourcen verwendet werden soll. | Erforderlich |
    | -ResourceGroup                              | Azure-Ressourcengruppenname, der den schlüsseltresor enthält oder enthalten soll. | Erforderlich |
    | -Keyvaultname                               | Azure Key Vault-Instanz, in der Ihr Zertifikat für die Post Fach Migrationsanwendung/Secret gespeichert wird. | Erforderlich |
    | -CertificateName                            | Zertifikatname beim Generieren oder suchen nach Zertifikat in Key Vault. | Erforderlich |
    | -CertificateSubject                         | Name des Zertifikatsantrags Teller namens Azure Key Vault, beispielsweise CN = contoso_fabrikam. | Erforderlich |
    | -ExistingApplicationId                      | Mail Migrationsanwendung, die verwendet werden soll, wenn bereits eine erstellt wurde. | Optional |
    | -AzureAppPermissions                        | Die erforderlichen Berechtigungen für die Post Fach Migrationsanwendung wie Exchange oder MSGraph (Exchange für das Verschieben von Postfächern, MSGraph für die Verwendung dieser Anwendung zum Senden einer Einladung zum Genehmigungs Link an den Ressourcen Mandanten). | Erforderlich |
    | -UseAppAndCertGeneratedForSendingInvitation | Parameter für die Verwendung der Anwendung, die für die Migration erstellt wurde, um eine Zustimmungs Link Einladung an den Quellmandanten-Administrator zu senden. Wenn dieser Wert nicht angegeben wird, werden die Anmeldeinformationen des Ziel Administrators aufgefordert, eine Verbindung mit dem Azure-Einladungs-Manager herzustellen und die Einladung als Zieladministrator zu senden. | Optional |
    | -KeyVaultAuditStorageAccountName            | Das Speicherkonto, in dem die Überwachungsprotokolle des Schlüsseldepots gespeichert würden. | Optional |
    | -KeyVaultAuditStorageResourceGroup          | Die Ressourcengruppe, die das Speicherkonto zum Speichern von Schlüsseldepot-Überwachungsprotokollen enthält. | Optional |
    ||||

6. Das Skript wird angehalten, und Sie werden aufgefordert, die Exchange-Post Fach Migrationsanwendung, die während dieses Prozesses erstellt wurde, anzunehmen oder Ihr zuzustimmen. Hier ein Beispiel.

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. Eine URL wird in der Remote-PowerShell-Sitzung angezeigt. Kopieren Sie den für Ihre Mandanten Zustimmung angegebenen Link, und fügen Sie ihn in einen Webbrowser ein.

8. Melden Sie sich mit ihren globalen Administratoranmeldeinformationen an. Wenn der folgende Bildschirm angezeigt wird, wählen Sie **akzeptieren** aus.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogfeld &quot;Berechtigungen akzeptieren&quot;":::
    
9. Wechseln Sie zurück zur PowerShell-Remote Sitzung, und drücken Sie die EINGABETASTE, um fortzufahren.

10. Mit dem Skript werden die restlichen Setup-Objekte konfiguriert. Hier ein Beispiel.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Das Setup des Ziel Administrators ist nun abgeschlossen!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Schritt-für-Schritt-Anweisungen für den Quellmandanten-Administrator

1.  Melden Sie sich bei Ihrem Postfach als vom Zieladministrator während des Setups angegebene-ResourceTenantAdminEmail an. Suchen Sie nach der e-Mail-Einladung des Zielmandanten, und wählen Sie dann die Schaltfläche **Erste Schritte** aus.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogfeld &quot;Sie wurden eingeladen&quot;":::

2. Wählen Sie **annehmen** aus, um die Einladung zu akzeptieren.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialog Feld zum Akzeptieren von Berechtigungen":::

   > [!NOTE]
   > Wenn Sie diese e-Mail nicht erhalten oder nicht finden können, wurde dem Zielmandanten Administrator eine direkte URL zur Verfügung gestellt, die Sie zur Annahme der Einladung erhalten können. Die URL sollte im Protokoll der Remote-PowerShell-Sitzung des Zielmandanten-Administrators sein.

3. Erstellen Sie entweder im Microsoft 365 Admin Center oder in einer Remote-PowerShell-Sitzung eine oder mehrere e-Mail-aktivierte Sicherheitsgruppen, um die Liste der Postfächer zu steuern, die vom Zielmandanten für das ziehen (verschieben) vom Quellmandanten an den Zielmandanten zulässig sind. Sie müssen diese Gruppe nicht im Voraus auffüllen, aber mindestens eine Gruppe muss bereitgestellt werden, um die Setupschritte (Skript) ausführen zu können. Geschachtelte Gruppen werden nicht unterstützt. 

4. Laden Sie [hier](https://github.com/microsoft/cross-tenant/releases/tag/Preview)das SetupCrossTenantRelationshipForTargetResource.ps1 Skript für das Setup des Quellmandanten aus dem GitHub-Repository herunter. 

5. Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Quellmandanten mit Ihren Exchange-Administrator Berechtigungen. Globale Administratorberechtigungen sind nicht erforderlich, um den Quellmandanten zu konfigurieren, sondern nur den Zielmandanten, da der Azure-Anwendungs Erstellungsprozess ausgeführt wird.

6. Ändern Sie das Verzeichnis in den Skript Speicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in der Remote-PowerShell-Sitzung befindet.

7. Führen Sie das Skript mit den folgenden erforderlichen Parametern und Werten aus.

    | Parameter | Wert |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Vom Quellmandanten erstellte e-Mail-aktivierte Sicherheitsgruppe für die Identitäten/Postfächer, die sich im Bereich der Migration befinden. |
    | -ResourceTenantDomain | Name der Quellmandanten Domäne, beispielsweise Fabrikam \. onmicrosoft.com. |
    | -TargetTenantDomain | Name der Zielmandanten Domäne, beispielsweise contoso \. onmicrosoft.com. |
    | -ApplicationId | Azure-Anwendungs-ID (GUID) der Anwendung, die für die Migration verwendet wird. Anwendungs-ID, die über Ihr Azure-Portal (Azure AD, Enterprise-Anwendungen, App-Name, Anwendungs-ID) oder in Ihrer Einladungs-e-Mail enthalten ist.  |
    | -TargetTenantId | Mandanten-ID des Zielmandanten. Beispielsweise die Azure AD Mandanten-ID des Contoso \. onmicrosoft.com-Mandanten. |
    |||
    
    Hier ein Beispiel.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Das Setup des Quell Administrators ist nun abgeschlossen!

### <a name="verify-setup"></a>Überprüfen des Setups

Stellen Sie sicher, dass die Organisationsbeziehungen in den Quell-und Zielmandanten und dem Migrations Endpunkt im Ziel erfolgreich erstellt wurden.

#### <a name="target-tenant"></a>Zielmandant

**Organisationsbeziehung**

Stellen Sie sicher, dass das Organisations Beziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Hier ein Beispiel:

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Migrations Endpunkt**

Stellen Sie sicher, dass das Migrations Endpunkt Objekt mit diesem Befehl erstellt und konfiguriert wurde.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Hier ein Beispiel.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Quellmandant

**Organisationsbeziehung**

Stellen Sie sicher, dass das Organisations Beziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
Hier ein Beispiel.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Verschieben von Postfächern zurück in die ursprüngliche Quelle

Wenn ein Postfach zurück zum ursprünglichen Quellmandanten wechselt, müssen dieselbe Reihe von Schritten und Skripts sowohl in der neuen als auch in den neuen Zielmandanten ausgeführt werden. Das vorhandene Organisations Beziehungsobjekt wird aktualisiert oder angefügt und nicht neu erstellt.

## <a name="prepare-target-user-objects-for-migration"></a>Vorbereiten von Zielbenutzer Objekten für die Migration

Die Migration von Benutzern muss im Zielmandanten vorhanden sein, und Exchange Online System (als MailUser), das mit bestimmten Attributen markiert ist, um die mandantenübergreifenden Verschiebungen zu ermöglichen. Das System führt keine Verschiebungen für Benutzer aus, die nicht ordnungsgemäß im Zielmandanten eingerichtet sind. Im folgenden Abschnitt werden die Anforderungen des MailUser-Objekts für den Zielmandanten erläutert.

### <a name="prerequisites"></a>Voraussetzungen
  
Sie müssen sicherstellen, dass die folgenden Objekte und Attribute in der Zielorganisation festgelegt sind.  

1. Für alle Postfächer, die von einer Quellorganisation aus verschoben werden, müssen Sie ein MailUser-Objekt in der Zielorganisation zur Verfügung stellen: 
   - Das Ziel-MailUser muss über diese Attribute aus dem Quellpostfach verfügen oder dem neuen Benutzerobjekt zugewiesen sein:
      - ExchangeGUID (direkter Fluss von der Quelle zum Ziel) – die Postfach-GUID muss übereinstimmen. Der Verschiebevorgang wird nicht fortgesetzt, wenn dieser nicht auf dem Zielobjekt vorhanden ist. 
      - ArchiveGUID (direkter Fluss von der Quelle zum Ziel) – die Archiv-GUID muss übereinstimmen. Der Verschiebevorgang wird nicht fortgesetzt, wenn dieser nicht im Zielobjekt vorhanden ist. (Dies ist nur erforderlich, wenn das Quellpostfach Archiv aktiviert ist). 
      - LegacyExchangeDN (Durchfluss als proxyAddress, "x500: <LegacyExchangeDN> ") – der legacyExchangeDN muss auf Ziel-MailUser als x500: proxyAddress vorhanden sein. Die Verschiebevorgänge werden nicht fortgesetzt, wenn diese nicht im Zielobjekt vorhanden sind. 
      - UserPrincipalName – UPN wird an der neuen Identität oder Zielgesellschaft des Benutzers ausgerichtet (beispielsweise User@northwindtraders.onmicrosoft.com). 
      - Primäre SMTPAddress – primäre SMTP-Adresse wird an das neue Unternehmen des Benutzers ausgerichtet (beispielsweise User@Northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser verweist auf das aktuelle Postfach des Benutzers, das im Quellmandanten gehostet wird (beispielsweise user@contoso.onmicrosoft.com). Wenn Sie diesen Wert zuweisen, überprüfen Sie, ob Sie auch PrimarySmtpAddress zuweisen oder diesen Wert festlegen, um die PrimarySmtpAddress festzulegen, die zu Verschiebe Fehlern führen wird. 
      - Sie können keine Legacy-SMTP-Proxyadressen aus dem Quellpostfach zu Target MailUser hinzufügen. Beispielsweise können Sie contoso.com auf dem meu in fabrikam.onmicrosoft.com-Mandanten Objekten nicht beibehalten). Domänen werden nur einem Azure AD oder Exchange Online Mandanten zugeordnet.
 
    Beispiel für ein MailUser- **Ziel** Objekt:
 
    | Attribut             | Wert                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | Alias                 | LaraN                                                                                                                    |
    | RecipientType         | MailUser                                                                                                                 |
    | RecipientTypeDetails  | MailUser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara \. Newton@Northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP: LaraN@Contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = erste Organisation/ou = administrative Exchange-Gruppe                                                                   |
    |                       | (FYDIBOHF23SPDLT)/CN = Recipients/CN = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | x500:/o = First Organization/ou = Exchange Administrative Group (FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | SMTP: LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP: Lara \. Newton@Northwind.com                                                                                           |
    |||

   Beispiel für ein **Quell** Postfach-Objekt:

   | Attribut             | Wert                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | Alias                 | LaraN                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@Contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = erste Organisation/ou = administrative Exchange-Gruppe                   |
   |                       | (FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | SMTP: LaraN@Contoso \. onmicrosoft.com 
   |                       | SMTP: Lara \. Newton@contoso.com          |
   |||

   - In Exchange-Hybrid-Write Back sind möglicherweise bereits weitere Attribute enthalten. Wenn dies nicht der Fall ist, sollten Sie eingeschlossen werden. 
   - msExchBlockedSendersHash – schreibt Online sichere und blockierte Absenderdaten von Clients in lokale Active Directory zurück.
   - msExchSafeRecipientsHash – schreibt Online sichere und blockierte Absenderdaten von Clients in lokale Active Directory zurück.
   - msExchSafeSendersHash – schreibt Online sichere und blockierte Absenderdaten von Clients in lokale Active Directory zurück.

2. Wenn sich das Quellpostfach in LitigationHold befindet und die Größe des Quellpostfachs "Wiederherstellbare Elemente" größer ist als der Standardwert unserer Datenbank (30 GB), wird Moves nicht fortgesetzt, da das Ziel Kontingent kleiner als die Größe des Quellpostfachs ist. Sie können das Ziel MailUser-Objekt aktualisieren, um die ELC-Post Fach Flags von der Quellumgebung zum Ziel zu überführen, wodurch das Zielsystem ausgelöst wird, um das Kontingent des MailUser auf 100 GB zu erweitern und somit den Übergang zum Ziel zu ermöglichen. Diese Anweisungen funktionieren nur für Hybrid Identitäten, die Azure AD Connect ausführen, da die Befehle zum Stempeln der ELC-Flags nicht für mandantenadministratoren verfügbar gemacht werden.

    >[!Note]
    > Beispiel – keine Garantie<br/>Dieses Skript nimmt eine Verbindung mit beiden Quellpostfächern (zum Abrufen der Quellwerte) und dem lokalen Ziel Active Directory (zum Stempeln des Benutzerobjekts) an. Wenn für Source das Verfahren für die Wiederherstellung von Einzelelementen aktiviert ist, legen Sie dies für das Ziel Konto fest.  Dadurch wird die Größe des Zielkontos für den Papierkorb auf 100 GB erhöht.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. Nicht-hybride Zielmandanten können das Kontingent für den Ordner "refundable Items" für die Mail-Benutzer vor der Migration ändern, indem Sie den folgenden Befehl ausführen, um das Beweissicherungsverfahren für das MailUser-Objekt zu aktivieren und das Kontingent auf 100 GB zu erhöhen: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Hinweis Dies ist für Mandanten in Hybrid nicht möglich.

4. Benutzer in der Zielorganisation müssen mit den entsprechenden Exchange Online Abonnements lizenziert sein, die für die Organisation gelten. Sie können eine Lizenz im Vorfeld einer Post Fach Verlagerung anwenden, jedoch nur, wenn der Ziel-MailUser ordnungsgemäß mit ExchangeGUID-und Proxyadressen eingerichtet wurde. Wenn Sie eine Lizenz anwenden, bevor das ExchangeGUID angewendet wird, wird ein neues Postfach in der Zielorganisation zur Verfügung gestellt. 

    > [!Note]
    > Wenn Sie eine Lizenz auf ein Postfach-oder MailUser-Objekt anwenden, werden alle SMTP-proxyAddresses bereinigt, um sicherzustellen, dass nur verifizierte Domänen im Exchange-Adress Array enthalten sind. 

5. Sie müssen sicherstellen, dass das Ziel MailUser keine vorherigen ExchangeGuid hat, die nicht mit der Quell-ExchangeGuid übereinstimmen. Dies kann der Fall sein, wenn das Ziel-meu zuvor für Exchange Online lizenziert und ein Postfach zur Verfügung gestellt wurde. Wenn das Ziel MailUser zuvor lizenziert wurde oder ein ExchangeGuid, das nicht mit dem Quell ExchangeGuid übereinstimmt, müssen Sie eine Bereinigung der Cloud meu durchführen. Für diese Cloud-aktivierte Benutzer können Sie den `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` Befehl ausführen. 

    > [!Caution]
    > Dieser Vorgang ist unumkehrbar. Wenn das Objekt über ein softDeleted-Postfach verfügt, kann es nach diesem Pfad nicht wiederhergestellt werden. Nachdem Sie jedoch gelöscht haben, können Sie die richtige ExchangeGuid mit dem Zielobjekt synchronisieren, und Mrs stellt eine Verbindung zwischen dem Quellpostfach und dem neu erstellten Zielpostfach her. (Verweisen Sie auf den EHLO-Blog auf den neuen Parameter.) 
 
    Suchen von Objekten, die zuvor Postfächer mit diesem Befehl waren.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    Hier ein Beispiel. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    Löschen Sie das vorläufig gelöschte Postfach mithilfe dieses Befehls.

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    Hier ein Beispiel.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>Durchführen von Postfachmigrationen

Mandantenübergreifende Exchange-Postfachmigrationen werden als Migrationsbatches übermittelt, die vom Zielmandanten initiiert wurden. Dies ist vergleichbar mit der Art und Weise, wie die Migration von Exchange-Batches bei der Migration von lokalen Exchange-Webdiensten zu Microsoft 365 erfolgt. 

### <a name="create-migration-batches"></a>Erstellen von Migrationsbatches

Hier ist ein Beispiel für ein Migrationsbatch-Cmdlet zum Starten von Moves.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Die e-Mail-Adresse in der CSV-Datei muss diejenige sein, die im Zielmandanten angegeben ist, nicht der Quellmandant.

Die Übermittlung von Migrations Batchen wird auch vom neuen Exchange Admin Center beim Auswählen der mandantenübergreifenden Option unterstützt.
 
#### <a name="update-on-premises-mailusers"></a>Lokale MailUser aktualisieren

Sobald das Postfach von Quelle zu Ziel verschoben wurde, sollten Sie sicherstellen, dass die lokalen e-Mail-Benutzer, sowohl Quelle als auch Ziel, mit dem neuen targetAddress aktualisiert werden. In den Beispielen lautet der bei der Migration verwendete targetDeliveryDomain **contoso \. onmicrosoft.com**. Aktualisieren Sie die e-Mail-Benutzer mit diesem targetAddress.
 
## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen
 
**Müssen wir RemoteMailboxes in der lokalen Quellumgebung nach dem Wechsel aktualisieren?**
 
Ja, Sie sollten die targetAddress (RemoteRoutingAddress/ExternalEmailAddress) der Quell lokalen Benutzer aktualisieren, wenn das Quellmandanten Postfach zu einem Zielmandanten verschoben wird.  Während die e-Mail-Weiterleitung die Verweise auf mehrere e-Mail-Benutzer mit unterschiedlichen targetAddresses verfolgen kann, müssen frei/Gebucht-Lookups für e-Mail-Benutzer auf den Speicherort des Postfachbenutzers Zielen. Bei Frei/Gebucht-Lookups werden mehrere Umleitungen nicht mehr verfolgt. 
 
**Migriert der Inhalt des Teams-Chat Ordners mandantenübergreifend?** 

Nein, der Inhalt des Teams-Chat Ordners migriert nicht mandantenübergreifend. 
 
**Wie kann ich nur Bewegungen sehen, bei denen es sich um Mandantenübergreifende Verschiebungen handelt, nicht um meine Onboarding-und offboarding-Moves?**

Verwenden Sie den `-flags` -Parameter. Hier ein Beispiel.

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**Können Sie Beispielskripts zum Kopieren von Attributen bereitstellen, die in Tests verwendet werden?**

> [!Note]
> Beispiel – keine Garantie<br/>Dieses Skript nimmt eine Verbindung mit beiden Quellpostfächern (zum Abrufen der Quellwerte) und dem lokalen Ziel Active Directory-Domänendienste (zum Stempeln des Benutzerobjekts) an. Wenn für Source das Verfahren für die Wiederherstellung von Einzelelementen aktiviert ist, legen Sie dies für das Ziel Konto fest.  Dadurch wird die Größe des Zielkontos für den Papierkorb auf 100 GB erhöht.

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
**Wie greifen wir an Tag 1 auf Outlook zu, nachdem das use-Postfach verschoben wurde?**

Da nur ein Mandant eine Domäne besitzen kann, wird der frühere primäre SMTPAddress dem Benutzer im Zielmandanten nicht zugeordnet, wenn die Post Fach Verlagerung abgeschlossen ist. nur die dem neuen Mandanten zugeordneten Domänen. Outlook verwendet den neuen UPN users zur Authentifizierung beim Dienst, und das Outlook-Profil erwartet, dass der primäre SMTPAddress der Vorgängerversion dem Postfach im Zielsystem entspricht. Da sich die Legacy Adresse nicht im Ziel System befindet, stellt das Outlook-Profil keine Verbindung her, um das neu verschobene Postfach zu finden. 

Für diese anfängliche Bereitstellung müssen Benutzer ihr Profil mit ihren neuen UPN-, primären SMTP-Adressen und Re-Sync-Ost-Inhalten neu erstellen. 

> [!Note]
> Planen Sie entsprechend, wenn Sie die Benutzer zur Fertigstellung stapeln. Sie müssen die Netzwerkauslastung und-Kapazität berücksichtigen, wenn Outlook-Client Profile erstellt werden und die nachfolgenden Ost-und OAB-Dateien auf Clients heruntergeladen werden. 
 
**Für welche Exchange-RBAC-Rollen muss ich Mitglied sein, um eine Mandantenübergreifende Verlagerung einzurichten oder abzuschließen?**
 
Eine Matrix mit Rollen, die auf der Übernahme von delegierten Aufgaben beim Ausführen einer Post Fach Verlagerung basiert. Derzeit sind zwei Rollen erforderlich:  

- Die erste Rolle ist für eine einmalige Einrichtungsaufgabe, die die Autorisierung zum Verschieben von Inhalt in oder aus Ihrer Mandanten-/organisationsgrenze herstellt. Da das Verschieben von Daten aus ihrer Organisationssteuerung ein wichtiges Anliegen für alle Unternehmen ist, haben wir uns für die höchste zugewiesene Rolle des Organisationsadministrators (OrgAdmin) entschieden. Diese Rolle muss eine neue OrganizationRelationship ändern oder einrichten, die die-MailboxMoveCapability mit der Remoteorganisation definiert. Nur die OrgAdmin kann die MailboxMoveCapability-Einstellung ändern, während andere Attribute in der OrganizationRelationhip vom Verbundfreigabe Administrator verwaltet werden können. 
 
- Die Rolle der Ausführung der tatsächlichen Verschiebe Befehle kann an eine niedrigere Ebene delegiert werden. Der Rolle von Verschieben von Postfächern wird die Möglichkeit zugewiesen, Postfächer mithilfe des Parameters in die oder aus der Organisation zu verschieben `-RemoteTenant` .  

**Wie soll die für targetAddress (TargetDeliveryDomain) ausgewählte SMTP-Adresse für das konvertierte Postfach (in MailUser-Konvertierung) ausgewählt werden?**
 
Exchange-Postfachverschiebungen mit Mrs Craft das targetAddress-Objekt für das ursprüngliche Quellpostfach bei der Konvertierung in ein MailUser durch übereinstimmen einer e-Mail-Adresse (proxyAddress) des Zielobjekts. Der-TargetDeliveryDomain-Wert wird an den Befehl zum Verlegen übergeben, und anschließend wird auf der Zielseite nach einem übereinstimmenden Proxy für diese Domäne gesucht. Wenn eine Übereinstimmung gefunden wird, wird der entsprechende proxyAddress verwendet, um den ExternalEmailAddress (targetAddress) für das konvertierte Postfach (jetzt MailUser)-Objekt festzulegen.
 
**Wie werden Postfachberechtigungen übergangen?**

Zu den Postfachberechtigungen gehören "Senden im Auftrag von" und "Postfachzugriff": 

- Senden im Auftrag von (AD: publicDelegates) speichert den DN von Empfängern mit Zugriff auf das Postfach eines Benutzers als Stellvertretung. Dieser Wert wird in Active Directory gespeichert und wird derzeit nicht als Teil des Post Fach Übergangs gewechselt. Wenn das Quellpostfach publicDelegates festgelegt hat, müssen Sie die publicDelegates im Zielpostfach nach Abschluss der meu-zu-Post Fach Konvertierung in der Zielumgebung mithilfe des Befehls erneut Stempeln `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` . 
 
- Postfachberechtigungen, die im Postfach gespeichert werden, werden mit dem Postfach verschoben, wenn sowohl der Prinzipal als auch der Delegat in das Zielsystem verschoben werden. Beispielsweise wird dem Benutzer TestUser_7 FullAccess für das Post Fach TestUser_8 im Mandanten SourceCompany.onmicrosoft.com erteilt. Nachdem die Post Fach Verlagerung auf TargetCompany.onmicrosoft.com abgeschlossen wurde, werden dieselben Berechtigungen im Zielverzeichnis eingerichtet. Beispiele zum Verwenden von *Get-MailboxPermission* für TestUser_7 in den Quell-und Zielmandanten werden unten angezeigt. Exchange-Cmdlets werden mit dem Präfix Source und Target entsprechend gekennzeichnet. 
 
Hier ist ein Beispiel für die Ausgabe der Postfach-Berechtigung vor einem Wechsel. 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Hier ist ein Beispiel für die Ausgabe der Post Fach Berechtigung nach dem Wechsel. 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Mandantenübergreifende Postfach-und Kalenderberechtigungen werden nicht unterstützt. Sie müssen Prinzipale und Delegaten in konsolidierte Batches verschieben organisieren, damit diese verbundenen Postfächer gleichzeitig vom Quellmandanten übergangen werden. 
 
## <a name="known-issues"></a>Bekannte Probleme 

-  **Problem: Auto Expanded Archives kann nicht migriert werden.** Das Feature für die Mandantenübergreifende Migration unterstützt Migrationen des primären Postfachs und des Archivpostfachs für einen bestimmten Benutzer. Wenn der Benutzer in der Quelle jedoch über ein automatisch erweitertes Archiv verfügt – das bedeutet mehr als ein Archivpostfach, kann das Feature die zusätzlichen Archive nicht migrieren.

- **Problem: Cloud-Mailbenutzer mit nicht im Besitz befindlichen SMTP-proxyAddress blockieren Mrs Moves background.** Beim Erstellen von MailUser-Objekten des Target-Mandanten müssen Sie sicherstellen, dass alle SMTP-Proxyadressen zur Zielmandanten Organisation gehören. Wenn ein SMTP-proxyAddress auf dem Ziel-e-Mail-Benutzer vorhanden ist, der nicht zum lokalen Mandanten gehört, wird die Konvertierung des MailUser in das Postfach verhindert. Dies ist darauf zurückzuführen, dass Postfachobjekte nur e-Mails von Domänen senden können, für die der Mandant autorisierend ist (vom Mandanten beanspruchte Domänen): 
- 
   - Wenn Sie Benutzer lokal mit Azure AD Connect synchronisieren, stellen Sie lokale MailUser-Objekte bereit, wobei ExternalEmailAddress auf den Quellmandanten zeigt, in dem das Postfach vorhanden ist (Laran@Contoso \. onmicrosoft.com), und das PrimarySmtpAddress als Domäne stempelt, die sich im Zielmandanten (Lara.Newton@Northwind \. com) befindet. Diese Werte werden mit dem Mandanten synchronisiert, und ein geeigneter e-Mail-Benutzer ist für die Migration verfügbar. Ein Beispielobjekt wird hier gezeigt.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Die com-Adresse " *contoso. onmicrosoft \. "* ist im Adressfeld "addresses/proxyAddresses" *nicht* vorhanden.

- **Problem: MailUser-Objekte mit "externen" primären SMTP-Adressen werden geändert/auf "interne" Unternehmen beansprucht Domains zurückgesetzt.**

   MailUser-Objekte sind Zeiger auf nicht lokale Postfächer. Im Fall von mandantenübergreifenden Postfachmigrationen verwenden wir MailUser-Objekte, um entweder das Quellpostfach (aus der Perspektive der Zielorganisation) oder das Zielpostfach (aus der Perspektive der Quellorganisation) darzustellen. Die Mailbenutzer verfügen über eine ExternalEmailAddress (targetAddress), die auf die SMTP-Adresse des tatsächlichen Postfachs (ProxyTest \@ Fabrikam \. onmicrosoft.com) und primarySMTP Address verweist, die die angezeigte SMTP-Adresse des Postfachbenutzers im Verzeichnis darstellt. In einigen Organisationen wird die primäre SMTP-Adresse als externe SMTP-Adresse angezeigt, nicht als Adresse, die vom lokalen Mandanten besessen/verifiziert wird (beispielsweise fabrikam.com statt als contoso.com).  Sobald jedoch ein Exchange-Dienstplan Objekt über Lizenzierungs Vorgänge auf das MailUser angewendet wird, wird die primäre SMTP-Adresse so geändert, dass Sie als von der lokalen Organisation verifizierte Domäne angezeigt wird (contoso.com). Es gibt zwei mögliche Gründe:
   
   - Wenn ein Exchange-Dienstplan auf ein MailUser angewendet wird, beginnt der Azure AD Prozess mit der Erzwingung der Proxy Bereinigung, um sicherzustellen, dass die lokale Organisation keine e-Mail-Nachrichten, Spoofing oder e-Mails von einem anderen Mandanten senden kann. Jede SMTP-Adresse in einem Empfängerobjekt mit diesen Dienstplänen wird entfernt, wenn die Adresse nicht von der lokalen Organisation überprüft wird. Wie im Beispiel wird die Fabikam- \. com-Domäne vom Contoso \. -onmicrosoft.com-Mandanten nicht überprüft, sodass durch die Bereinigung diese Fabrikam- \. com-Domäne entfernt wird. Wenn Sie diese externe Domäne auf MailUser speichern möchten, entweder vor der Migration oder nach der Migration, müssen Sie Ihre Migrationsprozesse so ändern, dass Lizenzen nach dem Abschluss oder vor dem Umzug entfernt werden, um sicherzustellen, dass die Benutzer das erwartete externe Branding angewendet haben. Sie müssen sicherstellen, dass das Mailbox-Objekt ordnungsgemäß lizenziert ist, um den e-Mail-Dienst nicht zu beeinträchtigen.<br/><br/>Hier sehen Sie ein Beispielskript zum Entfernen der Dienstpläne für ein MailUser im Contoso \. onmicrosoft.com-Mandanten.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Die Ergebnisse in der zugewiesenen ServicePlans werden hier angezeigt.

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
 
       Die PrimarySmtpAddress des Benutzers wird nicht mehr bereinigt. Die fabrikam.com-Domäne gehört nicht zum contoso.onmicrosoft.com-Mandanten und wird als primäre SMTP-Adresse im Verzeichnis gespeichert.

       Hier ein Beispiel.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Wenn msExchRemoteRecipientType auf 8 (DeprovisionMailbox) festgelegt ist, werden für lokale MailUser, die zum Zielmandanten migriert werden, die Proxy-Scrubbing-Logik in Azure nicht im Besitz befindliche Domänen entfernen und das primarySMTP-Objekt auf eine eigene Domäne zurücksetzen. Durch das Löschen von msExchRemoteRecipientType in der lokalen MailUser wird die Proxy-Scrub-Logik nicht mehr angewendet. <br/><br>Im folgenden finden Sie die vollständige Palette möglicher Dienstpläne, die Exchange Online umfassen.

   | Name                                              |
   |---------------------------------------------------|
   | Erweiterter eDiscovery-Speicher (500GB)               |
   | Kunden-Lockbox                                  |
   | Verhinderung von Datenverlust                              |
   | Exchange Enterprise CAL-Dienste (EoP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (Plan 1)                          |
   | Exchange Online (Plan 2)                          |
   | Exchange Online-Archivierung für Exchange Online     |
   | Exchange Online-Archivierung für Exchange Server     |
   | Exchange Online inaktives Benutzer-Add-on              |
   | Exchange Online-Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Plan 1                            |
   | Exchange Online Pop                               |
   | Exchange Online Protection                        |
   | Informationsbarrieren                              |
   | Information Protection für Office 365 – Premium   |
   | Information Protection für Office 365 – Standard  |
   | Einblicke von myAnalytics                           |
   | Microsoft 365 Advanced Auditing                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (Vollversion)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender für Office 365 (Plan 1)    |
   | Microsoft Defender für Office 365 (Plan 2)    |
   | Office 365 Privileged Access Management           |
   | Premium-Verschlüsselung in Office 365                  |
    
