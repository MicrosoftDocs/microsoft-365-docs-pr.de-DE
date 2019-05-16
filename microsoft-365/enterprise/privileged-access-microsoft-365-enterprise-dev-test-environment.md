---
title: Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung
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
description: Verwenden Sie dieses Test Labor Handbuch, um die privilegierte Zugriffsverwaltung Ihrer Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 306cd8d3cb574fd18a3d184898ead765936bf431
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073015"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="521f4-103">Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="521f4-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="521f4-104">Mit den Anweisungen in diesem Artikel Konfigurieren Sie die privilegierte Zugriffsverwaltung, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="521f4-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="521f4-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="521f4-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="521f4-107">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="521f4-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="521f4-108">Wenn Sie die Verwaltung von privilegierten Zugriffen nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="521f4-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="521f4-109">Wenn Sie die Verwaltung privilegierter Zugriffsrechte in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="521f4-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="521f4-110">Das Testen der privilegierten Zugriffsverwaltung erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine AD DS-Gesamtstruktur verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="521f4-110">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a AD DS forest.</span></span> <span data-ttu-id="521f4-111">Sie wird hier als Option bereitgestellt, damit Sie die privilegierte Zugriffsverwaltung testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="521f4-111">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="521f4-112">Phase 2: Konfigurieren der Verwaltung privilegierter Zugriffsrechte</span><span class="sxs-lookup"><span data-stu-id="521f4-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="521f4-113">In dieser Phase konfigurieren Sie eine genehmigende Gruppe und aktivieren die privilegierte Zugriffsverwaltung für Ihre Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="521f4-113">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="521f4-114">Weitere Details und eine Übersicht über die Verwaltung privilegierter Zugriffsrechte finden Sie unter [privilegierte Zugriffsverwaltung in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="521f4-114">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="521f4-115">Führen Sie die folgenden Schritte aus, um den privilegierten Zugriff in Ihrer Office 365-Organisation einzurichten und zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="521f4-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="521f4-116">Schritt 1: Erstellen der Gruppe einer genehmigenden Person</span><span class="sxs-lookup"><span data-stu-id="521f4-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="521f4-117">Bevor Sie mit dem Verwenden von Berechtigungszugriff beginnen, bestimmen Sie, wer über Genehmigungsautorität für eingehende Anforderungen für den Zugriff auf erhöhte und privilegierte Aufgaben verfügt.</span><span class="sxs-lookup"><span data-stu-id="521f4-117">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="521f4-118">Jeder Benutzer, der Teil der Gruppe der genehmigenden Personen ist, kann Zugriffsanforderungen genehmigen.</span><span class="sxs-lookup"><span data-stu-id="521f4-118">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="521f4-119">Dies wird durch das Erstellen einer e-Mail-aktivierten Sicherheitsgruppe in Office 365 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="521f4-119">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="521f4-120">Erstellen Sie in Ihrer Testumgebung eine neue Sicherheitsgruppe mit dem Namen "privilegierte Zugriffs genehmigende Personen", und fügen Sie den zuvor in den Schritten "Test Lab Guide" erstellten Benutzer 3 hinzu.</span><span class="sxs-lookup"><span data-stu-id="521f4-120">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="521f4-121">Schritt 2: Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="521f4-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="521f4-122">Privilegierter Zugriff muss explizit in Office 365 mit der standardmäßigen genehmigenden Gruppe aktiviert werden und eine Reihe von Systemkonten enthalten, die Sie aus der Zugriffssteuerung für die privilegierte Zugriffsverwaltung ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="521f4-122">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="521f4-123">Stellen Sie sicher, dass Sie den privilegierten Zugriff in Ihrer Office 365-Organisation aktivieren, bevor Sie mit Phase 3 dieses Handbuchs beginnen.</span><span class="sxs-lookup"><span data-stu-id="521f4-123">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="521f4-124">Phase 3: überprüfen, ob die Genehmigung für erhöhte und privilegierte Aufgaben erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="521f4-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="521f4-125">In dieser Phase stellen Sie sicher, dass die Richtlinie für den privilegierten Zugriff funktioniert, und die Benutzer benötigen die Genehmigung zum Ausführen definierter erhöhter und privilegierter Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="521f4-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="521f4-126">Testen der Fähigkeit zum Ausführen einer Aufgabe, die nicht in einer privilegierten Zugriffsrichtlinie definiert ist</span><span class="sxs-lookup"><span data-stu-id="521f4-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="521f4-127">Stellen Sie zunächst eine Verbindung mit Exchange Management PowerShell mit den Anmeldeinformationen eines in der Testumgebung als globaler Administrator konfigurierten Benutzers her, und versuchen Sie, eine neue Journal Regel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="521f4-127">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="521f4-128">Die [New-JournalRule-](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) Aufgabe ist derzeit nicht in einer privilegierten Zugriffsrichtlinie für Ihre Organisation definiert.</span><span class="sxs-lookup"><span data-stu-id="521f4-128">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="521f4-129">Öffnen Sie auf Ihrem lokalen Computer das Exchange Online-Remote-PowerShell-Modul bei **Microsoft** > **Exchange Online-Remote-PowerShell-Modul** unter Verwendung des globalen Administratorkontos für Ihre Testumgebung, und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="521f4-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="521f4-130">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="521f4-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="521f4-131">Zeigen Sie an, dass die neue Journal Regel erfolgreich in Exchange Management PowerShell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="521f4-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="521f4-132">Erstellen einer neuen privilegierten Zugriffsrichtlinie für die Aufgabe "New-JournalRule"</span><span class="sxs-lookup"><span data-stu-id="521f4-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="521f4-133">Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs noch nicht abgeschlossen haben, führen Sie die Schritte zum Erstellen einer genehmigenden Gruppe mit dem Namen "Berechtigungen für den Zugriff Genehmiger" aus, und aktivieren Sie den privilegierten Zugriff in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="521f4-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="521f4-134">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen das globale Administratorkonto für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="521f4-134">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="521f4-135">Navigieren Sie im Admin Center zu **Einstellungen** > **Security & Privacy** > **privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="521f4-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="521f4-136">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="521f4-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="521f4-137">Wählen Sie **Richtlinien konfigurieren** aus, und wählen Sie **Richtlinie hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="521f4-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="521f4-138">Wählen Sie in den Dropdownfeldern die folgenden Werte aus, oder geben Sie Sie ein:</span><span class="sxs-lookup"><span data-stu-id="521f4-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="521f4-139">**Richtlinientyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="521f4-139">**Policy type**: Task</span></span>

    <span data-ttu-id="521f4-140">**Richtlinienbereich**: Exchange</span><span class="sxs-lookup"><span data-stu-id="521f4-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="521f4-141">**Richtlinienname**: neue Journal Regel</span><span class="sxs-lookup"><span data-stu-id="521f4-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="521f4-142">\*\*\*\* Genehmigungs: manual</span><span class="sxs-lookup"><span data-stu-id="521f4-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="521f4-143">**Genehmigungsgruppe**: Berechtigungen für privilegierten Zugriff</span><span class="sxs-lookup"><span data-stu-id="521f4-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="521f4-144">Klicken Sie auf **Erstellen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="521f4-144">Select **Create** and then **Close**.</span></span> <span data-ttu-id="521f4-145">Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="521f4-145">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="521f4-146">Stellen Sie sicher, dass die vollständige Aktivierung der Richtlinie vor dem Testen der Genehmigungsanforderung im nächsten Schritt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="521f4-146">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="521f4-147">Test Genehmigungsanforderung für den New-JournalRule-Task, der in einer privilegierten Zugriffsrichtlinie definiert ist</span><span class="sxs-lookup"><span data-stu-id="521f4-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="521f4-148">Öffnen Sie auf Ihrem lokalen Computer das Exchange Online-Remote-PowerShell-Modul bei **Microsoft** > **Exchange Online-Remote-PowerShell-Modul** unter Verwendung des globalen Administratorkontos für Ihren Test, und melden Sie sich an. Umgebung.</span><span class="sxs-lookup"><span data-stu-id="521f4-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="521f4-149">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="521f4-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="521f4-150">Anzeigen des Fehlers "Insuffient-Berechtigungen" in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="521f4-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="521f4-151">Anfordern des Zugriffs zum Erstellen einer neuen Journal Regel mithilfe der New-JournalRule-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="521f4-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="521f4-152">Melden Sie sich im [Microsoft 365 Admin Center](https://admin.microsoft.com) unter Verwendung des globalen Administratorkontos für Ihre Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="521f4-152">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="521f4-153">Navigieren Sie im Admin Center zu **Einstellungen** > **Security & Privacy** > **privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="521f4-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="521f4-154">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="521f4-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="521f4-155">Wählen Sie **neue Anforderung**aus.</span><span class="sxs-lookup"><span data-stu-id="521f4-155">Select **New request**.</span></span> <span data-ttu-id="521f4-156">Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="521f4-156">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="521f4-157">**Anforderungstyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="521f4-157">**Request type**: Task</span></span>

    <span data-ttu-id="521f4-158">**Anforderungsbereich**: Exchange</span><span class="sxs-lookup"><span data-stu-id="521f4-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="521f4-159">**Anforderung für**: neue Journal Regel</span><span class="sxs-lookup"><span data-stu-id="521f4-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="521f4-160">**Dauer (Stunden)**: 2</span><span class="sxs-lookup"><span data-stu-id="521f4-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="521f4-161">**Kommentare**: Anfordern der Berechtigung zum Erstellen einer neuen Journal Regel</span><span class="sxs-lookup"><span data-stu-id="521f4-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="521f4-162">Klicken Sie auf **Speichern** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="521f4-162">Select **Save** and then **Close**.</span></span> <span data-ttu-id="521f4-163">Ihre Anfrage wird per e-Mail an die Gruppe der genehmigenden Person gesendet.</span><span class="sxs-lookup"><span data-stu-id="521f4-163">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="521f4-164">Genehmigen einer privilegierten Zugriffsanforderung für die Erstellung einer neuen Journal Regel</span><span class="sxs-lookup"><span data-stu-id="521f4-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="521f4-165">Melden Sie sich im [Microsoft 365 Admin Center](https://admin.microsoft.com) mithilfe der Anmeldeinformationen für Benutzer 3 in Ihrer Testumgebung an (Mitglied der Sicherheitsgruppe "privilegierte Zugriffs-genehmigende Personen" in Ihrer Testumgebung).</span><span class="sxs-lookup"><span data-stu-id="521f4-165">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="521f4-166">Navigieren Sie im Admin Center zu **Einstellungen** > **Security & Privacy** > **privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="521f4-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="521f4-167">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="521f4-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="521f4-168">Wählen Sie die ausstehende \*\*\*\* Anforderung aus, und wählen Sie genehmigen aus, um Zugriff auf das globale Administratorkonto zu gewähren, um eine neue Journal Regel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="521f4-168">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="521f4-169">Eine Benachrichtigungs-e-Mail, die bestätigt, dass die Genehmigung erteilt wurde, wird an das globale Administratorkonto (der anfordernde Benutzer) gesendet.</span><span class="sxs-lookup"><span data-stu-id="521f4-169">An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="521f4-170">Testen des Erstellens einer neuen Journal Regel mit genehmigtem privilegiertem Zugriff für die Aufgabe "New-JournalRule"</span><span class="sxs-lookup"><span data-stu-id="521f4-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="521f4-171">Öffnen Sie auf Ihrem lokalen Computer das Exchange Online-Remote-PowerShell-Modul bei **Microsoft** > **Exchange Online-Remote-PowerShell-Modul** unter Verwendung des globalen Administratorkontos für Ihre Testumgebung, und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="521f4-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="521f4-172">Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="521f4-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="521f4-173">Zeigen Sie an, dass die neue Journal Regel erfolgreich in Exchange Management PowerShell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="521f4-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="521f4-174">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="521f4-174">Next step</span></span>

<span data-ttu-id="521f4-175">Erkunden Sie zusätzliche Features und Funktionen zum [Schutz von Informationen](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="521f4-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="521f4-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="521f4-176">See also</span></span>

[<span data-ttu-id="521f4-177">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="521f4-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="521f4-178">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="521f4-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="521f4-179">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="521f4-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)