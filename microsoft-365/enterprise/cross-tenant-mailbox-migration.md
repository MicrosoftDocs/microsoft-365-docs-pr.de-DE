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
ms.openlocfilehash: f9a4b7679a33d6722336ee5412e4992389ba915f
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694413"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="2c239-103">Mandantenübergreifende Postfachmigration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="2c239-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="2c239-104">Wenn ein Exchange Online-Mandant Postfächer in einen anderen Mandanten im gleichen Exchange Online-Dienst verschieben musste, müssten sie sie vollständig in den lokalen Dienst verschieben und dann in einen neuen Mandanten integrieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="2c239-105">Mit dem neuen mandantenübergreifenden Migrationsfeature können Mandantenadministratoren sowohl in Quell- als auch in Ziel mandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben.</span><span class="sxs-lookup"><span data-stu-id="2c239-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="2c239-106">Dadurch wird die Notwendigkeit von Off-Board- und Onboardpostfächern entfernt.</span><span class="sxs-lookup"><span data-stu-id="2c239-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="2c239-107">In der Regel benötigen Sie bei Fusionen oder Übernahmen die Möglichkeit, Benutzer und Inhalte in einen neuen Mandanten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="2c239-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="2c239-108">Wenn der Ziel-Mandant-Administrator die Migration ausgeführt hat, wird dies als Pull-Move bezeichnet, ähnlich wie bei lokalen Migrationen mit Cloud-Onboarding.</span><span class="sxs-lookup"><span data-stu-id="2c239-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="2c239-109">Mandantenübergreifende postfachübergreifende Exchange werden von Mandantenadministratoren vollständig self-serviced ausgeführt und verwenden bekannte Schnittstellen, die in die größeren Workflows geschrieben werden können, die zum Übergang von Benutzern in ihre neue Organisation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2c239-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="2c239-110">Administratoren können das Über die Verwaltungsrolle Postfächer verschieben verfügbare `New-MigrationBatch` Cmdlet verwenden, um mandantenübergreifende Verschieben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2c239-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="2c239-111">Der Verschiebenprozess umfasst Mandantenautorisierungsüberprüfungen während der Postfachsynchronisierung und -finalisierung.</span><span class="sxs-lookup"><span data-stu-id="2c239-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="2c239-112">Benutzer, die migrieren, müssen im Ziel-Mandanten-Exchange Online mailUsers vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um mandantenübergreifende Bewegungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2c239-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="2c239-113">Für Benutzer, die im Ziel-Mandanten nicht ordnungsgemäß eingerichtet sind, wird beim System ein Fehler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2c239-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="2c239-114">Wenn die Verschieben abgeschlossen sind, wird das Quellsystempostfach in MailUser konvertiert, und die targetAddress (in Exchange als ExternalEmailAddress angezeigt) wird mit der Routingadresse an den Ziel-Mandanten gestempelt.</span><span class="sxs-lookup"><span data-stu-id="2c239-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="2c239-115">Bei diesem Prozess bleibt das legacy MailUser im Quell-Mandant und ermöglicht eine Zeit der Koexistenz und des E-Mail-Routings.</span><span class="sxs-lookup"><span data-stu-id="2c239-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="2c239-116">Wenn Geschäftsprozesse dies zulassen, kann der Quell-Mandant die Quelle MailUser entfernen oder in einen E-Mail-Kontakt konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="2c239-117">Mandantenübergreifende Exchange Postfachmigrationen werden nur für Mandanten in Hybrid- oder Cloud- oder einer beliebigen Kombination der beiden Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c239-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="2c239-118">In diesem Artikel wird der Prozess für mandantenübergreifende Postfachbewegungen beschrieben und Anleitungen zum Vorbereiten von Quell- und Ziel mandanten für die Inhaltsver verschieben.</span><span class="sxs-lookup"><span data-stu-id="2c239-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="2c239-119">Vorbereiten von Quell- und Ziel-Mandanten</span><span class="sxs-lookup"><span data-stu-id="2c239-119">Preparing source and target tenants</span></span>

