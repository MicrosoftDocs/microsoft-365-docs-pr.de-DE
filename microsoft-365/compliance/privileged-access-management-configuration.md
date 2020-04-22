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
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: In diesem Thema erfahren Sie mehr über die Konfiguration der privilegierten Zugriffsverwaltung.
ms.openlocfilehash: 196685eda6818b399c778363ee458f6f2792a33a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626511"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="963e8-103">Erste Schritte mit der Verwaltung des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="963e8-103">Get started with privileged access management</span></span>

<span data-ttu-id="963e8-104">Dieses Thema führt Sie durch das Aktivieren und Konfigurieren der privilegierten Zugriffsverwaltung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="963e8-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="963e8-105">Sie können entweder das Microsoft 365 Admin Center oder die Exchange-Verwaltungskonsole verwenden, um privilegierten Zugriff zu verwalten und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="963e8-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="963e8-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="963e8-106">Before you begin</span></span>

<span data-ttu-id="963e8-107">Bevor Sie mit der privilegierten Zugriffsverwaltung beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-ons bestätigen.</span><span class="sxs-lookup"><span data-stu-id="963e8-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="963e8-108">Für den Zugriff auf und die Verwendung der privilegierten Zugriffsverwaltung muss Ihre Organisation über eines der folgenden Abonnements oder Add-ons verfügen:</span><span class="sxs-lookup"><span data-stu-id="963e8-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="963e8-109">Microsoft 365 E5-Abonnement (kostenpflichtige oder Testversion)</span><span class="sxs-lookup"><span data-stu-id="963e8-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="963e8-110">Microsoft 365 E3-Abonnement (oder Office 365 E3-Abonnement + Enterprise Mobility and Security E3-Abonnement) + das Microsoft 365 E5-Compliance-Add-on</span><span class="sxs-lookup"><span data-stu-id="963e8-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="963e8-111">Alle Microsoft 365-, Office 365-, Exchange-, SharePoint-oder OneDrive für Unternehmen-Abonnements und das Microsoft 365 E5 Insider Risk Management-Add-on</span><span class="sxs-lookup"><span data-stu-id="963e8-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="963e8-112">Microsoft 365 A5-Abonnement (kostenpflichtige oder Testversion)</span><span class="sxs-lookup"><span data-stu-id="963e8-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="963e8-113">Microsoft 365 a3-Abonnement (oder Office 365 a3-Abonnement + Enterprise Mobility and Security a3-Abonnement) + das Microsoft A5-Konformitäts-Add-on</span><span class="sxs-lookup"><span data-stu-id="963e8-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="963e8-114">Alle Microsoft 365-, Office 365-, Exchange-, SharePoint-oder OneDrive for Education-Abonnements + das Microsoft 365 A5 Insider Risk Management-Add-on</span><span class="sxs-lookup"><span data-stu-id="963e8-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="963e8-115">Office 365 Enterprise E5-Abonnement (kostenpflichtige oder Testversion)</span><span class="sxs-lookup"><span data-stu-id="963e8-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="963e8-116">Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-on (nicht mehr für neue Abonnements verfügbar, siehe Hinweis)</span><span class="sxs-lookup"><span data-stu-id="963e8-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="963e8-117">Benutzern, die Zugriffs Verwaltungsanforderungen übermitteln und diese Antworten, muss eine der oben aufgeführten Lizenzen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="963e8-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="963e8-118">Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft.</span><span class="sxs-lookup"><span data-stu-id="963e8-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="963e8-119">Wenn die aktuellen Abonnements ablaufen, sollten Kunden zu einem der oben genannten Abonnements übergehen, die die gleichen oder zusätzliche Compliance-Features enthalten.</span><span class="sxs-lookup"><span data-stu-id="963e8-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="963e8-120">Wenn Sie keinen Office 365 Enterprise E5-Plan haben und die privilegierte Zugriffsverwaltung testen möchten, können Sie Microsoft 365 zu Ihrem vorhandenen Office 365-Abonnement [Hinzufügen](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) oder [sich für eine Testversion](https://www.microsoft.com/microsoft-365/enterprise) von Microsoft 365 Enterprise E5 registrieren.</span><span class="sxs-lookup"><span data-stu-id="963e8-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="963e8-121">Aktivieren und Konfigurieren der privilegierten Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="963e8-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="963e8-122">Führen Sie die folgenden Schritte zum Einrichten und Verwenden von privilegiertem Zugriff in Ihrer Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="963e8-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="963e8-123">Schritt 1: Erstellen einer Gruppe einer genehmigenden Person</span><span class="sxs-lookup"><span data-stu-id="963e8-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="963e8-124">Bevor Sie mit dem Verwenden des Zugriffs auf Berechtigungen beginnen, müssen Sie ermitteln, wer Genehmigungsautorität für eingehende Anforderungen für den Zugriff auf Erweiterte und privilegierte Aufgaben benötigt.</span><span class="sxs-lookup"><span data-stu-id="963e8-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="963e8-125">Jeder Benutzer, der Teil der Gruppe der genehmigenden Personen ist, kann Zugriffsanforderungen genehmigen.</span><span class="sxs-lookup"><span data-stu-id="963e8-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="963e8-126">Diese Gruppe wird durch Erstellen einer e-Mail-aktivierten Sicherheitsgruppe in Office 365 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="963e8-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="963e8-127">Schritt 2: Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="963e8-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="963e8-128">Der privilegierte Zugriff muss in Office 365 explizit mit der standardmäßigen genehmigenden Gruppe aktiviert sein, einschließlich einer Reihe von Systemkonten, die von der Zugriffssteuerung für privilegierte Zugriffsverwaltung ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="963e8-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="963e8-129">Schritt 3: Erstellen einer Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="963e8-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="963e8-130">Durch das Erstellen einer Genehmigungsrichtlinie können Sie die spezifischen Genehmigungsanforderungen definieren, die auf einzelne Vorgänge beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="963e8-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="963e8-131">Die Genehmigungs Typen Optionen sind **Auto** oder **manuell**.</span><span class="sxs-lookup"><span data-stu-id="963e8-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="963e8-132">Schritt 4: senden/genehmigen von Berechtigungen für privilegierte Zugriffe</span><span class="sxs-lookup"><span data-stu-id="963e8-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="963e8-133">Nach Aktivierung erfordert der privilegierte Zugriff Genehmigungen für jede Aufgabe, für die eine zugeordnete Genehmigungsrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="963e8-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="963e8-134">Für Aufgaben, die in einer Genehmigungsrichtlinie enthalten sind, müssen die Benutzer die Genehmigung für den Zugriff anfordern und erhalten, damit die erforderlichen Berechtigungen zum Ausführen der Aufgabe erteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="963e8-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="963e8-135">Nachdem die Genehmigung erteilt wurde, kann der anfordernde Benutzer die vorgesehene Aufgabe ausführen, und der privilegierte Zugriff autorisiert und führt die Aufgabe im Namen des Benutzers aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="963e8-136">Die Genehmigung bleibt für die angeforderte Dauer gültig (die Standarddauer beträgt 4 Stunden), während der der Anforderer die beabsichtigte Aufgabe mehrmals ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="963e8-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="963e8-137">Alle derartigen Ausführungen werden protokolliert und zur Überwachung der Sicherheit und Compliance zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="963e8-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="963e8-138">Wenn Sie die Exchange-Verwaltungs-PowerShell zum Aktivieren und Konfigurieren des privilegierten Zugriffs verwenden möchten, führen Sie die Schritte unter [Verbinden mit Exchange Online PowerShell mithilfe der mehrstufigen Authentifizierung](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) aus, um eine Verbindung mit Exchange Online PowerShell mit Ihren Office 365 Anmeldeinformationen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="963e8-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="963e8-139">Sie müssen die mehrstufige Authentifizierung für Ihre Organisation nicht aktivieren, um die erforderlichen Schritte zum Aktivieren des privilegierten Zugriffs beim Herstellen einer Verbindung mit Exchange Online PowerShell durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="963e8-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="963e8-140">Durch die Verbindung mit mehrstufiger Authentifizierung wird ein OAuth-Token erstellt, das von privilegiertem Zugriff zum Signieren Ihrer Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="963e8-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="963e8-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="963e8-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="963e8-142">Schritt 1: Erstellen einer Gruppe einer genehmigenden Person</span><span class="sxs-lookup"><span data-stu-id="963e8-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="963e8-143">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="963e8-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="963e8-144">Wechseln Sie im Admin Center zu **Gruppen** > **Hinzufügen einer Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="963e8-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="963e8-145">Wählen Sie **e-Mail-aktivierte Sicherheitsgruppe** aus, und füllen Sie dann die Felder **Name**, **Gruppen-e-Mail-Adresse**und **Beschreibung** für die neue Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="963e8-146">Speichern Sie die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="963e8-146">Save the group.</span></span> <span data-ttu-id="963e8-147">Es kann einige Minuten dauern, bis die Gruppe vollständig konfiguriert und im Microsoft 365 Admin Center angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="963e8-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="963e8-148">Wählen Sie die Gruppe neue genehmigende Person aus, und wählen Sie **Bearbeiten** aus, um der Gruppe Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="963e8-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="963e8-149">Speichern Sie die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="963e8-149">Save the group.</span></span>

