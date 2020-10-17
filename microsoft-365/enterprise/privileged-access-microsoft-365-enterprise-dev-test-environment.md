---
title: Privilegierte Zugriffsverwaltung für Ihre Microsoft 365 für Enterprise-Testumgebung
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
description: Verwenden Sie diese Test Umgebungs Anleitung, um die privilegierte Zugriffsverwaltung für Ihre Microsoft 365 für Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487588"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2ceca-103">Privilegierte Zugriffsverwaltung für Ihre Microsoft 365 für Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="2ceca-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2ceca-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="2ceca-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2ceca-105">In diesem Artikel wird beschrieben, wie Sie die privilegierte Zugriffsverwaltung konfigurieren, um die Sicherheit in Ihrer Microsoft 365 for Enterprise-Testumgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="2ceca-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="2ceca-106">Das Konfigurieren der privilegierten-Zugriffsverwaltung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="2ceca-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="2ceca-107">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="2ceca-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="2ceca-108">Phase 2: Konfigurieren der Verwaltung von privilegierten Zugriffsrechten</span><span class="sxs-lookup"><span data-stu-id="2ceca-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="2ceca-109">Phase 3: überprüfen, ob eine Genehmigung für erweiterte und privilegierte Aufgaben erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="2ceca-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="2ceca-111">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="2ceca-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2ceca-112">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="2ceca-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2ceca-113">Wenn Sie die privilegierte Zugriffsverwaltung auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="2ceca-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2ceca-114">Wenn Sie die privilegierte Zugriffsverwaltung in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2ceca-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="2ceca-115">Zum Testen der privilegierten Zugriffsverwaltung ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="2ceca-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="2ceca-116">Er wird hier als Option bereitgestellt, damit Sie die privilegierte Zugriffsverwaltung testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ceca-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="2ceca-117">Phase 2: Konfigurieren der Verwaltung von privilegierten Zugriffsrechten</span><span class="sxs-lookup"><span data-stu-id="2ceca-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="2ceca-118">Konfigurieren Sie in dieser Phase eine Gruppe Genehmigende Personen, und aktivieren Sie die privilegierte Zugriffsverwaltung für Ihre Microsoft 365 for Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="2ceca-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="2ceca-119">Weitere Details und eine Übersicht über die Verwaltung privilegierten Zugriffs finden Sie unter [privileged Access Management](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2ceca-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="2ceca-120">Führen Sie die folgenden Schritte aus, um den privilegierten Zugriff in Ihrer Organisation einzurichten und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ceca-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="2ceca-121">Schritt 1: Erstellen einer Gruppe einer genehmigenden Person</span><span class="sxs-lookup"><span data-stu-id="2ceca-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="2ceca-122">Bevor Sie mit der Verwendung von privilegiertem Zugriff beginnen, müssen Sie ermitteln, wer über Genehmigungsautorität für eingehende Anforderungen für den Zugriff auf Erweiterte und privilegierte Aufgaben verfügt.</span><span class="sxs-lookup"><span data-stu-id="2ceca-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="2ceca-123">Alle Benutzer, die Teil der Gruppe der genehmigenden Personen sind, können Zugriffsanforderungen genehmigen.</span><span class="sxs-lookup"><span data-stu-id="2ceca-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="2ceca-124">Zum Verwenden des privilegierten Zugriffs müssen Sie eine e-Mail-aktivierte Sicherheitsgruppe in Microsoft 365 erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ceca-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="2ceca-125">Nennen Sie in Ihrer Testumgebung die neue Sicherheitsgruppe "genehmigende Personen mit privilegiertem Zugriff", und fügen Sie den "Benutzer 3" hinzu, der zuvor in den vorherigen Schritten der Test Umgebungs Anleitung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ceca-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="2ceca-126">Schritt 2: Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="2ceca-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="2ceca-127">Der privilegierte Zugriff muss in Microsoft 365 mit der standardmäßigen genehmigenden Gruppe explizit aktiviert werden, und er muss eine Reihe von Systemkonten enthalten, die von der Zugriffssteuerung für privilegierte Zugriffsverwaltung ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2ceca-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="2ceca-128">Achten Sie darauf, den privilegierten Zugriff in Ihrer Organisation zu aktivieren, bevor Sie Phase 3 dieses Handbuchs starten.</span><span class="sxs-lookup"><span data-stu-id="2ceca-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="2ceca-129">Phase 3: überprüfen, ob eine Genehmigung für erweiterte und privilegierte Aufgaben erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="2ceca-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="2ceca-130">Stellen Sie in dieser Phase sicher, dass die Richtlinie für privilegierten Zugriff funktioniert und dass Benutzer eine Genehmigung zum Ausführen definierter erhöhter und privilegierter Aufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="2ceca-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="2ceca-131">Testen der Fähigkeit zum Ausführen einer Aufgabe, die nicht in einer privilegierten Zugriffsrichtlinie definiert ist</span><span class="sxs-lookup"><span data-stu-id="2ceca-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="2ceca-132">Stellen Sie zunächst eine Verbindung mit der Exchange-Verwaltungs-PowerShell mit den Anmeldeinformationen eines als globaler Administrator konfigurierten Benutzers in Ihrer Testumgebung her, und versuchen Sie, eine neue Journal Regel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ceca-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="2ceca-133">Der [New-JournalRule-](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) Vorgang ist derzeit nicht in einer privilegierten Zugriffsrichtlinie für Ihre Organisation definiert.</span><span class="sxs-lookup"><span data-stu-id="2ceca-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="2ceca-134">Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online Remote-PowerShell-Modul** mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="2ceca-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="2ceca-135">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="2ceca-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="2ceca-136">Zeigt an, dass die neue Journal Regel in der Exchange-Verwaltungs-PowerShell erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ceca-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="2ceca-137">Erstellen einer neuen Richtlinie für den privilegierten Zugriff für die New-JournalRule Aufgabe</span><span class="sxs-lookup"><span data-stu-id="2ceca-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="2ceca-138">Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs noch nicht abgeschlossen haben, müssen Sie sicherstellen, dass Sie die Schritte zum Erstellen einer genehmigenden Gruppe mit dem Namen "Berechtigungen für den genehmigenden Personen Zugriff" ausführen, um den privilegierten Zugriff in Ihrer Testumgebung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2ceca-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="2ceca-139">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen des globalen Administratorkontos für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="2ceca-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2ceca-140">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="2ceca-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2ceca-141">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="2ceca-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2ceca-142">Wählen Sie **Richtlinien konfigurieren**aus, und wählen Sie dann **Richtlinie hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="2ceca-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="2ceca-143">Wählen Sie in den Dropdownfeldern die folgenden Werte aus, oder geben Sie Sie ein:</span><span class="sxs-lookup"><span data-stu-id="2ceca-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="2ceca-144">**Richtlinientyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="2ceca-144">**Policy type**: Task</span></span>

    <span data-ttu-id="2ceca-145">**Geltungsbereich der Richtlinie**: Exchange</span><span class="sxs-lookup"><span data-stu-id="2ceca-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="2ceca-146">**Richtlinienname**: neue Journal Regel</span><span class="sxs-lookup"><span data-stu-id="2ceca-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="2ceca-147">**Genehmigungs**: manuell</span><span class="sxs-lookup"><span data-stu-id="2ceca-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="2ceca-148">**Genehmigungsgruppe**: genehmigende Personen mit privilegiertem Zugriff</span><span class="sxs-lookup"><span data-stu-id="2ceca-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="2ceca-149">Wählen Sie **Erstellen**aus, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="2ceca-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="2ceca-150">Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2ceca-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="2ceca-151">Achten Sie darauf, dass die Richtlinie erst vollständig aktiviert ist, bevor Sie die Genehmigungsanforderung im nächsten Schritt testen.</span><span class="sxs-lookup"><span data-stu-id="2ceca-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="2ceca-152">Testen der Genehmigungsanforderung für die in einer privilegierten Zugriffsrichtlinie definierte New-JournalRule Aufgabe</span><span class="sxs-lookup"><span data-stu-id="2ceca-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="2ceca-153">Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online-Remote-PowerShell-Modul** mithilfe eines globalen Administratorkontos für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="2ceca-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2ceca-154">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="2ceca-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="2ceca-155">Zeigen Sie den Fehler "unzureichende Berechtigungen" in der Exchange-Verwaltungs-PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="2ceca-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="2ceca-156">Anfordern von Zugriff zum Erstellen einer neuen Journal Regel mithilfe der New-JournalRule Aufgabe</span><span class="sxs-lookup"><span data-stu-id="2ceca-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="2ceca-157">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="2ceca-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2ceca-158">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="2ceca-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2ceca-159">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="2ceca-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2ceca-160">Wählen Sie **neue Anforderung**aus.</span><span class="sxs-lookup"><span data-stu-id="2ceca-160">Select **New request**.</span></span> <span data-ttu-id="2ceca-161">Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="2ceca-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="2ceca-162">**Anforderungstyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="2ceca-162">**Request type**: Task</span></span>

    <span data-ttu-id="2ceca-163">**Geltungsbereich der Anforderung**: Exchange</span><span class="sxs-lookup"><span data-stu-id="2ceca-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="2ceca-164">**Anforderung für**: neue Journal Regel</span><span class="sxs-lookup"><span data-stu-id="2ceca-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="2ceca-165">**Dauer (Stunden)**: 2</span><span class="sxs-lookup"><span data-stu-id="2ceca-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="2ceca-166">**Kommentare**: Anfordern einer Berechtigung zum Erstellen einer neuen Journal Regel</span><span class="sxs-lookup"><span data-stu-id="2ceca-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="2ceca-167">Wählen Sie **Speichern**aus, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="2ceca-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="2ceca-168">Ihre Anfrage wird per e-Mail an die Gruppe der genehmigenden Person gesendet.</span><span class="sxs-lookup"><span data-stu-id="2ceca-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="2ceca-169">Genehmigen einer privilegierten Zugriffsanforderung für die Erstellung einer neuen Journal Regel</span><span class="sxs-lookup"><span data-stu-id="2ceca-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="2ceca-170">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen für Benutzer 3 in Ihrer Testumgebung an (Mitglied der Sicherheitsgruppe "privilegierte Zugriffs genehmigende Personen" in Ihrer Testumgebung).</span><span class="sxs-lookup"><span data-stu-id="2ceca-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="2ceca-171">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="2ceca-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2ceca-172">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="2ceca-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2ceca-173">Wählen Sie die ausstehende Anforderung aus, und wählen Sie dann **genehmigen** aus, um dem globalen Administratorkonto Zugriff zum Erstellen einer neuen Journal Regel zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="2ceca-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="2ceca-174">Das globale Administratorkonto (der anfordernde Benutzer) erhält eine e-Mail-Bestätigung, dass die Genehmigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ceca-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="2ceca-175">Testen Erstellen einer neuen Journal Regel mit privilegiertem Zugriff für die New-JournalRule Aufgabe genehmigt</span><span class="sxs-lookup"><span data-stu-id="2ceca-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="2ceca-176">Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online Remote-PowerShell-Modul** mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="2ceca-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="2ceca-177">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="2ceca-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="2ceca-178">Zeigt an, dass die neue Journal Regel in der Exchange-Verwaltungs-PowerShell erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ceca-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="2ceca-179">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="2ceca-179">Next step</span></span>

<span data-ttu-id="2ceca-180">Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="2ceca-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ceca-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ceca-181">See also</span></span>

[<span data-ttu-id="2ceca-182">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2ceca-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2ceca-183">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2ceca-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2ceca-184">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="2ceca-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
