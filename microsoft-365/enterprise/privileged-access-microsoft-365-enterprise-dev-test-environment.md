---
title: Privileged Access Management für Ihre Microsoft 365 Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Verwenden Sie diese Testumgebungsanleitung, um ihre Microsoft 365 Enterprise-Testumgebung mit privilegiertem Zugriff zu aktivieren.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126417"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="74d84-103">Privileged Access Management für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="74d84-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="74d84-104">*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 Enterprise- als auch für Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="74d84-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="74d84-105">In diesem Artikel wird beschrieben, wie Sie privileged access management konfigurieren, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="74d84-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="74d84-106">Die Konfiguration der zugriffssteuerung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="74d84-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="74d84-107">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="74d84-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="74d84-108">Phase 2: Konfigurieren der Verwaltung des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="74d84-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="74d84-109">Phase 3: Überprüfen, ob eine Genehmigung für Aufgaben mit erhöhten rechten Rechten erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="74d84-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="74d84-111">Eine visuelle Übersicht zu allen Artikeln im Stapel der Testumgebungsanleitungen für Microsoft 365 Enterprise finden Sie im [Microsoft 365 Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="74d84-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="74d84-112">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="74d84-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="74d84-113">Wenn Sie die Verwaltung des privilegierten Zugriffs auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen in [der Lightweight-Basiskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="74d84-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="74d84-114">Wenn Sie die Verwaltung des privilegierten Zugriffs in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen in [der Pass-Through-Authentifizierung.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="74d84-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="74d84-115">Für das Testen der Verwaltung des privilegierten Zugriffs ist keine simulierte Unternehmenstestumgebung erforderlich, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services-Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="74d84-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="74d84-116">Es wird hier als Option bereitgestellt, damit Sie die Verwaltung des privilegierten Zugriffs testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="74d84-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="74d84-117">Phase 2: Konfigurieren der Verwaltung des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="74d84-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="74d84-118">Konfigurieren Sie in dieser Phase eine Gruppe genehmigende Personen, und aktivieren Sie die Verwaltung des privilegierten Zugriffs für Ihre Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="74d84-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="74d84-119">Weitere Details und eine Übersicht über privileged access management finden Sie unter [Privileged Access Management](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74d84-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="74d84-120">Führen Sie die folgenden Schritte aus, um privilegierten Zugriff in Ihrer Organisation einrichten und verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="74d84-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="74d84-121">Schritt 1: Erstellen einer Gruppe genehmigende Benutzer</span><span class="sxs-lookup"><span data-stu-id="74d84-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="74d84-122">Bevor Sie mit der Verwendung des privilegierten Zugriffs beginnen, sollten Sie bestimmen, wer die Genehmigungsgenehmigung für eingehende Anforderungen für den Zugriff auf erhöhte und privilegierte Aufgaben erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="74d84-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="74d84-123">Alle Benutzer, die der Gruppe der genehmigende Personen gehören, können Zugriffsanforderungen genehmigen.</span><span class="sxs-lookup"><span data-stu-id="74d84-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="74d84-124">Um privilegierten Zugriff zu verwenden, müssen Sie eine E-Mail-aktivierte Sicherheitsgruppe in Microsoft 365 erstellen.</span><span class="sxs-lookup"><span data-stu-id="74d84-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="74d84-125">Benennen Sie in Ihrer Testumgebung die neue Sicherheitsgruppe "Privileged Access Approvers", und fügen Sie die "Benutzer 3" hinzu, die zuvor in vorherigen Testumgebungsanleitungen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="74d84-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="74d84-126">Schritt 2: Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="74d84-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="74d84-127">Privilegierter Zugriff muss in Microsoft 365 explizit mit der standardmäßigen Genehmigende Gruppe aktiviert werden, und er muss einen Satz von Systemkonten enthalten, die Sie von der Zugriffssteuerung für die Verwaltung des privilegierten Zugriffs ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="74d84-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="74d84-128">Achten Sie darauf, privilegierten Zugriff in Ihrer Organisation zu aktivieren, bevor Sie mit Phase 3 dieses Handbuchs beginnen.</span><span class="sxs-lookup"><span data-stu-id="74d84-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="74d84-129">Phase 3: Überprüfen, ob eine Genehmigung für Aufgaben mit erhöhten rechten Rechten erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="74d84-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="74d84-130">Überprüfen Sie in dieser Phase, ob die Richtlinie für den privilegierten Zugriff funktioniert und dass Die Benutzer eine Genehmigung benötigen, um definierte Aufgaben mit erhöhten und privilegierten Rechten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="74d84-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="74d84-131">Testen der Fähigkeit zum Ausführen einer Aufgabe, die nicht in einer Richtlinie für privilegierten Zugriff definiert ist</span><span class="sxs-lookup"><span data-stu-id="74d84-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="74d84-132">Stellen Sie zunächst eine Verbindung mit Exchange Management PowerShell mit den Anmeldeinformationen eines Benutzers, der in Ihrer Testumgebung als globaler Administrator konfiguriert ist, und versuchen Sie, eine neue Journalregel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74d84-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="74d84-133">Die [Aufgabe "New-JournalRule"](/powershell/module/exchange/new-journalrule) ist derzeit nicht in einer Richtlinie für den privilegierten Zugriff für Ihre Organisation definiert.</span><span class="sxs-lookup"><span data-stu-id="74d84-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="74d84-134">Öffnen Sie auf Ihrem lokalen Computer das Exchange Online Remote PowerShell Module bei **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell Module,** und melden Sie sich mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="74d84-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="74d84-135">Erstellen Sie in Exchange Management PowerShell eine neue Journalregel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="74d84-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="74d84-136">Anzeigen, dass die neue Journalregel erfolgreich in Exchange Management PowerShell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="74d84-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="74d84-137">Erstellen einer neuen Richtlinie für privilegierten Zugriff für die New-JournalRule Aufgabe</span><span class="sxs-lookup"><span data-stu-id="74d84-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="74d84-138">Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs noch nicht abgeschlossen haben, führen Sie unbedingt die Schritte zum Erstellen der Gruppe der genehmigenden Benutzer mit dem Namen "Genehmiger für den Privilegierten Zugriff" aus, um privilegierten Zugriff in Ihrer Testumgebung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="74d84-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="74d84-139">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen des globalen Administratorkontos für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="74d84-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="74d84-140">Wechseln Sie im Admin Center zu **Settings**  >  **Security & Privacy** Privileged  >  **Access**.</span><span class="sxs-lookup"><span data-stu-id="74d84-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="74d84-141">Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="74d84-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="74d84-142">Wählen **Sie "Richtlinien konfigurieren"** und dann "Richtlinie **hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="74d84-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="74d84-143">Wählen Sie in den Dropdownfeldern die folgenden Werte aus, oder geben Sie sie ein:</span><span class="sxs-lookup"><span data-stu-id="74d84-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="74d84-144">**Richtlinientyp:** Aufgabe</span><span class="sxs-lookup"><span data-stu-id="74d84-144">**Policy type**: Task</span></span>

    <span data-ttu-id="74d84-145">**Geltungsbereich der Richtlinie**: Exchange</span><span class="sxs-lookup"><span data-stu-id="74d84-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="74d84-146">**Richtlinienname:** Neue Journalregel</span><span class="sxs-lookup"><span data-stu-id="74d84-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="74d84-147">**Genehmigungstyp**: Manuell</span><span class="sxs-lookup"><span data-stu-id="74d84-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="74d84-148">**Genehmigungsgruppe:** Genehmiger für privilegierten Zugriff</span><span class="sxs-lookup"><span data-stu-id="74d84-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="74d84-149">Wählen Sie **Erstellen** und dann **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="74d84-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="74d84-150">Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="74d84-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="74d84-151">Lassen Sie unbedingt zeit, bis die Richtlinie vollständig aktiviert ist, bevor Sie die Genehmigungsanforderung im nächsten Schritt testen.</span><span class="sxs-lookup"><span data-stu-id="74d84-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="74d84-152">Testgenehmigungsanforderung für die New-JournalRule, die in einer Richtlinie für privilegierten Zugriff definiert ist</span><span class="sxs-lookup"><span data-stu-id="74d84-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="74d84-153">Öffnen Sie auf Ihrem lokalen Computer das Exchange Online Remote PowerShell Module bei **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell Module,** und melden Sie sich mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="74d84-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="74d84-154">Erstellen Sie in Exchange Management PowerShell eine neue Journalregel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="74d84-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="74d84-155">Anzeigen des Fehlers "Unzureichende Berechtigungen" in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="74d84-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="74d84-156">Anfordern des Zugriffs zum Erstellen einer neuen Journalregel mithilfe der New-JournalRule Aufgabe</span><span class="sxs-lookup"><span data-stu-id="74d84-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="74d84-157">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="74d84-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="74d84-158">Wechseln Sie im Admin Center zu **Settings**  >  **Security & Privacy** Privileged  >  **Access**.</span><span class="sxs-lookup"><span data-stu-id="74d84-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="74d84-159">Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="74d84-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="74d84-160">Wählen Sie **"Neue Anforderung" aus.**</span><span class="sxs-lookup"><span data-stu-id="74d84-160">Select **New request**.</span></span> <span data-ttu-id="74d84-161">Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="74d84-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="74d84-162">**Anforderungstyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="74d84-162">**Request type**: Task</span></span>

    <span data-ttu-id="74d84-163">**Geltungsbereich der Anforderung**: Exchange</span><span class="sxs-lookup"><span data-stu-id="74d84-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="74d84-164">**Anforderung für**: Neue Journalregel</span><span class="sxs-lookup"><span data-stu-id="74d84-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="74d84-165">**Dauer (Stunden):** 2</span><span class="sxs-lookup"><span data-stu-id="74d84-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="74d84-166">**Kommentare**: Anfordern der Berechtigung zum Erstellen einer neuen Journalregel</span><span class="sxs-lookup"><span data-stu-id="74d84-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="74d84-167">Wählen Sie **"Speichern"** und dann **"Schließen" aus.**</span><span class="sxs-lookup"><span data-stu-id="74d84-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="74d84-168">Ihre Anforderung wird per E-Mail an die Gruppe der genehmigende Nachricht gesendet.</span><span class="sxs-lookup"><span data-stu-id="74d84-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="74d84-169">Genehmigen einer Privilegierten Zugriffsanforderung für die Erstellung einer neuen Journalregel</span><span class="sxs-lookup"><span data-stu-id="74d84-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="74d84-170">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen für Benutzer 3 in Ihrer Testumgebung an (Mitglied der Sicherheitsgruppe "Privileged Access Approvers" in Ihrer Testumgebung).</span><span class="sxs-lookup"><span data-stu-id="74d84-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="74d84-171">Wechseln Sie im Admin Center zu **Settings**  >  **Security & Privacy** Privileged  >  **Access**.</span><span class="sxs-lookup"><span data-stu-id="74d84-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="74d84-172">Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="74d84-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="74d84-173">Wählen Sie die ausstehende Anforderung  aus, und wählen Sie dann "Genehmigen" aus, um Zugriff auf das globale Administratorkonto zu gewähren, um eine neue Journalregel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74d84-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="74d84-174">Das globale Administratorkonto (der anfordernde Benutzer) erhält eine E-Mail-Bestätigung, dass die Genehmigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="74d84-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="74d84-175">Testen der Erstellung einer neuen Journalregel mit dem für die Aufgabe genehmigten privilegierten New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="74d84-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="74d84-176">Öffnen Sie auf Ihrem lokalen Computer das Exchange Online Remote PowerShell Module bei **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell Module,** und melden Sie sich mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="74d84-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="74d84-177">Erstellen Sie in Exchange Management PowerShell eine neue Journalregel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="74d84-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="74d84-178">Anzeigen, dass die neue Journalregel erfolgreich in Exchange Management PowerShell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="74d84-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="74d84-179">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="74d84-179">Next step</span></span>

<span data-ttu-id="74d84-180">Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#information-protection) Funktionen zum Schutz von Informationen in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="74d84-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="74d84-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74d84-181">See also</span></span>

[<span data-ttu-id="74d84-182">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="74d84-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="74d84-183">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="74d84-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="74d84-184">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="74d84-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
