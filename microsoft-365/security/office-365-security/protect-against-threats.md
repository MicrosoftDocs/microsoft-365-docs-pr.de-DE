---
title: Schutz vor Bedrohungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zum Bedrohungsschutz in Microsoft 365 und konfigurieren, wie Sie für Ihre Organisation verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4176aabb88d177c7cff0f32f32543a251b558170
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587992"
---
# <a name="protect-against-threats"></a><span data-ttu-id="dbbbd-103">Schutz vor Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="dbbbd-103">Protect against threats</span></span>

<span data-ttu-id="dbbbd-104">Microsoft 365 umfasst eine Vielzahl von Features zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="dbbbd-105">Hier ist eine Schnellstartanleitung, die Sie als Prüfliste verwenden können, um sicherzustellen, dass Ihre Threat Protection-Funktionen für Ihre Organisation eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="dbbbd-106">Wenn Sie neue Features für den Schutz vor Bedrohungen in Office 365 haben oder einfach nicht wissen, wo Sie beginnen sollten, verwenden Sie die folgende Anleitung als Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbbbd-107">Die **anfänglichen empfohlenen Einstellungen sind für jede Art von Richtlinie enthalten; viele Optionen sind jedoch verfügbar, und Sie können Ihre Einstellungen an die Anforderungen Ihrer Organisation anpassen**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="dbbbd-108">Lassen Sie etwa 30 Minuten zu, bis Ihre Richtlinien oder Änderungen sich über Ihr Rechenzentrum durchsetzen.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="dbbbd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbbbd-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="dbbbd-110">Abonnements</span><span class="sxs-lookup"><span data-stu-id="dbbbd-110">Subscriptions</span></span>

