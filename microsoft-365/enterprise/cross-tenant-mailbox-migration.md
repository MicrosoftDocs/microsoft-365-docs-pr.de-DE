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
ms.openlocfilehash: 06a82fda31e602ed2feb53d00e8839daf801bf7e
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277489"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="a3b1b-103">Mandantenübergreifende Postfachmigration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="a3b1b-104">Wenn ein Exchange Online-Mandant zuvor zum Verschieben von Postfächern in einen anderen Mandanten in demselben Exchange Online Dienst benötigt wurde, müsste er diese vollständig lokal extern und dann an einen neuen Mandanten an Bord bringen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="a3b1b-105">Mit dem neuen Feature für die Mandantenübergreifende Postfachmigration können mandantenadministratoren in den Quell-und Zielmandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in Ihren lokalen Systemen verschieben.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="a3b1b-106">Dadurch wird die Notwendigkeit, extern und Onboard-Postfächer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-106">This removes the need to offboard and onboard mailboxes.</span></span>

<span data-ttu-id="a3b1b-107">Bei Fusionen oder Veräußerungen benötigen Sie häufig die Möglichkeit, Benutzer und Inhalte in einen neuen Mandanten zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="a3b1b-108">Wenn der Zielmandanten Administrator den Umzug ausführt, wird er als Pull-Umzug bezeichnet, ähnlich wie bei Onboarding-Migrationen vor Ort und Cloud.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="a3b1b-109">Mandantenübergreifende Exchange-Postfachverschiebungen werden von mandantenadministratoren vollständig selbst gewartet, wobei bekannte Schnittstellen verwendet werden, die in die größeren Workflows geschrieben werden können, die für den Übergang von Benutzern zu ihrer neuen Organisation benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="a3b1b-110">Administratoren können das `New-MigrationBatch` Cmdlet verwenden, das über die Verwaltungsrolle "Postfächer verschieben" zur Verfügung steht, um Mandantenübergreifende Verschiebungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="a3b1b-111">Der Verschiebevorgang umfasst Mandanten Autorisierungsüberprüfungen während der Postfachsynchronisierung und-Fertigstellung.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="a3b1b-112">Benutzer, die migriert werden, müssen im Zielmandanten Exchange Online System als MailUser vorhanden sein, die mit bestimmten Attributen markiert sind, um die mandantenübergreifenden Verschiebungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="a3b1b-113">Das System führt keine Verschiebungen für Benutzer aus, die nicht ordnungsgemäß im Zielmandanten eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span> 

<span data-ttu-id="a3b1b-114">Wenn die Verschiebungen abgeschlossen sind, wird das Quellsystem Postfach in MailUser konvertiert, und die targetAddress (als ExternalEmailAddress in Exchange angezeigt) wird mit der Routingadresse an den Zielmandanten gestempelt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="a3b1b-115">Bei diesem Prozess bleibt die Legacy-MailUser im Quellmandanten und ermöglicht eine gewisse Zeit der Koexistenz und des e-Mail-Routings.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="a3b1b-116">Wenn Geschäftsprozesse dies zulassen, entfernt der Quellmandant möglicherweise die Quell-MailUser oder wandelt sie in einen e-Mail-Kontakt um.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="a3b1b-117">Mandantenübergreifende Exchange-Postfachmigrationen werden nur in Hybrid-oder Cloud-Umgebungen oder in einer beliebigen Kombination aus beiden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="a3b1b-118">In diesem Artikel wird der Prozess für Mandantenübergreifende Postfachverschiebungen beschrieben, und es werden Anleitungen zum Vorbereiten von Quell-und Zielmandanten für die Inhaltsverschiebung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span> 

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="a3b1b-119">Vorbereiten von Quell-und Zielmandanten</span><span class="sxs-lookup"><span data-stu-id="a3b1b-119">Preparing source and target tenants</span></span>

