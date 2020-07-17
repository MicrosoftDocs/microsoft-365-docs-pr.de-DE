---
title: Aktivieren von Office 365 ATP – SharePoint, OneDrive, & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Hier erfahren Sie, wie Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich der Vorgehensweise zum Festlegen von Benachrichtigungen für erkannte Dateien.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 976911abe047be350ae6c64409cd6607ea75de7a
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811074"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1414d-103">Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1414d-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1414d-104">Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="1414d-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="1414d-105">Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Links in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="1414d-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="1414d-106">[Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.</span><span class="sxs-lookup"><span data-stu-id="1414d-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="1414d-107">Wenn eine bösartige Datei erkannt wird, wird diese Datei blockiert, sodass niemand Sie öffnen, kopieren, weiterleiten oder freigeben kann, bis weitere Aktionen vom Sicherheitsteam der Organisation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1414d-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="1414d-108">Lesen Sie diesen Artikel, um ATP für SharePoint, OneDrive und Teams zu aktivieren, Warnungen einzurichten, um über erkannte Dateien benachrichtigt zu werden, und führen Sie die nächsten Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="1414d-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="1414d-109">Um ATP-Richtlinien zu definieren oder zu bearbeiten, muss Ihnen eine entsprechende Rolle zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="1414d-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="1414d-110">In der folgenden Tabelle werden einige Beispiele beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1414d-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="1414d-111">Rolle</span><span class="sxs-lookup"><span data-stu-id="1414d-111">Role</span></span>|<span data-ttu-id="1414d-112">Wo/wie zugewiesen</span><span class="sxs-lookup"><span data-stu-id="1414d-112">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="1414d-113">globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="1414d-113">global administrator</span></span>|<span data-ttu-id="1414d-114">Die Person, die sich zum Kauf von Microsoft 365 anmeldet, ist standardmäßig ein globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="1414d-114">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="1414d-115">(Weitere Informationen finden Sie unter [Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="1414d-115">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="1414d-116">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="1414d-116">Security Administrator</span></span>|<span data-ttu-id="1414d-117">Azure Active Directory Admin Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="1414d-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="1414d-118">Exchange Online-Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="1414d-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="1414d-119">Exchange Admin Center ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="1414d-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="1414d-120">oder</span><span class="sxs-lookup"><span data-stu-id="1414d-120">or</span></span> <br>  <span data-ttu-id="1414d-121">PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="1414d-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1414d-122">Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1414d-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="1414d-123">**Bevor Sie mit diesem Verfahren beginnen, müssen Sie sicherstellen, dass die Überwachungsprotokollierung für Ihre Microsoft 365-Umgebung bereits aktiviert ist**.</span><span class="sxs-lookup"><span data-stu-id="1414d-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="1414d-124">Dies erfolgt in der Regel durch eine Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1414d-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="1414d-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="1414d-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="1414d-126">Wechseln Sie zu [https://protection.office.com](https://protection.office.com) , und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="1414d-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>

2. <span data-ttu-id="1414d-127">Wählen Sie im Sicherheits & Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinien** für \> **sichere Anlagen**aus.</span><span class="sxs-lookup"><span data-stu-id="1414d-127">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![Wählen Sie im Security & Compliance Center die Option Threat Management Policy aus. \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="1414d-129">Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="1414d-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Aktivieren von Advanced Threat Protection für SharePoint Online, OneDrive für Unternehmen und Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="1414d-131">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1414d-131">Click **Save**.</span></span>

5. <span data-ttu-id="1414d-132">Überprüfen Sie (und bearbeiten Sie gegebenenfalls die Richtlinien für [sichere Anlagen](set-up-atp-safe-attachments-policies.md) Ihrer Organisation und [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md)).</span><span class="sxs-lookup"><span data-stu-id="1414d-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="1414d-133">Empfohlen Führen Sie als globaler Administrator oder SharePoint Online Administrator das Cmdlet " **[SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** " aus, wobei der Parameter " _DisallowInfectedFileDownload_ " auf " *true*" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1414d-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="1414d-134">Durch Festlegen des Parameters auf *true* werden alle Aktionen (außer DELETE) für erkannte Dateien blockiert.</span><span class="sxs-lookup"><span data-stu-id="1414d-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="1414d-135">Personen können erkannte Dateien nicht öffnen, kopieren oder freigeben.</span><span class="sxs-lookup"><span data-stu-id="1414d-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="1414d-136">Durch Festlegen des Parameters auf *false* werden alle Aktionen außer DELETE und Download blockiert.</span><span class="sxs-lookup"><span data-stu-id="1414d-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="1414d-137">Personen können wählen, das Risiko zu akzeptieren und eine erkannte Datei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1414d-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="1414d-138">Lassen Sie bis zu 30 Minuten zu, bis Ihre Änderungen auf alle Microsoft 365-Rechenzentren verteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="1414d-138">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

8. <span data-ttu-id="1414d-139">Empfohlen Fahren Sie mit Einrichten von Benachrichtigungen für erkannte Dateien fort.</span><span class="sxs-lookup"><span data-stu-id="1414d-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="1414d-140">Weitere Informationen zur Verwendung von PowerShell mit Microsoft 365 finden Sie unter [Verwalten von Microsoft 365 mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="1414d-140">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="1414d-141">Weitere Informationen zur Benutzerfreundlichkeit, wenn eine Datei als bösartig erkannt wurde, finden Sie unter [Vorgehensweise, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="1414d-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="1414d-142">Einrichten von Benachrichtigungen für erkannte Dateien</span><span class="sxs-lookup"><span data-stu-id="1414d-142">Set up alerts for detected files</span></span>

<span data-ttu-id="1414d-143">Um eine Benachrichtigung zu erhalten, wenn eine Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams als bösartig identifiziert wurde, können Sie eine Warnung einrichten.</span><span class="sxs-lookup"><span data-stu-id="1414d-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="1414d-144">Wählen Sie im [Security & Compliance Center](https://protection.office.com) **Alerts** \> **Manage Alerts**aus.</span><span class="sxs-lookup"><span data-stu-id="1414d-144">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="1414d-145">Wählen Sie **neue Warnungs Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="1414d-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="1414d-146">Geben Sie einen Namen für die Warnung an.</span><span class="sxs-lookup"><span data-stu-id="1414d-146">Specify a name for the alert.</span></span> <span data-ttu-id="1414d-147">Sie können beispielsweise böswillige Dateien in Bibliotheken eingeben.</span><span class="sxs-lookup"><span data-stu-id="1414d-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="1414d-148">Geben Sie eine Beschreibung für die Warnung ein.</span><span class="sxs-lookup"><span data-stu-id="1414d-148">Type a description for the alert.</span></span> <span data-ttu-id="1414d-149">Sie können beispielsweise benachrichtigte Administratoren eingeben, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="1414d-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="1414d-150">Führen Sie im Abschnitt **Diese Warnung senden, wenn...** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1414d-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="1414d-151">a.</span><span class="sxs-lookup"><span data-stu-id="1414d-151">a.</span></span> <span data-ttu-id="1414d-152">Wählen Sie in der Liste **Aktivitäten** die Option **erkannte Schadsoftware in Datei aus**.</span><span class="sxs-lookup"><span data-stu-id="1414d-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="1414d-153">b.</span><span class="sxs-lookup"><span data-stu-id="1414d-153">b.</span></span> <span data-ttu-id="1414d-154">Lassen Sie das Feld **Benutzer** leer.</span><span class="sxs-lookup"><span data-stu-id="1414d-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="1414d-155">Wählen Sie im Abschnitt **diese Benachrichtigung an... senden** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheits Leser aus, die eine Benachrichtigung erhalten sollen, wenn eine Schadsoftware erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1414d-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="1414d-156">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1414d-156">Click **Save**.</span></span>

<span data-ttu-id="1414d-157">Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitäts Warnungen im Security & Compliance Center](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="1414d-157">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1414d-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1414d-158">Next steps</span></span>

1. [<span data-ttu-id="1414d-159">Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="1414d-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="1414d-160">Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1414d-160">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
