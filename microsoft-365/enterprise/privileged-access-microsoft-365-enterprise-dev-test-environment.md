---
title: Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung
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
description: Verwenden Sie diese Test Umgebungs Anleitung, um die Verwaltung privilegierten Zugriffs für Ihre Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 1a81c62124177a328209f175262ac13455ca0899
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352522"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9bff1-103">Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="9bff1-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9bff1-104">*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="9bff1-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9bff1-105">Mit den Anweisungen in diesem Artikel Konfigurieren Sie die privilegierte Zugriffsverwaltung, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="9bff1-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="9bff1-107">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9bff1-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9bff1-108">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="9bff1-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9bff1-109">Wenn Sie die privilegierte Zugriffsverwaltung nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9bff1-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9bff1-110">Wenn Sie die privilegierte Zugriffsverwaltung in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9bff1-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="9bff1-111">Für das Testen der privilegierten Zugriffsverwaltung ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine AD DS Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="9bff1-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="9bff1-112">Sie wird hier als Option bereitgestellt, damit Sie die privilegierte Zugriffsverwaltung testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="9bff1-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="9bff1-113">Phase 2: Konfigurieren der Verwaltung von privilegierten Zugriffsrechten</span><span class="sxs-lookup"><span data-stu-id="9bff1-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="9bff1-114">In dieser Phase konfigurieren Sie eine Gruppe Genehmigende Personen und aktivieren die Verwaltung privilegierter Zugriffsrechte für Ihre Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="9bff1-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="9bff1-115">Weitere Details und eine Übersicht über die Verwaltung privilegierten Zugriffs finden Sie unter [privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="9bff1-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="9bff1-116">Führen Sie die folgenden Schritte zum Einrichten und Verwenden von privilegiertem Zugriff in Ihrer Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="9bff1-116">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="9bff1-117">Schritt 1: Erstellen einer Gruppe einer genehmigenden Person</span><span class="sxs-lookup"><span data-stu-id="9bff1-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="9bff1-118">Bevor Sie mit dem Verwenden des Zugriffs auf Berechtigungen beginnen, müssen Sie ermitteln, wer über Genehmigungsautorität für eingehende Anforderungen für den Zugriff auf Erweiterte und privilegierte Aufgaben verfügt.</span><span class="sxs-lookup"><span data-stu-id="9bff1-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="9bff1-119">Jeder Benutzer, der Teil der Gruppe der Genehmiger ist, kann Zugriffsanforderungen genehmigen.</span><span class="sxs-lookup"><span data-stu-id="9bff1-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="9bff1-120">Dies wird durch Erstellen einer e-Mail-aktivierten Sicherheitsgruppe in Office 365 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9bff1-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="9bff1-121">Erstellen Sie eine neue Sicherheitsgruppe mit dem Namen "privileged Access genehmigende Personen" in Ihrer Testumgebung, und fügen Sie den zuvor in den Schritten der Test Umgebungs Anleitung erstellten "Benutzer 3" hinzu.</span><span class="sxs-lookup"><span data-stu-id="9bff1-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="9bff1-122">Schritt 2: Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="9bff1-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="9bff1-123">Der privilegierte Zugriff muss in Office 365 explizit mit der standardmäßigen genehmigenden Gruppe aktiviert sein und eine Reihe von Systemkonten enthalten, die von der Zugriffssteuerung für privilegierte Zugriffsverwaltung ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9bff1-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="9bff1-124">Achten Sie darauf, den privilegierten Zugriff in Ihrer Organisation zu aktivieren, bevor Sie Phase 3 dieses Handbuchs starten.</span><span class="sxs-lookup"><span data-stu-id="9bff1-124">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="9bff1-125">Phase 3: überprüfen, ob eine Genehmigung für erweiterte und privilegierte Aufgaben erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="9bff1-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="9bff1-126">In dieser Phase stellen Sie sicher, dass die Richtlinie für privilegierten Zugriff funktioniert, und Benutzer benötigen eine Genehmigung zum Ausführen definierter erhöhter und privilegierter Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="9bff1-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="9bff1-127">Testen der Fähigkeit zum Ausführen einer Aufgabe, die nicht in einer privilegierten Zugriffsrichtlinie definiert ist</span><span class="sxs-lookup"><span data-stu-id="9bff1-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="9bff1-128">Stellen Sie zunächst eine Verbindung mit der Exchange-Verwaltungs-PowerShell mit den Anmeldeinformationen eines als globaler Administrator konfigurierten Benutzers in Ihrer Testumgebung her, und versuchen Sie, eine neue Journal Regel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9bff1-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="9bff1-129">Der [New-JournalRule-](https://docs.microsoft.com/powershell/module/exchange/new-journalrule?view=exchange-ps) Vorgang ist derzeit nicht in einer privilegierten Zugriffsrichtlinie für Ihre Organisation definiert.</span><span class="sxs-lookup"><span data-stu-id="9bff1-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="9bff1-130">Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online Remote-PowerShell-Modul** mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="9bff1-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="9bff1-131">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="9bff1-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="9bff1-132">Zeigt an, dass die neue Journal Regel in der Exchange-Verwaltungs-PowerShell erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9bff1-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="9bff1-133">Erstellen einer neuen Richtlinie für den privilegierten Zugriff für den Task "New-JournalRule"</span><span class="sxs-lookup"><span data-stu-id="9bff1-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="9bff1-134">Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs noch nicht abgeschlossen haben, müssen Sie sicherstellen, dass Sie die Schritte zum Erstellen einer genehmigenden Gruppe mit dem Namen "Berechtigungen für den genehmigenden Personen Zugriff" und zum Aktivieren des privilegierten Zugriffs in Ihrer Testumgebung ausführen.</span><span class="sxs-lookup"><span data-stu-id="9bff1-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="9bff1-135">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen des globalen Administratorkontos für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="9bff1-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="9bff1-136">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="9bff1-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="9bff1-137">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="9bff1-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="9bff1-138">Wählen Sie **Richtlinien konfigurieren** aus, und wählen Sie **Richtlinie hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="9bff1-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="9bff1-139">Wählen Sie in den Dropdownfeldern die folgenden Werte aus, oder geben Sie Sie ein:</span><span class="sxs-lookup"><span data-stu-id="9bff1-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="9bff1-140">**Richtlinientyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="9bff1-140">**Policy type**: Task</span></span>

    <span data-ttu-id="9bff1-141">**Richtlinienbereich**: Exchange</span><span class="sxs-lookup"><span data-stu-id="9bff1-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="9bff1-142">**Richtlinienname**: neue Journal Regel</span><span class="sxs-lookup"><span data-stu-id="9bff1-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="9bff1-143">**Genehmigungs**: manuell</span><span class="sxs-lookup"><span data-stu-id="9bff1-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="9bff1-144">**Genehmigungsgruppe**: genehmigende Personen mit privilegiertem Zugriff</span><span class="sxs-lookup"><span data-stu-id="9bff1-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="9bff1-145">Klicken Sie auf **Erstellen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9bff1-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="9bff1-146">Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9bff1-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="9bff1-147">Achten Sie darauf, dass die Richtlinie erst vollständig aktiviert ist, bevor Sie die Genehmigungsanforderung im nächsten Schritt testen.</span><span class="sxs-lookup"><span data-stu-id="9bff1-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="9bff1-148">Testen der Genehmigungsanforderung für den in einer privilegierten Zugriffsrichtlinie definierten New-JournalRule-Vorgang</span><span class="sxs-lookup"><span data-stu-id="9bff1-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="9bff1-149">Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online-Remote-PowerShell-Modul** mithilfe eines globalen Administratorkontos für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="9bff1-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="9bff1-150">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="9bff1-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="9bff1-151">Anzeigen des Fehlers "unzureichende Berechtigungen" in der Exchange-Verwaltungs-PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9bff1-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="9bff1-152">Anfordern von Zugriff zum Erstellen einer neuen Journal Regel mit dem Task "New-JournalRule"</span><span class="sxs-lookup"><span data-stu-id="9bff1-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="9bff1-153">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="9bff1-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="9bff1-154">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="9bff1-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="9bff1-155">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="9bff1-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="9bff1-156">Wählen Sie **neue Anforderung**aus.</span><span class="sxs-lookup"><span data-stu-id="9bff1-156">Select **New request**.</span></span> <span data-ttu-id="9bff1-157">Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="9bff1-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="9bff1-158">**Anforderungstyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="9bff1-158">**Request type**: Task</span></span>

    <span data-ttu-id="9bff1-159">**Anforderungsbereich**: Exchange</span><span class="sxs-lookup"><span data-stu-id="9bff1-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="9bff1-160">**Anforderung für**: neue Journal Regel</span><span class="sxs-lookup"><span data-stu-id="9bff1-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="9bff1-161">**Dauer (Stunden)**: 2</span><span class="sxs-lookup"><span data-stu-id="9bff1-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="9bff1-162">**Kommentare**: Anfordern einer Berechtigung zum Erstellen einer neuen Journal Regel</span><span class="sxs-lookup"><span data-stu-id="9bff1-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="9bff1-163">Klicken Sie auf **Speichern** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9bff1-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="9bff1-164">Ihre Anfrage wird per e-Mail an die Gruppe der genehmigenden Person gesendet.</span><span class="sxs-lookup"><span data-stu-id="9bff1-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="9bff1-165">Genehmigen einer privilegierten Zugriffsanforderung für die Erstellung einer neuen Journal Regel</span><span class="sxs-lookup"><span data-stu-id="9bff1-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="9bff1-166">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen für Benutzer 3 in Ihrer Testumgebung an (Mitglied der Sicherheitsgruppe "privilegierte Zugriffs genehmigende Personen" in Ihrer Testumgebung).</span><span class="sxs-lookup"><span data-stu-id="9bff1-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="9bff1-167">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="9bff1-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="9bff1-168">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="9bff1-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="9bff1-169">Wählen Sie die ausstehende Anforderung aus, und wählen Sie **genehmigen** aus, um dem globalen Administratorkonto Zugriff zum Erstellen einer neuen Journal Regel zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="9bff1-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="9bff1-170">Eine Benachrichtigungs-e-Mail, die bestätigt, dass die Genehmigung erteilt wurde, wird an das globale Administratorkonto (der anfordernde Benutzer) gesendet.</span><span class="sxs-lookup"><span data-stu-id="9bff1-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="9bff1-171">Testen Erstellen einer neuen Journal Regel mit privilegiertem Zugriff genehmigt für die Aufgabe "New-JournalRule"</span><span class="sxs-lookup"><span data-stu-id="9bff1-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="9bff1-172">Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online Remote-PowerShell-Modul** mit dem globalen Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="9bff1-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="9bff1-173">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="9bff1-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="9bff1-174">Zeigt an, dass die neue Journal Regel in der Exchange-Verwaltungs-PowerShell erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9bff1-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="9bff1-175">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="9bff1-175">Next step</span></span>

<span data-ttu-id="9bff1-176">Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="9bff1-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bff1-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bff1-177">See also</span></span>

[<span data-ttu-id="9bff1-178">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9bff1-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9bff1-179">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9bff1-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9bff1-180">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9bff1-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