<span data-ttu-id="963e8-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="963e8-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="963e8-151">Schritt 2: Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="963e8-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="963e8-152">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="963e8-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="963e8-153">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="963e8-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="963e8-154">Wechseln Sie im Admin Center zu **Einstellungen > Einstellungen > Security & Privacy** > **privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="963e8-154">In the Admin Center, go to **Settings > Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="963e8-155">Aktivieren Sie das Steuerelement **erforderliche Genehmigungen für privilegierte Aufgaben** .</span><span class="sxs-lookup"><span data-stu-id="963e8-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="963e8-156">Weisen Sie die Gruppe der genehmigenden Person, die Sie in Schritt 1 erstellt haben, als **Standard genehmigende Gruppe**zu.</span><span class="sxs-lookup"><span data-stu-id="963e8-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="963e8-157">**Speichern** und **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="963e8-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="963e8-158">In der Exchange-Verwaltungs-PowerShell</span><span class="sxs-lookup"><span data-stu-id="963e8-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="963e8-159">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den privilegierten Zugriff zu aktivieren und die Gruppe der genehmigenden Person zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="963e8-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="963e8-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="963e8-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="963e8-161">Die Funktion System Konten wird bereitgestellt, um sicherzustellen, dass bestimmte Automatisierungen in ihren Organisationen ohne Abhängigkeit von privilegiertem Zugriff funktionieren können, es wird jedoch empfohlen, dass diese Ausnahmen außergewöhnlich sind und die zulässigen regelmäßig genehmigt und überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="963e8-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="963e8-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="963e8-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="963e8-163">Schritt 3: Erstellen einer Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="963e8-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="963e8-164">Sie können bis zu 30 privilegierte Zugriffsrichtlinien für Ihre Organisation erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="963e8-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="963e8-165">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="963e8-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="963e8-166">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="963e8-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="963e8-167">Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="963e8-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="963e8-168">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="963e8-169">Wählen Sie **Richtlinien konfigurieren** aus, und wählen Sie **Richtlinie hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="963e8-170">Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="963e8-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="963e8-171">**Richtlinientyp**: Aufgabe, Rolle oder Rollengruppe</span><span class="sxs-lookup"><span data-stu-id="963e8-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="963e8-172">**Richtlinienbereich**: Exchange</span><span class="sxs-lookup"><span data-stu-id="963e8-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="963e8-173">**Richtlinienname**: Wählen Sie aus den verfügbaren Richtlinien aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="963e8-174">**Genehmigungs**: manuell oder automatisch</span><span class="sxs-lookup"><span data-stu-id="963e8-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="963e8-175">**Genehmigungsgruppe**: Wählen Sie die in Schritt 1 erstellte genehmigende Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="963e8-176">Klicken Sie auf **Erstellen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="963e8-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="963e8-177">Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="963e8-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="963e8-178">In der Exchange-Verwaltungs-PowerShell</span><span class="sxs-lookup"><span data-stu-id="963e8-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="963e8-179">Zum Erstellen und Definieren einer Genehmigungsrichtlinie führen Sie den folgenden Befehl in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="963e8-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="963e8-180">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="963e8-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="963e8-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="963e8-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="963e8-182">Schritt 4: senden/genehmigen von Berechtigungen für privilegierte Zugriffe</span><span class="sxs-lookup"><span data-stu-id="963e8-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="963e8-183">Anfordern von Höhen Autorisierung zum Ausführen privilegierter Aufgaben</span><span class="sxs-lookup"><span data-stu-id="963e8-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="963e8-184">Anforderungen für privilegierten Zugriff sind bis zu 24 Stunden nach der Übermittlung der Anforderung gültig.</span><span class="sxs-lookup"><span data-stu-id="963e8-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="963e8-185">Wenn diese nicht genehmigt oder verweigert werden, laufen die Anforderungen ab, und der Zugriff ist nicht genehmigt.</span><span class="sxs-lookup"><span data-stu-id="963e8-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="963e8-186">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="963e8-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="963e8-187">Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="963e8-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="963e8-188">Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="963e8-188">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="963e8-189">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="963e8-190">Wählen Sie **neue Anforderung**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-190">Select **New request**.</span></span> <span data-ttu-id="963e8-191">Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:</span><span class="sxs-lookup"><span data-stu-id="963e8-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="963e8-192">**Anforderungstyp**: Aufgabe, Rolle oder Rollengruppe</span><span class="sxs-lookup"><span data-stu-id="963e8-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="963e8-193">**Anforderungsbereich**: Exchange</span><span class="sxs-lookup"><span data-stu-id="963e8-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="963e8-194">**Anforderung für**: Wählen Sie aus den verfügbaren Richtlinien aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="963e8-195">**Dauer (Stunden)**: Anzahl der Stunden des angeforderten Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="963e8-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="963e8-196">Es gibt keinen Grenzwert für die Anzahl der Stunden, die angefordert werden können.</span><span class="sxs-lookup"><span data-stu-id="963e8-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="963e8-197">**Kommentare**: Text Feld für Kommentare im Zusammenhang mit ihrer Zugriffsanfrage</span><span class="sxs-lookup"><span data-stu-id="963e8-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="963e8-198">Klicken Sie auf **Speichern** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="963e8-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="963e8-199">Ihre Anfrage wird per e-Mail an die Gruppe der genehmigenden Person gesendet.</span><span class="sxs-lookup"><span data-stu-id="963e8-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="963e8-200">In der Exchange-Verwaltungs-PowerShell</span><span class="sxs-lookup"><span data-stu-id="963e8-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="963e8-201">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Genehmigungsanforderung an die Gruppe der genehmigenden Person zu erstellen und zu senden:</span><span class="sxs-lookup"><span data-stu-id="963e8-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="963e8-202">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="963e8-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="963e8-203">Anzeigen des Status von Ansichts Anforderungen</span><span class="sxs-lookup"><span data-stu-id="963e8-203">View status of elevation requests</span></span>

