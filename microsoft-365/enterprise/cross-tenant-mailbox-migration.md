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
ms.openlocfilehash: 7c3b4f82d94888cfa6c63b25f20130a38f8b4c9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919200"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="2fa4f-103">Mandantenübergreifende Postfachmigration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="2fa4f-104">Wenn ein Exchange Online-Mandant Postfächer in einen anderen Mandanten im gleichen Exchange Online-Dienst verschieben musste, müssten sie diese vollständig in den lokalen Dienst verschieben und dann in einen neuen Mandanten integrieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="2fa4f-105">Mit dem neuen mandantenübergreifenden Migrationsfeature können Mandantenadministratoren sowohl in Quell- als auch in Ziel mandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="2fa4f-106">Dadurch wird die Notwendigkeit von Off-Board- und Onboardpostfächern entfernt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="2fa4f-107">In der Regel benötigen Sie bei Fusionen oder Übernahmen die Möglichkeit, Benutzer und Inhalte in einen neuen Mandanten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="2fa4f-108">Wenn der Ziel-Mandant-Administrator die Migration ausgeführt hat, wird dies als Pull-Move bezeichnet, ähnlich wie bei lokalen Migrationen mit Cloud-Onboarding.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="2fa4f-109">Mandantenübergreifende Exchange-Postfachbewegungen werden von Mandantenadministratoren vollständig self-serviced ausgeführt. Dabei werden bekannte Schnittstellen verwendet, die in die größeren Workflows geschrieben werden können, die zum Übergang von Benutzern in ihre neue Organisation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="2fa4f-110">Administratoren können das Über die Verwaltungsrolle Postfächer verschieben verfügbare `New-MigrationBatch` Cmdlet verwenden, um mandantenübergreifende Verschieben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="2fa4f-111">Der Verschiebenprozess umfasst Mandantenautorisierungsüberprüfungen während der Postfachsynchronisierung und -finalisierung.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="2fa4f-112">Die Migration von Benutzern muss im Exchange Online-Ziel-Mandantensystem als MailUsers vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um mandantenübergreifende Bewegungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="2fa4f-113">Für Benutzer, die im Ziel-Mandanten nicht ordnungsgemäß eingerichtet sind, wird beim System ein Fehler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="2fa4f-114">Wenn die Verschieben abgeschlossen sind, wird das Quellsystempostfach in MailUser konvertiert, und die targetAddress (in Exchange als ExternalEmailAddress angezeigt) wird mit der Routingadresse an den Ziel-Mandanten gestempelt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="2fa4f-115">Bei diesem Prozess bleibt das legacy MailUser im Quell-Mandant und ermöglicht eine Zeit der Koexistenz und des E-Mail-Routings.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="2fa4f-116">Wenn Geschäftsprozesse dies zulassen, kann der Quell-Mandant die Quelle MailUser entfernen oder in einen E-Mail-Kontakt konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="2fa4f-117">Mandantenübergreifende Exchange-Postfachmigrationen werden nur für Mandanten in Hybrid- oder Cloud- oder einer beliebigen Kombination der beiden Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="2fa4f-118">In diesem Artikel wird der Prozess für mandantenübergreifende Postfachbewegungen beschrieben und Anleitungen zum Vorbereiten von Quell- und Ziel mandanten für die Inhaltsver verschieben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="2fa4f-119">Vorbereiten von Quell- und Ziel-Mandanten</span><span class="sxs-lookup"><span data-stu-id="2fa4f-119">Preparing source and target tenants</span></span>

