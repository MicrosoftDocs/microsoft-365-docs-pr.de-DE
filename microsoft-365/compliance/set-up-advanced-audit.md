---
title: Einrichten der erweiterten Überwachung in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Sie die erweiterte Überwachung einrichten, damit Sie forensische Untersuchungen durchführen können, wenn Benutzerkonten kompromittiert sind, oder um andere sicherheitsrelevante Vorfälle zu untersuchen.
ms.openlocfilehash: 825dadee5260a263d005eb3a37f280381f9425a2
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339226"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="29b25-103">Einrichten der erweiterten Überwachung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29b25-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="29b25-104">Wenn Ihre Organisation über eine Abonnement- und Endbenutzerlizenzierung verfügt, die die erweiterte Überwachung unterstützt, führen Sie die folgenden Schritte aus, um die zusätzlichen Funktionen in der erweiterten Überwachung einzurichten und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="29b25-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![Workflow zum Einrichten der Erweiterten Überwachung](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a><span data-ttu-id="29b25-106">Schritt 1: Einrichten der erweiterten Überwachung für Benutzer</span><span class="sxs-lookup"><span data-stu-id="29b25-106">Step 1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="29b25-107">Die Funktionen der Erweiterten Überwachung, wie z.B. die Möglichkeit wichtige Ereignisse, wie z.B. MailItemsAccessed und das Send-Ereignis, zu protokollieren, erfordern eine geeignete E5-Lizenz, die den Benutzern zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="29b25-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="29b25-108">Darüber hinaus muss die Erweiterte Überwachungs-App/ der Serviceplan für diese Benutzer aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="29b25-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="29b25-109">Um zu bestätigen, dass die Erweiterte Überwachungs-App an Benutzer zugewiesen ist, führen Sie für jeden Benutzer die folgenden Schritte durch:</span><span class="sxs-lookup"><span data-stu-id="29b25-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="29b25-110">Navigieren Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/Adminportal) zu **Benutzer** > **Aktive Benutzer**, und wählen Sie einen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="29b25-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="29b25-111">Klicken Sie auf der Benutzereigenschaften-Flyoutseite auf **Lizenzen und Apps**.</span><span class="sxs-lookup"><span data-stu-id="29b25-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="29b25-112">Überprüfen Sie im Abschnitt **"Lizenzen",** ob dem Benutzer eine E5-Lizenz oder eine entsprechende Add-On-Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="29b25-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="29b25-113">Eine Liste der Lizenzen, die die erweiterte Überwachung unterstützen, finden Sie unter ["Erweiterte Überwachung – Lizenzierungsanforderungen".](auditing-solutions-overview.md#advanced-audit-1)</span><span class="sxs-lookup"><span data-stu-id="29b25-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="29b25-114">Erweitern Sie den Abschnitt **Apps** und bestätigen Sie das Kontrollkästchen **Microsoft 365 – Erweiterte Überwachung** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="29b25-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="29b25-115">Wenn das Kontrollkästchen nicht aktiviert ist, aktivieren Sie es, und klicken Sie dann auf **"Änderungen speichern".**</span><span class="sxs-lookup"><span data-stu-id="29b25-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="29b25-116">Die Protokollierung von Überwachungsdatensätzen für MailItemsAccessed und Send beginnt innerhalb von 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="29b25-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="29b25-117">Sie müssen Schritt 3 ausführen, um mit der Protokollierung von zwei weiteren wichtigen Ereignissen der erweiterten Überwachung zu beginnen: SearchQueryInitiatedExchange und SearchQueryInitiatedSharePoint.</span><span class="sxs-lookup"><span data-stu-id="29b25-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="29b25-118">Für Organisationen, die Gruppen von Benutzern mithilfe einer gruppenbasierten Lizenzierung Lizenzen zuweisen, müssen Sie die Lizenzzuweisung für Microsoft 365 Advanced Auditing für die Gruppe deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="29b25-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="29b25-119">Nachdem Sie die Änderungen gespeichert haben, stellen Sie sicher, dass Microsoft 365 Erweiterte Überwachung für die Gruppe deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="29b25-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="29b25-120">Aktivieren Sie dann die Lizenzierungszuordnung für die Gruppe wieder.</span><span class="sxs-lookup"><span data-stu-id="29b25-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="29b25-121">Lesen Sie [Zuweisen von Lizenzen zu Benutzern mithilfe der Gruppenmitgliedschaft in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign) für Anweisungen zur gruppenbasierten Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="29b25-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="29b25-122">Wenn Sie die Postfachaktionen angepasst haben, die in Benutzerpostfächern oder freigegebenen Postfächern angemeldet sind, werden alle neuen wichtigen Ereignisse, die von Microsoft veröffentlicht werden, nicht automatisch für diese Postfächer überwacht.</span><span class="sxs-lookup"><span data-stu-id="29b25-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="29b25-123">Weitere Informationen über das Ändern von Postfachaktionen, die für jeden Anmeldetyp überwacht werden, finden Sie unter „Standardmäßig überwachte Postfachaktionen ändern oder wiederherstellen“ in [Verwalten der Postfächern](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span><span class="sxs-lookup"><span data-stu-id="29b25-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="29b25-124">Schritt 2: Aktivieren wichtiger Ereignisse</span><span class="sxs-lookup"><span data-stu-id="29b25-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="29b25-125">Sie müssen zwei wichtige Ereignisse (SearchQueryInitiatedExchange und SearchQueryInitiatedSharePoint) aktivieren, um protokolliert zu werden, wenn Benutzer Suchvorgänge in Exchange Online und SharePoint Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="29b25-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="29b25-126">Um die Überwachung dieser beiden Ereignisse für Benutzer zu ermöglichen, führen Sie den folgenden Befehl (für jeden Benutzer) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)aus:</span><span class="sxs-lookup"><span data-stu-id="29b25-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="29b25-127">In einer Multi-Geo-Umgebung müssen Sie den vorherigen Befehl **"Postfach festlegen"** in der Gesamtstruktur ausführen, in der sich das Postfach des Benutzers befindet.</span><span class="sxs-lookup"><span data-stu-id="29b25-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="29b25-128">Führen Sie den folgenden Befehl aus, um den Postfachspeicherort des Benutzers zu identifizieren:</span><span class="sxs-lookup"><span data-stu-id="29b25-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="29b25-129">Wenn der Befehl zum Aktivieren der Überwachung von Suchabfragen zuvor in einer Gesamtstruktur ausgeführt wurde, die sich von der Gesamtstruktur unterscheidet, in der sich das Postfach des Benutzers befindet, müssen Sie den SearchQueryInitiated-Wert durch Ausführen aus dem Postfach des Benutzers entfernen `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` und ihn dann dem Postfach des Benutzers in der Gesamtstruktur hinzufügen, in der sich das Postfach des Benutzers befindet.</span><span class="sxs-lookup"><span data-stu-id="29b25-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="29b25-130">Schritt 3: Einrichten von Aufbewahrungsrichtlinien für die Überwachung</span><span class="sxs-lookup"><span data-stu-id="29b25-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="29b25-131">Zusätzlich zur Standardrichtlinie, die Exchange-, SharePoint- und Azure AD-Überwachungsprotokolle ein Jahr lang aufbewahrt, können Sie weitere Richtlinien zur Aufbewahrung von Überwachungsprotokollen erstellen, um die Anforderungen der Sicherheits-, IT- und Compliance-Teams Ihres Unternehmens zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="29b25-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="29b25-132">Weitere Informationen finden Sie unter [Verwalten der Aufbewahrungsrichtlinien für Überwachungsprotokolle](audit-log-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="29b25-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="29b25-133">Schritt 4: Suchen nach wichtigen Ereignissen</span><span class="sxs-lookup"><span data-stu-id="29b25-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="29b25-134">Nachdem Sie die erweiterte Überwachung für Ihre Organisation eingerichtet haben, können Sie bei forensischen Untersuchungen nach wichtigen Ereignissen und anderen Aktivitäten suchen.</span><span class="sxs-lookup"><span data-stu-id="29b25-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="29b25-135">Nach Abschluss von Schritt 1 und Schritt 2 können Sie das Überwachungsprotokoll nach wichtigen Ereignissen und anderen Aktivitäten während forensischer Untersuchungen kompromittierte Konten und anderer Arten von Sicherheits- oder Complianceuntersuchungen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="29b25-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="29b25-136">Weitere Informationen zum Durchführen einer forensischen Untersuchung kompromittierte Benutzerkonten mithilfe des wichtigen MailItemsAccessed-Ereignisses finden Sie unter Verwenden der [erweiterten Überwachung, um kompromittierte Konten zu untersuchen.](mailitemsaccessed-forensics-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="29b25-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