<span data-ttu-id="dbbbd-111">Die Features für den Bedrohungsschutz sind in allen Microsoft 365-Abonnements enthalten; Einige Abonnements enthalten jedoch erweiterte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="dbbbd-112">In der folgenden Tabelle sind die in diesem Artikel enthaltenen Schutzfeatures zusammen mit den Mindestanforderungen für Abonnements aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|||
|---|---|
|<span data-ttu-id="dbbbd-113">**Protection-Typ**</span><span class="sxs-lookup"><span data-stu-id="dbbbd-113">**Protection type**</span></span>|<span data-ttu-id="dbbbd-114">**Abonnementanforderung**</span><span class="sxs-lookup"><span data-stu-id="dbbbd-114">**Subscription requirement**</span></span>|
|<span data-ttu-id="dbbbd-115">Schutz vor Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="dbbbd-115">Anti-malware protection</span></span>|<span data-ttu-id="dbbbd-116">[Exchange Online Schutz](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EoP)</span><span class="sxs-lookup"><span data-stu-id="dbbbd-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="dbbbd-117">Schutz vor bösartigen URLs und Dateien in e-Mail-und Office-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="dbbbd-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="dbbbd-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="dbbbd-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="dbbbd-119">Antiphishingschutz</span><span class="sxs-lookup"><span data-stu-id="dbbbd-119">Anti-phishing protection</span></span>|[<span data-ttu-id="dbbbd-120">EOP</span><span class="sxs-lookup"><span data-stu-id="dbbbd-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="dbbbd-121">Erweiterter Schutz gegen Phishing</span><span class="sxs-lookup"><span data-stu-id="dbbbd-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="dbbbd-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="dbbbd-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="dbbbd-123">Antispamschutz</span><span class="sxs-lookup"><span data-stu-id="dbbbd-123">Anti-spam protection</span></span>|[<span data-ttu-id="dbbbd-124">EOP</span><span class="sxs-lookup"><span data-stu-id="dbbbd-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="dbbbd-125">Automatische Bereinigung ohne Stunden (für e-Mail)</span><span class="sxs-lookup"><span data-stu-id="dbbbd-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="dbbbd-126">EOP</span><span class="sxs-lookup"><span data-stu-id="dbbbd-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="dbbbd-127">Überwachungsprotokollierung (wird für Berichtszwecke verwendet)</span><span class="sxs-lookup"><span data-stu-id="dbbbd-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="dbbbd-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dbbbd-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="dbbbd-129">Rollen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dbbbd-129">Roles and permissions</span></span>

<span data-ttu-id="dbbbd-130">Sie müssen eine geeignete Rolle zum Konfigurieren von Richtlinien im [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="dbbbd-131">Die folgende Tabelle enthält einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-131">The following table includes some examples:</span></span>

|<span data-ttu-id="dbbbd-132">Rolle oder Rollengruppe</span><span class="sxs-lookup"><span data-stu-id="dbbbd-132">Role or role group</span></span>|<span data-ttu-id="dbbbd-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbbbd-133">Where to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="dbbbd-134">globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="dbbbd-134">global administrator</span></span>|[<span data-ttu-id="dbbbd-135">Informationen zu Microsoft 365-Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="dbbbd-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="dbbbd-136">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="dbbbd-136">Security Administrator</span></span>|[<span data-ttu-id="dbbbd-137">Administratorrollenberechtigungen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dbbbd-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="dbbbd-138">Exchange Online-Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="dbbbd-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="dbbbd-139">Berechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dbbbd-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="dbbbd-140">und</span><span class="sxs-lookup"><span data-stu-id="dbbbd-140">and</span></span><br> [<span data-ttu-id="dbbbd-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbbbd-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

<span data-ttu-id="dbbbd-142">Weitere Informationen finden Sie unter [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="dbbbd-143">Part 1 – Schutz vor Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="dbbbd-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="dbbbd-144">Der [Schutz vor Schadsoftware](anti-malware-protection.md) ist in Abonnements, die [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)enthalten, verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="dbbbd-145">Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **Anti-Malware**" aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="dbbbd-146">Doppelklicken Sie auf die **Standard** Richtlinie, und wählen Sie dann **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="dbbbd-147">Geben Sie die folgenden Einstellungen an:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-147">Specify the following settings:</span></span>

    - <span data-ttu-id="dbbbd-148">Behalten Sie im Abschnitt " **Malware Erkennungs Antwort** " die Standardeinstellung " **Nein**" bei.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="dbbbd-149">Wählen Sie im Abschnitt **Filter für allgemeine Anlagentypen** die Option **ein**aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="dbbbd-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-150">Click **Save**.</span></span>

<span data-ttu-id="dbbbd-151">Weitere Informationen zu Anti-Malware-Richtlinienoptionen finden Sie unter [configure Anti-Malware Policies](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="dbbbd-152">Part 2 – Schutz vor bösartigen URLs und Dateien</span><span class="sxs-lookup"><span data-stu-id="dbbbd-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="dbbbd-153">Time-of-Click-Schutz vor bösartigen URLs und Dateien ist in Abonnements verfügbar, die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) enthalten, und wird über [ATP-sichere Anlagen](atp-safe-attachments.md) und Richtlinien für [ATP-sichere Links](atp-safe-links.md) eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="dbbbd-154">Richtlinien für ATP-sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="dbbbd-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="dbbbd-155">Um ATP- [sichere Anlagen](atp-safe-attachments.md)einzurichten, müssen Sie mindestens eine Richtlinie für ATP-sichere Anlagen definieren.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="dbbbd-156">Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **ATP Safe Attachments**" aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="dbbbd-157">Aktivieren Sie die Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="dbbbd-158">Klicken Sie im Abschnitt **e-Mail-Anlagen schützen** auf das Pluszeichen ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="dbbbd-159">Geben Sie die folgenden Einstellungen an:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-159">Specify the following settings:</span></span>

   - <span data-ttu-id="dbbbd-160">Geben Sie im Feld **Name den Namen** ein `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="dbbbd-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="dbbbd-161">Wählen Sie im Abschnitt Antwort die Option **blockieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="dbbbd-162">Wählen Sie im Abschnitt **Umleitungs Anlage** die Option **Umleitung aktivieren**aus, und geben Sie dann die e-Mail-Adresse für den Sicherheitsadministrator oder-Operator Ihres Unternehmens an, der erkannte Dateien prüft.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="dbbbd-163">Wählen Sie im Abschnitt **angewendet für** **die Option Empfängerdomäne lautet**aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="dbbbd-164">Wählen Sie dann Ihre Domäne aus, wählen Sie **Hinzufügen**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="dbbbd-165">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-165">Click **Save**.</span></span>

6. <span data-ttu-id="dbbbd-166">(**Empfohlener zusätzlicher Schritt**) Führen Sie als globaler Administrator oder SharePoint Online Administrator das Cmdlet " **[SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** " mit dem Parameter " **DisallowInfectedFileDownload** " für Ihre Microsoft 365-Umgebung auf *true* festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="dbbbd-167">(Dadurch wird verhindert, dass Benutzer Dateien öffnen, verschieben, kopieren oder freigeben, die als bösartig erkannt werden.)</span><span class="sxs-lookup"><span data-stu-id="dbbbd-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="dbbbd-168">Weitere Informationen finden Sie unter [Einrichten Office 365 ATP-Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) und [Aktivieren von Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="dbbbd-169">Richtlinien für ATP-sichere Links</span><span class="sxs-lookup"><span data-stu-id="dbbbd-169">ATP Safe Links policies</span></span>

<span data-ttu-id="dbbbd-170">Um ATP- [sichere Links](atp-safe-links.md)einzurichten, überprüfen und bearbeiten Sie die Standardrichtlinie, und fügen Sie eine Richtlinie für bestimmte Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="dbbbd-171">Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **ATP Safe Links**" aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="dbbbd-172">Doppelklicken Sie auf die **Standard** Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="dbbbd-173">Wählen Sie im Abschnitt **sichere Links in verwenden** die Option **Microsoft 365 Apps für Unternehmen, Office für IOS und Android**aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="dbbbd-174">Klicken Sie im Abschnitt **Richtlinien für bestimmte Empfänger** auf das Pluszeichen ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="dbbbd-175">Geben Sie die folgenden Einstellungen an:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-175">Specify the following settings:</span></span>

   - <span data-ttu-id="dbbbd-176">Geben Sie im Feld **Name** einen Namen ein, beispielsweise `Safe Links` .</span><span class="sxs-lookup"><span data-stu-id="dbbbd-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="dbbbd-177">Wählen Sie im Abschnitt **Aktion auswählen die** Option **ein**aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="dbbbd-178">Wählen Sie diese Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-178">Select these options:</span></span>

     - <span data-ttu-id="dbbbd-179">**Verwenden sicherer Anlagen zum Überprüfen herunterladbarer Inhalte**</span><span class="sxs-lookup"><span data-stu-id="dbbbd-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="dbbbd-180">**Anwenden von sicheren Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet werden**</span><span class="sxs-lookup"><span data-stu-id="dbbbd-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="dbbbd-181">**Nicht zulassen, dass Benutzer über sichere Links auf die ursprüngliche URL klicken**</span><span class="sxs-lookup"><span data-stu-id="dbbbd-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="dbbbd-182">Wählen Sie im Abschnitt **angewendet für** **die Option Empfängerdomäne lautet**aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="dbbbd-183">Wählen Sie dann Ihre Domäne aus, wählen Sie **Hinzufügen**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="dbbbd-184">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-184">Click **Save**.</span></span>

<span data-ttu-id="dbbbd-185">Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für Office 365 ATP-sichere Links](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="dbbbd-186">Part 3 – Schutz gegen Phishing</span><span class="sxs-lookup"><span data-stu-id="dbbbd-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="dbbbd-187">[Anti-Phishing]</span><span class="sxs-lookup"><span data-stu-id="dbbbd-187">[Anti-phishing]</span></span>

<span data-ttu-id="dbbbd-188">[Anti-Phishing-Schutz](anti-phishing-protection.md) ist in Abonnements verfügbar, die [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)enthalten.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="dbbbd-189">Advanced Anti-Phishing Protection ist in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="dbbbd-190">Im folgenden Verfahren wird beschrieben, wie Sie eine ATP-Richtlinie zum Schutz vor Phishing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="dbbbd-191">Die Schritte ähneln dem Konfigurieren einer Anti-Phishing-Richtlinie (ohne ATP).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="dbbbd-192">Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **ATP Anti-Phishing**" aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="dbbbd-193">Klicken Sie auf **Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="dbbbd-194">Klicken Sie im Abschnitt **Identitätswechsel** auf **Bearbeiten**, und geben Sie dann die folgenden Einstellungen an:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="dbbbd-195">Aktivieren Sie auf der Registerkarte **zu schützende Benutzer hinzufügen** den Schutz aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="dbbbd-196">Fügen Sie dann Benutzer wie die Verwaltungsratsmitglieder Ihrer Organisation, ihren CEO, CFO und andere Führungskräfte hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="dbbbd-197">(Sie können eine einzelne e-Mail-Adresse eingeben oder zum Anzeigen einer Liste klicken.)</span><span class="sxs-lookup"><span data-stu-id="dbbbd-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="dbbbd-198">Aktivieren Sie auf der Registerkarte **zu schützende Domänen hinzufügen** **die Domäne automatisch einschließen, die ich besitze**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="dbbbd-199">Wenn Sie benutzerdefinierte Domänen haben, fügen Sie diese ebenfalls hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="dbbbd-200">Wählen Sie auf der Registerkarte **Aktionen** die Option Nachricht für den **imitierten Benutzer** und die **Identität der imitierten Domäne** **isolieren** aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="dbbbd-201">Aktivieren Sie außerdem die Identitätswechsel-Sicherheitstipps.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="dbbbd-202">Stellen Sie sicher, dass auf der Registerkarte **Post Fach Intelligenz** die Option Post Fach Intelligenz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="dbbbd-203">Aktivieren Sie außerdem den Post Fachnachrichten basierten Identitätswechsel Schutz.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="dbbbd-204">Wählen Sie in der Liste **Wenn e-Mail von einer imitierten Benutzer gesendet wird** **die Option Nachricht isolieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="dbbbd-205">Geben Sie auf der Registerkarte **vertrauenswürdige Absender und Domänen hinzufügen** alle vertrauenswürdigen Absender oder Domänen an, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="dbbbd-206">Klicken Sie auf der Registerkarte **Überprüfen der Einstellungen** auf **Speichern**, nachdem Sie die Einstellungen überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="dbbbd-207">Klicken Sie im Abschnitt **Spoof** auf **Bearbeiten**, und geben Sie dann die folgenden Einstellungen an:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="dbbbd-208">Stellen Sie auf der Registerkarte **Spoofing-Filtereinstellungen** sicher, dass der Schutz vor Spoofing aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="dbbbd-209">Wählen Sie auf der Registerkarte **Aktionen** **die Option Nachricht isolieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="dbbbd-210">Klicken Sie auf der Registerkarte **Überprüfen der Einstellungen** auf **Speichern**, nachdem Sie die Einstellungen überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="dbbbd-211">(Wenn Sie keine Änderungen vorgenommen haben, klicken Sie auf **Abbrechen**.)</span><span class="sxs-lookup"><span data-stu-id="dbbbd-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="dbbbd-212">Schließen Sie die Seite Standardrichtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-212">Close the default policy settings page.</span></span>

<span data-ttu-id="dbbbd-213">Weitere Informationen zu den Optionen für Anti-Phishing-Richtlinien finden Sie unter [configure ATP Anti-Phishing Policies](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="dbbbd-214">Part 4 – Schutz vor Spam</span><span class="sxs-lookup"><span data-stu-id="dbbbd-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="dbbbd-215">[Anti-Spam Protection](anti-spam-protection.md) ist in Abonnements mit [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="dbbbd-216">Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **Anti-Spam**" aus.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="dbbbd-217">Aktivieren Sie auf der Registerkarte **Benutzerdefiniert** **benutzerdefinierte Einstellungen** .</span><span class="sxs-lookup"><span data-stu-id="dbbbd-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="dbbbd-218">Erweitern Sie **standardmäßige Spamfilter Richtlinie**, klicken Sie auf **Richtlinie bearbeiten**, und geben Sie dann die folgenden Einstellungen an:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="dbbbd-219">Legen Sie im Abschnitt **Spam-und Massenaktionen** den Schwellenwert auf den Wert 5 oder 6 fest.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="dbbbd-220">Im Abschnitt **Zulassungslisten können** Sie die zulässigen Absender und Domänen überprüfen (und gegebenenfalls Bearbeiten).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="dbbbd-221">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-221">Click **Save**.</span></span>

<span data-ttu-id="dbbbd-222">Weitere Informationen zu den Antispam-Richtlinienoptionen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="dbbbd-223">Part 5-zusätzliche Einstellungen für configure</span><span class="sxs-lookup"><span data-stu-id="dbbbd-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="dbbbd-224">Zusätzlich zum Konfigurieren von Schutz vor Schadsoftware, böswilligen URLs und Dateien, Phishing und Spam empfehlen wir Ihnen, die Einstellungen für die automatische Bereinigung und die Überwachungsprotokollierung für Null Stunden zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="dbbbd-225">Automatische Bereinigung ohne Stunden für e-Mail</span><span class="sxs-lookup"><span data-stu-id="dbbbd-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="dbbbd-226">In Abonnements mit [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)ist die [Automatische Bereinigung von Null Stunden](zero-hour-auto-purge.md) (zap) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="dbbbd-227">Dieser Schutz ist standardmäßig aktiviert. die folgenden Bedingungen müssen jedoch erfüllt sein, damit der Schutz wirksam ist:</span><span class="sxs-lookup"><span data-stu-id="dbbbd-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="dbbbd-228">Spam Aktionen sind so konfiguriert, dass die **Nachricht in den Junk-e-Mail-Ordner** in [Anti-Spam-Richtlinien](anti-spam-protection.md)verschiebt wird.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="dbbbd-229">Benutzer haben Ihre Standard [Einstellungen für Junk-e-Mails](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)beibehalten und den Junk-e-Mail-Schutz nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="dbbbd-230">Weitere Informationen finden Sie unter [Zero-Hour Auto Purge – Schutz vor Spam und Schadsoftware](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="dbbbd-231">Überwachungsprotokollierung für die Berichterstellung und Untersuchung</span><span class="sxs-lookup"><span data-stu-id="dbbbd-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="dbbbd-232">Die Überwachungsprotokollierung steht in Abonnements zur Verfügung, die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)umfassen.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="dbbbd-233">Um Daten in Threat Protection-Berichten wie dem [Sicherheits Dashboard](security-dashboard.md), [e-Mail-Sicherheitsberichten](view-email-security-reports.md)und dem [Explorer](threat-explorer.md)anzuzeigen, muss die Überwachungsprotokollierung für Ihre Organisation aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="dbbbd-234">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbd-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="dbbbd-235">Aufgaben nach dem Setup</span><span class="sxs-lookup"><span data-stu-id="dbbbd-235">Post-setup tasks</span></span>

<span data-ttu-id="dbbbd-236">Nachdem Sie die Features für den Schutz vor Bedrohungen konfiguriert haben, müssen Sie die Funktionsweise dieser Features überwachen, Ihre Richtlinien nach Bedarf überprüfen und überarbeiten sowie auf neue Features und dienstupdates achten.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|||
|---|---|
|<span data-ttu-id="dbbbd-237">**Nächste Schritte**</span><span class="sxs-lookup"><span data-stu-id="dbbbd-237">**What to do**</span></span>|<span data-ttu-id="dbbbd-238">**Ressourcen mit mehr Informationen**</span><span class="sxs-lookup"><span data-stu-id="dbbbd-238">**Resources to learn more**</span></span>|
|<span data-ttu-id="dbbbd-239">Erfahren Sie, wie die Features für den Schutz von Bedrohungen für Ihre Organisation durch Anzeigen von Berichten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="dbbbd-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="dbbbd-240">Sicherheits Dashboard</span><span class="sxs-lookup"><span data-stu-id="dbbbd-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="dbbbd-241">E-Mail-Sicherheitsberichte</span><span class="sxs-lookup"><span data-stu-id="dbbbd-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="dbbbd-242">Reportagen für Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="dbbbd-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="dbbbd-243">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="dbbbd-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="dbbbd-244">Regelmäßige Überprüfung und Überarbeitung ihrer Threat Protection-Richtlinien nach Bedarf</span><span class="sxs-lookup"><span data-stu-id="dbbbd-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="dbbbd-245">Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="dbbbd-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="dbbbd-246">Intelligente Berichte und Einblicke</span><span class="sxs-lookup"><span data-stu-id="dbbbd-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="dbbbd-247">Microsoft 365 Threat Investigation and Response Features</span><span class="sxs-lookup"><span data-stu-id="dbbbd-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="dbbbd-248">Überwachen neuer Features und dienstupdates</span><span class="sxs-lookup"><span data-stu-id="dbbbd-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="dbbbd-249">Standard mäßige und gezielte Veröffentlichungsoptionen</span><span class="sxs-lookup"><span data-stu-id="dbbbd-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="dbbbd-250">Nachrichtencenter</span><span class="sxs-lookup"><span data-stu-id="dbbbd-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="dbbbd-251">Microsoft 365-Roadmap</span><span class="sxs-lookup"><span data-stu-id="dbbbd-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="dbbbd-252">Dienstbeschreibungen</span><span class="sxs-lookup"><span data-stu-id="dbbbd-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