<span data-ttu-id="2c239-120">Das feature für die mandantenübergreifende Exchange erfordert autorisierungs- und scoping für mandantenübergreifende Migrationen.</span><span class="sxs-lookup"><span data-stu-id="2c239-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="2c239-121">Mithilfe der Azure Enterprise-Anwendung und Key Vault-Speicherlösungen sind Mandantenadministratoren nun in der Lage, sowohl die Autorisierung als auch das Scoping von Exchange Online Postfachmigrationen von einem Mandanten zum anderen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2c239-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="2c239-122">Mandantenübergreifende Postfachbewegungen unterstützen ein Einladungs- und Zustimmungsmodell zum Einrichten einer Azure Active Directory (Azure AD)-Anwendung, die für die Authentifizierung zwischen einem Mandantenpaar verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="2c239-123">Zusätzliche Komponenten wie eine Organisationsbeziehung und ein Migrationsendpunkt sind ebenfalls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c239-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="2c239-124">Dieser Abschnitt enthält weder die spezifischen Schritte, die zum Vorbereiten der MailUser-Benutzerobjekte im Zielverzeichnis erforderlich sind, noch den Beispielbefehl zum Übermitteln eines Migrationsbatches.</span><span class="sxs-lookup"><span data-stu-id="2c239-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="2c239-125">Weitere Informationen [finden Sie unter Prepare target user objects for migration.](#prepare-target-user-objects-for-migration)</span><span class="sxs-lookup"><span data-stu-id="2c239-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2c239-126">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2c239-126">Prerequisites</span></span>

<span data-ttu-id="2c239-127">Das mandantenübergreifende Postfach verschieben-Feature [erfordert,](/azure/key-vault/basic-concepts) dass Azure Key Vault eine mandantenpaarspezifische Azure-Anwendung zum sicheren Speichern und Zugreifen auf das Zertifikat/den geheimen Schlüssel einrichten kann, das zum Authentifizieren und Autorisieren der Postfachmigration von einem Mandanten zum anderen verwendet wird. Dabei werden alle Anforderungen zum Freigeben von Zertifikaten/Geheimschlüsseln zwischen Mandanten entfernt.</span><span class="sxs-lookup"><span data-stu-id="2c239-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="2c239-128">Stellen Sie vor dem Start sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um Azure Key Vault, Die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="2c239-129">In der Regel verfügt der globale Administrator über die Berechtigung zum Ausführen aller Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="2c239-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="2c239-130">Darüber hinaus sind E-Mail-aktivierte Sicherheitsgruppen im Quell-Mandant vor dem Ausführen des Setups erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c239-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="2c239-131">Diese Gruppen werden verwendet, um die Liste der Postfächer, die vom Quell-Mandanten (oder manchmal auch als Ressourcen-Mandant bezeichnet) zum Ziel-Mandanten verschoben werden können, zu bereichern.</span><span class="sxs-lookup"><span data-stu-id="2c239-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="2c239-132">Auf diese Weise kann der Quell-Mandant-Administrator die bestimmte Gruppe von Postfächern einschränken oder beschränken, die verschoben werden müssen, um zu verhindern, dass unbeabsichtigte Benutzer migriert werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="2c239-133">Geschachtelte Gruppen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c239-133">Nested groups are not supported.</span></span>

<span data-ttu-id="2c239-134">Sie müssen auch mit Ihrem vertrauenswürdigen Partnerunternehmen (mit dem Sie Postfächer verschieben) kommunizieren, um ihre Mandanten-ID Microsoft 365 erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c239-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="2c239-135">Diese Mandanten-ID wird im Feld Organisationsbeziehung `DomainName` verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c239-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="2c239-136">Um die Mandanten-ID eines Abonnements zu erhalten, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="2c239-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="2c239-137">Klicken Sie auf das Kopiersymbol für die Tenant ID-Eigenschaft, um sie in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="2c239-138">Hier sehen Sie, wie der Prozess funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2c239-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Mandantenvorbereitung für die Postfachmigration.":::

<span data-ttu-id="2c239-140">[Sehen Sie sich eine größere Version dieses Bilds an.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)</span><span class="sxs-lookup"><span data-stu-id="2c239-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="2c239-141">Vorbereiten von Mandanten</span><span class="sxs-lookup"><span data-stu-id="2c239-141">Prepare tenants</span></span>

<span data-ttu-id="2c239-142">Auf einer hohen Ebene werden die folgenden Konfigurationsaktionen beim Ausführen der Setupskripts ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2c239-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="2c239-143">Bereiten Sie den Ziel mandanten vor:</span><span class="sxs-lookup"><span data-stu-id="2c239-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="2c239-144">Wenn keine vorhandene Azure-Ressourcengruppe bereitgestellt wird, wird ein neues (SCRIPT) erstellt.</span><span class="sxs-lookup"><span data-stu-id="2c239-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="2c239-145">Wenn kein vorhandener Schlüsseltresor bereitgestellt wird, wird ein neues (SCRIPT) erstellt.</span><span class="sxs-lookup"><span data-stu-id="2c239-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="2c239-146">Eine neue Zugriffsrichtlinie wird für die Office 365 Exchange Online Mailbox Migration Application (SCRIPT) erstellt.</span><span class="sxs-lookup"><span data-stu-id="2c239-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="2c239-147">Ein neues Zertifikat wird erstellt (oder vorhanden, falls angegeben), um das Geheimnis der Migrationsanwendung (SCRIPT) zu halten.</span><span class="sxs-lookup"><span data-stu-id="2c239-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="2c239-148">Eine neue Azure AD-Anwendung wird erstellt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2c239-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="2c239-149">Das Zertifikat/der geheime Schlüssel wird in die Migrationsanwendung (SCRIPT) hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="2c239-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="2c239-150">Berechtigungen für die Postfachmigration werden der Anwendung (SCRIPT) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2c239-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="2c239-151">Das Bereitstellungsskript hält an, bis der Zieladministrator der eigenen Anwendung (SCRIPT) zuwilligt.</span><span class="sxs-lookup"><span data-stu-id="2c239-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="2c239-152">Der Ziel-Mandant-Administrator ist mit den Berechtigungen einverstanden, die der Anwendung erteilt werden (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="2c239-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="2c239-153">Eine Organisationsbeziehung wird zum Ziel-Mandant (SCRIPT) erstellt.</span><span class="sxs-lookup"><span data-stu-id="2c239-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="2c239-154">Ein Migrationsendpunkt wird erstellt, um Postfächer an den Ziel mandanten (SCRIPT) zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="2c239-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="2c239-155">Bereiten Sie den Quell-Mandanten vor:</span><span class="sxs-lookup"><span data-stu-id="2c239-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="2c239-156">Der Quell-Mandant-Administrator akzeptiert die Zustimmung zur Einladung der Postfachmigrationsanwendung vom Ziel-Mandanten (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="2c239-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="2c239-157">Der Quell-Mandantenadministrator erstellt eine E-Mail-aktivierte Sicherheitsgruppe in ihrem Mandanten, die die Liste der Postfächer enthält, die von der Migrationsanwendung verschoben werden dürfen (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="2c239-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="2c239-158">Es wird eine Organisationsbeziehung mit dem Ziel-Mandanten erstellt, der an die Postfachmigrationsanwendung annimmt, die für die OAuth-Überprüfung verwendet werden soll, um die Verschiebenanforderung (SCRIPT) zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="2c239-159">Schritt-für-Schritt-Anweisungen für den Ziel-Mandantenadministrator</span><span class="sxs-lookup"><span data-stu-id="2c239-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="2c239-160">Laden Sie SetupCrossTenantRelationshipForTargetTenant.ps1 Skript für das Ziel-Mandanten-Setup aus dem repository [GitHub herunter.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="2c239-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="2c239-161">Speichern Sie das Skript (SetupCrossTenantRelationshipForTargetTenant.ps1) auf dem Computer, von dem Sie das Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="2c239-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="2c239-162">Erstellen Sie eine Remote-PowerShell-Verbindung zum Exchange Online Ziel-Mandant.</span><span class="sxs-lookup"><span data-stu-id="2c239-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="2c239-163">Stellen Sie erneut sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um den Azure Key Vault-Speicher und -Zertifikat, die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="2c239-164">Ändern Sie das Verzeichnis des Dateiordners in den Skriptspeicherort, oder überprüfen Sie, ob das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Der Remote-PowerShell-Sitzung befindet.</span><span class="sxs-lookup"><span data-stu-id="2c239-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="2c239-165">Führen Sie das Skript mit den folgenden Parametern und Werten aus.</span><span class="sxs-lookup"><span data-stu-id="2c239-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="2c239-166">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c239-166">Parameter</span></span> | <span data-ttu-id="2c239-167">Wert</span><span class="sxs-lookup"><span data-stu-id="2c239-167">Value</span></span> | <span data-ttu-id="2c239-168">Erforderlich oder Optional</span><span class="sxs-lookup"><span data-stu-id="2c239-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="2c239-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2c239-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="2c239-170">Ziel-Mandantendomäne, z. B. fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2c239-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="2c239-171">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-171">Required</span></span> |
    | <span data-ttu-id="2c239-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2c239-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="2c239-173">Quell-Mandantendomäne, z. B. contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2c239-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="2c239-174">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-174">Required</span></span> |
    | <span data-ttu-id="2c239-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="2c239-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="2c239-176">E-Mail-Adresse des Quell-Mandantenadministrators.</span><span class="sxs-lookup"><span data-stu-id="2c239-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="2c239-177">Dies ist der Quell-Mandantenadministrator, der der Verwendung der Vom Zieladministrator gesendeten Postfachmigrationsanwendung zuwilligt. Dies ist der Administrator, der die E-Mail-Einladung für die Anwendung erhält.</span><span class="sxs-lookup"><span data-stu-id="2c239-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="2c239-178">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-178">Required</span></span> |
    | <span data-ttu-id="2c239-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="2c239-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="2c239-180">GuiD (Source Tenant Organization ID).</span><span class="sxs-lookup"><span data-stu-id="2c239-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="2c239-181">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-181">Required</span></span> |
    | <span data-ttu-id="2c239-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="2c239-182">-SubscriptionId</span></span>                             | <span data-ttu-id="2c239-183">Das Zum Erstellen von Ressourcen zu verwendende Azure-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="2c239-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="2c239-184">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-184">Required</span></span> |
    | <span data-ttu-id="2c239-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="2c239-185">-ResourceGroup</span></span>                              | <span data-ttu-id="2c239-186">Azure-Ressourcengruppenname, der den Schlüsseltresor enthält oder enthält.</span><span class="sxs-lookup"><span data-stu-id="2c239-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="2c239-187">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-187">Required</span></span> |
    | <span data-ttu-id="2c239-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="2c239-188">-KeyVaultName</span></span>                               | <span data-ttu-id="2c239-189">Azure Key Vault-Instanz, in der Ihr Zertifikat/geheimer Postfachmigrationsanwendung gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="2c239-190">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-190">Required</span></span> |
    | <span data-ttu-id="2c239-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="2c239-191">-CertificateName</span></span>                            | <span data-ttu-id="2c239-192">Zertifikatname beim Generieren oder Suchen nach Zertifikaten im Schlüsseltresor.</span><span class="sxs-lookup"><span data-stu-id="2c239-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="2c239-193">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-193">Required</span></span> |
    | <span data-ttu-id="2c239-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="2c239-194">-CertificateSubject</span></span>                         | <span data-ttu-id="2c239-195">Name des Azure Key Vault-Zertifikatsubjekts, z. B. CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="2c239-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="2c239-196">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-196">Required</span></span> |
    | <span data-ttu-id="2c239-197">-AzureResourceLocation</span><span class="sxs-lookup"><span data-stu-id="2c239-197">-AzureResourceLocation</span></span>                      | <span data-ttu-id="2c239-198">Der Speicherort der Azure-Ressourcengruppe und des Schlüsseltresor.</span><span class="sxs-lookup"><span data-stu-id="2c239-198">The location of the Azure resource group and key vault.</span></span> | <span data-ttu-id="2c239-199">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-199">Required</span></span> |
    | <span data-ttu-id="2c239-200">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="2c239-200">-ExistingApplicationId</span></span>                      | <span data-ttu-id="2c239-201">E-Mail-Migrationsanwendung, die verwendet werden soll, wenn sie bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2c239-201">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="2c239-202">Optional</span><span class="sxs-lookup"><span data-stu-id="2c239-202">Optional</span></span> |
    | <span data-ttu-id="2c239-203">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="2c239-203">-AzureAppPermissions</span></span>                        | <span data-ttu-id="2c239-204">Die erforderlichen Berechtigungen für die Postfachmigrationsanwendung, z. B. Exchange oder MSGraph (Exchange zum Verschieben von Postfächern, MSGraph für die Verwendung dieser Anwendung zum Senden einer Einladung zum Zustimmungslink an den Ressourcen-Mandanten).</span><span class="sxs-lookup"><span data-stu-id="2c239-204">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="2c239-205">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c239-205">Required</span></span> |
    | <span data-ttu-id="2c239-206">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="2c239-206">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="2c239-207">Parameter für die Verwendung der Anwendung, die für die Migration zum Senden einer Einladung zum Zustimmungslink an den Quell-Mandantenadministrator erstellt wurde. Wenn dies nicht vorhanden ist, werden die Anmeldeinformationen des Zieladministrators aufgefordert, eine Verbindung mit dem Azure-Einladungs-Manager herzustellen und die Einladung als Zieladministrator zu senden.</span><span class="sxs-lookup"><span data-stu-id="2c239-207">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="2c239-208">Optional</span><span class="sxs-lookup"><span data-stu-id="2c239-208">Optional</span></span> |
    | <span data-ttu-id="2c239-209">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="2c239-209">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="2c239-210">Das Speicherkonto, in dem die Überwachungsprotokolle von Key Vault gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-210">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="2c239-211">Optional</span><span class="sxs-lookup"><span data-stu-id="2c239-211">Optional</span></span> |
    | <span data-ttu-id="2c239-212">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="2c239-212">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="2c239-213">Die Ressourcengruppe, die das Speicherkonto zum Speichern von Key Vault-Überwachungsprotokollen enthält.</span><span class="sxs-lookup"><span data-stu-id="2c239-213">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="2c239-214">Optional</span><span class="sxs-lookup"><span data-stu-id="2c239-214">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="2c239-215">Stellen Sie sicher, dass Sie das Azure AD PowerShell-Modul installiert haben, bevor Sie die Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="2c239-215">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="2c239-216">Installationsschritte ![ ](/powershell/azure/install-az-ps?view=azps-5.1.0) finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="2c239-216">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="2c239-217">Das Skript hält an und bittet Sie, die während dieses Vorgangs erstellte Exchange postfachmigrationsanwendung zu akzeptieren oder zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-217">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="2c239-218">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-218">Here is an example.</span></span>

    ```powershell
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
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. <span data-ttu-id="2c239-219">In der Remote-PowerShell-Sitzung wird eine URL angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c239-219">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="2c239-220">Kopieren Sie den Link, der für Ihre Mandanten zustimmung bereitgestellt wurde, und fügen Sie ihn in einen Webbrowser ein.</span><span class="sxs-lookup"><span data-stu-id="2c239-220">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="2c239-221">Melden Sie sich mit Ihren Anmeldeinformationen für den globalen Administrator an.</span><span class="sxs-lookup"><span data-stu-id="2c239-221">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="2c239-222">Wenn der folgende Bildschirm angezeigt wird, wählen Sie **Akzeptieren aus.**</span><span class="sxs-lookup"><span data-stu-id="2c239-222">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogfeld Berechtigungen akzeptieren":::

9. <span data-ttu-id="2c239-224">Wechseln Sie zurück zur Remote-PowerShell-Sitzung, und fahren Sie mit enter fort.</span><span class="sxs-lookup"><span data-stu-id="2c239-224">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="2c239-225">Das Skript konfiguriert die verbleibenden Setupobjekte.</span><span class="sxs-lookup"><span data-stu-id="2c239-225">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="2c239-226">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-226">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="2c239-227">Das Setup des Zieladministrators ist nun abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="2c239-227">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="2c239-228">Schritt-für-Schritt-Anweisungen für den Quell-Mandantenadministrator</span><span class="sxs-lookup"><span data-stu-id="2c239-228">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="2c239-229">Melden Sie sich bei Ihrem Postfach als -ResourceTenantAdminEmail an, das vom Zieladministrator während des Setups angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2c239-229">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="2c239-230">Suchen Sie die E-Mail-Einladung vom Ziel-Mandanten, und wählen Sie **dann die Schaltfläche Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="2c239-230">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogfeld &quot;Eingeladen&quot;":::

2. <span data-ttu-id="2c239-232">Wählen **Sie Annehmen** aus, um die Einladung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-232">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialogfeld zum Akzeptieren von Berechtigungen":::

   > [!NOTE]
   > <span data-ttu-id="2c239-234">Wenn Sie diese E-Mail nicht erhalten oder nicht finden können, wurde dem Zielmandantadministrator eine direkte URL bereitgestellt, die Sie erhalten können, um die Einladung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-234">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="2c239-235">Die URL sollte in der Aufzeichnung der Remote-PowerShell-Sitzung des Ziel-Mandantenadministrators enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2c239-235">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="2c239-236">Erstellen Sie im Microsoft 365 Admin Center oder in einer Remote-PowerShell-Sitzung eine oder mehrere E-Mail-aktivierte Sicherheitsgruppen, um die Liste der Postfächer zu steuern, die der Ziel-Mandant vom Quell-Mandant zum Ziel mandanten ziehen (verschieben) darf.</span><span class="sxs-lookup"><span data-stu-id="2c239-236">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="2c239-237">Sie müssen diese Gruppe nicht im Voraus auffüllen, aber es muss mindestens eine Gruppe bereitgestellt werden, um die Setupschritte (Skript) ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="2c239-237">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="2c239-238">Schachtelgruppen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c239-238">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="2c239-239">Laden Sie SetupCrossTenantRelationshipForResourceTenant.ps1 Skript für das Quell-Mandanten-Setup aus dem GitHub hier herunter: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="2c239-239">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="2c239-240">Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Quell-Mandant mit Exchange Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="2c239-240">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="2c239-241">Globale Administratorberechtigungen sind nicht erforderlich, um den Quell-Mandanten zu konfigurieren, sondern nur den Ziel-Mandanten aufgrund des Erstellungsprozesses der Azure-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2c239-241">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="2c239-242">Ändern Sie das Verzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Der Remote-PowerShell-Sitzung befindet.</span><span class="sxs-lookup"><span data-stu-id="2c239-242">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="2c239-243">Führen Sie das Skript mit den folgenden erforderlichen Parametern und Werten aus.</span><span class="sxs-lookup"><span data-stu-id="2c239-243">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="2c239-244">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c239-244">Parameter</span></span> | <span data-ttu-id="2c239-245">Wert</span><span class="sxs-lookup"><span data-stu-id="2c239-245">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="2c239-246">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="2c239-246">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="2c239-247">E-Mail-aktivierte Sicherheitsgruppe, die vom Quell-Mandant für die Identitäten/Postfächer erstellt wurde, die sich im Bereich der Migration befinden.</span><span class="sxs-lookup"><span data-stu-id="2c239-247">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="2c239-248">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2c239-248">-ResourceTenantDomain</span></span> | <span data-ttu-id="2c239-249">Quell-Mandantendomänenname, z. B. contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2c239-249">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="2c239-250">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="2c239-250">-ApplicationId</span></span> | <span data-ttu-id="2c239-251">Azure-Anwendungs-ID (GUID) der Anwendung, die für die Migration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-251">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="2c239-252">Anwendungs-ID verfügbar über Ihr Azure-Portal (Azure AD, Enterprise Anwendungen, App-Name, Anwendungs-ID) oder in Ihrer Einladungs-E-Mail enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c239-252">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="2c239-253">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2c239-253">-TargetTenantDomain</span></span> | <span data-ttu-id="2c239-254">Ziel-Mandantendomänenname, z. B. fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2c239-254">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="2c239-255">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="2c239-255">-TargetTenantId</span></span> | <span data-ttu-id="2c239-256">Mandanten-ID des Ziel-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2c239-256">Tenant ID of the target tenant.</span></span> <span data-ttu-id="2c239-257">Beispielsweise ist die Azure AD-Mandanten-ID von contoso \. onmicrosoft.com Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2c239-257">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="2c239-258">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-258">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="2c239-259">Das Setup des Quelladministrators ist nun abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="2c239-259">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="2c239-260">Überprüfen des Setups</span><span class="sxs-lookup"><span data-stu-id="2c239-260">Verify setup</span></span>

<span data-ttu-id="2c239-261">Stellen Sie sicher, dass die Organisationsbeziehungen in Quell- und Ziel mandanten und Migrationsendpunkt im Ziel erfolgreich erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2c239-261">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="2c239-262">Ziel-Mandant</span><span class="sxs-lookup"><span data-stu-id="2c239-262">Target tenant</span></span>

<span data-ttu-id="2c239-263">**Organisationsbeziehung**</span><span class="sxs-lookup"><span data-stu-id="2c239-263">**Organization relationship**</span></span>

<span data-ttu-id="2c239-264">Stellen Sie sicher, dass das Organisationsbeziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c239-264">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="2c239-265">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2c239-265">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="2c239-266">**Migrationsendpunkt**</span><span class="sxs-lookup"><span data-stu-id="2c239-266">**Migration endpoint**</span></span>

<span data-ttu-id="2c239-267">Stellen Sie sicher, dass das Migrationsendpunktobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c239-267">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="2c239-268">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-268">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="2c239-269">Quell-Mandant</span><span class="sxs-lookup"><span data-stu-id="2c239-269">Source tenant</span></span>

<span data-ttu-id="2c239-270">**Organisationsbeziehung**</span><span class="sxs-lookup"><span data-stu-id="2c239-270">**Organization relationship**</span></span>

<span data-ttu-id="2c239-271">Stellen Sie sicher, dass das Organisationsbeziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c239-271">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="2c239-272">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-272">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="2c239-273">Überprüfen des Setupskripts</span><span class="sxs-lookup"><span data-stu-id="2c239-273">Verify Setup Script</span></span>

<span data-ttu-id="2c239-274">Wenn Bei der Konfiguration der Quell- oder Ziel-Mandanten Fehler auftreten, können [](https://github.com/microsoft/cross-tenant/releases/tag/Preview) Sie das skript VerifySetup.ps1 auf der GitHub ausführen und die Ausgabe überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2c239-274">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="2c239-275">Im Folgenden finden Sie ein Beispiel für die Ausführung VerifySetup.ps1 für den Ziel-Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2c239-275">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="2c239-276">Im Folgenden finden Sie ein Beispiel für VerifySetup.ps1 für den Quell-Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2c239-276">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="2c239-277">Verschieben von Postfächern zurück zur ursprünglichen Quelle</span><span class="sxs-lookup"><span data-stu-id="2c239-277">Move mailboxes back to the original source</span></span>

<span data-ttu-id="2c239-278">Wenn ein Postfach zurück zum ursprünglichen Quell-Mandant verschoben werden muss, müssen die gleichen Schritte und Skripts sowohl in neuen Quell- als auch in neuen Ziel-Mandanten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-278">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="2c239-279">Das vorhandene Organisationsbeziehungsobjekt wird aktualisiert oder angefügt, nicht neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="2c239-279">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="2c239-280">Vorbereiten von Zielbenutzerobjekten für die Migration</span><span class="sxs-lookup"><span data-stu-id="2c239-280">Prepare target user objects for migration</span></span>

<span data-ttu-id="2c239-281">Die Migration von Benutzern muss im Ziel mandanten- und Exchange Online -System (als MailUsers) vorhanden sein, das mit bestimmten Attributen gekennzeichnet ist, um mandantenübergreifende Bewegungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2c239-281">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="2c239-282">Für Benutzer, die im Ziel-Mandanten nicht ordnungsgemäß eingerichtet sind, wird beim System ein Fehler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2c239-282">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="2c239-283">Im folgenden Abschnitt werden die MailUser-Objektanforderungen für den Ziel mandanten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c239-283">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2c239-284">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2c239-284">Prerequisites</span></span>
  
<span data-ttu-id="2c239-285">Sie müssen sicherstellen, dass die folgenden Objekte und Attribute in der Zielorganisation festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2c239-285">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="2c239-286">Für alle Postfächer, die aus einer Quellorganisation verschoben werden, müssen Sie ein MailUser-Objekt in der Zielorganisation bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="2c239-286">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="2c239-287">Ziel-MailUser muss über die folgenden Attribute aus dem Quellpostfach verfügen oder dem neuen User-Objekt zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="2c239-287">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="2c239-288">ExchangeGUID (direkter Fluss von Quelle zu Ziel) – Die Postfach-GUID muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2c239-288">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="2c239-289">Der Verschiebevorgang wird nicht fortgesetzt, wenn dies für das Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2c239-289">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="2c239-290">ArchiveGUID (direkter Fluss von Quelle zu Ziel) – Die Guid des Archivs muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2c239-290">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="2c239-291">Der Verschiebevorgang wird nicht fortgesetzt, wenn dies für das Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2c239-291">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="2c239-292">(Dies ist nur erforderlich, wenn das Quellpostfach Archive aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="2c239-292">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="2c239-293">LegacyExchangeDN (flow as proxyAddress, "x500: ") – Der <LegacyExchangeDN> LegacyExchangeDN muss auf ziel-MailUser als x500: proxyAddress vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2c239-293">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="2c239-294">Die Verschiebeprozesse werden nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2c239-294">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="2c239-295">UserPrincipalName – UPN richtet sich an der NEUEN Identität oder dem Zielunternehmen des Benutzers aus (z. B. user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2c239-295">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="2c239-296">Primäre SMTPAddress– Primäre SMTP-Adresse richtet sich nach dem NEUEN Unternehmen des Benutzers aus (z. B. user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="2c239-296">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="2c239-297">TargetAddress/ExternalEmailAddress – MailUser referenziert das aktuelle Postfach des Benutzers, das im Quell-Mandant gehostet wird (z. B. user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2c239-297">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="2c239-298">Stellen Sie beim Zuweisen dieses Werts sicher, dass Sie auch PrimarySMTPAddress zugewiesen haben bzw. zuweisen, oder dieser Wert gibt den PrimarySMTPAddress-Wert an, der zu Verschiebefehlern führen wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-298">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="2c239-299">Sie können keine älteren SMTP-Proxyadressen aus dem Quellpostfach zu Ziel-MailUser hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2c239-299">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="2c239-300">Sie können z. B. keine contoso.com für die MEU in fabrikam.onmicrosoft.com Mandantenobjekten verwalten).</span><span class="sxs-lookup"><span data-stu-id="2c239-300">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="2c239-301">Domänen sind nur einem Azure AD- oder Exchange Online zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2c239-301">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="2c239-302">Beispiel **für ein** MailUser-Zielobjekt:</span><span class="sxs-lookup"><span data-stu-id="2c239-302">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="2c239-303">Attribut</span><span class="sxs-lookup"><span data-stu-id="2c239-303">Attribute</span></span>             | <span data-ttu-id="2c239-304">Wert</span><span class="sxs-lookup"><span data-stu-id="2c239-304">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="2c239-305">Alias</span><span class="sxs-lookup"><span data-stu-id="2c239-305">Alias</span></span>                 | <span data-ttu-id="2c239-306">Laran</span><span class="sxs-lookup"><span data-stu-id="2c239-306">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="2c239-307">RecipientType</span><span class="sxs-lookup"><span data-stu-id="2c239-307">RecipientType</span></span>         | <span data-ttu-id="2c239-308">MailUser</span><span class="sxs-lookup"><span data-stu-id="2c239-308">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="2c239-309">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="2c239-309">RecipientTypeDetails</span></span>  | <span data-ttu-id="2c239-310">MailUser</span><span class="sxs-lookup"><span data-stu-id="2c239-310">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="2c239-311">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2c239-311">UserPrincipalName</span></span>     | <span data-ttu-id="2c239-312">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2c239-312">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="2c239-313">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="2c239-313">PrimarySmtpAddress</span></span>    | <span data-ttu-id="2c239-314">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="2c239-314">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="2c239-315">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="2c239-315">ExternalEmailAddress</span></span>  | <span data-ttu-id="2c239-316">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2c239-316">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="2c239-317">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="2c239-317">ExchangeGuid</span></span>          | <span data-ttu-id="2c239-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="2c239-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="2c239-319">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="2c239-319">LegacyExchangeDN</span></span>      | <span data-ttu-id="2c239-320">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="2c239-320">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="2c239-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="2c239-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="2c239-322">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="2c239-322">EmailAddresses</span></span>        | <span data-ttu-id="2c239-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="2c239-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="2c239-324">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="2c239-324">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="2c239-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2c239-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="2c239-326">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="2c239-326">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="2c239-327">Beispiel **für das** Quellpostfachobjekt:</span><span class="sxs-lookup"><span data-stu-id="2c239-327">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="2c239-328">Attribut</span><span class="sxs-lookup"><span data-stu-id="2c239-328">Attribute</span></span>             | <span data-ttu-id="2c239-329">Wert</span><span class="sxs-lookup"><span data-stu-id="2c239-329">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="2c239-330">Alias</span><span class="sxs-lookup"><span data-stu-id="2c239-330">Alias</span></span>                 | <span data-ttu-id="2c239-331">Laran</span><span class="sxs-lookup"><span data-stu-id="2c239-331">LaraN</span></span>                                                                    |
     | <span data-ttu-id="2c239-332">RecipientType</span><span class="sxs-lookup"><span data-stu-id="2c239-332">RecipientType</span></span>         | <span data-ttu-id="2c239-333">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="2c239-333">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="2c239-334">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="2c239-334">RecipientTypeDetails</span></span>  | <span data-ttu-id="2c239-335">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="2c239-335">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="2c239-336">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2c239-336">UserPrincipalName</span></span>     | <span data-ttu-id="2c239-337">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2c239-337">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="2c239-338">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="2c239-338">PrimarySmtpAddress</span></span>    | <span data-ttu-id="2c239-339">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c239-339">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="2c239-340">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="2c239-340">ExchangeGuid</span></span>          | <span data-ttu-id="2c239-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="2c239-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="2c239-342">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="2c239-342">LegacyExchangeDN</span></span>      | <span data-ttu-id="2c239-343">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="2c239-343">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="2c239-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="2c239-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="2c239-345">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="2c239-345">EmailAddresses</span></span>        | <span data-ttu-id="2c239-346">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2c239-346">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="2c239-347">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c239-347">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="2c239-348">Zusätzliche Attribute können bereits in der Exchange enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2c239-348">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="2c239-349">Andern falls nicht, sollten sie eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-349">If not, they should be included.</span></span> 
   - <span data-ttu-id="2c239-350">msExchBlockedSendersHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="2c239-350">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="2c239-351">msExchSafeRecipientsHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="2c239-351">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="2c239-352">msExchSafeSendersHash – Schreibt sichere und blockierte Absenderdaten von Clients in das lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="2c239-352">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="2c239-353">Wenn sich das Quellpostfach auf LitigationHold befindet und die Größe des Quellpostfachs "Wiederherstellbare Elemente" größer als die Standardgröße der Datenbank (30 GB) ist, wird das Verschieben nicht fortgesetzt, da das Zielkontingent kleiner als die Größe des Quellpostfachs ist.</span><span class="sxs-lookup"><span data-stu-id="2c239-353">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="2c239-354">Sie können das MailUser-Zielobjekt so aktualisieren, dass die ELC-Postfachflags von der Quellumgebung zum Ziel verschoben werden. Dadurch wird das Zielsystem ausgelöst, um das Kontingent von MailUser auf 100 GB zu erweitern, sodass der Wechsel zum Ziel ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-354">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="2c239-355">Diese Anweisungen funktionieren nur für Hybrididentität mit Azure AD Verbinden, da die Befehle zum Stempeln der ELC-Flags für Mandantenadministratoren nicht verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-355">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="2c239-356">BEISPIEL – AS IS, NO WARRANTY</span><span class="sxs-lookup"><span data-stu-id="2c239-356">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="2c239-357">Dieses Skript setzt eine Verbindung mit dem Quellpostfach (um Quellwerte zu erhalten) und dem lokalen Active Directory-Ziel (zum Stempeln des ADUser-Objekts) voraus.</span><span class="sxs-lookup"><span data-stu-id="2c239-357">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="2c239-358">Wenn für die Quelle ein Rechtsstreit oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto ein.</span><span class="sxs-lookup"><span data-stu-id="2c239-358">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="2c239-359">Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="2c239-359">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="2c239-360">Nicht hybride Ziel-Mandanten können das Kontingent für den Ordner "Wiederherstellbare Elemente" für die MailUsers vor der Migration ändern, indem Sie den folgenden Befehl ausführen, um das Litigation Hold für das MailUser-Objekt zu aktivieren und das Kontingent auf 100 GB zu erhöhen: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="2c239-360">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="2c239-361">Beachten Sie, dass dies für Mandanten in Hybrid nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2c239-361">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="2c239-362">Benutzer in der Zielorganisation müssen mit entsprechenden Exchange Online für die Organisation gültigen Abonnements lizenziert werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-362">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="2c239-363">Sie können eine Lizenz vor dem Verschieben eines Postfachs anwenden, aber nur, wenn das Ziel-MailUser ordnungsgemäß mit ExchangeGUID und Proxyadressen eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="2c239-363">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="2c239-364">Das Anwenden einer Lizenz vor dem Anwenden der ExchangeGUID führt zu einem neuen Postfach, das in der Zielorganisation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-364">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="2c239-365">Wenn Sie eine Lizenz auf ein Mailbox- oder MailUser-Objekt anwenden, werden alle SMTP-Typproxyaddresses bereinigungt, um sicherzustellen, dass nur überprüfte Domänen im Exchange EmailAddresses-Array enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2c239-365">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="2c239-366">Sie müssen sicherstellen, dass das Ziel-MailUser-Ziel keine vorherige ExchangeGuid-Version hat, die nicht mit der ExchangeGuid-Quelle übereinstimmen kann.</span><span class="sxs-lookup"><span data-stu-id="2c239-366">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="2c239-367">Dies kann auftreten, wenn die Ziel-MEU zuvor für die Exchange Online und ein Postfach bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2c239-367">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="2c239-368">Wenn das Ziel-MailUser zuvor für exchangeGuid lizenziert wurde oder über eine ExchangeGuid verfügte, die nicht mit der ExchangeGuid-Quelle übereinstimmen, müssen Sie eine Bereinigung der Cloud-MEU durchführen.</span><span class="sxs-lookup"><span data-stu-id="2c239-368">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="2c239-369">Für diese Cloud-MEUs können Sie `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` ausführen.</span><span class="sxs-lookup"><span data-stu-id="2c239-369">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="2c239-370">Dieser Vorgang ist unwiderruflich.</span><span class="sxs-lookup"><span data-stu-id="2c239-370">This process is irreversible.</span></span> <span data-ttu-id="2c239-371">Wenn das Objekt über ein softDeleted-Postfach verfügt, kann es nach diesem Zeitpunkt nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-371">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="2c239-372">Nach dem Löschen können Sie jedoch das richtige ExchangeGuid-Objekt mit dem Zielobjekt synchronisieren, und MRS verbindet das Quellpostfach mit dem neu erstellten Zielpostfach.</span><span class="sxs-lookup"><span data-stu-id="2c239-372">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="2c239-373">(Referenz-EHLO-Blog zum neuen Parameter.)</span><span class="sxs-lookup"><span data-stu-id="2c239-373">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="2c239-374">Suchen Sie Objekte, die zuvor Postfächer waren, mithilfe dieses Befehls.</span><span class="sxs-lookup"><span data-stu-id="2c239-374">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="2c239-375">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-375">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="2c239-376">Löschen Sie das soft-deleted-Postfach mit diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="2c239-376">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="2c239-377">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-377">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="2c239-378">Durchführen von Postfachmigrationen</span><span class="sxs-lookup"><span data-stu-id="2c239-378">Perform mailbox migrations</span></span>

<span data-ttu-id="2c239-379">Mandantenübergreifende Exchange Postfachmigrationen werden als Migrationsbatches übermittelt, die vom Ziel mandanten initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2c239-379">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="2c239-380">Dies ähnelt der Art und Weise, wie Migrationsbatches bei der Migration von lokalen Exchange zu Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c239-380">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="2c239-381">Erstellen von Migrationsbatches</span><span class="sxs-lookup"><span data-stu-id="2c239-381">Create Migration batches</span></span>

<span data-ttu-id="2c239-382">Im Folgenden finden Sie ein Beispiel für ein Migrationsbatch-Cmdlet zum Starten von Bewegungen.</span><span class="sxs-lookup"><span data-stu-id="2c239-382">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="2c239-383">Die E-Mail-Adresse in der CSV-Datei muss die im Ziel-Mandant angegebene Adresse sein, nicht der Quell-Mandant.</span><span class="sxs-lookup"><span data-stu-id="2c239-383">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="2c239-384">Die Migrationsbatchübermittlung wird auch vom neuen Exchange Admin Center unterstützt, wenn die option mandantenübergreifendes Auswählen ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-384">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="2c239-385">Aktualisieren von lokalen MailUsers</span><span class="sxs-lookup"><span data-stu-id="2c239-385">Update on-premises MailUsers</span></span>

<span data-ttu-id="2c239-386">Sobald das Postfach von Quelle zu Ziel verschoben wird, sollten Sie sicherstellen, dass die lokalen E-Mail-Benutzer, sowohl Source als auch Target, mit dem neuen targetAddress aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-386">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="2c239-387">In den Beispielen ist die targetDeliveryDomain, die in der Bewegung verwendet wird, **contoso.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="2c239-387">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="2c239-388">Aktualisieren Sie die E-Mail-Benutzer mit dieser targetAddress.</span><span class="sxs-lookup"><span data-stu-id="2c239-388">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="2c239-389">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="2c239-389">Frequently asked questions</span></span>

<span data-ttu-id="2c239-390">**Müssen wir RemoteMailboxen nach dem Verschieben lokal in der Quelle aktualisieren?**</span><span class="sxs-lookup"><span data-stu-id="2c239-390">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="2c239-391">Ja, Sie sollten die targetAddress (RemoteRoutingAddress/ExternalEmailAddress) der lokalen Quellbenutzer aktualisieren, wenn das Quell-Mandantenpostfach in den Ziel mandanten verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-391">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="2c239-392">Während das E-Mail-Routing den Empfehlungen für mehrere E-Mail-Benutzer mit unterschiedlichen targetAddresses folgen kann, müssen Frei/Gebucht-Suchen für E-Mail-Benutzer auf den Speicherort des Postfachbenutzers zielen.</span><span class="sxs-lookup"><span data-stu-id="2c239-392">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="2c239-393">Frei/Gebucht-Suchen verfolgen nicht mehrere Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="2c239-393">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="2c239-394">**Werden Teams mandantenübergreifende Besprechungen migriert?**</span><span class="sxs-lookup"><span data-stu-id="2c239-394">**Do Teams meetings migrate cross-tenant?**</span></span>  

<span data-ttu-id="2c239-395">Die Besprechungen werden jedoch Teams die Besprechungs-URL nicht aktualisiert, wenn Elemente mandantenübergreifende Migriert werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-395">The meetings will move however the Teams meeting URL does not update when items migrate cross-tenant.</span></span> <span data-ttu-id="2c239-396">Da die URL im Ziel-Mandant ungültig ist, müssen Sie die Besprechungen entfernen und Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c239-396">Since the URL will be invalid in the target tenant you will need to remove and recreate the Teams meetings.</span></span>

<span data-ttu-id="2c239-397">**Migriert der Teams-Chatordner-Inhalt mandantenübergreifende Inhalte?**</span><span class="sxs-lookup"><span data-stu-id="2c239-397">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="2c239-398">Nein, der Inhalt Teams Chatordners wird nicht mandantenübergreifende migriert.</span><span class="sxs-lookup"><span data-stu-id="2c239-398">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="2c239-399">**Wie kann ich nur mandantenübergreifende Und nicht meine Onboarding- und Off-Boarding-Bewegungen sehen?**</span><span class="sxs-lookup"><span data-stu-id="2c239-399">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="2c239-400">Verwenden Sie den `-flags` Parameter.</span><span class="sxs-lookup"><span data-stu-id="2c239-400">Use the `-flags` parameter.</span></span> <span data-ttu-id="2c239-401">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-401">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="2c239-402">**Können Sie Beispielskripts zum Kopieren von Attributen bereitstellen, die in Tests verwendet werden?**</span><span class="sxs-lookup"><span data-stu-id="2c239-402">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="2c239-403">BEISPIEL – AS IS, NO WARRANTY</span><span class="sxs-lookup"><span data-stu-id="2c239-403">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="2c239-404">Dieses Skript setzt eine Verbindung mit dem Quellpostfach (zum Abspeichern von Quellwerten) und den lokalen Active Directory-Domänendiensten (zum Stempeln des ADUser-Objekts) voraus.</span><span class="sxs-lookup"><span data-stu-id="2c239-404">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="2c239-405">Wenn für die Quelle ein Rechtsstreit oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto ein.</span><span class="sxs-lookup"><span data-stu-id="2c239-405">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="2c239-406">Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="2c239-406">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="2c239-407">**Wie greifen wir auf Outlook tag 1 zu, nachdem das Verwendungspostfach verschoben wurde?**</span><span class="sxs-lookup"><span data-stu-id="2c239-407">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="2c239-408">Da nur ein Mandant eine Domäne besitzen kann, wird die frühere primäre SMTPAddress dem Benutzer im Ziel-Mandant nicht zugeordnet, wenn die Postfach verschieben abgeschlossen ist. nur die Domänen, die dem neuen Mandanten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2c239-408">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="2c239-409">Outlook verwendet den neuen BENUTZER-UPN, um sich beim Dienst zu authentifizieren, und das Outlook-Profil erwartet, dass das primäre SMTPAddress-Legacyobjekt mit dem Postfach im Zielsystem übereinstimmen soll.</span><span class="sxs-lookup"><span data-stu-id="2c239-409">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="2c239-410">Da sich die Legacyadresse nicht im Zielsystem befindet, wird im Outlook-Profil keine Verbindung hergestellt, um das neu verschobene Postfach zu finden.</span><span class="sxs-lookup"><span data-stu-id="2c239-410">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="2c239-411">Für diese anfängliche Bereitstellung müssen Benutzer ihr Profil mit dem neuen UPN, der primären SMTP-Adresse und dem erneuten Synchronisieren von OST-Inhalten neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c239-411">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="2c239-412">Planen Sie entsprechend, während Sie Ihre Benutzer für den Abschluss batchen.</span><span class="sxs-lookup"><span data-stu-id="2c239-412">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="2c239-413">Sie müssen die Netzwerkauslastung und -kapazität berücksichtigen, Outlook Clientprofile erstellt und nachfolgende OST- und OAB-Dateien auf Clients heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-413">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="2c239-414">**In Exchange rollenübergreifenden Rollen muss ich Mitglied sein, um eine mandantenübergreifende Bewegung einrichten oder abschließen zu können?**</span><span class="sxs-lookup"><span data-stu-id="2c239-414">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="2c239-415">Es gibt eine Matrix von Rollen, die auf der Annahme delegierter Aufgaben beim Ausführen einer Postfach verschieben basieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-415">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="2c239-416">Derzeit sind zwei Rollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="2c239-416">Currently, two roles are required:</span></span>  

- <span data-ttu-id="2c239-417">Die erste Rolle ist eine einmal durchgeführte Einrichtungsaufgabe, die die Autorisierung des Verschiebens von Inhalten in Oder aus Ihrer Mandanten-/Organisationsgrenze etabliert.</span><span class="sxs-lookup"><span data-stu-id="2c239-417">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="2c239-418">Da das Verschieben von Daten aus Ihrem Organisationssteuerelement für alle Unternehmen ein entscheidendes Problem ist, haben wir uns mit der höchsten zugewiesenen Rolle des Organisationsadministrators (OrgAdmin) entschieden.</span><span class="sxs-lookup"><span data-stu-id="2c239-418">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="2c239-419">Diese Rolle muss eine neue OrganizationRelationship ändern oder einrichten, die die -MailboxMoveCapability mit der Remoteorganisation definiert.</span><span class="sxs-lookup"><span data-stu-id="2c239-419">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="2c239-420">Nur orgAdmin kann die Einstellung MailboxMoveCapability ändern, während andere Attribute des OrganizationRelationhip vom Verbundfreigabeadministrator verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="2c239-420">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="2c239-421">Die Rolle der Ausführung der tatsächlichen Verschiebebefehle kann an eine Funktion auf niedrigerer Ebene delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-421">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="2c239-422">Der Rolle des Verschiebens von Postfächern wird die Möglichkeit zugewiesen, Postfächer mithilfe des Parameters in oder aus der Organisation zu `-RemoteTenant` verschieben.</span><span class="sxs-lookup"><span data-stu-id="2c239-422">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="2c239-423">**Wie wird gezielt die SMTP-Adresse für targetAddress (TargetDeliveryDomain) für das konvertierte Postfach (in Die MailUser-Konvertierung) ausgewählt?**</span><span class="sxs-lookup"><span data-stu-id="2c239-423">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="2c239-424">Exchange postfach verschiebt mithilfe von MRS die targetAddress für das ursprüngliche Quellpostfach beim Konvertieren in ein MailUser durch Abgleichen einer E-Mail-Adresse (proxyAddress) für das Zielobjekt.</span><span class="sxs-lookup"><span data-stu-id="2c239-424">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="2c239-425">Der Prozess übernimmt den -TargetDeliveryDomain-Wert, der an den Befehl move übergeben wurde, und sucht dann auf der Zielseite nach einem übereinstimmenden Proxy für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="2c239-425">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="2c239-426">Wenn eine Übereinstimmung gefunden wird, wird die übereinstimmende proxyAddress verwendet, um das ExternalEmailAddress (targetAddress) für das konvertierte Postfachobjekt (jetzt MailUser) zu setzen.</span><span class="sxs-lookup"><span data-stu-id="2c239-426">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="2c239-427">**Wie werden Postfachberechtigungen übergangen?**</span><span class="sxs-lookup"><span data-stu-id="2c239-427">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="2c239-428">Postfachberechtigungen umfassen Senden im Auftrag von und Postfachzugriff:</span><span class="sxs-lookup"><span data-stu-id="2c239-428">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="2c239-429">Send On Behalf Of (AD:publicDelegates) speichert den DN von Empfängern mit Zugriff auf das Postfach eines Benutzers als Stellvertretung.</span><span class="sxs-lookup"><span data-stu-id="2c239-429">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="2c239-430">Dieser Wert wird in Active Directory gespeichert und wird derzeit nicht als Teil des Postfachübergangs verschoben.</span><span class="sxs-lookup"><span data-stu-id="2c239-430">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="2c239-431">Wenn für das Quellpostfach publicDelegates festgelegt ist, müssen Sie die öffentlichenDelegates für das Zielpostfach erneut aufrüsten, sobald die Konvertierung "MEU in Mailbox" in der Zielumgebung abgeschlossen ist, indem Sie `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` ausführen.</span><span class="sxs-lookup"><span data-stu-id="2c239-431">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="2c239-432">Postfachberechtigungen, die im Postfach gespeichert sind, werden mit dem Postfach verschoben, wenn sowohl der Prinzipal als auch der Stellvertreter in das Zielsystem verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-432">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="2c239-433">Beispielsweise wird dem Benutzer TestUser_7 vollzugriff auf die Postfachdatenbank TestUser_8 Mandanten SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2c239-433">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="2c239-434">Nachdem die Postfach verschieben abgeschlossen TargetCompany.onmicrosoft.com, werden die gleichen Berechtigungen im Zielverzeichnis eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="2c239-434">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="2c239-435">Beispiele, *die Get-MailboxPermission* für TestUser_7 quell- und ziel mandanten verwenden, sind unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2c239-435">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="2c239-436">Exchange cmdlets werden Quelle und Ziel entsprechend vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="2c239-436">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="2c239-437">Hier sehen Sie ein Beispiel für die Ausgabe der Postfachberechtigung vor einer Bewegung.</span><span class="sxs-lookup"><span data-stu-id="2c239-437">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="2c239-438">Hier sehen Sie ein Beispiel für die Ausgabe der Postfachberechtigung nach dem Verschieben.</span><span class="sxs-lookup"><span data-stu-id="2c239-438">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="2c239-439">Mandantenübergreifende Postfach- und Kalenderberechtigungen werden NICHT unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c239-439">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="2c239-440">Sie müssen Prinzipale und Stellvertretung in konsolidierten Verschiebebatches organisieren, damit diese verbundenen Postfächer gleichzeitig vom Quell-Mandanten umgewechselt werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-440">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="2c239-441">**Welcher X500-Proxy sollte den Ziel-MailUser-Proxyadressen hinzugefügt werden, um die Migration zu ermöglichen?**</span><span class="sxs-lookup"><span data-stu-id="2c239-441">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="2c239-442">Für die mandantenübergreifende Postfachmigration muss der LegacyExchangeDN-Wert des Quellpostfachobjekts als x500-E-Mail-Adresse für das MailUser-Zielobjekt gestempelt werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-442">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="2c239-443">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2c239-443">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="2c239-444">Zusätzlich zu diesem X500-Proxy müssen Sie alle X500-Proxys aus dem Postfach in der Quelle in das Postfach im Ziel kopieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-444">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="2c239-445">**Wo beginne ich mit der Problembehandlung, wenn Bewegungen nicht funktionieren?**</span><span class="sxs-lookup"><span data-stu-id="2c239-445">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="2c239-446">Starten Sie, indem Sie VerifySetup.ps1 [Skript](https://github.com/microsoft/cross-tenant/releases/tag/Preview) auf der GitHub ausführen und die Ausgabe überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2c239-446">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="2c239-447">Im Folgenden finden Sie ein Beispiel für die Ausführung VerifySetup.ps1 für den Ziel-Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2c239-447">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="2c239-448">Hier ist ein eExample zum Ausführen von VerifySetup.ps1 für den Quell-Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2c239-448">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="2c239-449">**Kann der Quell- und Ziel-Mandant denselben Domänennamen verwenden?**</span><span class="sxs-lookup"><span data-stu-id="2c239-449">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="2c239-450">Nein.</span><span class="sxs-lookup"><span data-stu-id="2c239-450">No.</span></span> <span data-ttu-id="2c239-451">Die Quell- und Ziel-Mandantendomänennamen müssen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2c239-451">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="2c239-452">Beispielsweise eine Quelldomäne von contoso.com und die Zieldomäne von fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="2c239-452">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="2c239-453">**Werden freigegebene Postfächer verschoben und funktionieren weiterhin?**</span><span class="sxs-lookup"><span data-stu-id="2c239-453">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="2c239-454">Ja, wir behalten jedoch nur die Speicherberechtigungen wie in den folgenden Artikeln beschrieben bei:</span><span class="sxs-lookup"><span data-stu-id="2c239-454">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="2c239-455">Microsoft Docs | Verwalten von Berechtigungen für Empfänger in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2c239-455">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="2c239-456">Microsoft Support | Erteilen von Exchange und Outlook postfachberechtigungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="2c239-456">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="2c239-457">**Ist Azure Key Vault erforderlich und wann werden Transaktionen ausgeführt?**</span><span class="sxs-lookup"><span data-stu-id="2c239-457">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="2c239-458">Ja, ein Azure-Abonnement ist erforderlich, um Key Vault zum Speichern des Zertifikats zum Autorisieren der Migration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c239-458">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="2c239-459">Im Gegensatz zu Onboardingmigrationen, die den Benutzernamen & kennwort für die Authentifizierung bei der Quelle verwenden, verwenden mandantenübergreifende Postfachmigrationen OAuth und dieses Zertifikat als Geheim-/Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="2c239-459">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="2c239-460">Der Zugriff auf den Schlüsseltresor muss während aller Postfachmigrationen beibehalten werden, da am Anfang und am Ende der Migration einmal darauf zugegriffen wird, sowie einmal alle 24 Stunden während inkrementeller Synchronisierungszeiten.</span><span class="sxs-lookup"><span data-stu-id="2c239-460">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="2c239-461">Details zur AKV-Kostenkalkulation finden Sie [hier]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="2c239-461">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="2c239-462">**Gibt es Empfehlungen für Batches?**</span><span class="sxs-lookup"><span data-stu-id="2c239-462">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="2c239-463">Nicht mehr als 2.000 Postfächer pro Batch.</span><span class="sxs-lookup"><span data-stu-id="2c239-463">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="2c239-464">Es wird dringend empfohlen, Batches zwei Wochen vor dem Fälligkeitsdatum zu übermitteln, da während der Synchronisierung keine Auswirkungen auf die Endbenutzer zu sehen sind. Wenn Sie Anleitungen für Postfächer über 50.000 benötigen, können Sie sich an die Engineering Feedback Distribution List unter crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2c239-464">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="2c239-465">**Was passiert, wenn ich die Dienstverschlüsselung mit dem Kundenschlüssel verwende?**</span><span class="sxs-lookup"><span data-stu-id="2c239-465">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="2c239-466">Das Postfach wird vor dem Verschieben entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="2c239-466">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="2c239-467">Stellen Sie sicher, dass der Kundenschlüssel im Ziel-Mandant konfiguriert ist, wenn er weiterhin erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2c239-467">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="2c239-468">Weitere [Informationen](../compliance/customer-key-overview.md) finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="2c239-468">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="2c239-469">**Wie ist die geschätzte Migrationszeit?**</span><span class="sxs-lookup"><span data-stu-id="2c239-469">**What is the estimated migration time?**</span></span>

<span data-ttu-id="2c239-470">Um Die Migration zu planen, [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) enthält die hier gezeigte Tabelle die Richtlinien, wann Massenpostfachmigrationen oder einzelne Migrationen abgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2c239-470">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="2c239-471">Diese Schätzungen basieren auf einer Datenanalyse früherer Kundenmigrationen.</span><span class="sxs-lookup"><span data-stu-id="2c239-471">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="2c239-472">Da jede Umgebung eindeutig ist, kann die genaue Migrationsgeschwindigkeit variieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-472">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="2c239-473">Denken Sie daran, dass sich dieses Feature derzeit in der Vorschau befindet und die SLA und alle anwendbaren ServiceLevels während des Vorschaustatus dieses Features nicht auf Leistungs- oder Verfügbarkeitsprobleme angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c239-473">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2c239-474">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="2c239-474">Known issues</span></span>  

-  <span data-ttu-id="2c239-475">**Problem: Automatisch erweiterte Archive können nicht migriert werden.**</span><span class="sxs-lookup"><span data-stu-id="2c239-475">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="2c239-476">Das mandantenübergreifende Migrationsfeature unterstützt Migrationen des primären Und Archivpostfachs für einen bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2c239-476">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="2c239-477">Wenn der Benutzer in der Quelle jedoch über ein automatisch erweitertes Archiv verfügt , d. h. mehr als ein Archivpostfach, kann das Feature die zusätzlichen Archive nicht migrieren und sollte fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="2c239-477">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="2c239-478">**Problem: Cloud MailUsers mit nicht im Besitz des SmtpproxysAddress Block MRS verschiebt hintergrund.**</span><span class="sxs-lookup"><span data-stu-id="2c239-478">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="2c239-479">Beim Erstellen von MailUser-Ziel-Mandantenobjekten müssen Sie sicherstellen, dass alle SMTP-Proxyadressen zur Ziel mandantenorganisation gehören.</span><span class="sxs-lookup"><span data-stu-id="2c239-479">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="2c239-480">Wenn ein SMTP-proxyAddress für den Ziel-E-Mail-Benutzer vorhanden ist, der nicht zum lokalen Mandanten gehört, wird die Konvertierung von MailUser in Mailbox verhindert.</span><span class="sxs-lookup"><span data-stu-id="2c239-480">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="2c239-481">Dies liegt an der Zusicherung, dass Postfachobjekte nur E-Mails von Domänen senden können, für die der Mandant autorisierend ist (vom Mandanten beanspruchte Domänen):</span><span class="sxs-lookup"><span data-stu-id="2c239-481">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="2c239-482">Wenn Sie Benutzer lokal mit Azure AD Verbinden synchronisieren, stellen Sie lokale MailUser-Objekte mit ExternalEmailAddress bereit, die auf den Quell mandanten verweisen, in dem das Postfach vorhanden ist (laran@contoso.onmicrosoft.com), und Sie stempeln die PrimarySMTPAddress als Domäne, die sich im Ziel mandanten befindet (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="2c239-482">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="2c239-483">Diese Werte werden mit dem Mandanten synchronisiert, und ein entsprechender E-Mail-Benutzer ist bereitgestellt und für die Migration bereit.</span><span class="sxs-lookup"><span data-stu-id="2c239-483">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="2c239-484">Hier wird ein Beispielobjekt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c239-484">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="2c239-485">Die *contoso.onmicrosoft.com* adresse *ist nicht* im EmailAddresses /proxyAddresses-Array vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2c239-485">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="2c239-486">**Problem: MailUser-Objekte mit "externen" primären SMTP-Adressen werden geändert/auf "interne" vom Unternehmen beanspruchte Domänen zurückgesetzt**</span><span class="sxs-lookup"><span data-stu-id="2c239-486">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="2c239-487">MailUser-Objekte sind Zeiger auf nicht lokale Postfächer.</span><span class="sxs-lookup"><span data-stu-id="2c239-487">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="2c239-488">Bei mandantenübergreifenden Postfachmigrationen verwenden wir MailUser-Objekte, um entweder das Quellpostfach (aus Sicht der Zielorganisation) oder das Zielpostfach (aus der Perspektive der Quellorganisation) zu repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="2c239-488">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="2c239-489">Die MailUsers verfügen über eine ExternalEmailAddress (targetAddress), die auf die SMTP-Adresse des tatsächlichen Postfachs (ProxyTest@fabrikam.onmicrosoft.com) und der primärenSMTP-Adresse verweist, die die angezeigte SMTP-Adresse des Postfachbenutzers im Verzeichnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="2c239-489">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="2c239-490">Einige Organisationen entscheiden sich dafür, die primäre SMTP-Adresse als externe SMTP-Adresse und nicht als Adresse im Besitz des lokalen Mandanten (z. B. fabrikam.com anstatt als contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2c239-490">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="2c239-491">Sobald jedoch ein Exchange-Dienstplanobjekt über Lizenzierungsvorgänge auf den MailUser angewendet wird, wird die primäre SMTP-Adresse so geändert, dass sie von der lokalen Organisation (contoso.com) bestätigt wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-491">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="2c239-492">Es gibt zwei mögliche Gründe:</span><span class="sxs-lookup"><span data-stu-id="2c239-492">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="2c239-493">Wenn ein Exchange-Dienstplan auf einen MailUser angewendet wird, beginnt der Azure AD-Prozess, die Proxybereinigung zu erzwingen, um sicherzustellen, dass die lokale Organisation keine E-Mails, Spoof- oder E-Mails von einem anderen Mandanten senden kann.</span><span class="sxs-lookup"><span data-stu-id="2c239-493">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="2c239-494">Jede SMTP-Adresse für ein Empfängerobjekt mit diesen Dienstplänen wird entfernt, wenn die Adresse nicht von der lokalen Organisation überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-494">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="2c239-495">Wie im Beispiel wird die Fabikam.com-Domäne nicht vom contoso.onmicrosoft.com-Mandanten überprüft, sodass die Fabrikam.com entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="2c239-495">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="2c239-496">Wenn Sie diese externe Domäne auf MailUser beibehalten möchten, entweder vor der Migration oder nach der Migration, müssen Sie Ihre Migrationsprozesse so ändern, dass Lizenzen nach Abschluss des Verschiebens oder vor dem Verschieben gestreift werden, um sicherzustellen, dass die Benutzer das erwartete externe Branding angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="2c239-496">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="2c239-497">Sie müssen sicherstellen, dass das Postfachobjekt ordnungsgemäß lizenziert ist, um keinen Einfluss auf den E-Mail-Dienst zu haben.</span><span class="sxs-lookup"><span data-stu-id="2c239-497">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="2c239-498">Hier wird ein Beispielskript zum Entfernen der Dienstpläne für einen MailUser im Contoso.onmicrosoft.com mandanten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c239-498">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="2c239-499">Die Ergebnisse der zugewiesenen ServicePlans werden hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c239-499">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="2c239-500">PrimarySMTPAddress des Benutzers wird nicht mehr gestrubbt.</span><span class="sxs-lookup"><span data-stu-id="2c239-500">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="2c239-501">Die fabrikam.com befindet sich nicht im Besitz des contoso.onmicrosoft.com Mandanten und bleibt als primäre SMTP-Adresse im Verzeichnis erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c239-501">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="2c239-502">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c239-502">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="2c239-503">Wenn msExchRemoteRecipientType auf 8 (DeprovisionMailbox) festgelegt ist, werden für lokale MailUser, die zum Zielmandanten migriert werden, von der Proxybereinigungslogik in Azure nicht besitzereigene Domänen entfernt und der primäreSMTP auf eine eigene Domäne zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2c239-503">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="2c239-504">Durch Löschen von msExchRemoteRecipientType im lokalen MailUser wird die Proxybereinigungslogik nicht mehr angewendet.</span><span class="sxs-lookup"><span data-stu-id="2c239-504">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="2c239-505">Nachfolgend finden Sie den vollständigen Satz möglicher Dienstpläne, die Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2c239-505">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="2c239-506">Name</span><span class="sxs-lookup"><span data-stu-id="2c239-506">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="2c239-507">Advanced eDiscovery Storage (500 GB)</span><span class="sxs-lookup"><span data-stu-id="2c239-507">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="2c239-508">Kunden-Lockbox</span><span class="sxs-lookup"><span data-stu-id="2c239-508">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="2c239-509">Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="2c239-509">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="2c239-510">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="2c239-510">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="2c239-511">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="2c239-511">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="2c239-512">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="2c239-512">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="2c239-513">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="2c239-513">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="2c239-514">Exchange Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="2c239-514">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="2c239-515">Exchange Online (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2c239-515">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="2c239-516">Exchange Online-Archivierung für Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2c239-516">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="2c239-517">Exchange Online-Archivierung für Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2c239-517">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="2c239-518">Exchange Online Inaktives Benutzer-Add-On</span><span class="sxs-lookup"><span data-stu-id="2c239-518">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="2c239-519">Exchange Online-Kiosk</span><span class="sxs-lookup"><span data-stu-id="2c239-519">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="2c239-520">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="2c239-520">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="2c239-521">Exchange Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="2c239-521">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="2c239-522">Exchange Online-POP</span><span class="sxs-lookup"><span data-stu-id="2c239-522">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="2c239-523">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2c239-523">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="2c239-524">Informationsbarrieren</span><span class="sxs-lookup"><span data-stu-id="2c239-524">Information Barriers</span></span>                              |
   | <span data-ttu-id="2c239-525">Information Protection für Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="2c239-525">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="2c239-526">Information Protection für Office 365 – Standard</span><span class="sxs-lookup"><span data-stu-id="2c239-526">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="2c239-527">Einblicke von MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="2c239-527">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="2c239-528">Microsoft 365 Erweiterte Überwachung</span><span class="sxs-lookup"><span data-stu-id="2c239-528">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="2c239-529">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="2c239-529">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="2c239-530">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="2c239-530">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="2c239-531">Microsoft MyAnalytics (Vollversion)</span><span class="sxs-lookup"><span data-stu-id="2c239-531">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="2c239-532">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2c239-532">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="2c239-533">Microsoft Defender for Office 365 (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="2c239-533">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="2c239-534">Microsoft Defender for Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2c239-534">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="2c239-535">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="2c239-535">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="2c239-536">Premium Verschlüsselung in Office 365</span><span class="sxs-lookup"><span data-stu-id="2c239-536">Premium Encryption in Office 365</span></span>                  |
