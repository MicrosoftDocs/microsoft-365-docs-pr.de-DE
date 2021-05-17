---
title: Erste Schritte mit der Verwaltung des privilegierten Zugriffs
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: In diesem Artikel erfahren Sie mehr über das Aktivieren und Konfigurieren der Verwaltung des privilegierten Zugriffs in Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126532"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="6e45d-103">Erste Schritte mit der Verwaltung des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="6e45d-103">Get started with privileged access management</span></span>

<span data-ttu-id="6e45d-104">In diesem Thema werden Sie durch das Aktivieren und Konfigurieren der Privilegierten Zugriffsverwaltung in Ihrer Organisation begleitet.</span><span class="sxs-lookup"><span data-stu-id="6e45d-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="6e45d-105">Sie können entweder das Microsoft 365 Admin Center oder Exchange Management PowerShell verwenden, um privilegierten Zugriff zu verwalten und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e45d-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6e45d-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="6e45d-106">Before you begin</span></span>

<span data-ttu-id="6e45d-107">Bevor Sie mit der Verwaltung privilegierter Zugriffe beginnen, sollten Sie Ihr Microsoft 365 [und](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) alle Add-Ons bestätigen.</span><span class="sxs-lookup"><span data-stu-id="6e45d-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="6e45d-108">Um auf die Verwaltung privilegierter Zugriffe zu zugreifen und diese zu verwenden, muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:</span><span class="sxs-lookup"><span data-stu-id="6e45d-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="6e45d-109">Microsoft 365 E5 Abonnement (kostenpflichtig oder Testversion)</span><span class="sxs-lookup"><span data-stu-id="6e45d-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="6e45d-110">Microsoft 365 E3 (oder Office 365 E3-Abonnement + Enterprise Mobility and Security E3-Abonnement) + das Microsoft 365 E5 Compliance-Add-On</span><span class="sxs-lookup"><span data-stu-id="6e45d-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="6e45d-111">Alle Microsoft 365, Office 365, Exchange, SharePoint oder OneDrive for Business Abonnement + das Microsoft 365 E5 Insider Risk Management-Add-On</span><span class="sxs-lookup"><span data-stu-id="6e45d-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="6e45d-112">Microsoft 365 A5-Abonnement (kostenpflichtig oder Testversion)</span><span class="sxs-lookup"><span data-stu-id="6e45d-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="6e45d-113">Microsoft 365 A3-Abonnement (oder Office 365 A3 Abonnement + Enterprise Mobility and Security A3-Abonnement) + das Microsoft A5 Compliance-Add-On</span><span class="sxs-lookup"><span data-stu-id="6e45d-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="6e45d-114">Alle Microsoft 365, Office 365, Exchange, SharePoint oder OneDrive für Bildungseinrichtungen und das Microsoft 365 A5 Insider Risk Management-Add-On</span><span class="sxs-lookup"><span data-stu-id="6e45d-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="6e45d-115">Office 365 Enterprise E5-Abonnement (kostenpflichtig oder Testversion)</span><span class="sxs-lookup"><span data-stu-id="6e45d-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="6e45d-116">Office 365 Enterprise E3-Abonnement + Office 365 Advanced Compliance -Add-On (nicht mehr verfügbar für neue Abonnements, siehe Hinweis)</span><span class="sxs-lookup"><span data-stu-id="6e45d-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="6e45d-117">Benutzern, die Privilegierte Zugriffsverwaltungsanforderungen übermitteln und darauf reagieren, muss eine der oben genannten Lizenzen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6e45d-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="6e45d-118">Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft.</span><span class="sxs-lookup"><span data-stu-id="6e45d-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="6e45d-119">Wenn aktuelle Abonnements ablaufen, sollten Kunden zu einem der oben genannten Abonnements überwechseln, die die gleichen oder zusätzlichen Compliancefeatures enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e45d-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="6e45d-120">Wenn Sie keinen vorhandenen Office 365 Enterprise-E5-Plan haben und privilegierte Zugriffsverwaltung ausprobieren möchten, können Sie Microsoft 365 zu Ihrem [](https://www.microsoft.com/microsoft-365/enterprise) vorhandenen [Office 365-Abonnement](/office365/admin/try-or-buy-microsoft-365) hinzufügen oder sich für eine Testversion von Microsoft 365 Enterprise E5 registrieren.</span><span class="sxs-lookup"><span data-stu-id="6e45d-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="6e45d-121">Aktivieren und Konfigurieren der Privilegierten Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6e45d-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="6e45d-122">Führen Sie die folgenden Schritte aus, um privilegierten Zugriff in Ihrer Organisation zu einrichten und zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="6e45d-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="6e45d-123">Schritt 1: Erstellen einer Genehmigergruppe</span><span class="sxs-lookup"><span data-stu-id="6e45d-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="6e45d-124">Bevor Sie mit dem Verwenden von privilegiertem Zugriff beginnen, bestimmen Sie, wer die Berechtigung zum Genehmigen eingehender Anforderungen für den Zugriff auf Aufgaben mit erhöhten und privilegierten Rechten benötigt.</span><span class="sxs-lookup"><span data-stu-id="6e45d-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="6e45d-125">Jeder Benutzer, der zur Gruppe "Genehmiger" gehört, kann Zugriffsanforderungen genehmigen.</span><span class="sxs-lookup"><span data-stu-id="6e45d-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="6e45d-126">Diese Gruppe wird durch Erstellen einer E-Mail-aktivierten Sicherheitsgruppe in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e45d-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="6e45d-127">Schritt 2: Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="6e45d-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="6e45d-128">Privilegierter Zugriff muss in Office 365 explizit mit der Standardgenehmigungsgruppe aktiviert werden, einschließlich einer Reihe von Systemkonten, die Sie aus der Privileged Access Management-Zugriffssteuerung ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="6e45d-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="6e45d-129">Schritt 3: Erstellen einer Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6e45d-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="6e45d-130">Die Erstellung einer Genehmigungsrichtlinie ermöglicht es Ihnen, die spezifischen Genehmigungsanforderungen für einzelne Aufgaben zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6e45d-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="6e45d-131">Die Optionen für den Genehmigungstyp sind **Automatisch** oder **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="6e45d-132">Schritt 4: Übermitteln/Genehmigen privilegierter Zugriffsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e45d-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="6e45d-133">Nach der Aktivierung erfordert der privilegierte Zugriff Genehmigungen für jede Aufgabe, für die eine entsprechende Genehmigungsrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6e45d-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="6e45d-134">Für Aufgaben, die in einer Genehmigungsrichtlinie enthalten sind, müssen Benutzer eine Zugriffsgenehmigung anfordern und erhalten, um über die zur Ausführung der Aufgabe erforderlichen Berechtigungen zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="6e45d-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="6e45d-135">Nachdem die Genehmigung erteilt wurde, kann der anfragende Benutzer die beabsichtigte Aufgabe ausführen, und der privilegierte Zugriff autorisiert und führt die Aufgabe im Namen des Benutzers aus.</span><span class="sxs-lookup"><span data-stu-id="6e45d-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="6e45d-136">Die Genehmigung bleibt für die beantragte Dauer gültig (Standarddauer ist 4 Stunden), während der der Antragsteller die beabsichtigte Aufgabe mehrmals ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="6e45d-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="6e45d-137">Alle derartigen Ausführungen werden protokolliert und für Sicherheits- und Compliance-Audits zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="6e45d-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="6e45d-138">Wenn Sie Exchange Management PowerShell verwenden möchten, um privilegierten Zugriff zu aktivieren und zu konfigurieren, führen Sie die Schritte in Verbinden bis [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) mithilfe der mehrstufigen Authentifizierung aus, um eine Verbindung mit Exchange Online PowerShell mit Ihren Office 365-Anmeldeinformationen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6e45d-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="6e45d-139">Sie müssen die mehrstufige Authentifizierung nicht aktivieren, damit Ihre Organisation die Schritte zum Aktivieren des privilegierten Zugriffs während der Verbindung mit Exchange Online PowerShell ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="6e45d-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="6e45d-140">Beim Herstellen einer Verbindung mit der mehrstufigen Authentifizierung wird ein OAuth-Token erstellt, das vom privilegierten Zugriff zum Signieren Ihrer Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e45d-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="6e45d-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="6e45d-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="6e45d-142">Schritt 1: Erstellen einer Genehmigergruppe</span><span class="sxs-lookup"><span data-stu-id="6e45d-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="6e45d-143">Melden Sie sich [Microsoft 365 administrator center mit](https://admin.microsoft.com) Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="6e45d-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6e45d-144">Wechseln Sie im Admin Center zu **Gruppen**  >  **Hinzufügen einer Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="6e45d-145">Wählen **Sie E-Mail-aktivierte Sicherheitsgruppe** aus, und füllen Sie dann die Felder **Name,** **Gruppen-E-Mail-Adresse** und **Beschreibung** für die neue Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="6e45d-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="6e45d-146">Speichern Sie die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="6e45d-146">Save the group.</span></span> <span data-ttu-id="6e45d-147"> Es kann ein paar Minuten dauern, bis die Gruppe vollständig konfiguriert ist und im Microsoft 365 Admin Center angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6e45d-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="6e45d-148">Wählen Sie die Gruppe der neuen Genehmigende aus, und wählen Sie **Bearbeiten** aus, um der Gruppe Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e45d-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="6e45d-149">Speichern Sie die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="6e45d-149">Save the group.</span></span>

<span data-ttu-id="6e45d-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="6e45d-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="6e45d-151">Schritt 2: Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="6e45d-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6e45d-152">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6e45d-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="6e45d-153">Melden Sie sich [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="6e45d-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6e45d-154">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6e45d-155">Aktivieren Sie **das Steuerelement Genehmigungen für privilegierte Vorgänge** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e45d-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="6e45d-156">Weisen Sie die gruppe der genehmigeren Benutzer, die Sie in Schritt 1 erstellt haben, als **Standardgruppe genehmiger Benutzer zu.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="6e45d-157">**Speichern** und **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6e45d-158">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e45d-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6e45d-159">Führen Sie zum Aktivieren des privilegierten Zugriffs und zum Zuweisen der Gruppe der genehmigenden Exchange Online PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6e45d-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="6e45d-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e45d-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="6e45d-161">Die Systemkontenfunktion wird verfügbar gemacht, um sicherzustellen, dass bestimmte Automatisierungen in Ihrer Organisation ohne Abhängigkeit vom privilegierten Zugriff funktionieren können. Es wird jedoch empfohlen, dass solche Ausschlüsse außergewöhnlich sind und die zulässigen Automatisierungen regelmäßig genehmigt und überwacht werden sollten.</span><span class="sxs-lookup"><span data-stu-id="6e45d-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="6e45d-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="6e45d-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="6e45d-163">Schritt 3: Erstellen einer Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6e45d-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="6e45d-164">Sie können bis zu 30 Richtlinien für den privilegierten Zugriff für Ihre Organisation erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6e45d-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6e45d-165">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6e45d-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="6e45d-166">Melden Sie sich [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="6e45d-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6e45d-167">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6e45d-168">Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6e45d-169">Wählen **Sie Richtlinien konfigurieren** aus, und wählen Sie Richtlinie hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="6e45d-170">Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="6e45d-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="6e45d-171">**Richtlinientyp**: Aufgabe, Rolle oder Rollengruppe</span><span class="sxs-lookup"><span data-stu-id="6e45d-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="6e45d-172">**Geltungsbereich der Richtlinie**: Exchange</span><span class="sxs-lookup"><span data-stu-id="6e45d-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="6e45d-173">**Richtlinienname**: Aus den verfügbaren Richtlinien auswählen</span><span class="sxs-lookup"><span data-stu-id="6e45d-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="6e45d-174">**Genehmigungstyp**: Manuell oder automatisch</span><span class="sxs-lookup"><span data-stu-id="6e45d-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="6e45d-175">**Genehmigungsgruppe**: Wählen Sie die in Schritt 1 erstellte Gruppe der genehmigenden Personen aus.</span><span class="sxs-lookup"><span data-stu-id="6e45d-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="6e45d-176">Wählen **Sie Erstellen** und dann Schließen **aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="6e45d-177">Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6e45d-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6e45d-178">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e45d-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6e45d-179">Führen Sie zum Erstellen und Definieren einer Genehmigungsrichtlinie den folgenden Befehl in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="6e45d-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="6e45d-180">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e45d-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="6e45d-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="6e45d-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="6e45d-182">Schritt 4: Übermitteln/Genehmigen privilegierter Zugriffsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e45d-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="6e45d-183">Anforderung einer Erhebungsberechtigung zur Ausführung privilegierter Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6e45d-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="6e45d-184">Anforderungen für einen privilegierten Zugriff sind bis zu 24 Stunden nach Einreichung der Anforderung gültig.</span><span class="sxs-lookup"><span data-stu-id="6e45d-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="6e45d-185">Wenn sie nicht genehmigt oder abgelehnt werden, verfallen die Anforderungen und der Zugriff wird nicht genehmigt.</span><span class="sxs-lookup"><span data-stu-id="6e45d-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6e45d-186">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6e45d-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="6e45d-187">Melden Sie sich [Microsoft 365 Admin Center mit](https://admin.microsoft.com) Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6e45d-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="6e45d-188">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6e45d-189">Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6e45d-190">Wählen **Sie Neue Anforderung aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-190">Select **New request**.</span></span> <span data-ttu-id="6e45d-191">Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="6e45d-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="6e45d-192">**Anforderungstyp**: Aufgabe, Rolle oder Rollengruppe</span><span class="sxs-lookup"><span data-stu-id="6e45d-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="6e45d-193">**Geltungsbereich der Anforderung**: Exchange</span><span class="sxs-lookup"><span data-stu-id="6e45d-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="6e45d-194">**Anforderung für**: Aus den verfügbaren Richtlinien auswählen</span><span class="sxs-lookup"><span data-stu-id="6e45d-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="6e45d-195">**Dauer (Stunden)**: Anzahl der Stunden, die für den angeforderten Zugriff erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6e45d-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="6e45d-196">Es gibt keinen Grenzwert für die Anzahl der Stunden, die angefordert werden können.</span><span class="sxs-lookup"><span data-stu-id="6e45d-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="6e45d-197">**Kommentare**: Textfeld für Kommentare im Zusammenhang mit Ihrer Zugriffsanforderung</span><span class="sxs-lookup"><span data-stu-id="6e45d-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="6e45d-198">Wählen **Sie Speichern** und dann Schließen **aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="6e45d-199">Ihre Anforderung wird per E-Mail an die Gruppe der Genehmigende gesendet.</span><span class="sxs-lookup"><span data-stu-id="6e45d-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6e45d-200">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e45d-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6e45d-201">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Genehmigungsanforderung an die Gruppe der genehmigenden Benutzer zu erstellen und zu übermitteln:</span><span class="sxs-lookup"><span data-stu-id="6e45d-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="6e45d-202">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e45d-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="6e45d-203">Anzeigen des Status von Anforderungen für erhöhte Rechte</span><span class="sxs-lookup"><span data-stu-id="6e45d-203">View status of elevation requests</span></span>

<span data-ttu-id="6e45d-204">Nachdem eine Genehmigungsanforderung erstellt wurde, kann der Status der Erhöhungsanforderung im Admin Center oder in Exchange Management PowerShell mithilfe der anforderungs-ID überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="6e45d-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6e45d-205">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6e45d-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6e45d-206">Melden Sie sich [Microsoft 365 Admin Center mit](https://admin.microsoft.com) Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6e45d-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="6e45d-207">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6e45d-208">Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6e45d-209">Wählen **Sie Ansicht** aus, um übermittelte Anforderungen nach Status **"Ausstehend", "Genehmigt",** **"Verweigert"** oder **"Customer Lockbox" zu** filtern. </span><span class="sxs-lookup"><span data-stu-id="6e45d-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6e45d-210">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e45d-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6e45d-211">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um einen Genehmigungsanforderungsstatus für eine bestimmte Anforderungs-ID anzeigen:</span><span class="sxs-lookup"><span data-stu-id="6e45d-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="6e45d-212">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e45d-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="6e45d-213">Genehmigen einer Anforderung für die Erhöhungsautorisierung</span><span class="sxs-lookup"><span data-stu-id="6e45d-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="6e45d-214">Wenn eine Genehmigungsanforderung erstellt wird, erhalten Mitglieder der entsprechenden genehmigende Gruppe eine E-Mail-Benachrichtigung und können die Anforderung genehmigen, die der Anforderungs-ID zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6e45d-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="6e45d-215">Der Antragsteller wird über die Genehmigung oder Ablehnung der Anforderung per E-Mail benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="6e45d-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6e45d-216">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6e45d-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6e45d-217">Melden Sie sich [Microsoft 365 Admin Center mit](https://admin.microsoft.com) Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6e45d-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="6e45d-218">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6e45d-219">Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6e45d-220">Wählen Sie eine aufgelistete Anforderung aus, um die Details anzuzeigen und Maßnahmen für die Anforderung zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="6e45d-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="6e45d-221">Wählen **Sie Genehmigen** aus, um die Anforderung zu genehmigen, oder wählen Sie Verweigern **aus,** um die Anforderung zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="6e45d-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="6e45d-222">Zuvor genehmigte Anforderungen können den Zugriff widerrufen haben, indem Sie **Widerrufen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6e45d-223">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e45d-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6e45d-224">Führen Sie zum Genehmigen einer Anforderung für die Erhöhungsautorisierung den folgenden Befehl in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="6e45d-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="6e45d-225">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e45d-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="6e45d-226">Führen Sie zum Verweigern einer Anforderung für die Erhöhungsautorisierung den folgenden Befehl in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="6e45d-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="6e45d-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e45d-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="6e45d-228">Löschen einer Richtlinie für den privilegierten Zugriff in Office 365</span><span class="sxs-lookup"><span data-stu-id="6e45d-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="6e45d-229">Wenn sie in Ihrer Organisation nicht mehr benötigt wird, können Sie eine Richtlinie für den privilegierten Zugriff löschen.</span><span class="sxs-lookup"><span data-stu-id="6e45d-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6e45d-230">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6e45d-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6e45d-231">Melden Sie sich [Microsoft 365 administrator center mit](https://admin.microsoft.com) Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="6e45d-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6e45d-232">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6e45d-233">Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6e45d-234">Wählen **Sie Richtlinien konfigurieren aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="6e45d-235">Wählen Sie die Richtlinie aus, die Sie löschen möchten, und wählen Sie **dann Richtlinie entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="6e45d-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="6e45d-236">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e45d-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6e45d-237">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e45d-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6e45d-238">Führen Sie zum Löschen einer Richtlinie für den privilegierten Zugriff den folgenden Befehl in Exchange Online Powershell aus:</span><span class="sxs-lookup"><span data-stu-id="6e45d-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="6e45d-239">Deaktivieren des privilegierten Zugriffs in Office 365</span><span class="sxs-lookup"><span data-stu-id="6e45d-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="6e45d-240">Bei Bedarf können Sie die Verwaltung des privilegierten Zugriffs für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e45d-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="6e45d-241">Durch das Deaktivieren des privilegierten Zugriffs werden keine zugeordneten Genehmigungsrichtlinien oder genehmigenden Gruppen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6e45d-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6e45d-242">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6e45d-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6e45d-243">Melden Sie sich [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="6e45d-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6e45d-244">Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="6e45d-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6e45d-245">Aktivieren Sie die **Option Genehmigungen für privilegierte Zugriffssteuerung** erfordern.</span><span class="sxs-lookup"><span data-stu-id="6e45d-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6e45d-246">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e45d-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6e45d-247">Führen Sie zum Deaktivieren des privilegierten Zugriffs den folgenden Befehl in Exchange Online Powershell aus:</span><span class="sxs-lookup"><span data-stu-id="6e45d-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
