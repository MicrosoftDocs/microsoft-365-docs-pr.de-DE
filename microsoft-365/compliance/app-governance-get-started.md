---
title: Erste Schritte mit App-Governance
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Erste Schritte mit App-Governance-Funktionen zum Steuern Ihrer Apps.
ms.openlocfilehash: 80487298f2c3c3a93f0083337ddb223bd68e2611
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438036"
---
# <a name="get-started-with-app-governance-in-preview"></a><span data-ttu-id="155ae-103">Erste Schritte mit App-Governance (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="155ae-103">Get started with app governance (in preview)</span></span>

<span data-ttu-id="155ae-104">So beginnen Sie mit der Verwendung des App-Governance-Add-Ons für Microsoft Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="155ae-104">To begin using the app governance add-on to Microsoft Cloud App Security:</span></span>

1. <span data-ttu-id="155ae-p101">Bestätigen Sie, dass Ihr Konto über die erforderliche Lizenzierungsstufe verfügt. App-Governance ist ein Add-On-Feature für Microsoft Cloud App Security (MCAS). Daher muss MCAS in Ihrem Konto entweder als eigenständiges Produkt oder als Teil einer der unten aufgeführten Lizenzpakete vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="155ae-p101">Verify your account has the appropriate level of licensing. App governance is an add-on feature for Microsoft Cloud App Security (MCAS), and thus MCAS must be present in your account as either a standalone product or as part of the various license packages listed below.</span></span>
1. <span data-ttu-id="155ae-107">Sie müssen über eine der unten aufgeführten Administratorrollen verfügen, um auf die App-Governance-Seiten im Portal zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="155ae-107">You must have one of the administrator roles listed below to access the app governance pages in the portal.</span></span>

## <a name="licensing-for-app-governance"></a><span data-ttu-id="155ae-108">Lizenzierung für App-Governance</span><span class="sxs-lookup"><span data-stu-id="155ae-108">Licensing for app governance</span></span>

