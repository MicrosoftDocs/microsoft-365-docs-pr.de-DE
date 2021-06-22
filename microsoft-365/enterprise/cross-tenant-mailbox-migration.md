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
ms.openlocfilehash: 40ec3887cd37ddb412df3ae78300c1f9e9c60ecc
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053047"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="db661-103">Mandantenübergreifende Postfachmigration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="db661-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="db661-104">Wenn ein Exchange Online Mandant Postfächer in einen anderen Mandanten im selben Exchange Online Dienst verschieben musste, musste er sie zuvor vollständig an die lokale Bereitstellung auslagern und sie dann in einen neuen Mandanten integrieren.</span><span class="sxs-lookup"><span data-stu-id="db661-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="db661-105">Mit dem neuen mandantenübergreifenden Postfachmigrationsfeature können Mandantenadministratoren in Quell- und Zielmandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben.</span><span class="sxs-lookup"><span data-stu-id="db661-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="db661-106">Dadurch entgeht die Notwendigkeit, Postfächer zu off-board und zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="db661-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="db661-107">In der Regel benötigen Sie bei Fusionen oder Veräusserungen die Möglichkeit, Benutzer und Inhalte in einen neuen Mandanten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="db661-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="db661-108">Wenn der Zielmandantenadministrator die Verschiebung ausführt, wird dies als Pull-Verschiebung bezeichnet, ähnlich wie bei lokalen Migrationen zum Cloud-Onboarding.</span><span class="sxs-lookup"><span data-stu-id="db661-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="db661-109">Mandantenübergreifende Exchange Postfachverschiebungen werden von Mandantenadministratoren vollständig selbstverwendet und verwenden bekannte Schnittstellen, die in die größeren Workflows geschrieben werden können, die erforderlich sind, um Benutzer in ihre neue Organisation zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="db661-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="db661-110">Administratoren können das `New-MigrationBatch` Cmdlet verwenden, das über die Verwaltungsrolle "Postfächer verschieben" verfügbar ist, um mandantenübergreifende Verschiebungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db661-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="db661-111">Der Verschiebungsprozess umfasst Mandantenautorisierungsprüfungen während der Postfachsynchronisierung und -fertigstellung.</span><span class="sxs-lookup"><span data-stu-id="db661-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="db661-112">Benutzer, die migrieren, müssen im Zielmandanten Exchange Online System als MailUsers vorhanden sein, die mit bestimmten Attributen gekennzeichnet sind, um die mandantenübergreifenden Verschiebungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="db661-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="db661-113">Bei Benutzern, die im Zielmandanten nicht ordnungsgemäß eingerichtet sind, schlägt das System fehl.</span><span class="sxs-lookup"><span data-stu-id="db661-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="db661-114">Wenn die Verschiebungen abgeschlossen sind, wird das Postfach des Quellsystems in MailUser konvertiert, und die targetAddress (in Exchange als ExternalEmailAddress angezeigt) wird mit der Routingadresse an den Zielmandanten gestempelt.</span><span class="sxs-lookup"><span data-stu-id="db661-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="db661-115">Dieser Prozess belässt den Legacy-MailUser im Quellmandanten und ermöglicht einen Zeitraum des Koexistenz- und E-Mail-Routings.</span><span class="sxs-lookup"><span data-stu-id="db661-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="db661-116">Wenn Geschäftsprozesse dies zulassen, kann der Quellmandant die Quell-MailUser entfernen oder in einen E-Mail-Kontakt konvertieren.</span><span class="sxs-lookup"><span data-stu-id="db661-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="db661-117">Mandantenübergreifende Exchange Postfachmigrationen werden nur für Mandanten in Hybrid- oder Cloudumgebungen oder einer beliebigen Kombination der beiden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db661-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="db661-118">Dieser Artikel beschreibt den Prozess für mandantenübergreifende Postfachverschiebungen und enthält Anleitungen zum Vorbereiten von Quell- und Zielmandanten für die Inhaltsverschiebung.</span><span class="sxs-lookup"><span data-stu-id="db661-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="db661-119">Vorbereiten von Quell- und Zielmandanten</span><span class="sxs-lookup"><span data-stu-id="db661-119">Preparing source and target tenants</span></span>

<span data-ttu-id="db661-120">Das feature für die mandantenübergreifende Exchange Postfachmigration erfordert autorisierungs- und bereichsübergreifende Migrationen.</span><span class="sxs-lookup"><span data-stu-id="db661-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="db661-121">Mithilfe der Azure Enterprise-Anwendungs- und Key Vault-Speicherlösungen können Mandantenadministratoren jetzt sowohl die Autorisierung als auch die Bereichsdefinition von Exchange Online Postfachmigrationen von einem Mandanten zu einem anderen verwalten.</span><span class="sxs-lookup"><span data-stu-id="db661-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="db661-122">Mandantenübergreifende Postfachverschiebungen unterstützen ein Einladungs- und Zustimmungsmodell zum Einrichten einer Azure Active Directory (Azure AD)-Anwendung, die für die Authentifizierung zwischen einem Mandantenpaar verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="db661-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="db661-123">Zusätzliche Komponenten wie eine Organisationsbeziehung und ein Migrationsendpunkt sind ebenfalls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="db661-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="db661-124">Dieser Abschnitt enthält weder die spezifischen Schritte, die erforderlich sind, um die MailUser-Benutzerobjekte im Zielverzeichnis vorzubereiten, noch den Beispielbefehl zum Senden eines Migrationsbatches.</span><span class="sxs-lookup"><span data-stu-id="db661-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="db661-125">Weitere Informationen finden Sie unter [Vorbereiten von Zielbenutzerobjekten für](#prepare-target-user-objects-for-migration) die Migration.</span><span class="sxs-lookup"><span data-stu-id="db661-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db661-126">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="db661-126">Prerequisites</span></span>

<span data-ttu-id="db661-127">Das Feature zum verschieben von mandantenübergreifenden Postfächern erfordert, dass [Azure Key Vault](/azure/key-vault/basic-concepts) eine mandantenpaarspezifische Azure-Anwendung zum sicheren Speichern und Zugreifen auf das Zertifikat/den geheimen Schlüssel zum Authentifizieren und Autorisieren der Postfachmigration von einem Mandanten zum anderen erstellt, wodurch alle Anforderungen zum Freigeben von Zertifikaten/geheimen Schlüsseln zwischen Mandanten entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="db661-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="db661-128">Stellen Sie vor dem Start sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um Azure Key Vault, die Postfachanwendung verschieben, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="db661-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="db661-129">In der Regel verfügt der globale Administrator über die Berechtigung, alle Konfigurationsschritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db661-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="db661-130">Darüber hinaus sind E-Mail-aktivierte Sicherheitsgruppen im Quellmandanten vor dem Ausführen des Setups erforderlich.</span><span class="sxs-lookup"><span data-stu-id="db661-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="db661-131">Diese Gruppen werden verwendet, um die Liste der Postfächer zu beschränken, die vom Quellmandanten (oder manchmal auch als Ressourcenmandant bezeichnet) zum Zielmandanten verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="db661-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="db661-132">Dadurch kann der Quellmandantenadministrator die bestimmte Gruppe von Postfächern einschränken oder einschränken, die verschoben werden müssen, um zu verhindern, dass unbeabsichtigte Benutzer migriert werden.</span><span class="sxs-lookup"><span data-stu-id="db661-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="db661-133">Geschachtelte Gruppen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db661-133">Nested groups are not supported.</span></span>

<span data-ttu-id="db661-134">Sie müssen auch mit Ihrem vertrauenswürdigen Partnerunternehmen kommunizieren (mit dem Sie Postfächer verschieben), um deren Microsoft 365 Mandanten-ID zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="db661-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="db661-135">Diese Mandanten-ID wird im Feld "Organisationsbeziehung" `DomainName` verwendet.</span><span class="sxs-lookup"><span data-stu-id="db661-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="db661-136">Um die Mandanten-ID eines Abonnements abzurufen, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="db661-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="db661-137">Klicken Sie auf das Kopiersymbol für die Mandanten-ID-Eigenschaft, um sie in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="db661-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="db661-138">Hier sehen Sie, wie der Prozess funktioniert.</span><span class="sxs-lookup"><span data-stu-id="db661-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Mandantenvorbereitung für die Postfachmigration.":::

<span data-ttu-id="db661-140">[Sehen Sie sich eine größere Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)an.</span><span class="sxs-lookup"><span data-stu-id="db661-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="db661-141">Vorbereiten von Mandanten</span><span class="sxs-lookup"><span data-stu-id="db661-141">Prepare tenants</span></span>