<span data-ttu-id="963e8-204">Nach dem Erstellen einer Genehmigungsanforderung kann der Status der Ansichts Anforderung im Admin Center oder in der Exchange-Verwaltungskonsole mithilfe der zugeordneten Anforderungs-ID überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="963e8-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="963e8-205">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="963e8-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="963e8-206">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="963e8-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="963e8-207">Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="963e8-207">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="963e8-208">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="963e8-209">Wählen Sie **Ansicht** aus, um übermittelte Anforderungen nach **ausstehender**, **genehmigter**, **verweigerter**oder **Kunden sperrbox** -Status zu filtern.</span><span class="sxs-lookup"><span data-stu-id="963e8-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="963e8-210">In der Exchange-Verwaltungs-PowerShell</span><span class="sxs-lookup"><span data-stu-id="963e8-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="963e8-211">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den Status einer Genehmigungsanforderung für eine bestimmte Anforderungs-ID anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="963e8-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="963e8-212">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="963e8-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="963e8-213">Genehmigen einer Ansichts Autorisierungsanforderung</span><span class="sxs-lookup"><span data-stu-id="963e8-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="963e8-214">Wenn eine Genehmigungsanforderung erstellt wird, erhalten Mitglieder der entsprechenden genehmigenden Gruppe eine e-Mail-Benachrichtigung und können die Anforderung genehmigen, die der Anforderungs-ID zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="963e8-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="963e8-215">Der Anforderer wird über die Anforderungsgenehmigung oder Ablehnung per e-Mail-Nachricht benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="963e8-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="963e8-216">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="963e8-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="963e8-217">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="963e8-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="963e8-218">Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="963e8-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="963e8-219">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="963e8-220">Wählen Sie eine aufgeführte Anforderung aus, um die Details anzuzeigen und Aktionen für die Anforderung durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="963e8-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="963e8-221">Wählen Sie **genehmigen** , um die Anforderung zu genehmigen, oder wählen Sie **verweigern** aus, um die Anforderung zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="963e8-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="963e8-222">Für zuvor genehmigte Anforderungen kann der Zugriff aufgehoben werden, indem Sie **REVOKE**auswählen.</span><span class="sxs-lookup"><span data-stu-id="963e8-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="963e8-223">In der Exchange-Verwaltungs-PowerShell</span><span class="sxs-lookup"><span data-stu-id="963e8-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="963e8-224">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Berechtigungsanforderung für Berechtigungen zu genehmigen:</span><span class="sxs-lookup"><span data-stu-id="963e8-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="963e8-225">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="963e8-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="963e8-226">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Berechtigungsanforderung für Berechtigungen zu verweigern:</span><span class="sxs-lookup"><span data-stu-id="963e8-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="963e8-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="963e8-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="963e8-228">Löschen einer privilegierten Zugriffsrichtlinie in Office 365</span><span class="sxs-lookup"><span data-stu-id="963e8-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="963e8-229">Wenn Sie in Ihrer Organisation nicht mehr benötigt wird, können Sie eine privilegierte Zugriffsrichtlinie löschen.</span><span class="sxs-lookup"><span data-stu-id="963e8-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="963e8-230">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="963e8-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="963e8-231">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="963e8-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="963e8-232">Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="963e8-232">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="963e8-233">Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="963e8-234">Wählen Sie **configure Policies**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="963e8-235">Wählen Sie die Richtlinie aus, die Sie löschen möchten, und wählen Sie dann **Richtlinie entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="963e8-236">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="963e8-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="963e8-237">In der Exchange-Verwaltungs-PowerShell</span><span class="sxs-lookup"><span data-stu-id="963e8-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="963e8-238">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine privilegierte Zugriffsrichtlinie zu löschen:</span><span class="sxs-lookup"><span data-stu-id="963e8-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="963e8-239">Deaktivieren des privilegierten Zugriffs in Office 365</span><span class="sxs-lookup"><span data-stu-id="963e8-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="963e8-240">Bei Bedarf können Sie die privilegierte Zugriffsverwaltung für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="963e8-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="963e8-241">Durch Deaktivieren des privilegierten Zugriffs werden keine zugeordneten Genehmigungsrichtlinien oder genehmigenden Gruppen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="963e8-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="963e8-242">Im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="963e8-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="963e8-243">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="963e8-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="963e8-244">Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.</span><span class="sxs-lookup"><span data-stu-id="963e8-244">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="963e8-245">Aktivieren Sie die **Berechtigung Genehmigungen für privilegierte Zugriffssteuerung erfordern** .</span><span class="sxs-lookup"><span data-stu-id="963e8-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="963e8-246">In der Exchange-Verwaltungs-PowerShell</span><span class="sxs-lookup"><span data-stu-id="963e8-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="963e8-247">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den privilegierten Zugriff zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="963e8-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