<span data-ttu-id="a3b1b-120">Das Feature für die Mandantenübergreifende Exchange-Postfachmigration erfordert Autorisierung und Scoping für Mandantenübergreifende Migrationen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="a3b1b-121">Mithilfe der Azure Enterprise-Anwendung und Schlüsselspeicher Lösungen für Vault können mandantenadministratoren nun die Autorisierung und das Scoping von Exchange Online Postfachmigrationen von einem Mandanten auf einen anderen verwalten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="a3b1b-122">Mandantenübergreifende Postfachverschiebungen unterstützen ein Einladungs-und Zustimmungs Modell zum Einrichten einer Azure Active Directory (Azure AD)-Anwendung, die für die Authentifizierung zwischen einem Mandanten paar verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="a3b1b-123">Zusätzliche Komponenten wie eine Organisationsbeziehung und ein Migrations Endpunkt sind ebenfalls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="a3b1b-124">In diesem Abschnitt werden nicht die erforderlichen Schritte zum Vorbereiten der MailUser-Benutzerobjekte im Zielverzeichnis sowie der Beispielbefehl zum Übermitteln eines Migrationsbatches berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="a3b1b-125">Informationen hierzu finden Sie unter [Vorbereiten von Zielbenutzer Objekten für die Migration](#prepare-target-user-objects-for-migration) .</span><span class="sxs-lookup"><span data-stu-id="a3b1b-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3b1b-126">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a3b1b-126">Prerequisites</span></span>

<span data-ttu-id="a3b1b-127">Das Feature für die Mandantenübergreifende Post Fach Verlagerung erfordert [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) , um eine mandantenspezifische Azure-Anwendung einzurichten, mit der sicher gespeichert und auf das Zertifikat/das Geheimnis zugegriffen werden kann, das zur Authentifizierung und Autorisierung der Postfachmigration von einem Mandanten zum anderen verwendet wird, sodass alle Anforderungen zum Freigeben von Zertifikaten/Schlüsseln zwischen Mandanten entfernt werden</span><span class="sxs-lookup"><span data-stu-id="a3b1b-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="a3b1b-128">Stellen Sie vor dem Starten sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um Azure Key Vault, Post Fachanwendung, Exo-Migrations Endpunkt und die Exo-Organisationsbeziehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="a3b1b-129">Normalerweise verfügt der globale Administrator über die Berechtigung zum Ausführen aller Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="a3b1b-130">Darüber hinaus sind e-Mail-aktivierte Sicherheitsgruppen im Quellmandanten vor der Ausführung von Setup erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="a3b1b-131">Diese Gruppen werden verwendet, um die Liste der Postfächer zu belegen, die von einem Mandanten (oder auch als Ressource bezeichnet) in den Zielmandanten verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="a3b1b-132">Dadurch kann der Quellmandanten-Administrator die zu verschiebenden spezifischen Sätze von Postfächern einschränken oder auf den Bereich beschränken, wodurch verhindert werden kann, dass unbeabsichtigte Benutzer migriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="a3b1b-133">Geschachtelte Gruppen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-133">Nested groups are not supported.</span></span>

<span data-ttu-id="a3b1b-134">Sie müssen auch mit Ihrer vertrauenswürdigen Partnerfirma (mit der Sie Postfächer verschieben werden) kommunizieren, um Ihre Microsoft 365-Mandanten-ID zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="a3b1b-135">Diese Mandanten-ID wird im Feld Organisationsbeziehung verwendet `DomainName` .</span><span class="sxs-lookup"><span data-stu-id="a3b1b-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="a3b1b-136">Um die Mandanten-ID eines Abonnements zu erhalten, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="a3b1b-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="a3b1b-137">Klicken Sie auf das Symbol Kopieren für die Mandanten-ID-Eigenschaft, um es in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="a3b1b-138">Hier erfahren Sie, wie der Prozess funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Mandanten Vorbereitung für die Postfachmigration.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="a3b1b-140">Vorbereiten von Mandanten</span><span class="sxs-lookup"><span data-stu-id="a3b1b-140">Prepare tenants</span></span>

<span data-ttu-id="a3b1b-141">Auf einer hohen Ebene erfolgen die folgenden Konfigurationsaktionen beim Ausführen der Setupskripts.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-141">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="a3b1b-142">Vorbereiten des Zielmandanten:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-142">Prepare the target tenant:</span></span>

1. <span data-ttu-id="a3b1b-143">Wenn keine vorhandene Azure-Ressourcengruppe bereitgestellt wird, wird ein neues erstellt (Skript).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-143">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="a3b1b-144">Wenn kein vorhandener schlüsseltresor bereitgestellt wird, wird ein neues Schlüsseldepot erstellt (Skript).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-144">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="a3b1b-145">Für die Office 365 Exchange Online Post Fach Migrationsanwendung (Script) wird eine neue Zugriffsrichtlinie erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-145">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="a3b1b-146">Ein neues Zertifikat wird (falls angegeben) erstellt (oder vorhanden), um das Geheimnis für die Migrationsanwendung (Skript) zu halten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-146">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="a3b1b-147">Eine neue Azure AD Anwendung wird erstellt (Skript).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-147">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="a3b1b-148">Das Zertifikat/der geheime Schlüssel wird in die Migrationsanwendung (Skript) hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-148">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="a3b1b-149">Der Anwendung werden Berechtigungen für die Postfachmigration (Skript) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-149">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="a3b1b-150">Das Bereitstellungsskript wird angehalten, bis der Zieladministrator ihrer eigenen Anwendung (Skript) zustimmt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-150">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="a3b1b-151">Der Zielmandanten Administrator stimmt den Berechtigungen zu, die der Anwendung erteilt wurden (manuell).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-151">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="a3b1b-152">Eine Organisationsbeziehung wird mit dem Zielmandanten (Skript) erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-152">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="a3b1b-153">Ein Migrations Endpunkt wird erstellt, um Postfächer an den Zielmandanten (Skript) zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-153">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="a3b1b-154">Vorbereiten des Quellmandanten:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-154">Prepare the source tenant:</span></span>

1. <span data-ttu-id="a3b1b-155">Der Quellmandanten Administrator akzeptiert die Zustimmung zur Post Fach Migrations-Anwendungseinladung vom Zielmandanten (Manual).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-155">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="a3b1b-156">Der Quellmandanten Administrator erstellt eine e-Mail-aktivierte Sicherheitsgruppe in Ihrem Mandanten, die die Liste der Postfächer enthält, die von der Migrationsanwendung verschoben werden dürfen (manuell).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-156">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="a3b1b-157">Eine Organisationsbeziehung wird mit dem Zielmandanten erstellt, der angibt, dass die Post Fach Migrationsanwendung für die OAuth-Überprüfung verwendet werden soll, um die Verschiebe Anforderung (Skript) zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-157">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="a3b1b-158">Schritt-für-Schritt-Anweisungen für den Zielmandanten Administrator</span><span class="sxs-lookup"><span data-stu-id="a3b1b-158">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="a3b1b-159">Laden Sie das SetupCrossTenantRelationshipForTargetTenant.ps1-Skript für das Setup des Zielmandanten aus dem [GitHub-Repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview)herunter.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-159">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="a3b1b-160">Speichern Sie das Skript (SetupCrossTenantRelationshipForTargetTenant.ps1) auf dem Computer, auf dem das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-160">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="a3b1b-161">Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Exchange Online Zielmandanten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-161">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="a3b1b-162">Stellen Sie auch in diesem Fall sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Bereitstellungsskripts verfügen, um die Azure Key Vault-Speicherung und das Zertifikat, die Post Fachanwendung, den Exo-Migrations Endpunkt und die Exo-Organisationsbeziehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-162">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="a3b1b-163">Ändern Sie das Datei Ordner Verzeichnis in den Skript Speicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in der Remote-PowerShell-Sitzung befindet.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-163">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="a3b1b-164">Führen Sie das Skript mit den folgenden Parametern und Werten aus.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-164">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="a3b1b-165">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3b1b-165">Parameter</span></span> | <span data-ttu-id="a3b1b-166">Wert</span><span class="sxs-lookup"><span data-stu-id="a3b1b-166">Value</span></span> | <span data-ttu-id="a3b1b-167">Erforderlich oder optional</span><span class="sxs-lookup"><span data-stu-id="a3b1b-167">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="a3b1b-168">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="a3b1b-168">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="a3b1b-169">Quellmandanten Domäne, beispielsweise Fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-169">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="a3b1b-170">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-170">Required</span></span> |
    | <span data-ttu-id="a3b1b-171">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="a3b1b-171">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="a3b1b-172">Die e-Mail-Adresse des Quellmandanten-Administrators.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-172">Source tenant admin’s email address.</span></span> <span data-ttu-id="a3b1b-173">Dies ist der Quellmandanten Administrator, der der Verwendung der Post Fach Migrationsanwendung zustimmt, die vom Zieladministrator gesendet wird. Dies ist der Administrator, der die e-Mail-Einladung für die Anwendung erhalten wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-173">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="a3b1b-174">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-174">Required</span></span> |
    | <span data-ttu-id="a3b1b-175">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="a3b1b-175">-TargetTenantDomain</span></span>                         | <span data-ttu-id="a3b1b-176">Zielmandanten Domäne, wie Contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-176">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="a3b1b-177">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-177">Required</span></span> |
    | <span data-ttu-id="a3b1b-178">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="a3b1b-178">-ResourceTenantId</span></span>                           | <span data-ttu-id="a3b1b-179">Quellmandanten-Organisations-ID (GUID).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-179">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="a3b1b-180">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-180">Required</span></span> |
    | <span data-ttu-id="a3b1b-181">-Abonnement-Nr</span><span class="sxs-lookup"><span data-stu-id="a3b1b-181">-SubscriptionId</span></span>                             | <span data-ttu-id="a3b1b-182">Das Azure-Abonnement, das zum Erstellen von Ressourcen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-182">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="a3b1b-183">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-183">Required</span></span> |
    | <span data-ttu-id="a3b1b-184">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="a3b1b-184">-ResourceGroup</span></span>                              | <span data-ttu-id="a3b1b-185">Azure-Ressourcengruppenname, der den schlüsseltresor enthält oder enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-185">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="a3b1b-186">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-186">Required</span></span> |
    | <span data-ttu-id="a3b1b-187">-Keyvaultname</span><span class="sxs-lookup"><span data-stu-id="a3b1b-187">-KeyVaultName</span></span>                               | <span data-ttu-id="a3b1b-188">Azure Key Vault-Instanz, in der Ihr Zertifikat für die Post Fach Migrationsanwendung/Secret gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-188">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="a3b1b-189">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-189">Required</span></span> |
    | <span data-ttu-id="a3b1b-190">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="a3b1b-190">-CertificateName</span></span>                            | <span data-ttu-id="a3b1b-191">Zertifikatname beim Generieren oder suchen nach Zertifikat in Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-191">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="a3b1b-192">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-192">Required</span></span> |
    | <span data-ttu-id="a3b1b-193">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="a3b1b-193">-CertificateSubject</span></span>                         | <span data-ttu-id="a3b1b-194">Name des Zertifikatsantrags Teller namens Azure Key Vault, beispielsweise CN = contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-194">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="a3b1b-195">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-195">Required</span></span> |
    | <span data-ttu-id="a3b1b-196">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="a3b1b-196">-ExistingApplicationId</span></span>                      | <span data-ttu-id="a3b1b-197">Mail Migrationsanwendung, die verwendet werden soll, wenn bereits eine erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-197">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="a3b1b-198">Optional</span><span class="sxs-lookup"><span data-stu-id="a3b1b-198">Optional</span></span> |
    | <span data-ttu-id="a3b1b-199">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="a3b1b-199">-AzureAppPermissions</span></span>                        | <span data-ttu-id="a3b1b-200">Die erforderlichen Berechtigungen für die Post Fach Migrationsanwendung wie Exchange oder MSGraph (Exchange für das Verschieben von Postfächern, MSGraph für die Verwendung dieser Anwendung zum Senden einer Einladung zum Genehmigungs Link an den Ressourcen Mandanten).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-200">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="a3b1b-201">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a3b1b-201">Required</span></span> |
    | <span data-ttu-id="a3b1b-202">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="a3b1b-202">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="a3b1b-203">Parameter für die Verwendung der Anwendung, die für die Migration erstellt wurde, um eine Zustimmungs Link Einladung an den Quellmandanten-Administrator zu senden. Wenn dieser Wert nicht angegeben wird, werden die Anmeldeinformationen des Ziel Administrators aufgefordert, eine Verbindung mit dem Azure-Einladungs-Manager herzustellen und die Einladung als Zieladministrator zu senden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-203">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="a3b1b-204">Optional</span><span class="sxs-lookup"><span data-stu-id="a3b1b-204">Optional</span></span> |
    | <span data-ttu-id="a3b1b-205">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="a3b1b-205">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="a3b1b-206">Das Speicherkonto, in dem die Überwachungsprotokolle des Schlüsseldepots gespeichert würden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-206">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="a3b1b-207">Optional</span><span class="sxs-lookup"><span data-stu-id="a3b1b-207">Optional</span></span> |
    | <span data-ttu-id="a3b1b-208">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="a3b1b-208">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="a3b1b-209">Die Ressourcengruppe, die das Speicherkonto zum Speichern von Schlüsseldepot-Überwachungsprotokollen enthält.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-209">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="a3b1b-210">Optional</span><span class="sxs-lookup"><span data-stu-id="a3b1b-210">Optional</span></span> |
    ||||

6. <span data-ttu-id="a3b1b-211">Das Skript wird angehalten, und Sie werden aufgefordert, die Exchange-Post Fach Migrationsanwendung, die während dieses Prozesses erstellt wurde, anzunehmen oder Ihr zuzustimmen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-211">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="a3b1b-212">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-212">Here is an example.</span></span>

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

7. <span data-ttu-id="a3b1b-213">Eine URL wird in der Remote-PowerShell-Sitzung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-213">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="a3b1b-214">Kopieren Sie den für Ihre Mandanten Zustimmung angegebenen Link, und fügen Sie ihn in einen Webbrowser ein.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-214">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="a3b1b-215">Melden Sie sich mit ihren globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-215">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="a3b1b-216">Wenn der folgende Bildschirm angezeigt wird, wählen Sie **akzeptieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-216">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogfeld &quot;Berechtigungen akzeptieren&quot;":::
    
9. <span data-ttu-id="a3b1b-218">Wechseln Sie zurück zur PowerShell-Remote Sitzung, und drücken Sie die EINGABETASTE, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-218">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="a3b1b-219">Mit dem Skript werden die restlichen Setup-Objekte konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-219">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="a3b1b-220">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-220">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="a3b1b-221">Das Setup des Ziel Administrators ist nun abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="a3b1b-221">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="a3b1b-222">Schritt-für-Schritt-Anweisungen für den Quellmandanten-Administrator</span><span class="sxs-lookup"><span data-stu-id="a3b1b-222">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="a3b1b-223">Melden Sie sich bei Ihrem Postfach als vom Zieladministrator während des Setups angegebene-ResourceTenantAdminEmail an.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-223">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="a3b1b-224">Suchen Sie nach der e-Mail-Einladung des Zielmandanten, und wählen Sie dann die Schaltfläche **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-224">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogfeld &quot;Sie wurden eingeladen&quot;":::

2. <span data-ttu-id="a3b1b-226">Wählen Sie **annehmen** aus, um die Einladung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-226">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialog Feld zum Akzeptieren von Berechtigungen":::

   > [!NOTE]
   > <span data-ttu-id="a3b1b-228">Wenn Sie diese e-Mail nicht erhalten oder nicht finden können, wurde dem Zielmandanten Administrator eine direkte URL zur Verfügung gestellt, die Sie zur Annahme der Einladung erhalten können.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-228">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="a3b1b-229">Die URL sollte im Protokoll der Remote-PowerShell-Sitzung des Zielmandanten-Administrators sein.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-229">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="a3b1b-230">Erstellen Sie entweder im Microsoft 365 Admin Center oder in einer Remote-PowerShell-Sitzung eine oder mehrere e-Mail-aktivierte Sicherheitsgruppen, um die Liste der Postfächer zu steuern, die vom Zielmandanten für das ziehen (verschieben) vom Quellmandanten an den Zielmandanten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-230">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="a3b1b-231">Sie müssen diese Gruppe nicht im Voraus auffüllen, aber mindestens eine Gruppe muss bereitgestellt werden, um die Setupschritte (Skript) ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-231">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="a3b1b-232">Geschachtelte Gruppen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-232">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="a3b1b-233">Laden Sie [hier](https://github.com/microsoft/cross-tenant/releases/tag/Preview)das SetupCrossTenantRelationshipForTargetResource.ps1 Skript für das Setup des Quellmandanten aus dem GitHub-Repository herunter.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-233">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository [here](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="a3b1b-234">Erstellen Sie eine Remote-PowerShell-Verbindung mit dem Quellmandanten mit Ihren Exchange-Administrator Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-234">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="a3b1b-235">Globale Administratorberechtigungen sind nicht erforderlich, um den Quellmandanten zu konfigurieren, sondern nur den Zielmandanten, da der Azure-Anwendungs Erstellungsprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-235">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="a3b1b-236">Ändern Sie das Verzeichnis in den Skript Speicherort, oder stellen Sie sicher, dass das Skript derzeit an dem Speicherort gespeichert ist, der sich derzeit in der Remote-PowerShell-Sitzung befindet.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-236">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="a3b1b-237">Führen Sie das Skript mit den folgenden erforderlichen Parametern und Werten aus.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-237">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="a3b1b-238">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3b1b-238">Parameter</span></span> | <span data-ttu-id="a3b1b-239">Wert</span><span class="sxs-lookup"><span data-stu-id="a3b1b-239">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="a3b1b-240">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="a3b1b-240">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="a3b1b-241">Vom Quellmandanten erstellte e-Mail-aktivierte Sicherheitsgruppe für die Identitäten/Postfächer, die sich im Bereich der Migration befinden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-241">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="a3b1b-242">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="a3b1b-242">-ResourceTenantDomain</span></span> | <span data-ttu-id="a3b1b-243">Name der Quellmandanten Domäne, beispielsweise Fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-243">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="a3b1b-244">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="a3b1b-244">-TargetTenantDomain</span></span> | <span data-ttu-id="a3b1b-245">Name der Zielmandanten Domäne, beispielsweise contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-245">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="a3b1b-246">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="a3b1b-246">-ApplicationId</span></span> | <span data-ttu-id="a3b1b-247">Azure-Anwendungs-ID (GUID) der Anwendung, die für die Migration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-247">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="a3b1b-248">Anwendungs-ID, die über Ihr Azure-Portal (Azure AD, Enterprise-Anwendungen, App-Name, Anwendungs-ID) oder in Ihrer Einladungs-e-Mail enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-248">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="a3b1b-249">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="a3b1b-249">-TargetTenantId</span></span> | <span data-ttu-id="a3b1b-250">Mandanten-ID des Zielmandanten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-250">Tenant ID of the target tenant.</span></span> <span data-ttu-id="a3b1b-251">Beispielsweise die Azure AD Mandanten-ID des Contoso \. onmicrosoft.com-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-251">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||
    
    <span data-ttu-id="a3b1b-252">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-252">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="a3b1b-253">Das Setup des Quell Administrators ist nun abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="a3b1b-253">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="a3b1b-254">Überprüfen des Setups</span><span class="sxs-lookup"><span data-stu-id="a3b1b-254">Verify setup</span></span>

<span data-ttu-id="a3b1b-255">Stellen Sie sicher, dass die Organisationsbeziehungen in den Quell-und Zielmandanten und dem Migrations Endpunkt im Ziel erfolgreich erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-255">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="a3b1b-256">Zielmandant</span><span class="sxs-lookup"><span data-stu-id="a3b1b-256">Target tenant</span></span>

<span data-ttu-id="a3b1b-257">**Organisationsbeziehung**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-257">**Organization relationship**</span></span>

<span data-ttu-id="a3b1b-258">Stellen Sie sicher, dass das Organisations Beziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-258">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="a3b1b-259">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-259">Here is an example:</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="a3b1b-260">**Migrations Endpunkt**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-260">**Migration endpoint**</span></span>

<span data-ttu-id="a3b1b-261">Stellen Sie sicher, dass das Migrations Endpunkt Objekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-261">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="a3b1b-262">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-262">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="a3b1b-263">Quellmandant</span><span class="sxs-lookup"><span data-stu-id="a3b1b-263">Source tenant</span></span>

<span data-ttu-id="a3b1b-264">**Organisationsbeziehung**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-264">**Organization relationship**</span></span>

<span data-ttu-id="a3b1b-265">Stellen Sie sicher, dass das Organisations Beziehungsobjekt mit diesem Befehl erstellt und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-265">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
<span data-ttu-id="a3b1b-266">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-266">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="a3b1b-267">Verschieben von Postfächern zurück in die ursprüngliche Quelle</span><span class="sxs-lookup"><span data-stu-id="a3b1b-267">Move mailboxes back to the original source</span></span>

<span data-ttu-id="a3b1b-268">Wenn ein Postfach zurück zum ursprünglichen Quellmandanten wechselt, müssen dieselbe Reihe von Schritten und Skripts sowohl in der neuen als auch in den neuen Zielmandanten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-268">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="a3b1b-269">Das vorhandene Organisations Beziehungsobjekt wird aktualisiert oder angefügt und nicht neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-269">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="a3b1b-270">Vorbereiten von Zielbenutzer Objekten für die Migration</span><span class="sxs-lookup"><span data-stu-id="a3b1b-270">Prepare target user objects for migration</span></span>

<span data-ttu-id="a3b1b-271">Die Migration von Benutzern muss im Zielmandanten vorhanden sein, und Exchange Online System (als MailUser), das mit bestimmten Attributen markiert ist, um die mandantenübergreifenden Verschiebungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-271">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="a3b1b-272">Das System führt keine Verschiebungen für Benutzer aus, die nicht ordnungsgemäß im Zielmandanten eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-272">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="a3b1b-273">Im folgenden Abschnitt werden die Anforderungen des MailUser-Objekts für den Zielmandanten erläutert.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-273">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="a3b1b-274">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a3b1b-274">Prerequisites</span></span>
  
<span data-ttu-id="a3b1b-275">Sie müssen sicherstellen, dass die folgenden Objekte und Attribute in der Zielorganisation festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-275">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="a3b1b-276">Für alle Postfächer, die von einer Quellorganisation aus verschoben werden, müssen Sie ein MailUser-Objekt in der Zielorganisation zur Verfügung stellen:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-276">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 
   - <span data-ttu-id="a3b1b-277">Das Ziel-MailUser muss über diese Attribute aus dem Quellpostfach verfügen oder dem neuen Benutzerobjekt zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-277">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="a3b1b-278">ExchangeGUID (direkter Fluss von der Quelle zum Ziel) – die Postfach-GUID muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-278">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="a3b1b-279">Der Verschiebevorgang wird nicht fortgesetzt, wenn dieser nicht auf dem Zielobjekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-279">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="a3b1b-280">ArchiveGUID (direkter Fluss von der Quelle zum Ziel) – die Archiv-GUID muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-280">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="a3b1b-281">Der Verschiebevorgang wird nicht fortgesetzt, wenn dieser nicht im Zielobjekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-281">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="a3b1b-282">(Dies ist nur erforderlich, wenn das Quellpostfach Archiv aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-282">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="a3b1b-283">LegacyExchangeDN (Durchfluss als proxyAddress, "x500: <LegacyExchangeDN> ") – der legacyExchangeDN muss auf Ziel-MailUser als x500: proxyAddress vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-283">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="a3b1b-284">Die Verschiebevorgänge werden nicht fortgesetzt, wenn diese nicht im Zielobjekt vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-284">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="a3b1b-285">UserPrincipalName – UPN wird an der neuen Identität oder Zielgesellschaft des Benutzers ausgerichtet (beispielsweise User@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-285">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="a3b1b-286">Primäre SMTPAddress – primäre SMTP-Adresse wird an das neue Unternehmen des Benutzers ausgerichtet (beispielsweise User@Northwind.com).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-286">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="a3b1b-287">TargetAddress/ExternalEmailAddress – MailUser verweist auf das aktuelle Postfach des Benutzers, das im Quellmandanten gehostet wird (beispielsweise user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-287">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="a3b1b-288">Wenn Sie diesen Wert zuweisen, überprüfen Sie, ob Sie auch PrimarySmtpAddress zuweisen oder diesen Wert festlegen, um die PrimarySmtpAddress festzulegen, die zu Verschiebe Fehlern führen wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-288">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="a3b1b-289">Sie können keine Legacy-SMTP-Proxyadressen aus dem Quellpostfach zu Target MailUser hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-289">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="a3b1b-290">Beispielsweise können Sie contoso.com auf dem meu in fabrikam.onmicrosoft.com-Mandanten Objekten nicht beibehalten).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-290">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="a3b1b-291">Domänen werden nur einem Azure AD oder Exchange Online Mandanten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-291">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
    <span data-ttu-id="a3b1b-292">Beispiel für ein MailUser- **Ziel** Objekt:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-292">Example **target** MailUser object:</span></span>
 
    | <span data-ttu-id="a3b1b-293">Attribut</span><span class="sxs-lookup"><span data-stu-id="a3b1b-293">Attribute</span></span>             | <span data-ttu-id="a3b1b-294">Wert</span><span class="sxs-lookup"><span data-stu-id="a3b1b-294">Value</span></span>                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="a3b1b-295">Alias</span><span class="sxs-lookup"><span data-stu-id="a3b1b-295">Alias</span></span>                 | <span data-ttu-id="a3b1b-296">LaraN</span><span class="sxs-lookup"><span data-stu-id="a3b1b-296">LaraN</span></span>                                                                                                                    |
    | <span data-ttu-id="a3b1b-297">RecipientType</span><span class="sxs-lookup"><span data-stu-id="a3b1b-297">RecipientType</span></span>         | <span data-ttu-id="a3b1b-298">MailUser</span><span class="sxs-lookup"><span data-stu-id="a3b1b-298">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="a3b1b-299">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="a3b1b-299">RecipientTypeDetails</span></span>  | <span data-ttu-id="a3b1b-300">MailUser</span><span class="sxs-lookup"><span data-stu-id="a3b1b-300">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="a3b1b-301">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a3b1b-301">UserPrincipalName</span></span>     | <span data-ttu-id="a3b1b-302">LaraN@northwintraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-302">LaraN@northwintraders\.onmicrosoft.com</span></span>                                                                                    |
    | <span data-ttu-id="a3b1b-303">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="a3b1b-303">PrimarySmtpAddress</span></span>    | <span data-ttu-id="a3b1b-304">Lara \. Newton@Northwind.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-304">Lara\.Newton@northwind.com</span></span>                                                                                                |
    | <span data-ttu-id="a3b1b-305">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="a3b1b-305">ExternalEmailAddress</span></span>  | <span data-ttu-id="a3b1b-306">SMTP: LaraN@Contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-306">SMTP:LaraN@contoso\.onmicrosoft.com</span></span>                                                                                       |
    | <span data-ttu-id="a3b1b-307">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="a3b1b-307">ExchangeGuid</span></span>          | <span data-ttu-id="a3b1b-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="a3b1b-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
    | <span data-ttu-id="a3b1b-309">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="a3b1b-309">LegacyExchangeDN</span></span>      | <span data-ttu-id="a3b1b-310">/o = erste Organisation/ou = administrative Exchange-Gruppe</span><span class="sxs-lookup"><span data-stu-id="a3b1b-310">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
    |                       | <span data-ttu-id="a3b1b-311">(FYDIBOHF23SPDLT)/CN = Recipients/CN = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="a3b1b-311">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
    | <span data-ttu-id="a3b1b-312">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="a3b1b-312">EmailAddresses</span></span>        | <span data-ttu-id="a3b1b-313">x500:/o = First Organization/ou = Exchange Administrative Group (FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="a3b1b-313">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
    |                       | <span data-ttu-id="a3b1b-314">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="a3b1b-314">7273f1f9-Lara</span></span>                                                                                                            |
    |                       | <span data-ttu-id="a3b1b-315">SMTP: LaraN@northwindtraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-315">smtp:LaraN@northwindtraders\.onmicrosoft.com</span></span>                                                                              |
    |                       | <span data-ttu-id="a3b1b-316">SMTP: Lara \. Newton@Northwind.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-316">SMTP:Lara\.Newton@northwind.com</span></span>                                                                                           |
    |||

   <span data-ttu-id="a3b1b-317">Beispiel für ein **Quell** Postfach-Objekt:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-317">Example **source** Mailbox object:</span></span>

   | <span data-ttu-id="a3b1b-318">Attribut</span><span class="sxs-lookup"><span data-stu-id="a3b1b-318">Attribute</span></span>             | <span data-ttu-id="a3b1b-319">Wert</span><span class="sxs-lookup"><span data-stu-id="a3b1b-319">Value</span></span>                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | <span data-ttu-id="a3b1b-320">Alias</span><span class="sxs-lookup"><span data-stu-id="a3b1b-320">Alias</span></span>                 | <span data-ttu-id="a3b1b-321">LaraN</span><span class="sxs-lookup"><span data-stu-id="a3b1b-321">LaraN</span></span>                                                                    |
   | <span data-ttu-id="a3b1b-322">RecipientType</span><span class="sxs-lookup"><span data-stu-id="a3b1b-322">RecipientType</span></span>         | <span data-ttu-id="a3b1b-323">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="a3b1b-323">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="a3b1b-324">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="a3b1b-324">RecipientTypeDetails</span></span>  | <span data-ttu-id="a3b1b-325">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="a3b1b-325">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="a3b1b-326">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a3b1b-326">UserPrincipalName</span></span>     | <span data-ttu-id="a3b1b-327">LaraN@Contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-327">LaraN@contoso\.onmicrosoft.com</span></span>                                            |
   | <span data-ttu-id="a3b1b-328">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="a3b1b-328">PrimarySmtpAddress</span></span>    | <span data-ttu-id="a3b1b-329">Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-329">Lara\.Newton@contoso.com</span></span>                                                  |
   | <span data-ttu-id="a3b1b-330">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="a3b1b-330">ExchangeGuid</span></span>          | <span data-ttu-id="a3b1b-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="a3b1b-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
   | <span data-ttu-id="a3b1b-332">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="a3b1b-332">LegacyExchangeDN</span></span>      | <span data-ttu-id="a3b1b-333">/o = erste Organisation/ou = administrative Exchange-Gruppe</span><span class="sxs-lookup"><span data-stu-id="a3b1b-333">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
   |                       | <span data-ttu-id="a3b1b-334">(FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="a3b1b-334">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
   | <span data-ttu-id="a3b1b-335">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="a3b1b-335">EmailAddresses</span></span>        | <span data-ttu-id="a3b1b-336">SMTP: LaraN@Contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-336">smtp:LaraN@contoso\.onmicrosoft.com</span></span> 
   |                       | <span data-ttu-id="a3b1b-337">SMTP: Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3b1b-337">SMTP:Lara\.Newton@contoso.com</span></span>          |
   |||

   - <span data-ttu-id="a3b1b-338">In Exchange-Hybrid-Write Back sind möglicherweise bereits weitere Attribute enthalten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-338">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="a3b1b-339">Wenn dies nicht der Fall ist, sollten Sie eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-339">If not, they should be included.</span></span> 
   - <span data-ttu-id="a3b1b-340">msExchBlockedSendersHash – schreibt Online sichere und blockierte Absenderdaten von Clients in lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-340">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="a3b1b-341">msExchSafeRecipientsHash – schreibt Online sichere und blockierte Absenderdaten von Clients in lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-341">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="a3b1b-342">msExchSafeSendersHash – schreibt Online sichere und blockierte Absenderdaten von Clients in lokale Active Directory zurück.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-342">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="a3b1b-343">Wenn sich das Quellpostfach in LitigationHold befindet und die Größe des Quellpostfachs "Wiederherstellbare Elemente" größer ist als der Standardwert unserer Datenbank (30 GB), wird Moves nicht fortgesetzt, da das Ziel Kontingent kleiner als die Größe des Quellpostfachs ist.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-343">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="a3b1b-344">Sie können das Ziel MailUser-Objekt aktualisieren, um die ELC-Post Fach Flags von der Quellumgebung zum Ziel zu überführen, wodurch das Zielsystem ausgelöst wird, um das Kontingent des MailUser auf 100 GB zu erweitern und somit den Übergang zum Ziel zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-344">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="a3b1b-345">Diese Anweisungen funktionieren nur für Hybrid Identitäten, die Azure AD Connect ausführen, da die Befehle zum Stempeln der ELC-Flags nicht für mandantenadministratoren verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-345">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="a3b1b-346">Beispiel – keine Garantie</span><span class="sxs-lookup"><span data-stu-id="a3b1b-346">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="a3b1b-347">Dieses Skript nimmt eine Verbindung mit beiden Quellpostfächern (zum Abrufen der Quellwerte) und dem lokalen Ziel Active Directory (zum Stempeln des Benutzerobjekts) an.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-347">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="a3b1b-348">Wenn für Source das Verfahren für die Wiederherstellung von Einzelelementen aktiviert ist, legen Sie dies für das Ziel Konto fest.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-348">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="a3b1b-349">Dadurch wird die Größe des Zielkontos für den Papierkorb auf 100 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-349">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. <span data-ttu-id="a3b1b-350">Nicht-hybride Zielmandanten können das Kontingent für den Ordner "refundable Items" für die Mail-Benutzer vor der Migration ändern, indem Sie den folgenden Befehl ausführen, um das Beweissicherungsverfahren für das MailUser-Objekt zu aktivieren und das Kontingent auf 100 GB zu erhöhen: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="a3b1b-350">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="a3b1b-351">Hinweis Dies ist für Mandanten in Hybrid nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-351">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="a3b1b-352">Benutzer in der Zielorganisation müssen mit den entsprechenden Exchange Online Abonnements lizenziert sein, die für die Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-352">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="a3b1b-353">Sie können eine Lizenz im Vorfeld einer Post Fach Verlagerung anwenden, jedoch nur, wenn der Ziel-MailUser ordnungsgemäß mit ExchangeGUID-und Proxyadressen eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-353">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="a3b1b-354">Wenn Sie eine Lizenz anwenden, bevor das ExchangeGUID angewendet wird, wird ein neues Postfach in der Zielorganisation zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-354">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="a3b1b-355">Wenn Sie eine Lizenz auf ein Postfach-oder MailUser-Objekt anwenden, werden alle SMTP-proxyAddresses bereinigt, um sicherzustellen, dass nur verifizierte Domänen im Exchange-Adress Array enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-355">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="a3b1b-356">Sie müssen sicherstellen, dass das Ziel MailUser keine vorherigen ExchangeGuid hat, die nicht mit der Quell-ExchangeGuid übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-356">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="a3b1b-357">Dies kann der Fall sein, wenn das Ziel-meu zuvor für Exchange Online lizenziert und ein Postfach zur Verfügung gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-357">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="a3b1b-358">Wenn das Ziel MailUser zuvor lizenziert wurde oder ein ExchangeGuid, das nicht mit dem Quell ExchangeGuid übereinstimmt, müssen Sie eine Bereinigung der Cloud meu durchführen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-358">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="a3b1b-359">Für diese Cloud-aktivierte Benutzer können Sie den `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-359">For these cloud MEUs, you can run the `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` command.</span></span> 

    > [!Caution]
    > <span data-ttu-id="a3b1b-360">Dieser Vorgang ist unumkehrbar.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-360">This process is irreversible.</span></span> <span data-ttu-id="a3b1b-361">Wenn das Objekt über ein softDeleted-Postfach verfügt, kann es nach diesem Pfad nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-361">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="a3b1b-362">Nachdem Sie jedoch gelöscht haben, können Sie die richtige ExchangeGuid mit dem Zielobjekt synchronisieren, und Mrs stellt eine Verbindung zwischen dem Quellpostfach und dem neu erstellten Zielpostfach her.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-362">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="a3b1b-363">(Verweisen Sie auf den EHLO-Blog auf den neuen Parameter.)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-363">(Reference EHLO blog on the new parameter.)</span></span> 
 
    <span data-ttu-id="a3b1b-364">Suchen von Objekten, die zuvor Postfächer mit diesem Befehl waren.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-364">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    <span data-ttu-id="a3b1b-365">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-365">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    <span data-ttu-id="a3b1b-366">Löschen Sie das vorläufig gelöschte Postfach mithilfe dieses Befehls.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-366">Clear the soft-deleted mailbox using this command.</span></span>

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    <span data-ttu-id="a3b1b-367">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-367">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="a3b1b-368">Durchführen von Postfachmigrationen</span><span class="sxs-lookup"><span data-stu-id="a3b1b-368">Perform mailbox migrations</span></span>

<span data-ttu-id="a3b1b-369">Mandantenübergreifende Exchange-Postfachmigrationen werden als Migrationsbatches übermittelt, die vom Zielmandanten initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-369">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="a3b1b-370">Dies ist vergleichbar mit der Art und Weise, wie die Migration von Exchange-Batches bei der Migration von lokalen Exchange-Webdiensten zu Microsoft 365 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-370">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="a3b1b-371">Erstellen von Migrationsbatches</span><span class="sxs-lookup"><span data-stu-id="a3b1b-371">Create Migration batches</span></span>

<span data-ttu-id="a3b1b-372">Hier ist ein Beispiel für ein Migrationsbatch-Cmdlet zum Starten von Moves.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-372">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="a3b1b-373">Die e-Mail-Adresse in der CSV-Datei muss diejenige sein, die im Zielmandanten angegeben ist, nicht der Quellmandant.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-373">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="a3b1b-374">Die Übermittlung von Migrations Batchen wird auch vom neuen Exchange Admin Center beim Auswählen der mandantenübergreifenden Option unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-374">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>
 
#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="a3b1b-375">Lokale MailUser aktualisieren</span><span class="sxs-lookup"><span data-stu-id="a3b1b-375">Update on-premises MailUsers</span></span>

<span data-ttu-id="a3b1b-376">Sobald das Postfach von Quelle zu Ziel verschoben wurde, sollten Sie sicherstellen, dass die lokalen e-Mail-Benutzer, sowohl Quelle als auch Ziel, mit dem neuen targetAddress aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-376">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="a3b1b-377">In den Beispielen lautet der bei der Migration verwendete targetDeliveryDomain **contoso \. onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-377">In the examples, the targetDeliveryDomain used in the move is **contoso\.onmicrosoft.com**.</span></span> <span data-ttu-id="a3b1b-378">Aktualisieren Sie die e-Mail-Benutzer mit diesem targetAddress.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-378">Update the mail users with this targetAddress.</span></span>
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="a3b1b-379">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="a3b1b-379">Frequently asked questions</span></span>
 
<span data-ttu-id="a3b1b-380">**Müssen wir RemoteMailboxes in der lokalen Quellumgebung nach dem Wechsel aktualisieren?**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-380">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>
 
<span data-ttu-id="a3b1b-381">Ja, Sie sollten die targetAddress (RemoteRoutingAddress/ExternalEmailAddress) der Quell lokalen Benutzer aktualisieren, wenn das Quellmandanten Postfach zu einem Zielmandanten verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-381">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="a3b1b-382">Während die e-Mail-Weiterleitung die Verweise auf mehrere e-Mail-Benutzer mit unterschiedlichen targetAddresses verfolgen kann, müssen frei/Gebucht-Lookups für e-Mail-Benutzer auf den Speicherort des Postfachbenutzers Zielen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-382">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="a3b1b-383">Bei Frei/Gebucht-Lookups werden mehrere Umleitungen nicht mehr verfolgt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-383">Free/Busy lookups will not chase multiple redirects.</span></span> 
 
<span data-ttu-id="a3b1b-384">**Migriert der Inhalt des Teams-Chat Ordners mandantenübergreifend?**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-384">**Does the Teams chat folder content migrate cross-tenant?**</span></span> 

<span data-ttu-id="a3b1b-385">Nein, der Inhalt des Teams-Chat Ordners migriert nicht mandantenübergreifend.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-385">No, the Teams chat folder content does not migrate cross-tenant.</span></span> 
 
<span data-ttu-id="a3b1b-386">**Wie kann ich nur Bewegungen sehen, bei denen es sich um Mandantenübergreifende Verschiebungen handelt, nicht um meine Onboarding-und offboarding-Moves?**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-386">**How can I see just moves that are cross-tenant moves, not my onboarding and offboarding moves?**</span></span>

<span data-ttu-id="a3b1b-387">Verwenden Sie den `-flags` -Parameter.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-387">Use the `-flags` parameter.</span></span> <span data-ttu-id="a3b1b-388">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-388">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
<span data-ttu-id="a3b1b-389">**Können Sie Beispielskripts zum Kopieren von Attributen bereitstellen, die in Tests verwendet werden?**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-389">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="a3b1b-390">Beispiel – keine Garantie</span><span class="sxs-lookup"><span data-stu-id="a3b1b-390">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="a3b1b-391">Dieses Skript nimmt eine Verbindung mit beiden Quellpostfächern (zum Abrufen der Quellwerte) und dem lokalen Ziel Active Directory-Domänendienste (zum Stempeln des Benutzerobjekts) an.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-391">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="a3b1b-392">Wenn für Source das Verfahren für die Wiederherstellung von Einzelelementen aktiviert ist, legen Sie dies für das Ziel Konto fest.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-392">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="a3b1b-393">Dadurch wird die Größe des Zielkontos für den Papierkorb auf 100 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-393">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="a3b1b-394">**Wie greifen wir an Tag 1 auf Outlook zu, nachdem das use-Postfach verschoben wurde?**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-394">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="a3b1b-395">Da nur ein Mandant eine Domäne besitzen kann, wird der frühere primäre SMTPAddress dem Benutzer im Zielmandanten nicht zugeordnet, wenn die Post Fach Verlagerung abgeschlossen ist. nur die dem neuen Mandanten zugeordneten Domänen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-395">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="a3b1b-396">Outlook verwendet den neuen UPN users zur Authentifizierung beim Dienst, und das Outlook-Profil erwartet, dass der primäre SMTPAddress der Vorgängerversion dem Postfach im Zielsystem entspricht.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-396">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="a3b1b-397">Da sich die Legacy Adresse nicht im Ziel System befindet, stellt das Outlook-Profil keine Verbindung her, um das neu verschobene Postfach zu finden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-397">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="a3b1b-398">Für diese anfängliche Bereitstellung müssen Benutzer ihr Profil mit ihren neuen UPN-, primären SMTP-Adressen und Re-Sync-Ost-Inhalten neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-398">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="a3b1b-399">Planen Sie entsprechend, wenn Sie die Benutzer zur Fertigstellung stapeln.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-399">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="a3b1b-400">Sie müssen die Netzwerkauslastung und-Kapazität berücksichtigen, wenn Outlook-Client Profile erstellt werden und die nachfolgenden Ost-und OAB-Dateien auf Clients heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-400">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="a3b1b-401">**Für welche Exchange-RBAC-Rollen muss ich Mitglied sein, um eine Mandantenübergreifende Verlagerung einzurichten oder abzuschließen?**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-401">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="a3b1b-402">Eine Matrix mit Rollen, die auf der Übernahme von delegierten Aufgaben beim Ausführen einer Post Fach Verlagerung basiert.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-402">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="a3b1b-403">Derzeit sind zwei Rollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-403">Currently, two roles are required:</span></span>  

- <span data-ttu-id="a3b1b-404">Die erste Rolle ist für eine einmalige Einrichtungsaufgabe, die die Autorisierung zum Verschieben von Inhalt in oder aus Ihrer Mandanten-/organisationsgrenze herstellt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-404">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="a3b1b-405">Da das Verschieben von Daten aus ihrer Organisationssteuerung ein wichtiges Anliegen für alle Unternehmen ist, haben wir uns für die höchste zugewiesene Rolle des Organisationsadministrators (OrgAdmin) entschieden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-405">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="a3b1b-406">Diese Rolle muss eine neue OrganizationRelationship ändern oder einrichten, die die-MailboxMoveCapability mit der Remoteorganisation definiert.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-406">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="a3b1b-407">Nur die OrgAdmin kann die MailboxMoveCapability-Einstellung ändern, während andere Attribute in der OrganizationRelationhip vom Verbundfreigabe Administrator verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-407">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="a3b1b-408">Die Rolle der Ausführung der tatsächlichen Verschiebe Befehle kann an eine niedrigere Ebene delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-408">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="a3b1b-409">Der Rolle von Verschieben von Postfächern wird die Möglichkeit zugewiesen, Postfächer mithilfe des Parameters in die oder aus der Organisation zu verschieben `-RemoteTenant` .</span><span class="sxs-lookup"><span data-stu-id="a3b1b-409">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="a3b1b-410">**Wie soll die für targetAddress (TargetDeliveryDomain) ausgewählte SMTP-Adresse für das konvertierte Postfach (in MailUser-Konvertierung) ausgewählt werden?**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-410">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="a3b1b-411">Exchange-Postfachverschiebungen mit Mrs Craft das targetAddress-Objekt für das ursprüngliche Quellpostfach bei der Konvertierung in ein MailUser durch übereinstimmen einer e-Mail-Adresse (proxyAddress) des Zielobjekts.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-411">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="a3b1b-412">Der-TargetDeliveryDomain-Wert wird an den Befehl zum Verlegen übergeben, und anschließend wird auf der Zielseite nach einem übereinstimmenden Proxy für diese Domäne gesucht.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-412">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="a3b1b-413">Wenn eine Übereinstimmung gefunden wird, wird der entsprechende proxyAddress verwendet, um den ExternalEmailAddress (targetAddress) für das konvertierte Postfach (jetzt MailUser)-Objekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-413">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="a3b1b-414">**Wie werden Postfachberechtigungen übergangen?**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-414">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="a3b1b-415">Zu den Postfachberechtigungen gehören "Senden im Auftrag von" und "Postfachzugriff":</span><span class="sxs-lookup"><span data-stu-id="a3b1b-415">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="a3b1b-416">Senden im Auftrag von (AD: publicDelegates) speichert den DN von Empfängern mit Zugriff auf das Postfach eines Benutzers als Stellvertretung.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-416">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="a3b1b-417">Dieser Wert wird in Active Directory gespeichert und wird derzeit nicht als Teil des Post Fach Übergangs gewechselt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-417">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="a3b1b-418">Wenn das Quellpostfach publicDelegates festgelegt hat, müssen Sie die publicDelegates im Zielpostfach nach Abschluss der meu-zu-Post Fach Konvertierung in der Zielumgebung mithilfe des Befehls erneut Stempeln `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="a3b1b-418">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment using the `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` command.</span></span> 
 
- <span data-ttu-id="a3b1b-419">Postfachberechtigungen, die im Postfach gespeichert werden, werden mit dem Postfach verschoben, wenn sowohl der Prinzipal als auch der Delegat in das Zielsystem verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-419">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="a3b1b-420">Beispielsweise wird dem Benutzer TestUser_7 FullAccess für das Post Fach TestUser_8 im Mandanten SourceCompany.onmicrosoft.com erteilt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-420">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="a3b1b-421">Nachdem die Post Fach Verlagerung auf TargetCompany.onmicrosoft.com abgeschlossen wurde, werden dieselben Berechtigungen im Zielverzeichnis eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-421">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="a3b1b-422">Beispiele zum Verwenden von *Get-MailboxPermission* für TestUser_7 in den Quell-und Zielmandanten werden unten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-422">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="a3b1b-423">Exchange-Cmdlets werden mit dem Präfix Source und Target entsprechend gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-423">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="a3b1b-424">Hier ist ein Beispiel für die Ausgabe der Postfach-Berechtigung vor einem Wechsel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-424">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="a3b1b-425">Hier ist ein Beispiel für die Ausgabe der Post Fach Berechtigung nach dem Wechsel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-425">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="a3b1b-426">Mandantenübergreifende Postfach-und Kalenderberechtigungen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-426">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="a3b1b-427">Sie müssen Prinzipale und Delegaten in konsolidierte Batches verschieben organisieren, damit diese verbundenen Postfächer gleichzeitig vom Quellmandanten übergangen werden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-427">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 
 
## <a name="known-issues"></a><span data-ttu-id="a3b1b-428">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="a3b1b-428">Known issues</span></span> 

-  <span data-ttu-id="a3b1b-429">**Problem: Auto Expanded Archives kann nicht migriert werden.**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-429">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="a3b1b-430">Das Feature für die Mandantenübergreifende Migration unterstützt Migrationen des primären Postfachs und des Archivpostfachs für einen bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-430">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="a3b1b-431">Wenn der Benutzer in der Quelle jedoch über ein automatisch erweitertes Archiv verfügt – das bedeutet mehr als ein Archivpostfach, kann das Feature die zusätzlichen Archive nicht migrieren.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-431">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="a3b1b-432">**Problem: Cloud-Mailbenutzer mit nicht im Besitz befindlichen SMTP-proxyAddress blockieren Mrs Moves background.**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-432">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="a3b1b-433">Beim Erstellen von MailUser-Objekten des Target-Mandanten müssen Sie sicherstellen, dass alle SMTP-Proxyadressen zur Zielmandanten Organisation gehören.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-433">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="a3b1b-434">Wenn ein SMTP-proxyAddress auf dem Ziel-e-Mail-Benutzer vorhanden ist, der nicht zum lokalen Mandanten gehört, wird die Konvertierung des MailUser in das Postfach verhindert.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-434">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="a3b1b-435">Dies ist darauf zurückzuführen, dass Postfachobjekte nur e-Mails von Domänen senden können, für die der Mandant autorisierend ist (vom Mandanten beanspruchte Domänen):</span><span class="sxs-lookup"><span data-stu-id="a3b1b-435">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 
- 
   - <span data-ttu-id="a3b1b-436">Wenn Sie Benutzer lokal mit Azure AD Connect synchronisieren, stellen Sie lokale MailUser-Objekte bereit, wobei ExternalEmailAddress auf den Quellmandanten zeigt, in dem das Postfach vorhanden ist (Laran@Contoso \. onmicrosoft.com), und das PrimarySmtpAddress als Domäne stempelt, die sich im Zielmandanten befindet (Lara. Newton@Northwind \. com).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-436">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso\.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind\.com).</span></span> <span data-ttu-id="a3b1b-437">Diese Werte werden mit dem Mandanten synchronisiert, und ein geeigneter e-Mail-Benutzer ist für die Migration verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-437">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="a3b1b-438">Ein Beispielobjekt wird hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-438">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="a3b1b-439">Die com-Adresse " *contoso. onmicrosoft \. "* ist im Adressfeld "addresses/proxyAddresses" *nicht* vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-439">The *contoso.onmicrosoft\.com* address is *not* present in the EmailAddresses/proxyAddresses array.</span></span>

- <span data-ttu-id="a3b1b-440">**Problem: MailUser-Objekte mit "externen" primären SMTP-Adressen werden geändert/auf "interne" Unternehmen beansprucht Domains zurückgesetzt.**</span><span class="sxs-lookup"><span data-stu-id="a3b1b-440">**Issue: MailUser objects with “external” primary SMTP addresses are modified/reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="a3b1b-441">MailUser-Objekte sind Zeiger auf nicht lokale Postfächer.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-441">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="a3b1b-442">Im Fall von mandantenübergreifenden Postfachmigrationen verwenden wir MailUser-Objekte, um entweder das Quellpostfach (aus der Perspektive der Zielorganisation) oder das Zielpostfach (aus der Perspektive der Quellorganisation) darzustellen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-442">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="a3b1b-443">Die Mailbenutzer verfügen über eine ExternalEmailAddress (targetAddress), die auf die SMTP-Adresse des tatsächlichen Postfachs (ProxyTest \@ Fabrikam \. onmicrosoft.com) und primarySMTP Address verweist, die die angezeigte SMTP-Adresse des Postfachbenutzers im Verzeichnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-443">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest\@fabrikam\.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="a3b1b-444">In einigen Organisationen wird die primäre SMTP-Adresse als externe SMTP-Adresse angezeigt, nicht als Adresse, die vom lokalen Mandanten besessen/verifiziert wird (beispielsweise fabrikam.com statt als contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-444">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="a3b1b-445">Sobald jedoch ein Exchange-Dienstplan Objekt über Lizenzierungs Vorgänge auf das MailUser angewendet wird, wird die primäre SMTP-Adresse so geändert, dass Sie als von der lokalen Organisation verifizierte Domäne angezeigt wird (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a3b1b-445">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="a3b1b-446">Es gibt zwei mögliche Gründe:</span><span class="sxs-lookup"><span data-stu-id="a3b1b-446">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="a3b1b-447">Wenn ein Exchange-Dienstplan auf ein MailUser angewendet wird, beginnt der Azure AD Prozess mit der Erzwingung der Proxy Bereinigung, um sicherzustellen, dass die lokale Organisation keine e-Mail-Nachrichten, Spoofing oder e-Mails von einem anderen Mandanten senden kann.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-447">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="a3b1b-448">Jede SMTP-Adresse in einem Empfängerobjekt mit diesen Dienstplänen wird entfernt, wenn die Adresse nicht von der lokalen Organisation überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-448">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="a3b1b-449">Wie im Beispiel wird die Fabikam- \. com-Domäne vom Contoso \. -onmicrosoft.com-Mandanten nicht überprüft, sodass durch die Bereinigung diese Fabrikam- \. com-Domäne entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-449">As is the case in the example, the Fabikam\.com domain is NOT verified by the contoso\.onmicrosoft.com tenant, so the scrubbing removes that fabrikam\.com domain.</span></span> <span data-ttu-id="a3b1b-450">Wenn Sie diese externe Domäne auf MailUser speichern möchten, entweder vor der Migration oder nach der Migration, müssen Sie Ihre Migrationsprozesse so ändern, dass Lizenzen nach dem Abschluss oder vor dem Umzug entfernt werden, um sicherzustellen, dass die Benutzer das erwartete externe Branding angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-450">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="a3b1b-451">Sie müssen sicherstellen, dass das Mailbox-Objekt ordnungsgemäß lizenziert ist, um den e-Mail-Dienst nicht zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-451">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="a3b1b-452">Hier sehen Sie ein Beispielskript zum Entfernen der Dienstpläne für ein MailUser im Contoso \. onmicrosoft.com-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-452">An example script to remove the service plans on a MailUser in the Contoso\.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="a3b1b-453">Die Ergebnisse in der zugewiesenen ServicePlans werden hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-453">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="a3b1b-454">Die PrimarySmtpAddress des Benutzers wird nicht mehr bereinigt.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-454">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="a3b1b-455">Die fabrikam.com-Domäne gehört nicht zum contoso.onmicrosoft.com-Mandanten und wird als primäre SMTP-Adresse im Verzeichnis gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-455">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="a3b1b-456">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-456">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="a3b1b-457">Wenn msExchRemoteRecipientType auf 8 (DeprovisionMailbox) festgelegt ist, werden für lokale MailUser, die zum Zielmandanten migriert werden, die Proxy-Scrubbing-Logik in Azure nicht im Besitz befindliche Domänen entfernen und das primarySMTP-Objekt auf eine eigene Domäne zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-457">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="a3b1b-458">Durch das Löschen von msExchRemoteRecipientType in der lokalen MailUser wird die Proxy-Scrub-Logik nicht mehr angewendet.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-458">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="a3b1b-459">Im folgenden finden Sie die vollständige Palette möglicher Dienstpläne, die Exchange Online umfassen.</span><span class="sxs-lookup"><span data-stu-id="a3b1b-459">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="a3b1b-460">Name</span><span class="sxs-lookup"><span data-stu-id="a3b1b-460">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="a3b1b-461">Erweiterter eDiscovery-Speicher (500GB)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-461">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="a3b1b-462">Kunden-Lockbox</span><span class="sxs-lookup"><span data-stu-id="a3b1b-462">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="a3b1b-463">Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="a3b1b-463">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="a3b1b-464">Exchange Enterprise CAL-Dienste (EoP, DLP)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-464">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="a3b1b-465">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="a3b1b-465">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="a3b1b-466">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="a3b1b-466">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="a3b1b-467">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-467">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="a3b1b-468">Exchange Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-468">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="a3b1b-469">Exchange Online (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-469">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="a3b1b-470">Exchange Online-Archivierung für Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3b1b-470">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="a3b1b-471">Exchange Online-Archivierung für Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a3b1b-471">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="a3b1b-472">Exchange Online inaktives Benutzer-Add-on</span><span class="sxs-lookup"><span data-stu-id="a3b1b-472">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="a3b1b-473">Exchange Online-Kiosk</span><span class="sxs-lookup"><span data-stu-id="a3b1b-473">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="a3b1b-474">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="a3b1b-474">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="a3b1b-475">Exchange Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="a3b1b-475">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="a3b1b-476">Exchange Online Pop</span><span class="sxs-lookup"><span data-stu-id="a3b1b-476">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="a3b1b-477">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a3b1b-477">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="a3b1b-478">Informationsbarrieren</span><span class="sxs-lookup"><span data-stu-id="a3b1b-478">Information Barriers</span></span>                              |
   | <span data-ttu-id="a3b1b-479">Information Protection für Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="a3b1b-479">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="a3b1b-480">Information Protection für Office 365 – Standard</span><span class="sxs-lookup"><span data-stu-id="a3b1b-480">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="a3b1b-481">Einblicke von myAnalytics</span><span class="sxs-lookup"><span data-stu-id="a3b1b-481">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="a3b1b-482">Microsoft 365 Advanced Auditing</span><span class="sxs-lookup"><span data-stu-id="a3b1b-482">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="a3b1b-483">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="a3b1b-483">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="a3b1b-484">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="a3b1b-484">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="a3b1b-485">Microsoft MyAnalytics (Vollversion)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-485">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="a3b1b-486">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a3b1b-486">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="a3b1b-487">Office 365 Advanced Threat Protection (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-487">Office 365 Advanced Threat Protection (Plan 1)</span></span>    |
   | <span data-ttu-id="a3b1b-488">Office 365 Advanced Threat Protection (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="a3b1b-488">Office 365 Advanced Threat Protection (Plan 2)</span></span>    |
   | <span data-ttu-id="a3b1b-489">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="a3b1b-489">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="a3b1b-490">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="a3b1b-490">Outlook Customer Manager</span></span>                          |
   | <span data-ttu-id="a3b1b-491">Premium-Verschlüsselung in Office 365</span><span class="sxs-lookup"><span data-stu-id="a3b1b-491">Premium Encryption in Office 365</span></span>                  |
   || 
 