<span data-ttu-id="db661-142">Auf hoher Ebene werden beim Ausführen der Setupskripts die folgenden Konfigurationsaktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="db661-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="db661-143">Vorbereiten des Zielmandanten:</span><span class="sxs-lookup"><span data-stu-id="db661-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="db661-144">Wenn keine vorhandene Azure-Ressourcengruppe bereitgestellt wird, wird eine neue erstellt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="db661-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="db661-145">Wenn kein vorhandener Key Vault bereitgestellt wird, wird ein neuer erstellt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="db661-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="db661-146">Für die Office 365 Exchange Online Mailbox Migration Application (SCRIPT) wird eine neue Zugriffsrichtlinie erstellt.</span><span class="sxs-lookup"><span data-stu-id="db661-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="db661-147">Ein neues Zertifikat wird erstellt (oder ein vorhandenes, falls angegeben), um den geheimen Schlüssel für die Migrationsanwendung (SCRIPT) zu speichern.</span><span class="sxs-lookup"><span data-stu-id="db661-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="db661-148">Eine neue Azure AD-Anwendung wird erstellt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="db661-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="db661-149">Das Zertifikat/geheimnis wird in die Migrationsanwendung (SCRIPT) hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="db661-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="db661-150">Postfachmigrationsberechtigungen werden der Anwendung (SCRIPT) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="db661-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="db661-151">Das Bereitstellungsskript wird angehalten, bis der Zieladministrator seiner eigenen Anwendung (SCRIPT) zustimmt.</span><span class="sxs-lookup"><span data-stu-id="db661-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="db661-152">Der Zielmandantenadministrator stimmt den Berechtigungen zu, die der Anwendung erteilt werden (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="db661-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="db661-153">Eine Organisationsbeziehung wird mit dem Zielmandanten (SCRIPT) erstellt.</span><span class="sxs-lookup"><span data-stu-id="db661-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="db661-154">Ein Migrationsendpunkt wird erstellt, um Postfächer an den Zielmandanten (SCRIPT) zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="db661-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="db661-155">Vorbereiten des Quellmandanten:</span><span class="sxs-lookup"><span data-stu-id="db661-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="db661-156">Der Administrator des Quellmandanten akzeptiert die Zustimmung zur Postfachmigrationsanwendungseinladung vom Zielmandanten (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="db661-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="db661-157">Der Administrator des Quellmandanten erstellt eine E-Mail-aktivierte Sicherheitsgruppe in ihrem Mandanten, die die Liste der Postfächer enthält, die von der Migrationsanwendung verschoben werden dürfen (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="db661-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="db661-158">Es wird eine Organisationsbeziehung mit dem Zielmandanten erstellt, der angibt, dass die Postfachmigrationsanwendung für die OAuth-Überprüfung verwendet werden soll, um die Verschiebungsanforderung (SCRIPT) zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="db661-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="db661-159">Schritt-für-Schritt-Anweisungen für den Zielmandantenadministrator</span><span class="sxs-lookup"><span data-stu-id="db661-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="db661-160">Laden Sie das Skript SetupCrossTenantRelationshipForTargetTenant.ps1 für das Setup des Zielmandanten aus dem [GitHub-Repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview)herunter.</span><span class="sxs-lookup"><span data-stu-id="db661-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="db661-161">Speichern Sie das Skript (SetupCrossTenantRelationshipForTargetTenant.ps1) auf dem Computer, auf dem Sie das Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="db661-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="db661-162">Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Exchange Online Zielmandanten.</span><span class="sxs-lookup"><span data-stu-id="db661-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="db661-163">Stellen Sie erneut sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um den Azure Key Vault-Speicher und das Azure Key Vault-Zertifikat, die Move Mailbox-Anwendung, den EXO-Migrationsendpunkt und die EXO-Organisationsbeziehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="db661-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="db661-164">Ändern Sie das Dateiordnerverzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Ihrer Remote-PowerShell-Sitzung befindet.</span><span class="sxs-lookup"><span data-stu-id="db661-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="db661-165">Führen Sie das Skript mit den folgenden Parametern und Werten aus.</span><span class="sxs-lookup"><span data-stu-id="db661-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="db661-166">Parameter</span><span class="sxs-lookup"><span data-stu-id="db661-166">Parameter</span></span> | <span data-ttu-id="db661-167">Wert</span><span class="sxs-lookup"><span data-stu-id="db661-167">Value</span></span> | <span data-ttu-id="db661-168">Erforderlich oder optional</span><span class="sxs-lookup"><span data-stu-id="db661-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="db661-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="db661-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="db661-170">Zielmandantendomäne, z. B. fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="db661-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="db661-171">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-171">Required</span></span> |
    | <span data-ttu-id="db661-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="db661-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="db661-173">Quellmandantendomäne, z. B. contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="db661-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="db661-174">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-174">Required</span></span> |
    | <span data-ttu-id="db661-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="db661-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="db661-176">E-Mail-Adresse des Quellmandantenadministrators.</span><span class="sxs-lookup"><span data-stu-id="db661-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="db661-177">Dies ist der Quellmandantenadministrator, der der Verwendung der Vom Zieladministrator gesendeten Postfachmigrationsanwendung zustimmt. Dies ist der Administrator, der die E-Mail-Einladung für die Anwendung erhält.</span><span class="sxs-lookup"><span data-stu-id="db661-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="db661-178">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-178">Required</span></span> |
    | <span data-ttu-id="db661-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="db661-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="db661-180">Quellmandanten-Organisations-ID (GUID).</span><span class="sxs-lookup"><span data-stu-id="db661-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="db661-181">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-181">Required</span></span> |
    | <span data-ttu-id="db661-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="db661-182">-SubscriptionId</span></span>                             | <span data-ttu-id="db661-183">Das Azure-Abonnement, das zum Erstellen von Ressourcen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="db661-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="db661-184">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-184">Required</span></span> |
    | <span data-ttu-id="db661-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="db661-185">-ResourceGroup</span></span>                              | <span data-ttu-id="db661-186">Name der Azure-Ressourcengruppe, die den Key Vault enthält oder enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="db661-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="db661-187">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-187">Required</span></span> |
    | <span data-ttu-id="db661-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="db661-188">-KeyVaultName</span></span>                               | <span data-ttu-id="db661-189">Azure Key Vault-Instanz, die Ihr Postfachmigrationsanwendungszertifikat/-geheimnis speichert.</span><span class="sxs-lookup"><span data-stu-id="db661-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="db661-190">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-190">Required</span></span> |
    | <span data-ttu-id="db661-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="db661-191">-CertificateName</span></span>                            | <span data-ttu-id="db661-192">Zertifikatname beim Generieren oder Suchen nach Zertifikaten im Schlüsseltresor.</span><span class="sxs-lookup"><span data-stu-id="db661-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="db661-193">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-193">Required</span></span> |
    | <span data-ttu-id="db661-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="db661-194">-CertificateSubject</span></span>                         | <span data-ttu-id="db661-195">Name des Azure Key Vault-Zertifikatantragstellers, z. B. CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="db661-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="db661-196">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-196">Required</span></span> |
    | <span data-ttu-id="db661-197">-AzureResourceLocation</span><span class="sxs-lookup"><span data-stu-id="db661-197">-AzureResourceLocation</span></span>                      | <span data-ttu-id="db661-198">Der Speicherort der Azure-Ressourcengruppe und des Schlüsseltresors.</span><span class="sxs-lookup"><span data-stu-id="db661-198">The location of the Azure resource group and key vault.</span></span> | <span data-ttu-id="db661-199">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-199">Required</span></span> |
    | <span data-ttu-id="db661-200">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="db661-200">-ExistingApplicationId</span></span>                      | <span data-ttu-id="db661-201">E-Mail-Migrationsanwendung, die verwendet werden soll, wenn eine bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="db661-201">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="db661-202">Optional</span><span class="sxs-lookup"><span data-stu-id="db661-202">Optional</span></span> |
    | <span data-ttu-id="db661-203">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="db661-203">-AzureAppPermissions</span></span>                        | <span data-ttu-id="db661-204">Die erforderlichen Berechtigungen für die Postfachmigrationsanwendung, z. B. Exchange oder MSGraph (Exchange zum Verschieben von Postfächern, MSGraph für die Verwendung dieser Anwendung zum Senden einer Zustimmungslink-Einladung an den Ressourcenmandanten).</span><span class="sxs-lookup"><span data-stu-id="db661-204">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="db661-205">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="db661-205">Required</span></span> |
    | <span data-ttu-id="db661-206">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="db661-206">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="db661-207">Parameter für die Verwendung der Anwendung, die für die Migration erstellt wurde, um die Einladung zum Senden von Zustimmungslinks an den Administrator des Quellmandanten zu senden. Wenn dies nicht vorhanden ist, werden die Anmeldeinformationen des Zieladministrators aufgefordert, eine Verbindung mit dem Azure-Einladungs-Manager herzustellen und die Einladung als Zieladministrator zu senden.</span><span class="sxs-lookup"><span data-stu-id="db661-207">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="db661-208">Optional</span><span class="sxs-lookup"><span data-stu-id="db661-208">Optional</span></span> |
    | <span data-ttu-id="db661-209">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="db661-209">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="db661-210">Das Speicherkonto, in dem die Überwachungsprotokolle von Key Vault gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="db661-210">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="db661-211">Optional</span><span class="sxs-lookup"><span data-stu-id="db661-211">Optional</span></span> |
    | <span data-ttu-id="db661-212">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="db661-212">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="db661-213">Die Ressourcengruppe, die das Speicherkonto zum Speichern von Key Vault-Überwachungsprotokollen enthält.</span><span class="sxs-lookup"><span data-stu-id="db661-213">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="db661-214">Optional</span><span class="sxs-lookup"><span data-stu-id="db661-214">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="db661-215">Stellen Sie sicher, dass Sie das Azure AD PowerShell-Modul installiert haben, bevor Sie die Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="db661-215">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="db661-216">Installationsschritte finden Sie ![ hier. ](/powershell/azure/install-az-ps?view=azps-5.1.0)</span><span class="sxs-lookup"><span data-stu-id="db661-216">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="db661-217">Das Skript hält an und fordert Sie auf, die Exchange Postfachmigrationsanwendung zu akzeptieren oder zuzustimmen, die während dieses Prozesses erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="db661-217">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="db661-218">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-218">Here is an example.</span></span>

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

7. <span data-ttu-id="db661-219">Eine URL wird in der Remote-PowerShell-Sitzung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db661-219">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="db661-220">Kopieren Sie den Link, der für Die Zustimmung Ihres Mandanten bereitgestellt wurde, und fügen Sie ihn in einen Webbrowser ein.</span><span class="sxs-lookup"><span data-stu-id="db661-220">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="db661-221">Melden Sie sich mit Ihren Anmeldeinformationen für den globalen Administrator an.</span><span class="sxs-lookup"><span data-stu-id="db661-221">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="db661-222">Wenn der folgende Bildschirm angezeigt wird, wählen Sie **"Annehmen"** aus.</span><span class="sxs-lookup"><span data-stu-id="db661-222">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogfeld &quot;Berechtigungen akzeptieren&quot;":::

9. <span data-ttu-id="db661-224">Wechseln Sie zurück zur Remote-PowerShell-Sitzung, und drücken Sie die EINGABETASTE, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="db661-224">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="db661-225">Das Skript konfiguriert die verbleibenden Setupobjekte.</span><span class="sxs-lookup"><span data-stu-id="db661-225">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="db661-226">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-226">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="db661-227">Das Setup des Zieladministrators ist jetzt abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="db661-227">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="db661-228">Schritt-für-Schritt-Anleitungen für den Administrator des Quellmandanten</span><span class="sxs-lookup"><span data-stu-id="db661-228">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="db661-229">Melden Sie sich bei Ihrem Postfach als -ResourceTenantAdminEmail an, das vom Zieladministrator während der Einrichtung angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="db661-229">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="db661-230">Suchen Sie die E-Mail-Einladung vom Zielmandanten, und wählen Sie dann die **Schaltfläche Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="db661-230">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogfeld &quot;Sie wurden eingeladen&quot;":::

2. <span data-ttu-id="db661-232">Wählen Sie **"Annehmen"** aus, um die Einladung anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="db661-232">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialogfeld zum Akzeptieren von Berechtigungen":::

   > [!NOTE]
   > <span data-ttu-id="db661-234">Wenn Sie diese E-Mail nicht erhalten oder nicht finden können, wurde dem Zielmandantenadministrator eine direkte URL bereitgestellt, die Ihnen zur Annahme der Einladung zur Verfügung gestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="db661-234">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="db661-235">Die URL sollte sich in der Aufzeichnung der Remote-PowerShell-Sitzung des Zielmandantenadministrators befinden.</span><span class="sxs-lookup"><span data-stu-id="db661-235">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="db661-236">Erstellen Sie in der Microsoft 365 Admin Center oder einer Remote-PowerShell-Sitzung eine oder mehrere E-Mail-aktivierte Sicherheitsgruppen, um die Liste der Postfächer zu steuern, die vom Zielmandanten zum Abrufen (Verschieben) vom Quellmandanten zum Zielmandanten zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="db661-236">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="db661-237">Sie müssen diese Gruppe nicht im Voraus auffüllen, aber mindestens eine Gruppe muss bereitgestellt werden, um die Setupschritte (Skript) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db661-237">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="db661-238">Schachtelungsgruppen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db661-238">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="db661-239">Laden Sie das Skript SetupCrossTenantRelationshipForResourceTenant.ps1 für das Setup des Quellmandanten aus dem GitHub-Repository herunter: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="db661-239">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="db661-240">Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Quellmandanten mit Ihren Exchange Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="db661-240">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="db661-241">Globale Administratorberechtigungen sind nicht erforderlich, um den Quellmandanten zu konfigurieren, nur den Zielmandanten aufgrund des Erstellungsprozesses der Azure-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="db661-241">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="db661-242">Ändern Sie das Verzeichnis in den Skriptspeicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in Ihrer Remote-PowerShell-Sitzung befindet.</span><span class="sxs-lookup"><span data-stu-id="db661-242">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="db661-243">Führen Sie das Skript mit den folgenden erforderlichen Parametern und Werten aus.</span><span class="sxs-lookup"><span data-stu-id="db661-243">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="db661-244">Parameter</span><span class="sxs-lookup"><span data-stu-id="db661-244">Parameter</span></span> | <span data-ttu-id="db661-245">Wert</span><span class="sxs-lookup"><span data-stu-id="db661-245">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="db661-246">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="db661-246">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="db661-247">E-Mail-aktivierte Sicherheitsgruppe, die vom Quellmandanten für die Identitäten/Postfächer erstellt wird, die sich im Bereich der Migration befinden.</span><span class="sxs-lookup"><span data-stu-id="db661-247">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="db661-248">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="db661-248">-ResourceTenantDomain</span></span> | <span data-ttu-id="db661-249">Domänenname des Quellmandanten, z. B. contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="db661-249">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="db661-250">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="db661-250">-ApplicationId</span></span> | <span data-ttu-id="db661-251">Die Azure-Anwendungs-ID (GUID) der für die Migration verwendeten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="db661-251">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="db661-252">Anwendungs-ID, die über Ihr Azure-Portal (Azure AD, Enterprise Anwendungen, App-Name, Anwendungs-ID) oder in Ihrer Einladungs-E-Mail enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="db661-252">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="db661-253">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="db661-253">-TargetTenantDomain</span></span> | <span data-ttu-id="db661-254">Zielmandantendomänenname, z. B. fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="db661-254">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="db661-255">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="db661-255">-TargetTenantId</span></span> | <span data-ttu-id="db661-256">Mandanten-ID des Zielmandanten.</span><span class="sxs-lookup"><span data-stu-id="db661-256">Tenant ID of the target tenant.</span></span> <span data-ttu-id="db661-257">Beispielsweise die Azure AD-Mandanten-ID von contoso \. onmicrosoft.com Mandanten.</span><span class="sxs-lookup"><span data-stu-id="db661-257">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="db661-258">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-258">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="db661-259">Das Setup des Quelladministrators ist jetzt abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="db661-259">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="db661-260">Überprüfen der Einrichtung</span><span class="sxs-lookup"><span data-stu-id="db661-260">Verify setup</span></span>

<span data-ttu-id="db661-261">Stellen Sie sicher, dass die Organisationsbeziehungen in Quell- und Zielmandanten sowie der Migrationsendpunkt im Ziel erfolgreich erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="db661-261">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="db661-262">Zielmandant</span><span class="sxs-lookup"><span data-stu-id="db661-262">Target tenant</span></span>

<span data-ttu-id="db661-263">**Organisationsbeziehung**</span><span class="sxs-lookup"><span data-stu-id="db661-263">**Organization relationship**</span></span>

<span data-ttu-id="db661-264">Stellen Sie sicher, dass das Organisationsbeziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="db661-264">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="db661-265">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="db661-265">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="db661-266">**Migrationsendpunkt**</span><span class="sxs-lookup"><span data-stu-id="db661-266">**Migration endpoint**</span></span>

<span data-ttu-id="db661-267">Stellen Sie sicher, dass das Migrationsendpunktobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="db661-267">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="db661-268">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-268">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="db661-269">Quellmandant</span><span class="sxs-lookup"><span data-stu-id="db661-269">Source tenant</span></span>

<span data-ttu-id="db661-270">**Organisationsbeziehung**</span><span class="sxs-lookup"><span data-stu-id="db661-270">**Organization relationship**</span></span>

<span data-ttu-id="db661-271">Stellen Sie sicher, dass das Organisationsbeziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="db661-271">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="db661-272">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-272">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="db661-273">Überprüfen des Setupskripts</span><span class="sxs-lookup"><span data-stu-id="db661-273">Verify Setup Script</span></span>

<span data-ttu-id="db661-274">Wenn während der Konfiguration der Quell- oder Zielmandanten Fehler auftreten, können Sie das VerifySetup.ps1 Skript ausführen, das sich [auf GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) befindet, und die Ausgabe überprüfen.</span><span class="sxs-lookup"><span data-stu-id="db661-274">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="db661-275">Hier ist ein Beispiel für die Ausführung von VerifySetup.ps1 auf dem Zielmandanten:</span><span class="sxs-lookup"><span data-stu-id="db661-275">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="db661-276">Hier ist ein Beispiel für VerifySetup.ps1 auf dem Quellmandanten:</span><span class="sxs-lookup"><span data-stu-id="db661-276">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="db661-277">Verschieben von Postfächern zurück zur ursprünglichen Quelle</span><span class="sxs-lookup"><span data-stu-id="db661-277">Move mailboxes back to the original source</span></span>

<span data-ttu-id="db661-278">Wenn ein Postfach zurück zum ursprünglichen Quellmandanten verschoben werden muss, müssen die gleichen Schritte und Skripts sowohl in neuen Quell- als auch in neuen Zielmandanten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="db661-278">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="db661-279">Das vorhandene Organization Relationship-Objekt wird aktualisiert oder angefügt, nicht neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="db661-279">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="db661-280">Vorbereiten von Zielbenutzerobjekten für die Migration</span><span class="sxs-lookup"><span data-stu-id="db661-280">Prepare target user objects for migration</span></span>

<span data-ttu-id="db661-281">Benutzer, die migrieren, müssen im Zielmandanten vorhanden sein und Exchange Online System (als MailUsers) mit bestimmten Attributen gekennzeichnet sein, um mandantenübergreifende Verschiebungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="db661-281">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="db661-282">Bei Benutzern, die im Zielmandanten nicht ordnungsgemäß eingerichtet sind, schlägt das System fehl.</span><span class="sxs-lookup"><span data-stu-id="db661-282">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="db661-283">Im folgenden Abschnitt werden die MailUser-Objektanforderungen für den Zielmandanten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db661-283">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="db661-284">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="db661-284">Prerequisites</span></span>
  
<span data-ttu-id="db661-285">Sie müssen sicherstellen, dass die folgenden Objekte und Attribute in der Zielorganisation festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="db661-285">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="db661-286">Für jedes Postfach, das aus einer Quellorganisation verschoben wird, müssen Sie ein MailUser-Objekt in der Zielorganisation bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="db661-286">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="db661-287">Der Ziel-MailUser muss über diese Attribute aus dem Quellpostfach verfügen oder dem neuen User-Objekt zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="db661-287">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="db661-288">ExchangeGUID (direkter Fluss von Quelle zu Ziel) – Die Postfach-GUID muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="db661-288">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="db661-289">Der Verschiebungsprozess wird nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="db661-289">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="db661-290">ArchiveGUID (direkter Fluss von Quelle zu Ziel) – Die Archiv-GUID muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="db661-290">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="db661-291">Der Verschiebungsprozess wird nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="db661-291">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="db661-292">(Dies ist nur erforderlich, wenn das Quellpostfach archiviert ist).</span><span class="sxs-lookup"><span data-stu-id="db661-292">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="db661-293">LegacyExchangeDN (Flow as proxyAddress, "x500: <LegacyExchangeDN> ") – Der LegacyExchangeDN muss auf MailUser als x500 vorhanden sein: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="db661-293">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="db661-294">Die Verschiebungsprozesse werden nicht fortgesetzt, wenn dies im Zielobjekt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="db661-294">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="db661-295">UserPrincipalName – UPN richtet sich nach der NEUEN Identität oder dem Zielunternehmen des Benutzers (z. B. user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="db661-295">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="db661-296">Primäre SMTPAddress – Primäre SMTP-Adresse richtet sich nach dem NEUEN Unternehmen des Benutzers (z. B. user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="db661-296">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="db661-297">TargetAddress/ExternalEmailAddress – MailUser verweist auf das aktuelle Postfach des Benutzers, das im Quellmandanten gehostet wird (z. B. user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="db661-297">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="db661-298">Stellen Sie beim Zuweisen dieses Werts sicher, dass Sie PrimarySMTPAddress zugewiesen haben/sind, oder dieser Wert legt die PrimarySMTPAddress fest, was zu Verschiebungsfehlern führt.</span><span class="sxs-lookup"><span data-stu-id="db661-298">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="db661-299">Sie können keine älteren SMTP-Proxyadressen aus dem Quellpostfach zum MailUser-Ziel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="db661-299">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="db661-300">Beispielsweise können Sie contoso.com auf dem MEU in fabrikam.onmicrosoft.com Mandantenobjekten nicht verwalten).</span><span class="sxs-lookup"><span data-stu-id="db661-300">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="db661-301">Domänen sind nur einem Azure AD- oder Exchange Online-Mandanten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="db661-301">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="db661-302">Beispiel **für ein** MailUser-Zielobjekt:</span><span class="sxs-lookup"><span data-stu-id="db661-302">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="db661-303">Attribut</span><span class="sxs-lookup"><span data-stu-id="db661-303">Attribute</span></span>             | <span data-ttu-id="db661-304">Wert</span><span class="sxs-lookup"><span data-stu-id="db661-304">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="db661-305">Alias</span><span class="sxs-lookup"><span data-stu-id="db661-305">Alias</span></span>                 | <span data-ttu-id="db661-306">LaraN</span><span class="sxs-lookup"><span data-stu-id="db661-306">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="db661-307">RecipientType</span><span class="sxs-lookup"><span data-stu-id="db661-307">RecipientType</span></span>         | <span data-ttu-id="db661-308">MailUser</span><span class="sxs-lookup"><span data-stu-id="db661-308">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="db661-309">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="db661-309">RecipientTypeDetails</span></span>  | <span data-ttu-id="db661-310">MailUser</span><span class="sxs-lookup"><span data-stu-id="db661-310">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="db661-311">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="db661-311">UserPrincipalName</span></span>     | <span data-ttu-id="db661-312">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="db661-312">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="db661-313">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="db661-313">PrimarySmtpAddress</span></span>    | <span data-ttu-id="db661-314">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="db661-314">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="db661-315">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="db661-315">ExternalEmailAddress</span></span>  | <span data-ttu-id="db661-316">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="db661-316">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="db661-317">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="db661-317">ExchangeGuid</span></span>          | <span data-ttu-id="db661-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="db661-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="db661-319">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="db661-319">LegacyExchangeDN</span></span>      | <span data-ttu-id="db661-320">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="db661-320">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="db661-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="db661-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="db661-322">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="db661-322">EmailAddresses</span></span>        | <span data-ttu-id="db661-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="db661-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="db661-324">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="db661-324">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="db661-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="db661-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="db661-326">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="db661-326">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="db661-327">Beispiel für ein Quellpostfachobjekt: </span><span class="sxs-lookup"><span data-stu-id="db661-327">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="db661-328">Attribut</span><span class="sxs-lookup"><span data-stu-id="db661-328">Attribute</span></span>             | <span data-ttu-id="db661-329">Wert</span><span class="sxs-lookup"><span data-stu-id="db661-329">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="db661-330">Alias</span><span class="sxs-lookup"><span data-stu-id="db661-330">Alias</span></span>                 | <span data-ttu-id="db661-331">LaraN</span><span class="sxs-lookup"><span data-stu-id="db661-331">LaraN</span></span>                                                                    |
     | <span data-ttu-id="db661-332">RecipientType</span><span class="sxs-lookup"><span data-stu-id="db661-332">RecipientType</span></span>         | <span data-ttu-id="db661-333">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="db661-333">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="db661-334">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="db661-334">RecipientTypeDetails</span></span>  | <span data-ttu-id="db661-335">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="db661-335">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="db661-336">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="db661-336">UserPrincipalName</span></span>     | <span data-ttu-id="db661-337">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="db661-337">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="db661-338">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="db661-338">PrimarySmtpAddress</span></span>    | <span data-ttu-id="db661-339">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="db661-339">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="db661-340">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="db661-340">ExchangeGuid</span></span>          | <span data-ttu-id="db661-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="db661-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="db661-342">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="db661-342">LegacyExchangeDN</span></span>      | <span data-ttu-id="db661-343">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="db661-343">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="db661-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="db661-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="db661-345">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="db661-345">EmailAddresses</span></span>        | <span data-ttu-id="db661-346">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="db661-346">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="db661-347">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="db661-347">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="db661-348">Zusätzliche Attribute können bereits in Exchange Hybridrückschreiben enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="db661-348">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="db661-349">Wenn nicht, sollten sie eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="db661-349">If not, they should be included.</span></span> 
   - <span data-ttu-id="db661-350">msExchBlockedSendersHash – Schreibt online sichere und blockierte Absenderdaten von Clients in lokales Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="db661-350">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="db661-351">msExchSafeRecipientsHash – Schreibt online sichere und blockierte Absenderdaten von Clients in lokales Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="db661-351">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="db661-352">msExchSafeSendersHash – Schreibt online sichere und blockierte Absenderdaten von Clients in lokales Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="db661-352">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="db661-353">Wenn sich das Quellpostfach auf LitigationHold befindet und die Größe des Quellpostfachs "Wiederherstellbare Elemente" größer als der Datenbankstandard (30 GB) ist, werden Verschiebungen nicht fortgesetzt, da das Zielkontingent kleiner als die Größe des Quellpostfachs ist.</span><span class="sxs-lookup"><span data-stu-id="db661-353">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="db661-354">Sie können das MailUser-Zielobjekt so aktualisieren, dass die ELC-Postfachflags von der Quellumgebung auf das Ziel übertragen werden. Dadurch wird das Zielsystem veranlasst, das Kontingent der MailUser auf 100 GB zu erweitern, wodurch die Verschiebung zum Ziel ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="db661-354">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="db661-355">Diese Anweisungen funktionieren nur für hybride Identitäten, die Azure AD Verbinden ausführen, da die Befehle zum Stempeln der ELC-Flags für Mandantenadministratoren nicht verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="db661-355">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="db661-356">BEISPIEL – WIE BESEHEN KEINE GARANTIE</span><span class="sxs-lookup"><span data-stu-id="db661-356">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="db661-357">Dieses Skript geht von einer Verbindung mit dem Quellpostfach (zum Abrufen von Quellwerten) und dem lokalen Ziel-Active Directory (zum Stempeln des ADUser-Objekts) aus.</span><span class="sxs-lookup"><span data-stu-id="db661-357">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="db661-358">Wenn für die Quelle rechtsstreitigkeiten oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto fest.</span><span class="sxs-lookup"><span data-stu-id="db661-358">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="db661-359">Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="db661-359">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="db661-360">Nicht hybride Zielmandanten können das Kontingent im Ordner "Wiederherstellbare Elemente" für die MailUsers vor der Migration ändern, indem sie den folgenden Befehl ausführen, um das Beweissicherungsverfahren für das MailUser-Objekt zu aktivieren und das Kontingent auf 100 GB zu erhöhen: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="db661-360">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="db661-361">Beachten Sie, dass dies für Mandanten in hybriden Umgebungen nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="db661-361">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="db661-362">Benutzer in der Zielorganisation müssen mit entsprechenden Exchange Online Abonnements lizenziert werden, die für die Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="db661-362">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="db661-363">Sie können eine Lizenz vor einer Postfachverlagerung anwenden, jedoch NUR, wenn das Ziel-MailUser ordnungsgemäß mit ExchangeGUID- und Proxyadressen eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="db661-363">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="db661-364">Das Anwenden einer Lizenz vor der Anwendung von ExchangeGUID führt zu einem neuen Postfach, das in der Zielorganisation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="db661-364">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="db661-365">Wenn Sie eine Lizenz auf ein Postfach- oder MailUser-Objekt anwenden, werden alle PROXYAddresses des SMTP-Typs bereinigt, um sicherzustellen, dass nur überprüfte Domänen im Exchange EmailAddresses-Array enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="db661-365">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="db661-366">Sie müssen sicherstellen, dass das Ziel-MailUser keine vorherige ExchangeGuid-Datei aufweist, die nicht mit der ExchangeGuid-Quelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="db661-366">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="db661-367">Dies kann vorkommen, wenn die Ziel-MEU zuvor für Exchange Online lizenziert und ein Postfach bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="db661-367">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="db661-368">Wenn das Ziel-MailUser zuvor für ExchangeGuid lizenziert wurde oder über ein ExchangeGuid verfügt, das nicht mit der ExchangeGuid-Quelle übereinstimmt, müssen Sie eine Bereinigung der Cloud-MEU durchführen.</span><span class="sxs-lookup"><span data-stu-id="db661-368">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="db661-369">Für diese Cloud-MEUs können Sie `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` ausführen.</span><span class="sxs-lookup"><span data-stu-id="db661-369">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="db661-370">Dieser Vorgang ist unumkehrbar.</span><span class="sxs-lookup"><span data-stu-id="db661-370">This process is irreversible.</span></span> <span data-ttu-id="db661-371">Wenn das Objekt über ein "softDeleted"-Postfach verfügt, kann es nach diesem Punkt nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="db661-371">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="db661-372">Nach dem Löschen können Sie jedoch die richtige ExchangeGuid mit dem Zielobjekt synchronisieren, und MRS verbindet das Quellpostfach mit dem neu erstellten Zielpostfach.</span><span class="sxs-lookup"><span data-stu-id="db661-372">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="db661-373">(Verweisen Sie auf den EHLO-Blog zum neuen Parameter.)</span><span class="sxs-lookup"><span data-stu-id="db661-373">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="db661-374">Suchen Sie objekte, bei denen es sich zuvor um Postfächer handelte, mit diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="db661-374">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="db661-375">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-375">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="db661-376">Löschen Sie das vorläufig gelöschte Postfach mit diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="db661-376">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="db661-377">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-377">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="db661-378">Durchführen von Postfachmigrationen</span><span class="sxs-lookup"><span data-stu-id="db661-378">Perform mailbox migrations</span></span>

<span data-ttu-id="db661-379">Mandantenübergreifende Exchange Postfachmigrationen werden als Migrationsbatches übermittelt, die vom Zielmandanten initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="db661-379">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="db661-380">Dies ähnelt der Art und Weise, wie Migrationsbatches beim Onboarding von Exchange lokalen zu Microsoft 365 funktionieren.</span><span class="sxs-lookup"><span data-stu-id="db661-380">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="db661-381">Erstellen von Migrationsbatches</span><span class="sxs-lookup"><span data-stu-id="db661-381">Create Migration batches</span></span>

<span data-ttu-id="db661-382">Nachfolgend sehen Sie ein Beispiel für ein Cmdlet für migrationsbatches Cmdlet zum Starten von Verschiebungen.</span><span class="sxs-lookup"><span data-stu-id="db661-382">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="db661-383">Die E-Mail-Adresse in der CSV-Datei muss die im Zielmandanten und nicht im Quellmandanten angegebene Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="db661-383">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="db661-384">Die Batchübermittlung für die Migration wird auch vom neuen Exchange Admin Center unterstützt, wenn Sie die mandantenübergreifende Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="db661-384">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="db661-385">Aktualisieren von lokalen MailUsers</span><span class="sxs-lookup"><span data-stu-id="db661-385">Update on-premises MailUsers</span></span>

<span data-ttu-id="db661-386">Sobald das Postfach von der Quelle zum Ziel wechselt, sollten Sie sicherstellen, dass die lokalen E-Mail-Benutzer (Quelle und Ziel) mit der neuen targetAddress aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="db661-386">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="db661-387">In den Beispielen ist die targetDeliveryDomain, die bei der Verschiebung verwendet **wird, contoso.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="db661-387">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="db661-388">Aktualisieren Sie die E-Mail-Benutzer mit dieser targetAddress.</span><span class="sxs-lookup"><span data-stu-id="db661-388">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="db661-389">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="db661-389">Frequently asked questions</span></span>

<span data-ttu-id="db661-390">**Müssen RemoteMailboxes nach dem Verschieben lokal in der Quelle aktualisiert werden?**</span><span class="sxs-lookup"><span data-stu-id="db661-390">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="db661-391">Ja, Sie sollten die targetAddress (RemoteRoutingAddress/ExternalEmailAddress) der lokalen Quellbenutzer aktualisieren, wenn das Quellmandantenpostfach zum Zielmandanten verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="db661-391">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="db661-392">Während das E-Mail-Routing den Empfehlungen für mehrere E-Mail-Benutzer mit unterschiedlichen TargetAddresses folgen kann, MÜSSEN Frei/Gebucht-Nachschlagevorgänge für E-Mail-Benutzer auf den Speicherort des Postfachbenutzers abzielen.</span><span class="sxs-lookup"><span data-stu-id="db661-392">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="db661-393">Frei/Gebucht-Nachschlagevorgänge verfolgen nicht mehrere Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="db661-393">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="db661-394">**Migrieren Teams Besprechungen mandantenübergreifend?**</span><span class="sxs-lookup"><span data-stu-id="db661-394">**Do Teams meetings migrate cross-tenant?**</span></span>  

<span data-ttu-id="db661-395">Die Besprechungen werden jedoch verschoben, aber die Teams Besprechungs-URL wird nicht aktualisiert, wenn Elemente mandantenübergreifend migriert werden.</span><span class="sxs-lookup"><span data-stu-id="db661-395">The meetings will move however the Teams meeting URL does not update when items migrate cross-tenant.</span></span> <span data-ttu-id="db661-396">Da die URL im Zielmandanten ungültig ist, müssen Sie die Teams Besprechungen entfernen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="db661-396">Since the URL will be invalid in the target tenant you will need to remove and recreate the Teams meetings.</span></span>

<span data-ttu-id="db661-397">**Werden die Inhalte des Teams Chatordners mandantenübergreifend migriert?**</span><span class="sxs-lookup"><span data-stu-id="db661-397">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="db661-398">Nein, der inhalt des Teams Chatordners migriert nicht mandantenübergreifend.</span><span class="sxs-lookup"><span data-stu-id="db661-398">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="db661-399">**Wie kann ich nur Verschiebungen sehen, bei denen es sich um mandantenübergreifende Verschiebungen handelt, nicht um meine Onboarding- und Offboard-Verschiebungen?**</span><span class="sxs-lookup"><span data-stu-id="db661-399">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="db661-400">Verwenden Sie den `-flags` Parameter.</span><span class="sxs-lookup"><span data-stu-id="db661-400">Use the `-flags` parameter.</span></span> <span data-ttu-id="db661-401">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-401">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="db661-402">**Können Sie Beispielskripts zum Kopieren von Attributen bereitstellen, die beim Testen verwendet werden?**</span><span class="sxs-lookup"><span data-stu-id="db661-402">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="db661-403">BEISPIEL – WIE BESEHEN KEINE GARANTIE</span><span class="sxs-lookup"><span data-stu-id="db661-403">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="db661-404">Dieses Skript geht von einer Verbindung mit dem Quellpostfach (zum Abrufen von Quellwerten) und dem lokalen Active Directory Domain Services-Ziel (zum Stempeln des ADUser-Objekts) aus.</span><span class="sxs-lookup"><span data-stu-id="db661-404">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="db661-405">Wenn für die Quelle rechtsstreitigkeiten oder die Wiederherstellung einzelner Elemente aktiviert ist, legen Sie dies für das Zielkonto fest.</span><span class="sxs-lookup"><span data-stu-id="db661-405">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="db661-406">Dadurch wird die Dumpstergröße des Zielkontos auf 100 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="db661-406">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="db661-407">**Wie greifen wir am 1. Tag nach dem Verschieben des Verwendungspostfachs auf Outlook zu?**</span><span class="sxs-lookup"><span data-stu-id="db661-407">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="db661-408">Da nur ein Mandant eine Domäne besitzen kann, wird die frühere primäre SMTPAddress dem Benutzer im Zielmandanten nicht zugeordnet, wenn die Postfach-Verschiebung abgeschlossen ist. nur die Domänen, die dem neuen Mandanten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="db661-408">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="db661-409">Outlook verwendet den neuen BENUTZER-UPN, um sich beim Dienst zu authentifizieren, und das Outlook-Profil erwartet, dass die primäre SMTPAddress der Vorversion gefunden wird, die dem Postfach im Zielsystem entspricht.</span><span class="sxs-lookup"><span data-stu-id="db661-409">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="db661-410">Da sich die Legacyadresse nicht im Zielsystem befindet, stellt das Outlook-Profil keine Verbindung her, um das neu verschobene Postfach zu finden.</span><span class="sxs-lookup"><span data-stu-id="db661-410">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="db661-411">Für diese anfängliche Bereitstellung müssen Benutzer ihr Profil mit dem neuen UPN, der primären SMTP-Adresse und dem erneuten Synchronisieren von OST-Inhalten neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="db661-411">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="db661-412">Planen Sie entsprechend, wenn Sie Ihre Benutzer für den Abschluss batchen.</span><span class="sxs-lookup"><span data-stu-id="db661-412">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="db661-413">Sie müssen die Netzwerkauslastung und -kapazität berücksichtigen, wenn Outlook Clientprofile erstellt und nachfolgende OST- und OAB-Dateien auf Clients heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="db661-413">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="db661-414">**In welchen Exchange RBAC-Rollen muss ich Mitglied sein, um eine mandantenübergreifende Verschiebung einzurichten oder abzuschließen?**</span><span class="sxs-lookup"><span data-stu-id="db661-414">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="db661-415">Es gibt eine Matrix von Rollen, die auf der Annahme delegierter Aufgaben beim Ausführen einer Postfach-Verschiebung basiert.</span><span class="sxs-lookup"><span data-stu-id="db661-415">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="db661-416">Derzeit sind zwei Rollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="db661-416">Currently, two roles are required:</span></span>  

- <span data-ttu-id="db661-417">Die erste Rolle ist für eine einmalige Einrichtungsaufgabe, die die Autorisierung zum Verschieben von Inhalten in oder aus Ihrer Mandanten-/Organisationsgrenze festlegt.</span><span class="sxs-lookup"><span data-stu-id="db661-417">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="db661-418">Da das Verschieben von Daten aus Ihrer Organisatorischen Kontrolle für alle Unternehmen ein wichtiges Problem ist, haben wir uns für die höchste zugewiesene Rolle des Organisationsadministrators (OrgAdmin) entschieden.</span><span class="sxs-lookup"><span data-stu-id="db661-418">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="db661-419">Diese Rolle muss eine neue OrganizationRelationship ändern oder einrichten, die die -MailboxMoveCapability mit der Remoteorganisation definiert.</span><span class="sxs-lookup"><span data-stu-id="db661-419">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="db661-420">Nur der OrgAdmin kann die MailboxMoveCapability-Einstellung ändern, während andere Attribute in OrganizationRelationhip vom Verbundfreigabeadministrator verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="db661-420">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="db661-421">Die Rolle der Ausführung der tatsächlichen Verschiebungsbefehle kann an eine Funktion auf niedrigerer Ebene delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="db661-421">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="db661-422">Der Rolle des Verschiebens von Postfächern wird die Funktion zum Verschieben von Postfächern in oder aus der Organisation mithilfe des `-RemoteTenant` Parameters zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="db661-422">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="db661-423">**Wie wird die SMTP-Adresse als Ziel für targetAddress (TargetDeliveryDomain) im konvertierten Postfach (in MailUser-Konvertierung) ausgewählt?**</span><span class="sxs-lookup"><span data-stu-id="db661-423">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="db661-424">Exchange Postfach wird mithilfe von MRS verschoben, indem die targetAddress für das ursprüngliche Quellpostfach beim Konvertieren in einen MailUser erstellt wird, indem eine E-Mail-Adresse (proxyAddress) für das Zielobjekt zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="db661-424">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="db661-425">Der Prozess verwendet den Wert "-TargetDeliveryDomain", der an den Verschiebungsbefehl übergeben wird, und sucht dann auf der Zielseite nach einem übereinstimmenden Proxy für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="db661-425">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="db661-426">Wenn eine Übereinstimmung gefunden wird, wird die übereinstimmende proxyAddress verwendet, um die ExternalEmailAddress (targetAddress) für das konvertierte Postfachobjekt (jetzt MailUser) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="db661-426">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="db661-427">**Wie werden Postfachberechtigungen übertragen?**</span><span class="sxs-lookup"><span data-stu-id="db661-427">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="db661-428">Postfachberechtigungen umfassen "Senden im Auftrag von" und "Postfachzugriff":</span><span class="sxs-lookup"><span data-stu-id="db661-428">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="db661-429">Send On Behalf Of (AD:publicDelegates) speichert den DN von Empfängern mit Zugriff auf das Postfach eines Benutzers als Stellvertretung.</span><span class="sxs-lookup"><span data-stu-id="db661-429">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="db661-430">Dieser Wert wird in Active Directory gespeichert und wird derzeit nicht als Teil des Postfachübergangs verschoben.</span><span class="sxs-lookup"><span data-stu-id="db661-430">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="db661-431">Wenn für das Quellpostfach publicDelegates festgelegt sind, müssen Sie die publicDelegates für das Zielpostfach neu erstellen, sobald die MEU-in-Postfach-Konvertierung in der Zielumgebung abgeschlossen ist, indem Sie `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` ausführen.</span><span class="sxs-lookup"><span data-stu-id="db661-431">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="db661-432">Postfachberechtigungen, die im Postfach gespeichert sind, werden mit dem Postfach verschoben, wenn sowohl der Prinzipal als auch der Stellvertreter in das Zielsystem verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="db661-432">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="db661-433">Beispielsweise wird dem Benutzer TestUser_7 FullAccess für das Postfach gewährt, TestUser_8 im Mandanten-SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="db661-433">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="db661-434">Nachdem die Postfach-Verschiebung in TargetCompany.onmicrosoft.com abgeschlossen ist, werden die gleichen Berechtigungen im Zielverzeichnis eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="db661-434">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="db661-435">Beispiele für die Verwendung von *"Get-MailboxPermission"* für TestUser_7 in Quell- und Zielmandanten finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="db661-435">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="db661-436">Exchange Cmdlets wird das Präfix "Quelle" und "Ziel" entsprechend vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="db661-436">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="db661-437">Hier ist ein Beispiel für die Ausgabe der Postfachberechtigung vor einer Verschiebung.</span><span class="sxs-lookup"><span data-stu-id="db661-437">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="db661-438">Hier ist ein Beispiel für die Ausgabe der Postfachberechtigung nach der Verschiebung.</span><span class="sxs-lookup"><span data-stu-id="db661-438">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="db661-439">Mandantenübergreifende Postfach- und Kalenderberechtigungen werden NICHT unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db661-439">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="db661-440">Sie müssen Prinzipale und Stellvertretungen in konsolidierten Verschiebungsbatches organisieren, damit diese verbundenen Postfächer gleichzeitig vom Quellmandanten übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="db661-440">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="db661-441">**Welcher X500-Proxy sollte den MailUser-Zielproxyadressen hinzugefügt werden, um die Migration zu ermöglichen?**</span><span class="sxs-lookup"><span data-stu-id="db661-441">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="db661-442">Die mandantenübergreifende Postfachmigration erfordert, dass der LegacyExchangeDN-Wert des Quellpostfachobjekts als x500-E-Mail-Adresse im MailUser-Zielobjekt gestempelt wird.</span><span class="sxs-lookup"><span data-stu-id="db661-442">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="db661-443">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="db661-443">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="db661-444">Zusätzlich zu diesem X500-Proxy müssen Sie alle X500-Proxys aus dem Postfach in der Quelle in das Postfach im Ziel kopieren.</span><span class="sxs-lookup"><span data-stu-id="db661-444">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="db661-445">**Wo beginne ich mit der Problembehandlung, wenn Verschiebungen nicht funktionieren?**</span><span class="sxs-lookup"><span data-stu-id="db661-445">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="db661-446">Führen Sie zunächst das VerifySetup.ps1 Skript [aus,](https://github.com/microsoft/cross-tenant/releases/tag/Preview) das sich auf GitHub befindet, und überprüfen Sie die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="db661-446">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="db661-447">Hier ist ein Beispiel für die Ausführung von VerifySetup.ps1 auf dem Zielmandanten:</span><span class="sxs-lookup"><span data-stu-id="db661-447">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="db661-448">Hier ist ein eExample zum Ausführen von VerifySetup.ps1 auf dem Quellmandanten:</span><span class="sxs-lookup"><span data-stu-id="db661-448">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="db661-449">**Kann der Quell- und Zielmandant denselben Domänennamen verwenden?**</span><span class="sxs-lookup"><span data-stu-id="db661-449">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="db661-450">Nein</span><span class="sxs-lookup"><span data-stu-id="db661-450">No.</span></span> <span data-ttu-id="db661-451">Die Quell- und Zielmandantendomänennamen müssen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="db661-451">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="db661-452">Beispielsweise eine Quelldomäne von contoso.com und die Zieldomäne von fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="db661-452">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="db661-453">**Werden freigegebene Postfächer verschoben und funktionieren weiterhin?**</span><span class="sxs-lookup"><span data-stu-id="db661-453">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="db661-454">Ja, wir behalten jedoch nur die Speicherberechtigungen, wie in diesen Artikeln beschrieben:</span><span class="sxs-lookup"><span data-stu-id="db661-454">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="db661-455">Microsoft Docs | Verwalten von Berechtigungen für Empfänger in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="db661-455">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="db661-456">Microsoft-Support | So erteilen Sie Exchange und Outlook Postfachberechtigungen in Office 365 dedizierten</span><span class="sxs-lookup"><span data-stu-id="db661-456">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="db661-457">**Ist Azure Key Vault erforderlich und wann werden Transaktionen ausgeführt?**</span><span class="sxs-lookup"><span data-stu-id="db661-457">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="db661-458">Ja, ein Azure-Abonnement ist erforderlich, um Key Vault zum Speichern des Zertifikats zum Autorisieren der Migration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="db661-458">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="db661-459">Im Gegensatz zum Onboarding von Migrationen, bei denen Benutzername & Kennwort für die Authentifizierung bei der Quelle verwendet wird, verwenden mandantenübergreifende Postfachmigrationen OAuth und dieses Zertifikat als Geheimschlüssel/Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="db661-459">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="db661-460">Der Zugriff auf den Key Vault muss während aller Postfachmigrationen aufrechterhalten werden, da er einmal am Anfang und nach Ende der Migration sowie einmal alle 24 Stunden während inkrementeller Synchronisierungszeiten aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="db661-460">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="db661-461">Details zur AKV-Kostenkalkulation finden Sie [hier.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="db661-461">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="db661-462">**Haben Sie Empfehlungen für Batches?**</span><span class="sxs-lookup"><span data-stu-id="db661-462">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="db661-463">2000 Postfächer pro Batch nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="db661-463">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="db661-464">Es wird dringend empfohlen, Batches zwei Wochen vor dem Übernahmedatum zu übermitteln, da es während der Synchronisierung keine Auswirkungen auf die Endbenutzer gibt. Wenn Sie Anleitungen für Postfächer mit mehr als 50.000 Postfächern benötigen, können Sie sich an die Engineering Feedback Distribution List unter crosstenantmigrationpreview@service.microsoft.com wenden.</span><span class="sxs-lookup"><span data-stu-id="db661-464">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="db661-465">**Was geschieht, wenn ich die Dienstverschlüsselung mit Customer Key verwende?**</span><span class="sxs-lookup"><span data-stu-id="db661-465">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="db661-466">Das Postfach wird vor dem Verschieben entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="db661-466">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="db661-467">Stellen Sie sicher, dass der Kundenschlüssel im Zielmandanten konfiguriert ist, wenn er noch erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="db661-467">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="db661-468">Weitere Informationen finden Sie [hier.](../compliance/customer-key-overview.md)</span><span class="sxs-lookup"><span data-stu-id="db661-468">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="db661-469">**Wie lautet die geschätzte Migrationszeit?**</span><span class="sxs-lookup"><span data-stu-id="db661-469">**What is the estimated migration time?**</span></span>

<span data-ttu-id="db661-470">Um Sie bei der Planung Ihrer Migration zu unterstützen, enthält die [hier](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) aufgeführte Tabelle die Richtlinien dazu, wann Massenmigrationen von Postfächern oder einzelne Migrationen zu erwarten sind.</span><span class="sxs-lookup"><span data-stu-id="db661-470">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="db661-471">Diese Schätzungen basieren auf einer Datenanalyse vorheriger Kundenmigrationen.</span><span class="sxs-lookup"><span data-stu-id="db661-471">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="db661-472">Da jede Umgebung einzigartig ist, kann ihre genaue Migrationsgeschwindigkeit variieren.</span><span class="sxs-lookup"><span data-stu-id="db661-472">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="db661-473">Denken Sie daran, dass sich dieses Feature derzeit in der Vorschau befindet und die SLA und alle anwendbaren ServiceLevels während des Vorschaustatus dieses Features nicht auf Leistungs- oder Verfügbarkeitsprobleme angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="db661-473">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="db661-474">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="db661-474">Known issues</span></span>  

-  <span data-ttu-id="db661-475">**Problem: Automatisch erweiterte Archive können nicht migriert werden.**</span><span class="sxs-lookup"><span data-stu-id="db661-475">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="db661-476">Die mandantenübergreifende Migrationsfunktion unterstützt Migrationen des primären Postfachs und des Archivpostfachs für einen bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="db661-476">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="db661-477">Wenn der Benutzer in der Quelle jedoch über ein automatisch erweitertes Archiv verfügt , d. h. mehrere Archivpostfächer, kann das Feature die zusätzlichen Archive nicht migrieren und sollte fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="db661-477">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="db661-478">**Problem: Cloud-MailUsers mit nicht-owned smtp proxyAddress block MRS verschiebt Hintergrund.**</span><span class="sxs-lookup"><span data-stu-id="db661-478">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="db661-479">Beim Erstellen von MailUser-Zielmandantenobjekten müssen Sie sicherstellen, dass alle SMTP-Proxyadressen zur Zielmandantenorganisation gehören.</span><span class="sxs-lookup"><span data-stu-id="db661-479">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="db661-480">Wenn eine SMTP-Proxyadresse für den E-Mail-Zielbenutzer vorhanden ist, der nicht zum lokalen Mandanten gehört, wird die Konvertierung von MailUser in Postfach verhindert.</span><span class="sxs-lookup"><span data-stu-id="db661-480">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="db661-481">Dies ist aufgrund unserer Zusicherung, dass Postfachobjekte nur E-Mails von Domänen senden können, für die der Mandant autoritativ ist (vom Mandanten beanspruchte Domänen):</span><span class="sxs-lookup"><span data-stu-id="db661-481">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="db661-482">Wenn Sie Benutzer mithilfe von Azure AD Verbinden lokal synchronisieren, stellen Sie lokale MailUser-Objekte mit ExternalEmailAddress bereit, die auf den Quellmandanten zeigen, in dem das Postfach vorhanden ist (laran@contoso.onmicrosoft.com), und Sie stempeln die PrimarySMTPAddress als Domäne, die sich im Zielmandanten (Lara.Newton@northwind.com) befindet.</span><span class="sxs-lookup"><span data-stu-id="db661-482">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="db661-483">Diese Werte werden mit dem Mandanten synchronisiert, und ein entsprechender E-Mail-Benutzer wird bereitgestellt und für die Migration bereit.</span><span class="sxs-lookup"><span data-stu-id="db661-483">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="db661-484">Hier ist ein Beispielobjekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="db661-484">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="db661-485">Die *contoso.onmicrosoft.com Adresse* ist im Array EmailAddresses/proxyAddresses *nicht* vorhanden.</span><span class="sxs-lookup"><span data-stu-id="db661-485">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="db661-486">**Problem: MailUser-Objekte mit "externen" primären SMTP-Adressen werden geändert/auf "interne" vom Unternehmen beanspruchte Domänen zurückgesetzt.**</span><span class="sxs-lookup"><span data-stu-id="db661-486">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="db661-487">MailUser-Objekte sind Zeiger auf nicht lokale Postfächer.</span><span class="sxs-lookup"><span data-stu-id="db661-487">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="db661-488">Bei mandantenübergreifenden Postfachmigrationen verwenden wir MailUser-Objekte, um entweder das Quellpostfach (aus Sicht der Zielorganisation) oder das Zielpostfach (aus Sicht der Quellorganisation) darzustellen.</span><span class="sxs-lookup"><span data-stu-id="db661-488">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="db661-489">Die MailUsers verfügen über eine ExternalEmailAddress (targetAddress), die auf die SMTP-Adresse des tatsächlichen Postfachs (ProxyTest@fabrikam.onmicrosoft.com) und die primarySMTP-Adresse verweist, die die angezeigte SMTP-Adresse des Postfachbenutzers im Verzeichnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="db661-489">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="db661-490">Einige Organisationen entscheiden sich dafür, die primäre SMTP-Adresse als externe SMTP-Adresse anzuzeigen, nicht als Adresse, die dem lokalen Mandanten gehört/bestätigt wird (z. B. fabrikam.com statt als contoso.com).</span><span class="sxs-lookup"><span data-stu-id="db661-490">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="db661-491">Sobald jedoch ein Exchange Dienstplanobjekt über Lizenzierungsvorgänge auf mailUser angewendet wird, wird die primäre SMTP-Adresse so geändert, dass sie als von der lokalen Organisation überprüfte Domäne angezeigt wird (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="db661-491">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="db661-492">Es gibt zwei mögliche Gründe:</span><span class="sxs-lookup"><span data-stu-id="db661-492">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="db661-493">Wenn ein Exchange Serviceplan auf einen MailUser angewendet wird, erzwingt der Azure AD-Prozess das Proxy-Scrubbing, um sicherzustellen, dass die lokale Organisation keine E-Mails von einem anderen Mandanten senden kann.</span><span class="sxs-lookup"><span data-stu-id="db661-493">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="db661-494">Alle SMTP-Adressen in einem Empfängerobjekt mit diesen Serviceplänen werden entfernt, wenn die Adresse von der lokalen Organisation nicht überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="db661-494">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="db661-495">Wie im Beispiel wird die Fabikam.com Domäne nicht vom contoso.onmicrosoft.com Mandanten überprüft, sodass das Scrubbing diese Fabrikam.com Domäne entfernt.</span><span class="sxs-lookup"><span data-stu-id="db661-495">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="db661-496">Wenn Sie diese externe Domäne auf MailUser beibehalten möchten, entweder vor der Migration oder nach der Migration, müssen Sie Ihre Migrationsprozesse ändern, um Lizenzen nach Abschluss der Verschiebung oder vor der Verschiebung zu entfernen, um sicherzustellen, dass die Benutzer das erwartete externe Branding angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="db661-496">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="db661-497">Sie müssen sicherstellen, dass das Postfachobjekt ordnungsgemäß lizenziert ist, um keinen Einfluss auf den E-Mail-Dienst zu haben.</span><span class="sxs-lookup"><span data-stu-id="db661-497">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="db661-498">Ein Beispielskript zum Entfernen der Dienstpläne für einen MailUser im Contoso.onmicrosoft.com Mandanten wird hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="db661-498">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="db661-499">Hier werden ergebnisse in der Gruppe der zugewiesenen ServicePlans angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db661-499">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="db661-500">Die PrimarySMTPAddress des Benutzers wird nicht mehr bereinigt.</span><span class="sxs-lookup"><span data-stu-id="db661-500">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="db661-501">Die fabrikam.com Domäne gehört nicht dem contoso.onmicrosoft.com Mandanten und bleibt als primäre SMTP-Adresse im Verzeichnis erhalten.</span><span class="sxs-lookup"><span data-stu-id="db661-501">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="db661-502">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="db661-502">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="db661-503">Wenn msExchRemoteRecipientType auf 8 (DeprovisionMailbox) festgelegt ist, entfernt die Proxy-Scrubbinglogik in Azure für lokale MailUser, die zum Zielmandanten migriert werden, nicht zugewiesene Domänen und setzt das primarySMTP auf eine eigene Domäne zurück.</span><span class="sxs-lookup"><span data-stu-id="db661-503">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="db661-504">Durch Löschen von msExchRemoteRecipientType im lokalen MailUser wird die Proxy-Scrub-Logik nicht mehr angewendet.</span><span class="sxs-lookup"><span data-stu-id="db661-504">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="db661-505">Nachfolgend finden Sie den vollständigen Satz möglicher Servicepläne, die Exchange Online enthalten.</span><span class="sxs-lookup"><span data-stu-id="db661-505">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="db661-506">Name</span><span class="sxs-lookup"><span data-stu-id="db661-506">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="db661-507">Advanced eDiscovery Storage (500 GB)</span><span class="sxs-lookup"><span data-stu-id="db661-507">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="db661-508">Kunden-Lockbox</span><span class="sxs-lookup"><span data-stu-id="db661-508">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="db661-509">Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="db661-509">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="db661-510">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="db661-510">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="db661-511">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="db661-511">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="db661-512">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="db661-512">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="db661-513">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="db661-513">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="db661-514">Exchange Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="db661-514">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="db661-515">Exchange Online (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="db661-515">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="db661-516">Exchange Online-Archivierung für Exchange Online</span><span class="sxs-lookup"><span data-stu-id="db661-516">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="db661-517">Exchange Online-Archivierung für Exchange Server</span><span class="sxs-lookup"><span data-stu-id="db661-517">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="db661-518">Exchange Online Inaktives Benutzer-Add-On</span><span class="sxs-lookup"><span data-stu-id="db661-518">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="db661-519">Exchange Online-Kiosk</span><span class="sxs-lookup"><span data-stu-id="db661-519">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="db661-520">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="db661-520">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="db661-521">Exchange Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="db661-521">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="db661-522">Exchange Online-POP</span><span class="sxs-lookup"><span data-stu-id="db661-522">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="db661-523">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="db661-523">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="db661-524">Informationsbarrieren</span><span class="sxs-lookup"><span data-stu-id="db661-524">Information Barriers</span></span>                              |
   | <span data-ttu-id="db661-525">Information Protection für Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="db661-525">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="db661-526">Information Protection für Office 365 – Standard</span><span class="sxs-lookup"><span data-stu-id="db661-526">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="db661-527">Insights von MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="db661-527">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="db661-528">Microsoft 365 Erweiterte Überwachung</span><span class="sxs-lookup"><span data-stu-id="db661-528">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="db661-529">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="db661-529">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="db661-530">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="db661-530">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="db661-531">Microsoft MyAnalytics (Vollversion)</span><span class="sxs-lookup"><span data-stu-id="db661-531">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="db661-532">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="db661-532">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="db661-533">Microsoft Defender für Office 365 (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="db661-533">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="db661-534">Microsoft Defender für Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="db661-534">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="db661-535">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="db661-535">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="db661-536">Premium Verschlüsselung in Office 365</span><span class="sxs-lookup"><span data-stu-id="db661-536">Premium Encryption in Office 365</span></span>                  |
