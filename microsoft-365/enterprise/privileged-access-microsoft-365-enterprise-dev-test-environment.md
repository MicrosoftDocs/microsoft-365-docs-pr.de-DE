---
title: Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Verwenden Sie in diesem Test Lab Guide um Systemzugriff-Verwaltung aktivieren Ihrer unternehmensumgebung Microsoft 365 testen.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867567"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="662c8-103">Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="662c8-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="662c8-104">Mit den Anweisungen in diesem Artikel konfigurieren Sie Systemzugriff Management zum Erhöhen der Sicherheit in Ihrer testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="662c8-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="662c8-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="662c8-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="662c8-107">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="662c8-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="662c8-108">Wenn Sie auf einfache Weise mit den Mindestanforderungen Systemzugriff Management konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="662c8-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="662c8-109">Wenn Sie in einer simulierten Enterprise Systemzugriff Management konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="662c8-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="662c8-p101">Testen der Systemzugriff Management erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Hier bereitgestellten wird als Option, damit Sie testen können Berechtigungen Zugriff auf Verwaltung und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="662c8-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="662c8-112">Phase 2: Konfigurieren der Verwaltung von Systemzugriff</span><span class="sxs-lookup"><span data-stu-id="662c8-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="662c8-p102">In dieser Phase konfigurieren eine Gruppe der genehmigenden Personen und Aktivieren von Systemzugriff Management für Ihre Umgebung für Microsoft 365 Enterprise. Zusätzliche Informationen und eine Übersicht über Berechtigungen Management zugreifen, finden Sie unter [Systemzugriff Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="662c8-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="662c8-115">Führen Sie diese Schritte zum Einrichten und Verwenden von Systemzugriff in Office 365-Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="662c8-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="662c8-116">Schritt 1: Erstellen einer genehmigenden Person Gruppe</span><span class="sxs-lookup"><span data-stu-id="662c8-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="662c8-p103">Bevor Sie mit Berechtigung Access beginnen, bestimmen Sie die Genehmigungsberechtigung für eingehende Anforderungen für den Zugriff auf Aufgaben mit erhöhten Rechten und Berechtigungen besitzen. Jeder Benutzer, der Teil der Gruppe der genehmigenden Personen ist werden Genehmigen von zugriffsanforderungen. Dies ist aktiviert, indem Sie eine e-Mail-aktivierte Sicherheitsgruppe in Office 365 erstellen. Erstellen eine neuen Sicherheitsgruppe mit dem Namen "Privilegierten Zugriff genehmigende Personen" in Ihrer testumgebung und Hinzufügen der "Benutzer 3" in den vorherigen Test Lab Guide Schritten zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="662c8-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="662c8-121">Schritt 2: Aktivieren von Systemzugriff</span><span class="sxs-lookup"><span data-stu-id="662c8-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="662c8-p104">Systemzugriff muss explizit aktiviert werden in Office 365 mit der Standardgruppe genehmigende Person und einschließlich einer Reihe von Systemkonten, die Sie aus der Systemzugriff Management Zugriffssteuerung ausgeschlossen werden möchten. Achten Sie darauf, dass in Office 365-Organisation, bevor Sie beginnen Phase 3 dieses Handbuchs Systemzugriff aktiviert.</span><span class="sxs-lookup"><span data-stu-id="662c8-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="662c8-124">Phase 3: Stellen Sie sicher, dass die Genehmigung für Aufgaben mit erhöhten Rechten und Berechtigungen erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="662c8-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="662c8-125">In dieser Phase überprüfen Sie, dass die Richtlinie Systemzugriff funktioniert und Benutzer genehmigt definierte mit erhöhten Rechten und privilegierte Aufgaben ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="662c8-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="662c8-126">Testen Sie die Möglichkeit zum Ausführen einer Aufgabe in einer Richtlinie Systemzugriff nicht definiert</span><span class="sxs-lookup"><span data-stu-id="662c8-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="662c8-p105">Erstens Verbinden mit Exchange Management PowerShell mit den Anmeldeinformationen eines Benutzers als ein globaler Administrator in Ihrer testumgebung konfiguriert und versuchen, eine neue Journalregel zu erstellen. Die [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) Aufgabe ist derzeit nicht in einer Richtlinie Systemzugriff für Ihre Organisation definiert.</span><span class="sxs-lookup"><span data-stu-id="662c8-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="662c8-129">Öffnen Sie auf dem lokalen Computer, und melden Sie sich bei der der Exchange Online Remote PowerShell-Modul bei der **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell-Modul** mithilfe globaler Administrator Konto für Ihre testumgebung.</span><span class="sxs-lookup"><span data-stu-id="662c8-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="662c8-130">Erstellen Sie eine neue Journalregel für Ihre Organisation in Exchange Management Powershell:</span><span class="sxs-lookup"><span data-stu-id="662c8-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="662c8-131">Ansicht, dass die neue Journalregel erfolgreich in Exchange Management PowerShell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="662c8-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="662c8-132">Erstellen einer neuen Systemzugriff Richtlinie für den New-JournalRule-Vorgang</span><span class="sxs-lookup"><span data-stu-id="662c8-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="662c8-133">Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs bereits abgeschlossen haben, werden Sie sicher führen Sie die Schritte zum Erstellen einer genehmigenden Person Gruppe mit dem Namen "Berechtigung Access genehmigende Personen" und die Systemzugriff in Ihrer Umgebung Tests zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="662c8-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="662c8-134">Melden Sie sich bei der [Microsoft 365 Admin Center](https://portal.office.com) mit Anmeldeinformationen für Ihre Umgebung für das globale Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="662c8-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="662c8-135">Wechseln Sie in der Verwaltungskonsole auf **Einstellungen** > **Sicherheit und Datenschutz** > **Systemzugriff**.</span><span class="sxs-lookup"><span data-stu-id="662c8-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="662c8-136">Wählen Sie **Verwalten Zugriffsrichtlinien und Anforderungen**.</span><span class="sxs-lookup"><span data-stu-id="662c8-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="662c8-137">Wählen Sie **Richtlinien konfigurieren** , und wählen Sie **eine Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="662c8-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="662c8-138">Wählen Sie aus den Feldern Dropdown-aus, oder geben Sie die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="662c8-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="662c8-139">**Richtlinientyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="662c8-139">**Policy type**: Task</span></span>

    <span data-ttu-id="662c8-140">**Richtlinie auf Benutzerebene**: Exchange</span><span class="sxs-lookup"><span data-stu-id="662c8-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="662c8-141">**Richtlinienname**: neue Journalregel</span><span class="sxs-lookup"><span data-stu-id="662c8-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="662c8-142">**Typ der statusgenehmigung**: Manual (engl.)</span><span class="sxs-lookup"><span data-stu-id="662c8-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="662c8-143">**Genehmigungsgruppe**: privilegierten Zugriff genehmigende Personen</span><span class="sxs-lookup"><span data-stu-id="662c8-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="662c8-p106">Wählen Sie **Erstellen** und dann auf **Schließen**. Es kann einige Minuten für die Richtlinie vollständig konfiguriert und aktiviert worden ist. Achten Sie darauf, dass Sie Zeit für die Richtlinie vollständig aktiviert werden soll, bevor Sie die Genehmigung-Anforderung im nächsten Schritt testen.</span><span class="sxs-lookup"><span data-stu-id="662c8-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="662c8-147">Testen der Genehmigung-Anforderung für das New-JournalRule Aufgabe in einer Richtlinie Systemzugriff definiert</span><span class="sxs-lookup"><span data-stu-id="662c8-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="662c8-148">Öffnen Sie auf dem lokalen Computer, und melden Sie sich bei der der Exchange Online Remote PowerShell-Modul bei der **Microsoft Corporation** > mit ein globaler Administrator mit**Microsoft Exchange Online Remote PowerShell-Modul** Konto für den Test Umgebung.</span><span class="sxs-lookup"><span data-stu-id="662c8-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="662c8-149">Erstellen Sie eine neue Journalregel für Ihre Organisation in Exchange Management Powershell:</span><span class="sxs-lookup"><span data-stu-id="662c8-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="662c8-150">Ansicht "Unzureichende Berechtigungen" Fehler in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="662c8-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="662c8-151">Anfordern von Zugriff auf eine neue Journalregel mithilfe des New-JournalRule Tasks erstellen</span><span class="sxs-lookup"><span data-stu-id="662c8-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="662c8-152">Melden Sie sich bei der [Microsoft 365 Admin Center](https://portal.office.com) über das globale Administratorkonto für Ihre testumgebung.</span><span class="sxs-lookup"><span data-stu-id="662c8-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="662c8-153">Wechseln Sie in der Verwaltungskonsole auf **Einstellungen** > **Sicherheit und Datenschutz** > **Systemzugriff**.</span><span class="sxs-lookup"><span data-stu-id="662c8-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="662c8-154">Wählen Sie **Verwalten Zugriffsrichtlinien und Anforderungen**.</span><span class="sxs-lookup"><span data-stu-id="662c8-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="662c8-p107">Wählen Sie **neue Anforderung**. Wählen Sie aus dem Dropdown-Feldern die entsprechenden Werte für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="662c8-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="662c8-157">**Anforderungstyp**: Aufgabe</span><span class="sxs-lookup"><span data-stu-id="662c8-157">**Request type**: Task</span></span>

    <span data-ttu-id="662c8-158">**Bereich anfordern**: Exchange</span><span class="sxs-lookup"><span data-stu-id="662c8-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="662c8-159">**Anforderung für**: neue Journalregel</span><span class="sxs-lookup"><span data-stu-id="662c8-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="662c8-160">**Dauer (in Stunden)**: 2</span><span class="sxs-lookup"><span data-stu-id="662c8-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="662c8-161">**Kommentare**: Berechtigung zum Erstellen einer neuen Journalregel anfordern</span><span class="sxs-lookup"><span data-stu-id="662c8-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="662c8-p108">Wählen Sie **Speichern** und dann auf **Schließen**. Ihre Anforderung wird der genehmigenden Person Gruppe per e-Mail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="662c8-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="662c8-164">Genehmigen Sie Anforderung für die Erstellung einer neuen Journalregel Systemzugriff</span><span class="sxs-lookup"><span data-stu-id="662c8-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="662c8-165">Melden Sie sich bei der [Microsoft 365 Admin Center](https://portal.office.com) mit den Anmeldeinformationen für Benutzer 3 in Ihrer testumgebung (Mitglied der Sicherheitsgruppe "Privilegierten Zugriff genehmigende Personen" in Ihrer testumgebung).</span><span class="sxs-lookup"><span data-stu-id="662c8-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="662c8-166">Wechseln Sie in der Verwaltungskonsole auf **Einstellungen** > **Sicherheit und Datenschutz** > **Systemzugriff**.</span><span class="sxs-lookup"><span data-stu-id="662c8-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="662c8-167">Wählen Sie **Verwalten Zugriffsrichtlinien und Anforderungen**.</span><span class="sxs-lookup"><span data-stu-id="662c8-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="662c8-p109">Wählen Sie die ausstehende Anforderung, und wählen Sie **Genehmigen** , an das globale Administratorkonto zum Erstellen einer neuen Journalregel Zugriff zu gewähren. Eine Benachrichtigung e-Mail bestätigt, dass die Genehmigung erteilt wurde, wird an das globale Administratorkonto (dem anfordernden Benutzer) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="662c8-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="662c8-170">Erstellen eine neue Journalregel mit Systemzugriff für den New-JournalRule Vorgang genehmigt Test</span><span class="sxs-lookup"><span data-stu-id="662c8-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="662c8-171">Öffnen Sie auf dem lokalen Computer, und melden Sie sich bei der der Exchange Online Remote PowerShell-Modul bei der **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell-Modul** mithilfe globaler Administrator Konto für Ihre testumgebung.</span><span class="sxs-lookup"><span data-stu-id="662c8-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="662c8-172">Erstellen Sie eine neue Journalregel für Ihre Organisation in Exchange Management Powershell:</span><span class="sxs-lookup"><span data-stu-id="662c8-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="662c8-173">Ansicht, dass die neue Journalregel erfolgreich in Exchange Management PowerShell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="662c8-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="662c8-174">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="662c8-174">Next step</span></span>

<span data-ttu-id="662c8-175">Hier finden Sie zusätzliche [Informationen Protection](m365-enterprise-test-lab-guides.md#information-protection) Features und Funktionen in Ihrer testumgebung.</span><span class="sxs-lookup"><span data-stu-id="662c8-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="662c8-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="662c8-176">See also</span></span>

[<span data-ttu-id="662c8-177">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="662c8-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="662c8-178">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="662c8-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="662c8-179">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="662c8-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)