<span data-ttu-id="155ae-109">Bevor Sie mit App-Governance beginnen, sollten Sie Ihr [Microsoft 365 Admin Center-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und etwaige Add-Ons überprüfen.</span><span class="sxs-lookup"><span data-stu-id="155ae-109">Before you get started with app governance, you should confirm your [Microsoft 365 admin center - subscriptions](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="155ae-110">Für den Zugriff auf und die Nutzung von App-Governance muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:</span><span class="sxs-lookup"><span data-stu-id="155ae-110">To access and use app governance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="155ae-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="155ae-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="155ae-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="155ae-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="155ae-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="155ae-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="155ae-114">Microsoft 365 E5 Developer (ohne Windows und Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="155ae-114">Microsoft 365 E5 Developer (without Windows and Audio Conferencing)</span></span>
- <span data-ttu-id="155ae-115">Microsoft 365 E5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="155ae-115">Microsoft 365 E5 Information Protection and Governance</span></span>
- <span data-ttu-id="155ae-116">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="155ae-116">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="155ae-117">Microsoft 365 E5 mit Gesprächsminuten</span><span class="sxs-lookup"><span data-stu-id="155ae-117">Microsoft 365 E5 with Calling Minutes</span></span>
- <span data-ttu-id="155ae-118">Microsoft 365 E5 ohne Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="155ae-118">Microsoft 365 E5 without Audio Conferencing</span></span>
- <span data-ttu-id="155ae-119">Microsoft 365 A5-Compliance für Lehrpersonal</span><span class="sxs-lookup"><span data-stu-id="155ae-119">Microsoft 365 A5 Compliance for faculty</span></span>
- <span data-ttu-id="155ae-120">Microsoft 365 A5-Compliance für Schüler/Studenten</span><span class="sxs-lookup"><span data-stu-id="155ae-120">Microsoft 365 A5 Compliance for students</span></span>
- <span data-ttu-id="155ae-121">Microsoft 365 A5 für Lehrpersonal</span><span class="sxs-lookup"><span data-stu-id="155ae-121">Microsoft 365 A5 for faculty</span></span>
- <span data-ttu-id="155ae-122">Microsoft 365 A5 für Schüler und Studenten</span><span class="sxs-lookup"><span data-stu-id="155ae-122">Microsoft 365 A5 for students</span></span>
- <span data-ttu-id="155ae-123">Microsoft 365 A5 Information Protection und Governance für Lehrpersonal</span><span class="sxs-lookup"><span data-stu-id="155ae-123">Microsoft 365 A5 Information Protection and Governance for faculty</span></span>
- <span data-ttu-id="155ae-124">Microsoft 365 A5 Information Protection und Governance für Schüler und Studenten</span><span class="sxs-lookup"><span data-stu-id="155ae-124">Microsoft 365 A5 Information Protection and Governance for students</span></span>
- <span data-ttu-id="155ae-125">Microsoft 365 A5-Sicherheit für Lehrpersonal</span><span class="sxs-lookup"><span data-stu-id="155ae-125">Microsoft 365 A5 Security for faculty</span></span>
- <span data-ttu-id="155ae-126">Microsoft 365 A5-Sicherheit für Schüler/Studenten</span><span class="sxs-lookup"><span data-stu-id="155ae-126">Microsoft 365 A5 Security for students</span></span>
- <span data-ttu-id="155ae-127">Microsoft 365 A5 – Vorteile für Schüler und Studenten</span><span class="sxs-lookup"><span data-stu-id="155ae-127">Microsoft 365 A5 student use benefits</span></span>
- <span data-ttu-id="155ae-128">Microsoft 365 A5 mit Gesprächsminuten für Lehrpersonal</span><span class="sxs-lookup"><span data-stu-id="155ae-128">Microsoft 365 A5 with Calling Minutes for Faculty</span></span>
- <span data-ttu-id="155ae-129">Microsoft 365 A5 mit Gesprächsminuten für Schüler und Studenten</span><span class="sxs-lookup"><span data-stu-id="155ae-129">Microsoft 365 A5 with Calling Minutes for Students</span></span>
- <span data-ttu-id="155ae-130">Microsoft 365 A5 ohne Audiokonferenz für Lehrpersonal</span><span class="sxs-lookup"><span data-stu-id="155ae-130">Microsoft 365 A5 without Audio Conferencing for faculty</span></span>
- <span data-ttu-id="155ae-131">Microsoft 365 A5 ohne Audiokonferenz für Schüler und Studenten</span><span class="sxs-lookup"><span data-stu-id="155ae-131">Microsoft 365 A5 without Audio Conferencing for students</span></span>
- <span data-ttu-id="155ae-132">Microsoft 365 A5 ohne Audiokonferenz für Schüler und Studenten – Vorteilsprogramm</span><span class="sxs-lookup"><span data-stu-id="155ae-132">Microsoft 365 A5 without Audio Conferencing for students use benefit</span></span>

## <a name="administrator-roles"></a><span data-ttu-id="155ae-133">Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="155ae-133">Administrator roles</span></span>

<span data-ttu-id="155ae-134">Eine der folgenden Administratorrollen ist erforderlich, um App-Governance-Seiten anzuzeigen oder Richtlinien und Einstellungen zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="155ae-134">One of the following administrator roles is required to see app governance pages or manage policies and settings:</span></span>

- <span data-ttu-id="155ae-135">Anwendungsadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-135">Application Administrator</span></span>
- <span data-ttu-id="155ae-136">Cloudanwendungsadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-136">Cloud Application Administrator</span></span>
- <span data-ttu-id="155ae-137">Unternehmensadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-137">Company Administrator</span></span>
- <span data-ttu-id="155ae-138">Complianceadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-138">Compliance Administrator</span></span>
- <span data-ttu-id="155ae-139">Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-139">Compliance Data Administrator</span></span>
- <span data-ttu-id="155ae-140">Complianceleseberechtigter (schreibgeschützt)</span><span class="sxs-lookup"><span data-stu-id="155ae-140">Compliance Reader (read-only)</span></span>
- <span data-ttu-id="155ae-141">Globaler Leseberechtigter</span><span class="sxs-lookup"><span data-stu-id="155ae-141">Global Reader</span></span>
- <span data-ttu-id="155ae-142">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-142">Security Administrator</span></span>
- <span data-ttu-id="155ae-143">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="155ae-143">Security Operator</span></span>
- <span data-ttu-id="155ae-144">Sicherheitsleseberechtigter (schreibgeschützt)</span><span class="sxs-lookup"><span data-stu-id="155ae-144">Security Reader (read-only)</span></span>

> [!NOTE]
> <span data-ttu-id="155ae-145">Nur ein globaler Administrator kann die kostenlose Testversion von App Governance aktivieren.</span><span class="sxs-lookup"><span data-stu-id="155ae-145">Only a Global Admin can activate the app governance free trial.</span></span>

<span data-ttu-id="155ae-146">Im Folgenden sind die Funktionen für die einzelnen Rollen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="155ae-146">Here are the capabilities for each role.</span></span>

| <span data-ttu-id="155ae-147">Rolle</span><span class="sxs-lookup"><span data-stu-id="155ae-147">Role</span></span> | <span data-ttu-id="155ae-148">Lesezugriff auf das Dashboard</span><span class="sxs-lookup"><span data-stu-id="155ae-148">Read the dashboard</span></span> | <span data-ttu-id="155ae-149">Lesezugriff auf installierten Apps</span><span class="sxs-lookup"><span data-stu-id="155ae-149">Read all apps</span></span> |<span data-ttu-id="155ae-150">Lesezugriff auf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="155ae-150">Read policies</span></span> | <span data-ttu-id="155ae-151">Richtlinien erstellen, aktualisieren oder löschen</span><span class="sxs-lookup"><span data-stu-id="155ae-151">Create, update, or delete policies</span></span> | <span data-ttu-id="155ae-152">Lesezugriff auf Warnungen</span><span class="sxs-lookup"><span data-stu-id="155ae-152">Read alerts</span></span> | <span data-ttu-id="155ae-153">Warnungen aktualisieren</span><span class="sxs-lookup"><span data-stu-id="155ae-153">Update alerts</span></span> | <span data-ttu-id="155ae-154">Lesezugriff auf Einstellungen</span><span class="sxs-lookup"><span data-stu-id="155ae-154">Read settings</span></span> | <span data-ttu-id="155ae-155">Einstellungen aktualisieren</span><span class="sxs-lookup"><span data-stu-id="155ae-155">Update settings</span></span> | <span data-ttu-id="155ae-156">Lesezugriff auf Korrekturen</span><span class="sxs-lookup"><span data-stu-id="155ae-156">Read Remediation</span></span> | <span data-ttu-id="155ae-157">Korrekturen aktualisieren</span><span class="sxs-lookup"><span data-stu-id="155ae-157">Update Remediation</span></span> |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="155ae-158">Anwendungsadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-158">Application Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |
| <span data-ttu-id="155ae-169">Cloudanwendungsadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-169">Cloud Application Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | | | | | | | | | |
| <span data-ttu-id="155ae-171">Unternehmensadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-171">Company Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |
| <span data-ttu-id="155ae-182">Complianceadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-182">Compliance Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | |
| <span data-ttu-id="155ae-191">Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-191">Compliance Data Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | |
| <span data-ttu-id="155ae-200">Complianceleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="155ae-200">Compliance Reader</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | | |
| <span data-ttu-id="155ae-206">Globaler Leseberechtigter</span><span class="sxs-lookup"><span data-stu-id="155ae-206">Global Reader</span></span>  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | | |
| <span data-ttu-id="155ae-212">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="155ae-212">Security Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | |
| <span data-ttu-id="155ae-221">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="155ae-221">Security Operator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | |
| <span data-ttu-id="155ae-231">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="155ae-231">Security Reader</span></span>  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) | |
|||||||||| | |

<span data-ttu-id="155ae-238">Weitere Informationen zu den einzelnen Rollen finden Sie unter [Administratorrollenberechtigungen](/azure/active-directory/roles/permissions-reference).</span><span class="sxs-lookup"><span data-stu-id="155ae-238">For additional information about each role, see [Administrator role permissions](/azure/active-directory/roles/permissions-reference).</span></span>

## <a name="add-app-governance-to-your-microsoft-365-account"></a><span data-ttu-id="155ae-239">Hinzufügen von App-Governance zu Ihrem Microsoft 365-Konto</span><span class="sxs-lookup"><span data-stu-id="155ae-239">Add app governance to your Microsoft 365 account</span></span>

<span data-ttu-id="155ae-240">Für bestehende Microsoft 365-Kunden:</span><span class="sxs-lookup"><span data-stu-id="155ae-240">For existing Microsoft 365 customers:</span></span>

1. <span data-ttu-id="155ae-241">Navigieren Sie in Ihrem [Microsoft 365 Admin Center](https://admin.microsoft.com) zu **Abrechnung – Dienste kaufen**, und klicken Sie auf **Add-Ons**.</span><span class="sxs-lookup"><span data-stu-id="155ae-241">In your [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Billing - Purchase services** and click **Add-ons**.</span></span>
1. <span data-ttu-id="155ae-242">Klicken Sie auf der App-Governance-Karte auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="155ae-242">In the app governance card, click **Details**.</span></span>
1. <span data-ttu-id="155ae-243">Klicken Sie auf **Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="155ae-243">Click **Start free trial**.</span></span>
1. <span data-ttu-id="155ae-244">Füllen Sie die angeforderten Informationen aus, um App-Governance zu Ihrem ausgewählten Mandanten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="155ae-244">Complete the requested information to add app governance to your selected tenant.</span></span> <span data-ttu-id="155ae-245">Wenn Sie ein neuer Kunde sind, müssen Sie zuerst bestimmte Informationen angeben, um ein Konto einzurichten und einen Mandanten für Ihren Testzeitraum zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="155ae-245">I you are a new customer, you must first provide information to establish an account and create a tenant for your trial period.</span></span> <span data-ttu-id="155ae-246">Sobald dies abgeschlossen ist, können Sie App-Governance zur Testversion hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="155ae-246">Once this is done you can add app governance to the trial.</span></span>

<span data-ttu-id="155ae-247">Für neue Microsoft 365-Kunden:</span><span class="sxs-lookup"><span data-stu-id="155ae-247">For new Microsoft 365 customers:</span></span>

1. <span data-ttu-id="155ae-248">Klicken Sie oben auf dieser Seite auf die Schaltfläche **Kostenloses Konto**.</span><span class="sxs-lookup"><span data-stu-id="155ae-248">At the top of this page, click the **Free Account** button.</span></span>
1. <span data-ttu-id="155ae-249">Klicken Sie unter **Microsoft 365 for Business testen** auf **1 Monat kostenlos testen**.</span><span class="sxs-lookup"><span data-stu-id="155ae-249">Under **Try Microsoft 365 for business** click **Try 1 month free**.</span></span>

<span data-ttu-id="155ae-250">Für beide:</span><span class="sxs-lookup"><span data-stu-id="155ae-250">For both:</span></span>

1. <span data-ttu-id="155ae-251">Geben Sie im Registrierungsportal Ihre E-Mail-Adresse für die Testversion an.</span><span class="sxs-lookup"><span data-stu-id="155ae-251">In the sign-up portal, provide your email address to use for the trial.</span></span> <span data-ttu-id="155ae-252">Wenn Sie bereits Kunde sind, verwenden Sie die E-Mail-Adresse, die Ihrem Konto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="155ae-252">If you are an existing customer, use the email associated with your account.</span></span> <span data-ttu-id="155ae-253">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="155ae-253">Click **Next**</span></span>
1. <span data-ttu-id="155ae-254">Nachdem Sie sich angemeldet haben, klicken Sie auf **Jetzt testen**, um die kostenlose Testversion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="155ae-254">Once you have signed in, click **Try now** to get the free trial.</span></span>
1. <span data-ttu-id="155ae-255">Klicken Sie auf **Weiter**, um die Seite zu schließen und mit der Einrichtung der Testversion zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="155ae-255">Click **Continue** to close page and begin trial setup.</span></span> <span data-ttu-id="155ae-256">Für neue App-Governance-Kunden dauert es bis zu zwei Stunden, bis die App Governance-Instanz verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="155ae-256">For new app governance customers, it will take up to two hours for your app governance instance to become available.</span></span> <span data-ttu-id="155ae-257">Für Bestandskunden kommt es zu keiner Unterbrechung vorhandener Dienste.</span><span class="sxs-lookup"><span data-stu-id="155ae-257">For existing customers, there will be no interruption of existing services.</span></span>
  > [!NOTE]
<span data-ttu-id="155ae-258">Wenn Sie noch nicht über ein Konto verfügen, werden Sie aufgefordert, ein neues Konto einzurichten, bevor Sie mit der Testversion fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="155ae-258">If you do not already have an account you will be prompted to set up a new account before you can proceed with the trial.</span></span>

1. <span data-ttu-id="155ae-259">Geben Sie einen verfügbaren Domänennamen für Ihren AAD-Mandanten ein, und klicken Sie auf **Verfügbarkeit überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="155ae-259">Enter in an available domain name for your AAD tenant and click **Check availability**.</span></span> <span data-ttu-id="155ae-260">Ihnen wird automatisch eine Administratorrolle zugewiesen (wenn Sie über keine vorhandene Rolle für die App-Governance verfügen). Sie können den Domänennamen jederzeit ändern und/oder später weitere Mandanten über das Microsoft 365 Admin Center erwerben.</span><span class="sxs-lookup"><span data-stu-id="155ae-260">You will automatically be assigned an Admin role (if you don’t have an existing role for app governance) and can always change the domain name and/or purchase more tenants later through the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="155ae-261">Geben Sie den Benutzernamen und das Kennwort ein, die Sie für die Anmeldung bei Ihrem Konto verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="155ae-261">Enter the username and password you would like to use to login to your account.</span></span> <span data-ttu-id="155ae-262">Klicken Sie auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="155ae-262">Click **Sign up**.</span></span>
1. <span data-ttu-id="155ae-263">Klicken Sie auf **Erste Schritte**, um zum App-Governance-Portal zu wechseln, oder auf **Abonnement verwalten**, um zum Microsoft 365 Admin Center zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="155ae-263">Click **Get started** to go to the app governance portal or **Manage your subscription** to go to the Microsoft 365 admin center.</span></span>