<span data-ttu-id="2fa4f-120">Das Mandantenübergreifende Exchange-Postfachmigrationsfeature erfordert autorisierungs- und scoping für mandantenübergreifende Migrationen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="2fa4f-121">Mithilfe der Azure Enterprise-Anwendung und der Key Vault-Speicherlösungen können Mandantenadministratoren jetzt sowohl die Autorisierung als auch das Scoping von Exchange Online-Postfachmigrationen von einem Mandanten zum anderen verwalten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="2fa4f-122">Mandantenübergreifende Postfachbewegungen unterstützen ein Einladungs- und Zustimmungsmodell zum Einrichten einer Azure Active Directory (Azure AD)-Anwendung, die für die Authentifizierung zwischen einem Mandantenpaar verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="2fa4f-123">Zusätzliche Komponenten wie eine Organisationsbeziehung und ein Migrationsendpunkt sind ebenfalls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="2fa4f-124">Dieser Abschnitt enthält weder die spezifischen Schritte, die zum Vorbereiten der MailUser-Benutzerobjekte im Zielverzeichnis erforderlich sind, noch den Beispielbefehl zum Übermitteln eines Migrationsbatches.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="2fa4f-125">Weitere Informationen [finden Sie unter Prepare target user objects for migration.](#prepare-target-user-objects-for-migration)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fa4f-126">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2fa4f-126">Prerequisites</span></span>

<span data-ttu-id="2fa4f-127">Das mandantenübergreifende Postfach verschieben-Feature [erfordert,](/azure/key-vault/basic-concepts) dass Azure Key Vault eine mandantenpaarspezifische Azure-Anwendung zum sicheren Speichern und Zugreifen auf das Zertifikat/den geheimen Schlüssel einrichten kann, das zum Authentifizieren und Autorisieren der Postfachmigration von einem Mandanten zum anderen verwendet wird. Dabei werden alle Anforderungen zum Freigeben von Zertifikaten/Geheimschlüsseln zwischen Mandanten entfernt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="2fa4f-128">Stellen Sie vor dem Start sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um Azure Key Vault, Die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="2fa4f-129">In der Regel verfügt der globale Administrator über die Berechtigung zum Ausführen aller Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="2fa4f-130">Darüber hinaus sind E-Mail-aktivierte Sicherheitsgruppen im Quell-Mandant vor dem Ausführen des Setups erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="2fa4f-131">Diese Gruppen werden verwendet, um die Liste der Postfächer, die vom Quell-Mandanten (oder manchmal auch als Ressourcen-Mandant bezeichnet) zum Ziel-Mandanten verschoben werden können, zu bereichern.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="2fa4f-132">Auf diese Weise kann der Quell-Mandant-Administrator die bestimmte Gruppe von Postfächern einschränken oder beschränken, die verschoben werden müssen, um zu verhindern, dass unbeabsichtigte Benutzer migriert werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="2fa4f-133">Geschachtelte Gruppen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-133">Nested groups are not supported.</span></span>

<span data-ttu-id="2fa4f-134">Sie müssen auch mit Ihrem vertrauenswürdigen Partnerunternehmen kommunizieren (mit dem Sie Postfächer verschieben), um ihre Microsoft 365-Mandanten-ID zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="2fa4f-135">Diese Mandanten-ID wird im Feld Organisationsbeziehung `DomainName` verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="2fa4f-136">Um die Mandanten-ID eines Abonnements zu erhalten, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="2fa4f-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="2fa4f-137">Klicken Sie auf das Kopiersymbol für die Tenant ID-Eigenschaft, um sie in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="2fa4f-138">Hier sehen Sie, wie der Prozess funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Mandantenvorbereitung für die Postfachmigration.":::

<span data-ttu-id="2fa4f-140">[Sehen Sie sich eine größere Version dieses Bilds an.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="2fa4f-141">Vorbereiten von Mandanten</span><span class="sxs-lookup"><span data-stu-id="2fa4f-141">Prepare tenants</span></span>

<span data-ttu-id="2fa4f-142">Auf einer hohen Ebene werden die folgenden Konfigurationsaktionen beim Ausführen der Setupskripts ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="2fa4f-143">Bereiten Sie den Ziel mandanten vor:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="2fa4f-144">Wenn keine vorhandene Azure-Ressourcengruppe bereitgestellt wird, wird ein neues (SCRIPT) erstellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="2fa4f-145">Wenn kein vorhandener Schlüsseltresor bereitgestellt wird, wird ein neues (SCRIPT) erstellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="2fa4f-146">Für die Office 365 Exchange Online Mailbox Migration Application (SCRIPT) wird eine neue Zugriffsrichtlinie erstellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="2fa4f-147">Ein neues Zertifikat wird erstellt (oder vorhanden, falls angegeben), um das Geheimnis der Migrationsanwendung (SCRIPT) zu halten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="2fa4f-148">Eine neue Azure AD-Anwendung wird erstellt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="2fa4f-149">Das Zertifikat/der geheime Schlüssel wird in die Migrationsanwendung (SCRIPT) hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="2fa4f-150">Berechtigungen für die Postfachmigration werden der Anwendung (SCRIPT) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="2fa4f-151">Das Bereitstellungsskript hält an, bis der Zieladministrator der eigenen Anwendung (SCRIPT) zuwilligt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="2fa4f-152">Der Ziel-Mandant-Administrator ist mit den Berechtigungen einverstanden, die der Anwendung erteilt werden (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="2fa4f-153">Eine Organisationsbeziehung wird zum Ziel-Mandant (SCRIPT) erstellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="2fa4f-154">Ein Migrationsendpunkt wird erstellt, um Postfächer an den Ziel mandanten (SCRIPT) zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="2fa4f-155">Bereiten Sie den Quell-Mandanten vor:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="2fa4f-156">Der Quell-Mandant-Administrator akzeptiert die Zustimmung zur Einladung der Postfachmigrationsanwendung vom Ziel-Mandanten (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="2fa4f-157">Der Quell-Mandantenadministrator erstellt eine E-Mail-aktivierte Sicherheitsgruppe in ihrem Mandanten, die die Liste der Postfächer enthält, die von der Migrationsanwendung verschoben werden dürfen (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="2fa4f-158">Es wird eine Organisationsbeziehung mit dem Ziel-Mandanten erstellt, der an die Postfachmigrationsanwendung annimmt, die für die OAuth-Überprüfung verwendet werden soll, um die Verschiebenanforderung (SCRIPT) zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="2fa4f-159">Schritt-für-Schritt-Anweisungen für den Ziel-Mandantenadministrator</span><span class="sxs-lookup"><span data-stu-id="2fa4f-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="2fa4f-160">Laden Sie SetupCrossTenantRelationshipForTargetTenant.ps1 Skript für das Ziel-Mandanten-Setup aus dem [GitHub-Repository herunter.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="2fa4f-161">Speichern Sie das Skript (SetupCrossTenantRelationshipForTargetTenant.ps1) auf dem Computer, von dem Sie das Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="2fa4f-162">Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Exchange Online-Ziel-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="2fa4f-163">Stellen Sie erneut sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um den Azure Key Vault-Speicher und -Zertifikat, die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="2fa4f-164">Ändern Sie das Verzeichnis des Dateiordners in den Skriptspeicherort, oder überprüfen Sie, ob das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Der Remote-PowerShell-Sitzung befindet.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="2fa4f-165">Führen Sie das Skript mit den folgenden Parametern und Werten aus.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="2fa4f-166">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fa4f-166">Parameter</span></span> | <span data-ttu-id="2fa4f-167">Wert</span><span class="sxs-lookup"><span data-stu-id="2fa4f-167">Value</span></span> | <span data-ttu-id="2fa4f-168">Erforderlich oder Optional</span><span class="sxs-lookup"><span data-stu-id="2fa4f-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="2fa4f-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2fa4f-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="2fa4f-170">Ziel-Mandantendomäne, z. B. fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="2fa4f-171">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-171">Required</span></span> |
    | <span data-ttu-id="2fa4f-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2fa4f-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="2fa4f-173">Quell-Mandantendomäne, z. B. contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="2fa4f-174">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-174">Required</span></span> |
    | <span data-ttu-id="2fa4f-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="2fa4f-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="2fa4f-176">E-Mail-Adresse des Quell-Mandantenadministrators.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="2fa4f-177">Dies ist der Quell-Mandantenadministrator, der der Verwendung der Vom Zieladministrator gesendeten Postfachmigrationsanwendung zuwilligt. Dies ist der Administrator, der die E-Mail-Einladung für die Anwendung erhält.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="2fa4f-178">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-178">Required</span></span> |
    | <span data-ttu-id="2fa4f-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="2fa4f-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="2fa4f-180">GuiD (Source Tenant Organization ID).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="2fa4f-181">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-181">Required</span></span> |
    | <span data-ttu-id="2fa4f-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="2fa4f-182">-SubscriptionId</span></span>                             | <span data-ttu-id="2fa4f-183">Das Zum Erstellen von Ressourcen zu verwendende Azure-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="2fa4f-184">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-184">Required</span></span> |
    | <span data-ttu-id="2fa4f-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="2fa4f-185">-ResourceGroup</span></span>                              | <span data-ttu-id="2fa4f-186">Azure-Ressourcengruppenname, der den Schlüsseltresor enthält oder enthält.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="2fa4f-187">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-187">Required</span></span> |
    | <span data-ttu-id="2fa4f-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="2fa4f-188">-KeyVaultName</span></span>                               | <span data-ttu-id="2fa4f-189">Azure Key Vault-Instanz, in der Ihr Zertifikat/geheimer Postfachmigrationsanwendung gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="2fa4f-190">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-190">Required</span></span> |
    | <span data-ttu-id="2fa4f-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="2fa4f-191">-CertificateName</span></span>                            | <span data-ttu-id="2fa4f-192">Zertifikatname beim Generieren oder Suchen nach Zertifikaten im Schlüsseltresor.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="2fa4f-193">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-193">Required</span></span> |
    | <span data-ttu-id="2fa4f-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="2fa4f-194">-CertificateSubject</span></span>                         | <span data-ttu-id="2fa4f-195">Name des Azure Key Vault-Zertifikatsubjekts, z. B. CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="2fa4f-196">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-196">Required</span></span> |
    | <span data-ttu-id="2fa4f-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="2fa4f-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="2fa4f-198">E-Mail-Migrationsanwendung, die verwendet werden soll, wenn sie bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="2fa4f-199">Optional</span><span class="sxs-lookup"><span data-stu-id="2fa4f-199">Optional</span></span> |
    | <span data-ttu-id="2fa4f-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="2fa4f-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="2fa4f-201">Die erforderlichen Berechtigungen für die Postfachmigrationsanwendung, z. B. Exchange oder MSGraph (Exchange zum Verschieben von Postfächern, MSGraph für die Verwendung dieser Anwendung zum Senden einer Einladung zum Zustimmungslink an den Ressourcen-Mandanten).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="2fa4f-202">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2fa4f-202">Required</span></span> |
    | <span data-ttu-id="2fa4f-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="2fa4f-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="2fa4f-204">Parameter für die Verwendung der Anwendung, die für die Migration zum Senden einer Einladung zum Zustimmungslink an den Quell-Mandantenadministrator erstellt wurde. Wenn dies nicht vorhanden ist, werden die Anmeldeinformationen des Zieladministrators aufgefordert, eine Verbindung mit dem Azure-Einladungs-Manager herzustellen und die Einladung als Zieladministrator zu senden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="2fa4f-205">Optional</span><span class="sxs-lookup"><span data-stu-id="2fa4f-205">Optional</span></span> |
    | <span data-ttu-id="2fa4f-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="2fa4f-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="2fa4f-207">Das Speicherkonto, in dem die Überwachungsprotokolle von Key Vault gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="2fa4f-208">Optional</span><span class="sxs-lookup"><span data-stu-id="2fa4f-208">Optional</span></span> |
    | <span data-ttu-id="2fa4f-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="2fa4f-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="2fa4f-210">Die Ressourcengruppe, die das Speicherkonto zum Speichern von Key Vault-Überwachungsprotokollen enthält.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="2fa4f-211">Optional</span><span class="sxs-lookup"><span data-stu-id="2fa4f-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="2fa4f-212">Stellen Sie sicher, dass Sie das Azure AD PowerShell-Modul installiert haben, bevor Sie die Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="2fa4f-213">Installationsschritte ![ ](/powershell/azure/install-az-ps?view=azps-5.1.0) finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-213">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="2fa4f-214">Das Skript hält an und bittet Sie, die während dieses Vorgangs erstellte Exchange-Postfachmigrationsanwendung zu akzeptieren oder zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="2fa4f-215">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-215">Here is an example.</span></span>

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

7. <span data-ttu-id="2fa4f-216">In der Remote-PowerShell-Sitzung wird eine URL angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="2fa4f-217">Kopieren Sie den Link, der für Ihre Mandanten zustimmung bereitgestellt wurde, und fügen Sie ihn in einen Webbrowser ein.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="2fa4f-218">Melden Sie sich mit Ihren Anmeldeinformationen für den globalen Administrator an.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="2fa4f-219">Wenn der folgende Bildschirm angezeigt wird, wählen Sie **Akzeptieren aus.**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogfeld Berechtigungen akzeptieren":::

9. <span data-ttu-id="2fa4f-221">Wechseln Sie zurück zur Remote-PowerShell-Sitzung, und fahren Sie mit enter fort.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="2fa4f-222">Das Skript konfiguriert die verbleibenden Setupobjekte.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="2fa4f-223">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="2fa4f-224">Das Setup des Zieladministrators ist nun abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="2fa4f-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="2fa4f-225">Schritt-für-Schritt-Anweisungen für den Quell-Mandantenadministrator</span><span class="sxs-lookup"><span data-stu-id="2fa4f-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="2fa4f-226">Melden Sie sich bei Ihrem Postfach als -ResourceTenantAdminEmail an, das vom Zieladministrator während des Setups angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="2fa4f-227">Suchen Sie die E-Mail-Einladung vom Ziel-Mandanten, und wählen Sie dann die Schaltfläche **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogfeld &quot;Eingeladen&quot;":::

2. <span data-ttu-id="2fa4f-229">Wählen **Sie Annehmen** aus, um die Einladung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialogfeld zum Akzeptieren von Berechtigungen":::

   > [!NOTE]
   > <span data-ttu-id="2fa4f-231">Wenn Sie diese E-Mail nicht erhalten oder nicht finden können, wurde dem Zielmandantadministrator eine direkte URL bereitgestellt, die Sie erhalten können, um die Einladung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="2fa4f-232">Die URL sollte in der Aufzeichnung der Remote-PowerShell-Sitzung des Ziel-Mandantenadministrators enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="2fa4f-233">Erstellen Sie im Microsoft 365 Admin Center oder in einer Remote-PowerShell-Sitzung eine oder mehrere E-Mail-aktivierte Sicherheitsgruppen, um die Liste der Postfächer zu steuern, die der Ziel-Mandant vom Quell-Mandant zum Ziel mandanten ziehen (verschieben) darf.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="2fa4f-234">Sie müssen diese Gruppe nicht im Voraus auffüllen, aber es muss mindestens eine Gruppe bereitgestellt werden, um die Setupschritte (Skript) ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="2fa4f-235">Schachtelgruppen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="2fa4f-236">Laden Sie SetupCrossTenantRelationshipForResourceTenant.ps1 Skript für das Setup des Quell-Mandanten aus dem GitHub-Repository herunter: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="2fa4f-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="2fa4f-237">Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Quell-Mandanten mit Ihren Exchange-Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="2fa4f-238">Globale Administratorberechtigungen sind nicht erforderlich, um den Quell-Mandanten zu konfigurieren, sondern nur den Ziel-Mandanten aufgrund des Erstellungsprozesses der Azure-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="2fa4f-239">Ändern Sie das Verzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Der Remote-PowerShell-Sitzung befindet.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="2fa4f-240">Führen Sie das Skript mit den folgenden erforderlichen Parametern und Werten aus.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="2fa4f-241">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fa4f-241">Parameter</span></span> | <span data-ttu-id="2fa4f-242">Wert</span><span class="sxs-lookup"><span data-stu-id="2fa4f-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="2fa4f-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="2fa4f-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="2fa4f-244">E-Mail-aktivierte Sicherheitsgruppe, die vom Quell-Mandant für die Identitäten/Postfächer erstellt wurde, die sich im Bereich der Migration befinden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="2fa4f-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2fa4f-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="2fa4f-246">Quell-Mandantendomänenname, z. B. contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-246">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="2fa4f-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="2fa4f-247">-ApplicationId</span></span> | <span data-ttu-id="2fa4f-248">Azure-Anwendungs-ID (GUID) der Anwendung, die für die Migration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="2fa4f-249">Anwendungs-ID, die über Ihr Azure-Portal (Azure AD, Unternehmensanwendungen, App-Name, Anwendungs-ID) oder in Ihrer Einladungs-E-Mail enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="2fa4f-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2fa4f-250">-TargetTenantDomain</span></span> | <span data-ttu-id="2fa4f-251">Ziel-Mandantendomänenname, z. B. fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-251">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="2fa4f-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="2fa4f-252">-TargetTenantId</span></span> | <span data-ttu-id="2fa4f-253">Mandanten-ID des Ziel-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="2fa4f-254">Beispielsweise ist die Azure AD-Mandanten-ID von contoso \. onmicrosoft.com Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="2fa4f-255">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="2fa4f-256">Das Setup des Quelladministrators ist nun abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="2fa4f-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="2fa4f-257">Überprüfen des Setups</span><span class="sxs-lookup"><span data-stu-id="2fa4f-257">Verify setup</span></span>

<span data-ttu-id="2fa4f-258">Stellen Sie sicher, dass die Organisationsbeziehungen in Quell- und Ziel mandanten und Migrationsendpunkt im Ziel erfolgreich erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="2fa4f-259">Ziel-Mandant</span><span class="sxs-lookup"><span data-stu-id="2fa4f-259">Target tenant</span></span>

<span data-ttu-id="2fa4f-260">**Organisationsbeziehung**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-260">**Organization relationship**</span></span>

<span data-ttu-id="2fa4f-261">Stellen Sie sicher, dass das Organisationsbeziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="2fa4f-262">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="2fa4f-263">**Migrationsendpunkt**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-263">**Migration endpoint**</span></span>

<span data-ttu-id="2fa4f-264">Stellen Sie sicher, dass das Migrationsendpunktobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="2fa4f-265">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="2fa4f-266">Quell-Mandant</span><span class="sxs-lookup"><span data-stu-id="2fa4f-266">Source tenant</span></span>

<span data-ttu-id="2fa4f-267">**Organisationsbeziehung**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-267">**Organization relationship**</span></span>

<span data-ttu-id="2fa4f-268">Stellen Sie sicher, dass das Organisationsbeziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="2fa4f-269">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="2fa4f-270">Überprüfen des Setupskripts</span><span class="sxs-lookup"><span data-stu-id="2fa4f-270">Verify Setup Script</span></span>

<span data-ttu-id="2fa4f-271">Wenn Bei der Konfiguration der Quell- oder Ziel-Mandanten Fehler auftreten, können Sie das Skript VerifySetup.ps1 [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ausführen und die Ausgabe überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-271">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="2fa4f-272">Im Folgenden finden Sie ein Beispiel für die Ausführung VerifySetup.ps1 für den Ziel-Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-272">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="2fa4f-273">Im Folgenden finden Sie ein Beispiel für VerifySetup.ps1 für den Quell-Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-273">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="2fa4f-274">Verschieben von Postfächern zurück zur ursprünglichen Quelle</span><span class="sxs-lookup"><span data-stu-id="2fa4f-274">Move mailboxes back to the original source</span></span>

<span data-ttu-id="2fa4f-275">Wenn ein Postfach zurück zum ursprünglichen Quell-Mandant verschoben werden muss, müssen die gleichen Schritte und Skripts sowohl in neuen Quell- als auch in neuen Ziel-Mandanten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-275">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="2fa4f-276">Das vorhandene Organisationsbeziehungsobjekt wird aktualisiert oder angefügt, nicht neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-276">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="2fa4f-277">Vorbereiten von Zielbenutzerobjekten für die Migration</span><span class="sxs-lookup"><span data-stu-id="2fa4f-277">Prepare target user objects for migration</span></span>

<span data-ttu-id="2fa4f-278">Die Migration von Benutzern muss im Ziel mandanten- und Exchange Online-System (als MailUsers) vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um mandantenübergreifende Bewegungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-278">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="2fa4f-279">Für Benutzer, die im Ziel-Mandanten nicht ordnungsgemäß eingerichtet sind, wird beim System ein Fehler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-279">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="2fa4f-280">Im folgenden Abschnitt werden die MailUser-Objektanforderungen für den Ziel mandanten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-280">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2fa4f-281">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2fa4f-281">Prerequisites</span></span>
  
<span data-ttu-id="2fa4f-282">Sie müssen sicherstellen, dass die folgenden Objekte und Attribute in der Zielorganisation festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-282">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="2fa4f-283">Für alle Postfächer, die aus einer Quellorganisation verschoben werden, müssen Sie ein MailUser-Objekt in der Zielorganisation bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-283">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="2fa4f-284">Ziel-MailUser muss über die folgenden Attribute aus dem Quellpostfach verfügen oder dem neuen User-Objekt zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-284">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="2fa4f-285">ExchangeGUID (direkter Fluss von Quelle zu Ziel) – Die Postfach-GUID muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-285">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="2fa4f-286">Der Verschiebevorgang wird nicht fortgesetzt, wenn dies für das Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-286">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="2fa4f-287">ArchiveGUID (direkter Fluss von Quelle zu Ziel) – Die Guid des Archivs muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-287">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="2fa4f-288">Der Verschiebevorgang wird nicht fortgesetzt, wenn dies für das Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-288">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="2fa4f-289">(Dies ist nur erforderlich, wenn das Quellpostfach Archive aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-289">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="2fa4f-290">LegacyExchangeDN (flow as proxyAddress, "x500: ") – Der <LegacyExchangeDN> LegacyExchangeDN muss auf ziel-MailUser als x500: proxyAddress vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-290">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="2fa4f-291">Die Verschiebeprozesse werden nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-291">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="2fa4f-292">UserPrincipalName – UPN richtet sich an der NEUEN Identität oder dem Zielunternehmen des Benutzers aus (z. B. user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-292">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="2fa4f-293">Primäre SMTPAddress– Primäre SMTP-Adresse richtet sich nach dem NEUEN Unternehmen des Benutzers aus (z. B. user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-293">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="2fa4f-294">TargetAddress/ExternalEmailAddress – MailUser referenziert das aktuelle Postfach des Benutzers, das im Quell-Mandant gehostet wird (z. B. user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-294">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="2fa4f-295">Stellen Sie beim Zuweisen dieses Werts sicher, dass Sie auch PrimarySMTPAddress zugewiesen haben bzw. zuweisen, oder dieser Wert gibt den PrimarySMTPAddress-Wert an, der zu Verschiebefehlern führen wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-295">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="2fa4f-296">Sie können keine älteren SMTP-Proxyadressen aus dem Quellpostfach zu Ziel-MailUser hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-296">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="2fa4f-297">Sie können z. B. keine contoso.com für die MEU in fabrikam.onmicrosoft.com Mandantenobjekten verwalten).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-297">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="2fa4f-298">Domänen sind nur einem Azure AD- oder Exchange Online-Mandanten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-298">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="2fa4f-299">Beispiel **für ein** MailUser-Zielobjekt:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-299">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="2fa4f-300">Attribut</span><span class="sxs-lookup"><span data-stu-id="2fa4f-300">Attribute</span></span>             | <span data-ttu-id="2fa4f-301">Wert</span><span class="sxs-lookup"><span data-stu-id="2fa4f-301">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="2fa4f-302">Alias</span><span class="sxs-lookup"><span data-stu-id="2fa4f-302">Alias</span></span>                 | <span data-ttu-id="2fa4f-303">Laran</span><span class="sxs-lookup"><span data-stu-id="2fa4f-303">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="2fa4f-304">RecipientType</span><span class="sxs-lookup"><span data-stu-id="2fa4f-304">RecipientType</span></span>         | <span data-ttu-id="2fa4f-305">MailUser</span><span class="sxs-lookup"><span data-stu-id="2fa4f-305">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="2fa4f-306">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="2fa4f-306">RecipientTypeDetails</span></span>  | <span data-ttu-id="2fa4f-307">MailUser</span><span class="sxs-lookup"><span data-stu-id="2fa4f-307">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="2fa4f-308">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2fa4f-308">UserPrincipalName</span></span>     | <span data-ttu-id="2fa4f-309">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-309">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="2fa4f-310">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="2fa4f-310">PrimarySmtpAddress</span></span>    | <span data-ttu-id="2fa4f-311">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-311">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="2fa4f-312">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="2fa4f-312">ExternalEmailAddress</span></span>  | <span data-ttu-id="2fa4f-313">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-313">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="2fa4f-314">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="2fa4f-314">ExchangeGuid</span></span>          | <span data-ttu-id="2fa4f-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="2fa4f-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="2fa4f-316">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="2fa4f-316">LegacyExchangeDN</span></span>      | <span data-ttu-id="2fa4f-317">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="2fa4f-317">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="2fa4f-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="2fa4f-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="2fa4f-319">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="2fa4f-319">EmailAddresses</span></span>        | <span data-ttu-id="2fa4f-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="2fa4f-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="2fa4f-321">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="2fa4f-321">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="2fa4f-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="2fa4f-323">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-323">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="2fa4f-324">Beispiel **für das** Quellpostfachobjekt:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-324">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="2fa4f-325">Attribut</span><span class="sxs-lookup"><span data-stu-id="2fa4f-325">Attribute</span></span>             | <span data-ttu-id="2fa4f-326">Wert</span><span class="sxs-lookup"><span data-stu-id="2fa4f-326">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="2fa4f-327">Alias</span><span class="sxs-lookup"><span data-stu-id="2fa4f-327">Alias</span></span>                 | <span data-ttu-id="2fa4f-328">Laran</span><span class="sxs-lookup"><span data-stu-id="2fa4f-328">LaraN</span></span>                                                                    |
     | <span data-ttu-id="2fa4f-329">RecipientType</span><span class="sxs-lookup"><span data-stu-id="2fa4f-329">RecipientType</span></span>         | <span data-ttu-id="2fa4f-330">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="2fa4f-330">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="2fa4f-331">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="2fa4f-331">RecipientTypeDetails</span></span>  | <span data-ttu-id="2fa4f-332">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="2fa4f-332">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="2fa4f-333">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2fa4f-333">UserPrincipalName</span></span>     | <span data-ttu-id="2fa4f-334">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-334">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="2fa4f-335">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="2fa4f-335">PrimarySmtpAddress</span></span>    | <span data-ttu-id="2fa4f-336">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-336">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="2fa4f-337">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="2fa4f-337">ExchangeGuid</span></span>          | <span data-ttu-id="2fa4f-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="2fa4f-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="2fa4f-339">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="2fa4f-339">LegacyExchangeDN</span></span>      | <span data-ttu-id="2fa4f-340">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="2fa4f-340">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="2fa4f-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="2fa4f-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="2fa4f-342">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="2fa4f-342">EmailAddresses</span></span>        | <span data-ttu-id="2fa4f-343">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-343">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="2fa4f-344">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fa4f-344">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="2fa4f-345">Zusätzliche Attribute sind möglicherweise bereits in der Exchange-Hybrid-Rückschreiben enthalten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-345">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="2fa4f-346">Andern falls nicht, sollten sie eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-346">If not, they should be included.</span></span> 
   - <span data-ttu-id="2fa4f-347">msExchBlockedSendersHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-347">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="2fa4f-348">msExchSafeRecipientsHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-348">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="2fa4f-349">msExchSafeSendersHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-349">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="2fa4f-350">Wenn sich das Quellpostfach auf LitigationHold befindet und die Größe des Quellpostfachs "Wiederherstellbare Elemente" größer als die Standardgröße der Datenbank (30 GB) ist, wird das Verschieben nicht fortgesetzt, da das Zielkontingent kleiner als die Größe des Quellpostfachs ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-350">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="2fa4f-351">Sie können das MailUser-Zielobjekt so aktualisieren, dass die ELC-Postfachflags von der Quellumgebung zum Ziel verschoben werden. Dadurch wird das Zielsystem ausgelöst, um das Kontingent von MailUser auf 100 GB zu erweitern, sodass der Wechsel zum Ziel ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-351">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="2fa4f-352">Diese Anweisungen funktionieren nur für Hybrididentität mit Azure AD Connect, da die Befehle zum Stempeln der ELC-Flags nicht für Mandantenadministratoren verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-352">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="2fa4f-353">BEISPIEL – AS IS, NO WARRANTY</span><span class="sxs-lookup"><span data-stu-id="2fa4f-353">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="2fa4f-354">Dieses Skript setzt eine Verbindung mit dem Quellpostfach (um Quellwerte zu erhalten) und dem lokalen Active Directory-Ziel (zum Stempeln des ADUser-Objekts) voraus.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-354">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="2fa4f-355">Wenn für die Quelle ein Rechtsstreit oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto ein.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-355">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="2fa4f-356">Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-356">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="2fa4f-357">Nicht hybride Ziel-Mandanten können das Kontingent für den Ordner "Wiederherstellbare Elemente" für die MailUsers vor der Migration ändern, indem Sie den folgenden Befehl ausführen, um das Litigation Hold für das MailUser-Objekt zu aktivieren und das Kontingent auf 100 GB zu erhöhen: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="2fa4f-357">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="2fa4f-358">Beachten Sie, dass dies für Mandanten in Hybrid nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-358">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="2fa4f-359">Benutzer in der Zielorganisation müssen mit entsprechenden Exchange Online-Abonnements lizenziert werden, die für die Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-359">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="2fa4f-360">Sie können eine Lizenz vor dem Verschieben eines Postfachs anwenden, aber nur, wenn das Ziel-MailUser ordnungsgemäß mit ExchangeGUID und Proxyadressen eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-360">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="2fa4f-361">Das Anwenden einer Lizenz vor dem Anwenden der ExchangeGUID führt zu einem neuen Postfach, das in der Zielorganisation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-361">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="2fa4f-362">Wenn Sie eine Lizenz auf ein Mailbox- oder MailUser-Objekt anwenden, werden alle SMTP-Typproxyaddresses bereinigunget, um sicherzustellen, dass nur überprüfte Domänen im Exchange EmailAddresses-Array enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-362">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="2fa4f-363">Sie müssen sicherstellen, dass das Ziel-MailUser-Ziel keine vorherige ExchangeGuid-Version hat, die nicht mit der ExchangeGuid-Quelle übereinstimmen kann.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-363">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="2fa4f-364">Dies kann auftreten, wenn die Ziel-MEU zuvor für Exchange Online lizenziert und ein Postfach bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-364">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="2fa4f-365">Wenn das Ziel-MailUser zuvor für exchangeGuid lizenziert wurde oder über eine ExchangeGuid verfügte, die nicht mit der ExchangeGuid-Quelle übereinstimmen, müssen Sie eine Bereinigung der Cloud-MEU durchführen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-365">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="2fa4f-366">Für diese Cloud-MEUs können Sie `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-366">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="2fa4f-367">Dieser Vorgang ist unwiderruflich.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-367">This process is irreversible.</span></span> <span data-ttu-id="2fa4f-368">Wenn das Objekt über ein softDeleted-Postfach verfügt, kann es nach diesem Zeitpunkt nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-368">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="2fa4f-369">Nach dem Löschen können Sie jedoch das richtige ExchangeGuid-Objekt mit dem Zielobjekt synchronisieren, und MRS verbindet das Quellpostfach mit dem neu erstellten Zielpostfach.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-369">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="2fa4f-370">(Referenz-EHLO-Blog zum neuen Parameter.)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-370">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="2fa4f-371">Suchen Sie Objekte, die zuvor Postfächer waren, mithilfe dieses Befehls.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-371">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="2fa4f-372">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-372">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="2fa4f-373">Löschen Sie das soft-deleted-Postfach mit diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-373">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="2fa4f-374">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-374">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="2fa4f-375">Durchführen von Postfachmigrationen</span><span class="sxs-lookup"><span data-stu-id="2fa4f-375">Perform mailbox migrations</span></span>

<span data-ttu-id="2fa4f-376">Mandantenübergreifende Exchange-Postfachmigrationen werden als Migrationsbatches übermittelt, die vom Ziel mandanten initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-376">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="2fa4f-377">Dies ähnelt der Art und Weise, wie Migrationsbatches beim Einsteigen bei der Migration von lokalen Exchange zu Microsoft 365 funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-377">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="2fa4f-378">Erstellen von Migrationsbatches</span><span class="sxs-lookup"><span data-stu-id="2fa4f-378">Create Migration batches</span></span>

<span data-ttu-id="2fa4f-379">Im Folgenden finden Sie ein Beispiel für ein Migrationsbatch-Cmdlet zum Starten von Bewegungen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-379">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="2fa4f-380">Die E-Mail-Adresse in der CSV-Datei muss die im Ziel-Mandant angegebene Adresse sein, nicht der Quell-Mandant.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-380">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="2fa4f-381">Die Migrationsbatchübermittlung wird auch vom neuen Exchange Admin Center unterstützt, wenn die mandantenübergreifende Option ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-381">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="2fa4f-382">Aktualisieren von lokalen MailUsers</span><span class="sxs-lookup"><span data-stu-id="2fa4f-382">Update on-premises MailUsers</span></span>

<span data-ttu-id="2fa4f-383">Sobald das Postfach von Quelle zu Ziel verschoben wird, sollten Sie sicherstellen, dass die lokalen E-Mail-Benutzer, sowohl Source als auch Target, mit dem neuen targetAddress aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-383">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="2fa4f-384">In den Beispielen ist die targetDeliveryDomain, die in der Bewegung verwendet wird, **contoso.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-384">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="2fa4f-385">Aktualisieren Sie die E-Mail-Benutzer mit dieser targetAddress.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-385">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="2fa4f-386">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="2fa4f-386">Frequently asked questions</span></span>

<span data-ttu-id="2fa4f-387">**Müssen wir RemoteMailboxen nach dem Verschieben lokal in der Quelle aktualisieren?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-387">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="2fa4f-388">Ja, Sie sollten die targetAddress (RemoteRoutingAddress/ExternalEmailAddress) der lokalen Quellbenutzer aktualisieren, wenn das Quell-Mandantenpostfach in den Ziel mandanten verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-388">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="2fa4f-389">Während das E-Mail-Routing den Empfehlungen für mehrere E-Mail-Benutzer mit unterschiedlichen targetAddresses folgen kann, müssen Frei/Gebucht-Suchen für E-Mail-Benutzer auf den Speicherort des Postfachbenutzers zielen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-389">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="2fa4f-390">Frei/Gebucht-Suchen verfolgen nicht mehrere Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-390">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="2fa4f-391">**Migriert der Inhalt des Teams-Chatordners mandantenübergreifende Inhalte?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-391">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="2fa4f-392">Nein, der Inhalt des Teams-Chatordners wird nicht mandantenübergreifende migriert.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-392">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="2fa4f-393">**Wie kann ich nur mandantenübergreifende Und nicht meine Onboarding- und Off-Boarding-Bewegungen sehen?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-393">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="2fa4f-394">Verwenden Sie den `-flags` Parameter.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-394">Use the `-flags` parameter.</span></span> <span data-ttu-id="2fa4f-395">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-395">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="2fa4f-396">**Können Sie Beispielskripts zum Kopieren von Attributen bereitstellen, die in Tests verwendet werden?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-396">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="2fa4f-397">BEISPIEL – AS IS, NO WARRANTY</span><span class="sxs-lookup"><span data-stu-id="2fa4f-397">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="2fa4f-398">Dieses Skript setzt eine Verbindung mit dem Quellpostfach (zum Abspeichern von Quellwerten) und den lokalen Active Directory-Domänendiensten (zum Stempeln des ADUser-Objekts) voraus.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-398">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="2fa4f-399">Wenn für die Quelle ein Rechtsstreit oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto ein.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-399">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="2fa4f-400">Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-400">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="2fa4f-401">**Wie greifen wir auf Outlook an Tag 1 zu, nachdem das Verwendungspostfach verschoben wurde?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-401">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="2fa4f-402">Da nur ein Mandant eine Domäne besitzen kann, wird die frühere primäre SMTPAddress dem Benutzer im Ziel-Mandant nicht zugeordnet, wenn die Postfach verschieben abgeschlossen ist. nur die Domänen, die dem neuen Mandanten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-402">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="2fa4f-403">Outlook verwendet den neuen BENUTZER-UPN, um sich beim Dienst zu authentifizieren, und das Outlook-Profil erwartet, dass das primäre SMTPAddress-Legacy für das Postfach im Zielsystem zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-403">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="2fa4f-404">Da sich die Legacyadresse nicht im Zielsystem befindet, wird im Outlook-Profil keine Verbindung hergestellt, um das neu verschobene Postfach zu finden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-404">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="2fa4f-405">Für diese anfängliche Bereitstellung müssen Benutzer ihr Profil mit dem neuen UPN, der primären SMTP-Adresse und dem erneuten Synchronisieren von OST-Inhalten neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-405">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="2fa4f-406">Planen Sie entsprechend, während Sie Ihre Benutzer für den Abschluss batchen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-406">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="2fa4f-407">Sie müssen die Netzwerkauslastung und -kapazität berücksichtigen, wenn Outlook-Clientprofile erstellt und nachfolgende OST- und OAB-Dateien auf Clients heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-407">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="2fa4f-408">**In welchen Exchange-Rollen muss ich Mitglied sein, um eine mandantenübergreifende Bewegung einrichten oder abschließen zu können?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-408">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="2fa4f-409">Es gibt eine Matrix von Rollen, die auf der Annahme delegierter Aufgaben beim Ausführen einer Postfach verschieben basieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-409">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="2fa4f-410">Derzeit sind zwei Rollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-410">Currently, two roles are required:</span></span>  

- <span data-ttu-id="2fa4f-411">Die erste Rolle ist eine einmal durchgeführte Einrichtungsaufgabe, die die Autorisierung des Verschiebens von Inhalten in Oder aus Ihrer Mandanten-/Organisationsgrenze etabliert.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-411">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="2fa4f-412">Da das Verschieben von Daten aus Ihrem Organisationssteuerelement für alle Unternehmen ein entscheidendes Problem ist, haben wir uns mit der höchsten zugewiesenen Rolle des Organisationsadministrators (OrgAdmin) entschieden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-412">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="2fa4f-413">Diese Rolle muss eine neue OrganizationRelationship ändern oder einrichten, die die -MailboxMoveCapability mit der Remoteorganisation definiert.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-413">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="2fa4f-414">Nur orgAdmin kann die Einstellung MailboxMoveCapability ändern, während andere Attribute des OrganizationRelationhip vom Verbundfreigabeadministrator verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-414">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="2fa4f-415">Die Rolle der Ausführung der tatsächlichen Verschiebebefehle kann an eine Funktion auf niedrigerer Ebene delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-415">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="2fa4f-416">Der Rolle des Verschiebens von Postfächern wird die Möglichkeit zugewiesen, Postfächer mithilfe des Parameters in oder aus der Organisation zu `-RemoteTenant` verschieben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-416">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="2fa4f-417">**Wie wird gezielt die SMTP-Adresse für targetAddress (TargetDeliveryDomain) für das konvertierte Postfach (in Die MailUser-Konvertierung) ausgewählt?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-417">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="2fa4f-418">Exchange-Postfach verschiebt mithilfe von MRS die targetAddress für das ursprüngliche Quellpostfach beim Konvertieren in ein MailUser-Objekt durch Abgleichen einer E-Mail-Adresse (proxyAddress) für das Zielobjekt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-418">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="2fa4f-419">Der Prozess übernimmt den -TargetDeliveryDomain-Wert, der an den Befehl move übergeben wurde, und sucht dann auf der Zielseite nach einem übereinstimmenden Proxy für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-419">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="2fa4f-420">Wenn eine Übereinstimmung gefunden wird, wird die übereinstimmende proxyAddress verwendet, um das ExternalEmailAddress (targetAddress) für das konvertierte Postfachobjekt (jetzt MailUser) zu setzen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-420">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="2fa4f-421">**Wie werden Postfachberechtigungen übergangen?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-421">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="2fa4f-422">Postfachberechtigungen umfassen Senden im Auftrag von und Postfachzugriff:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-422">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="2fa4f-423">Send On Behalf Of (AD:publicDelegates) speichert den DN von Empfängern mit Zugriff auf das Postfach eines Benutzers als Stellvertretung.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-423">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="2fa4f-424">Dieser Wert wird in Active Directory gespeichert und wird derzeit nicht als Teil des Postfachübergangs verschoben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-424">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="2fa4f-425">Wenn für das Quellpostfach publicDelegates festgelegt ist, müssen Sie die öffentlichenDelegates für das Zielpostfach erneut aufrüsten, sobald die Konvertierung "MEU in Mailbox" in der Zielumgebung abgeschlossen ist, indem Sie `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-425">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="2fa4f-426">Postfachberechtigungen, die im Postfach gespeichert sind, werden mit dem Postfach verschoben, wenn sowohl der Prinzipal als auch der Stellvertreter in das Zielsystem verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-426">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="2fa4f-427">Beispielsweise wird dem Benutzer TestUser_7 vollzugriff auf die Postfachdatenbank TestUser_8 Mandanten SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-427">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="2fa4f-428">Nachdem die Postfach verschieben abgeschlossen TargetCompany.onmicrosoft.com, werden die gleichen Berechtigungen im Zielverzeichnis eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-428">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="2fa4f-429">Beispiele, *die Get-MailboxPermission* für TestUser_7 quell- und ziel mandanten verwenden, sind unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-429">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="2fa4f-430">Exchange-Cmdlets wird quell- und zielpräfixiert.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-430">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="2fa4f-431">Hier sehen Sie ein Beispiel für die Ausgabe der Postfachberechtigung vor einer Bewegung.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-431">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="2fa4f-432">Hier sehen Sie ein Beispiel für die Ausgabe der Postfachberechtigung nach dem Verschieben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-432">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="2fa4f-433">Mandantenübergreifende Postfach- und Kalenderberechtigungen werden NICHT unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-433">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="2fa4f-434">Sie müssen Prinzipale und Stellvertretung in konsolidierten Verschiebebatches organisieren, damit diese verbundenen Postfächer gleichzeitig vom Quell-Mandanten umgewechselt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-434">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="2fa4f-435">**Welcher X500-Proxy sollte den Ziel-MailUser-Proxyadressen hinzugefügt werden, um die Migration zu ermöglichen?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-435">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="2fa4f-436">Für die mandantenübergreifende Postfachmigration muss der LegacyExchangeDN-Wert des Quellpostfachobjekts als x500-E-Mail-Adresse für das MailUser-Zielobjekt gestempelt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-436">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="2fa4f-437">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-437">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="2fa4f-438">Zusätzlich zu diesem X500-Proxy müssen Sie alle X500-Proxys aus dem Postfach in der Quelle in das Postfach im Ziel kopieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-438">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="2fa4f-439">**Wo beginne ich mit der Problembehandlung, wenn Bewegungen nicht funktionieren?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-439">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="2fa4f-440">Starten Sie, indem Sie VerifySetup.ps1 Skript auf [GitHub ausführen](https://github.com/microsoft/cross-tenant/releases/tag/Preview) und die Ausgabe überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-440">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="2fa4f-441">Im Folgenden finden Sie ein Beispiel für die Ausführung VerifySetup.ps1 für den Ziel-Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-441">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="2fa4f-442">Hier ist ein eExample zum Ausführen von VerifySetup.ps1 für den Quell-Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-442">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="2fa4f-443">**Kann der Quell- und Ziel-Mandant denselben Domänennamen verwenden?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-443">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="2fa4f-444">Nein.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-444">No.</span></span> <span data-ttu-id="2fa4f-445">Die Quell- und Ziel-Mandantendomänennamen müssen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-445">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="2fa4f-446">Beispielsweise eine Quelldomäne von contoso.com und die Zieldomäne von fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-446">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="2fa4f-447">**Werden freigegebene Postfächer verschoben und funktionieren weiterhin?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-447">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="2fa4f-448">Ja, wir behalten jedoch nur die Speicherberechtigungen wie in den folgenden Artikeln beschrieben bei:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-448">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="2fa4f-449">Microsoft Docs | Verwalten von Berechtigungen für Empfänger in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2fa4f-449">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="2fa4f-450">Microsoft Support | Erteilen von Exchange- und Outlook-Postfachberechtigungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="2fa4f-450">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="2fa4f-451">**Ist Azure Key Vault erforderlich und wann werden Transaktionen ausgeführt?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-451">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="2fa4f-452">Ja, ein Azure-Abonnement ist erforderlich, um Key Vault zum Speichern des Zertifikats zum Autorisieren der Migration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-452">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="2fa4f-453">Im Gegensatz zu Onboardingmigrationen, die den Benutzernamen & kennwort für die Authentifizierung bei der Quelle verwenden, verwenden mandantenübergreifende Postfachmigrationen OAuth und dieses Zertifikat als Geheim-/Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-453">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="2fa4f-454">Der Zugriff auf den Schlüsseltresor muss während aller Postfachmigrationen beibehalten werden, da am Anfang und am Ende der Migration einmal darauf zugegriffen wird, sowie einmal alle 24 Stunden während inkrementeller Synchronisierungszeiten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-454">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="2fa4f-455">Details zur AKV-Kostenkalkulation finden Sie [hier]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-455">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="2fa4f-456">**Gibt es Empfehlungen für Batches?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-456">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="2fa4f-457">Nicht mehr als 2.000 Postfächer pro Batch.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-457">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="2fa4f-458">Es wird dringend empfohlen, Batches zwei Wochen vor dem Fälligkeitsdatum zu übermitteln, da während der Synchronisierung keine Auswirkungen auf die Endbenutzer zu sehen sind. Wenn Sie Anleitungen für Postfächer über 50.000 benötigen, können Sie sich an die Engineering Feedback Distribution List unter crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-458">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="2fa4f-459">**Was passiert, wenn ich die Dienstverschlüsselung mit dem Kundenschlüssel verwende?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-459">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="2fa4f-460">Das Postfach wird vor dem Verschieben entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-460">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="2fa4f-461">Stellen Sie sicher, dass der Kundenschlüssel im Ziel-Mandant konfiguriert ist, wenn er weiterhin erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-461">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="2fa4f-462">Weitere [Informationen](../compliance/customer-key-overview.md) finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-462">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="2fa4f-463">**Wie ist die geschätzte Migrationszeit?**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-463">**What is the estimated migration time?**</span></span>

<span data-ttu-id="2fa4f-464">Um Die Migration zu planen, [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) enthält die hier gezeigte Tabelle die Richtlinien, wann Massenpostfachmigrationen oder einzelne Migrationen abgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-464">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="2fa4f-465">Diese Schätzungen basieren auf einer Datenanalyse früherer Kundenmigrationen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-465">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="2fa4f-466">Da jede Umgebung eindeutig ist, kann die genaue Migrationsgeschwindigkeit variieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-466">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="2fa4f-467">Denken Sie daran, dass sich dieses Feature derzeit in der Vorschau befindet und die SLA und alle anwendbaren ServiceLevels während des Vorschaustatus dieses Features nicht auf Leistungs- oder Verfügbarkeitsprobleme angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-467">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2fa4f-468">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="2fa4f-468">Known issues</span></span>  

-  <span data-ttu-id="2fa4f-469">**Problem: Automatisch erweiterte Archive können nicht migriert werden.**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-469">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="2fa4f-470">Das mandantenübergreifende Migrationsfeature unterstützt Migrationen des primären Und Archivpostfachs für einen bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-470">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="2fa4f-471">Wenn der Benutzer in der Quelle jedoch über ein automatisch erweitertes Archiv verfügt , d. h. mehr als ein Archivpostfach, kann das Feature die zusätzlichen Archive nicht migrieren und sollte fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-471">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="2fa4f-472">**Problem: Cloud MailUsers mit nicht im Besitz des SmtpproxysAddress Block MRS verschiebt hintergrund.**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-472">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="2fa4f-473">Beim Erstellen von MailUser-Ziel-Mandantenobjekten müssen Sie sicherstellen, dass alle SMTP-Proxyadressen zur Ziel mandantenorganisation gehören.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-473">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="2fa4f-474">Wenn ein SMTP-proxyAddress für den Ziel-E-Mail-Benutzer vorhanden ist, der nicht zum lokalen Mandanten gehört, wird die Konvertierung von MailUser in Mailbox verhindert.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-474">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="2fa4f-475">Dies liegt an der Zusicherung, dass Postfachobjekte nur E-Mails von Domänen senden können, für die der Mandant autorisierend ist (vom Mandanten beanspruchte Domänen):</span><span class="sxs-lookup"><span data-stu-id="2fa4f-475">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="2fa4f-476">Wenn Sie Benutzer lokal mit Azure AD Connect synchronisieren, stellen Sie lokale MailUser-Objekte mit ExternalEmailAddress bereit, die auf den Quell mandanten verweisen, in dem das Postfach vorhanden ist (laran@contoso.onmicrosoft.com), und Sie stempeln die PrimarySMTPAddress als Domäne, die sich im Ziel mandanten befindet (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-476">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="2fa4f-477">Diese Werte werden mit dem Mandanten synchronisiert, und ein entsprechender E-Mail-Benutzer ist bereitgestellt und für die Migration bereit.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-477">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="2fa4f-478">Hier wird ein Beispielobjekt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-478">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="2fa4f-479">Die *contoso.onmicrosoft.com* adresse *ist nicht* im EmailAddresses /proxyAddresses-Array vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-479">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="2fa4f-480">**Problem: MailUser-Objekte mit "externen" primären SMTP-Adressen werden geändert/auf "interne" vom Unternehmen beanspruchte Domänen zurückgesetzt**</span><span class="sxs-lookup"><span data-stu-id="2fa4f-480">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="2fa4f-481">MailUser-Objekte sind Zeiger auf nicht lokale Postfächer.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-481">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="2fa4f-482">Bei mandantenübergreifenden Postfachmigrationen verwenden wir MailUser-Objekte, um entweder das Quellpostfach (aus Sicht der Zielorganisation) oder das Zielpostfach (aus der Perspektive der Quellorganisation) zu repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-482">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="2fa4f-483">Die MailUsers verfügen über eine ExternalEmailAddress (targetAddress), die auf die SMTP-Adresse des tatsächlichen Postfachs (ProxyTest@fabrikam.onmicrosoft.com) und der primärenSMTP-Adresse verweist, die die angezeigte SMTP-Adresse des Postfachbenutzers im Verzeichnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-483">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="2fa4f-484">Einige Organisationen entscheiden sich dafür, die primäre SMTP-Adresse als externe SMTP-Adresse und nicht als Adresse im Besitz des lokalen Mandanten (z. B. fabrikam.com anstatt als contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2fa4f-484">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="2fa4f-485">Nachdem jedoch ein Exchange-Dienstplanobjekt über Lizenzierungsvorgänge auf das MailUser-Objekt angewendet wurde, wird die primäre SMTP-Adresse so geändert, dass sie von der lokalen Organisation (contoso.com) überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-485">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="2fa4f-486">Es gibt zwei mögliche Gründe:</span><span class="sxs-lookup"><span data-stu-id="2fa4f-486">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="2fa4f-487">Wenn ein Exchange-Dienstplan auf einen MailUser angewendet wird, beginnt der Azure AD-Prozess, die Proxybereinigung zu erzwingen, um sicherzustellen, dass die lokale Organisation keine E-Mails, Spoof- oder E-Mails von einem anderen Mandanten senden kann.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-487">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="2fa4f-488">Jede SMTP-Adresse für ein Empfängerobjekt mit diesen Dienstplänen wird entfernt, wenn die Adresse nicht von der lokalen Organisation überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-488">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="2fa4f-489">Wie im Beispiel wird die Fabikam.com-Domäne nicht vom contoso.onmicrosoft.com-Mandanten überprüft, sodass die Fabrikam.com entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-489">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="2fa4f-490">Wenn Sie diese externe Domäne auf MailUser beibehalten möchten, entweder vor der Migration oder nach der Migration, müssen Sie Ihre Migrationsprozesse so ändern, dass Lizenzen nach Abschluss des Verschiebens oder vor dem Verschieben gestreift werden, um sicherzustellen, dass die Benutzer das erwartete externe Branding angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-490">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="2fa4f-491">Sie müssen sicherstellen, dass das Postfachobjekt ordnungsgemäß lizenziert ist, um keinen Einfluss auf den E-Mail-Dienst zu haben.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-491">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="2fa4f-492">Hier wird ein Beispielskript zum Entfernen der Dienstpläne für einen MailUser im Contoso.onmicrosoft.com mandanten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-492">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="2fa4f-493">Die Ergebnisse der zugewiesenen ServicePlans werden hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-493">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="2fa4f-494">PrimarySMTPAddress des Benutzers wird nicht mehr gestrubbt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-494">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="2fa4f-495">Die fabrikam.com befindet sich nicht im Besitz des contoso.onmicrosoft.com Mandanten und bleibt als primäre SMTP-Adresse im Verzeichnis erhalten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-495">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="2fa4f-496">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-496">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="2fa4f-497">Wenn msExchRemoteRecipientType auf 8 (DeprovisionMailbox) festgelegt ist, werden für lokale MailUser, die zum Zielmandanten migriert werden, von der Proxybereinigungslogik in Azure nicht besitzereigene Domänen entfernt und der primäreSMTP auf eine eigene Domäne zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-497">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="2fa4f-498">Durch Löschen von msExchRemoteRecipientType im lokalen MailUser wird die Proxybereinigungslogik nicht mehr angewendet.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-498">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="2fa4f-499">Nachfolgend finden Sie den vollständigen Satz möglicher Dienstpläne, die Exchange Online enthalten.</span><span class="sxs-lookup"><span data-stu-id="2fa4f-499">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="2fa4f-500">Name</span><span class="sxs-lookup"><span data-stu-id="2fa4f-500">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="2fa4f-501">Advanced eDiscovery Storage (500 GB)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-501">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="2fa4f-502">Kunden-Lockbox</span><span class="sxs-lookup"><span data-stu-id="2fa4f-502">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="2fa4f-503">Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="2fa4f-503">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="2fa4f-504">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-504">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="2fa4f-505">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="2fa4f-505">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="2fa4f-506">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="2fa4f-506">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="2fa4f-507">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-507">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="2fa4f-508">Exchange Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-508">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="2fa4f-509">Exchange Online (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-509">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="2fa4f-510">Exchange Online-Archivierung für Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2fa4f-510">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="2fa4f-511">Exchange Online-Archivierung für Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2fa4f-511">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="2fa4f-512">Exchange Online Inaktives Benutzer-Add-On</span><span class="sxs-lookup"><span data-stu-id="2fa4f-512">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="2fa4f-513">Exchange Online-Kiosk</span><span class="sxs-lookup"><span data-stu-id="2fa4f-513">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="2fa4f-514">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="2fa4f-514">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="2fa4f-515">Exchange Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="2fa4f-515">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="2fa4f-516">Exchange Online-POP</span><span class="sxs-lookup"><span data-stu-id="2fa4f-516">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="2fa4f-517">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2fa4f-517">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="2fa4f-518">Informationsbarrieren</span><span class="sxs-lookup"><span data-stu-id="2fa4f-518">Information Barriers</span></span>                              |
   | <span data-ttu-id="2fa4f-519">Information Protection für Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="2fa4f-519">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="2fa4f-520">Information Protection für Office 365 – Standard</span><span class="sxs-lookup"><span data-stu-id="2fa4f-520">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="2fa4f-521">Einblicke von MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="2fa4f-521">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="2fa4f-522">Erweiterte Microsoft 365-Überwachung</span><span class="sxs-lookup"><span data-stu-id="2fa4f-522">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="2fa4f-523">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="2fa4f-523">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="2fa4f-524">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="2fa4f-524">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="2fa4f-525">Microsoft MyAnalytics (Vollversion)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-525">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="2fa4f-526">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2fa4f-526">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="2fa4f-527">Microsoft Defender für Office 365 (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-527">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="2fa4f-528">Microsoft Defender für Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2fa4f-528">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="2fa4f-529">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="2fa4f-529">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="2fa4f-530">Premium-Verschlüsselung in Office 365</span><span class="sxs-lookup"><span data-stu-id="2fa4f-530">Premium Encryption in Office 365</span></span>                  |
