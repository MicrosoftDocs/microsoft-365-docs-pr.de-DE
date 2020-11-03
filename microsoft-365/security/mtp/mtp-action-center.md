---
title: Aufrufen des Info-Centers zum Anzeigen und Genehmigen der Aufgaben für die automatisierte Untersuchung und Wartung
description: Verwenden Sie das Info-Center, um Details zur automatisierten Untersuchung und ausstehenden Genehmigungsaktionen anzuzeigen.
keywords: Info-Center, Bedrohungsschutz, Untersuchung, Warnung, Ausstehend, automatisiert, Erkennung
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 3ec17204903f3e83f3fbfd126d57d0b9ca5d56f7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843792"
---
# <a name="the-action-center"></a><span data-ttu-id="f5e09-104">Das Info-Center</span><span class="sxs-lookup"><span data-stu-id="f5e09-104">The Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5e09-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f5e09-105">**Applies to:**</span></span>
- <span data-ttu-id="f5e09-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5e09-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f5e09-107">Verwenden Sie das Info-Center, um die Ergebnisse aktueller und früherer Untersuchungen auf den Geräten und in den Postfächern Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5e09-107">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="f5e09-108">Je nach Art der Bedrohung und dem daraus resultierenden Urteil werden [Korrekturaktionen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) automatisch oder nach Genehmigung durch das Sicherheits Betriebsteam Ihrer Organisation durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5e09-108">Depending on the type of threat and resulting verdict, [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="f5e09-109">Alle Wartungsaktionen – unabhängig davon, ob eine Genehmigung aussteht oder diese bereits genehmigt wurden – werden im Info-Center zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="f5e09-109">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

![Info-Center](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="f5e09-111">Eine einzige Oberfläche</span><span class="sxs-lookup"><span data-stu-id="f5e09-111">A "single pane of glass" experience</span></span>

<span data-ttu-id="f5e09-112">Das Info-Center bietet eine einzige Oberfläche für folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="f5e09-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="f5e09-113">Genehmigen ausstehender Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="f5e09-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="f5e09-114">Anzeigen eines Überwachungsprotokolls von bereits genehmigten Wartungsaktionen und</span><span class="sxs-lookup"><span data-stu-id="f5e09-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="f5e09-115">Überprüfen abgeschlossener Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="f5e09-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="f5e09-116">Ihr Sicherheits Betriebsteam kann effektiver und effizienter arbeiten, da das Action Center eine umfassende Ansicht von Microsoft 365 Defender bei der Arbeit bietet.</span><span class="sxs-lookup"><span data-stu-id="f5e09-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft 365 Defender at work.</span></span>

## <a name="go-to-the-action-center"></a><span data-ttu-id="f5e09-117">Aufrufen des Info-Centers</span><span class="sxs-lookup"><span data-stu-id="f5e09-117">Go to the Action center</span></span>

1. <span data-ttu-id="f5e09-118">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="f5e09-118">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="f5e09-119">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="f5e09-119">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="f5e09-120">Im Wartungscenter werden zwei Registerkarten angezeigt: **Ausstehend** und **Verlauf**.</span><span class="sxs-lookup"><span data-stu-id="f5e09-120">In the Action center, you'll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="f5e09-121">Auf der Registerkarte **Ausstehend** werden Untersuchungen aufgeführt, die von einer Person in Ihrem Sicherheitsteam überprüft und genehmigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f5e09-121">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="f5e09-122">Überprüfen Sie alle ausstehenden Elemente, die hier angezeigt werden, und ergreifen Sie entsprechende Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="f5e09-122">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="f5e09-123">Auf der Registerkarte **Verlauf** werden frühere Untersuchungen und Wartungsaktionen aufgeführt, die automatisch ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="f5e09-123">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="f5e09-124">Sie können Daten für den vergangenen Tag, die letzte Woche, den letzten Monat oder die letzten sechs Monate anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5e09-124">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="f5e09-125">Wenn nur bestimmte Spalten angezeigt werden sollen, wählen Sie **Spalten anpassen** aus.</span><span class="sxs-lookup"><span data-stu-id="f5e09-125">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="f5e09-126">![Action Center in Microsoft 365 Defender](../../media/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="f5e09-126">![Action Center in Microsoft 365 Defender](../../media/mtp-action-center.png)</span></span>

5. <span data-ttu-id="f5e09-127">Wählen Sie ein Element in der Liste aus, um weitere Details zu einer Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5e09-127">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="f5e09-128">Die Untersuchungsdetailansicht wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f5e09-128">The investigation details view opens.</span></span><br/>![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

    - <span data-ttu-id="f5e09-130">Wenn sich die Untersuchung auf e-Mail-Inhalte bezieht (beispielsweise die Entität ist ein Postfach), werden Ermittlungs Details im Security & Compliance Center ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f5e09-130">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="f5e09-131">Wenn es bei der Untersuchung um ein Gerät geht, werden die Untersuchungsdetails im Security Center ([https://security.microsoft.com](https://security.microsoft.com)) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f5e09-131">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

> [!TIP]
> <span data-ttu-id="f5e09-132">Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft 365 Defender etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen!</span><span class="sxs-lookup"><span data-stu-id="f5e09-132">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="f5e09-133">Weitere Informationen finden Sie unter [How to Report false positives/negatives in Automated Investigation and Response (Air) Capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="f5e09-133">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="available-actions"></a><span data-ttu-id="f5e09-134">Verfügbare Aktionen</span><span class="sxs-lookup"><span data-stu-id="f5e09-134">Available actions</span></span>

<span data-ttu-id="f5e09-135">Wenn Korrekturaktionen ausgeführt werden, werden Sie auf der Registerkarte Verlauf im Wartungscenter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5e09-135">As remediation actions are taken, they're listed on the History tab in the Action center.</span></span> <span data-ttu-id="f5e09-136">Solche Aktionen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f5e09-136">Such actions include the following:</span></span>

- <span data-ttu-id="f5e09-137">Ermittlungs Paket sammeln</span><span class="sxs-lookup"><span data-stu-id="f5e09-137">Collect investigation package</span></span> 
- <span data-ttu-id="f5e09-138">Gerät isolieren (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="f5e09-138">Isolate device (this action can be undone)</span></span> 
- <span data-ttu-id="f5e09-139">Extern-Computer</span><span class="sxs-lookup"><span data-stu-id="f5e09-139">Offboard machine</span></span> 
- <span data-ttu-id="f5e09-140">Freigabecode Ausführung</span><span class="sxs-lookup"><span data-stu-id="f5e09-140">Release code execution</span></span> 
- <span data-ttu-id="f5e09-141">Freigabe aus Quarantäne</span><span class="sxs-lookup"><span data-stu-id="f5e09-141">Release from quarantine</span></span> 
- <span data-ttu-id="f5e09-142">Anforderungs Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5e09-142">Request sample</span></span> 
- <span data-ttu-id="f5e09-143">Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="f5e09-143">Restrict code execution (this action can be undone)</span></span> 
- <span data-ttu-id="f5e09-144">Ausführen des Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="f5e09-144">Run antivirus scan</span></span> 
- <span data-ttu-id="f5e09-145">Beenden und isolieren</span><span class="sxs-lookup"><span data-stu-id="f5e09-145">Stop and quarantine</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="f5e09-146">Erforderliche Berechtigungen für Info-Center-Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f5e09-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="f5e09-147">Um ausstehende Aktionen im Info-Center zu genehmigen oder abzulehnen, müssen Sie über die Berechtigungen verfügen, die in der folgenden Tabelle aufgeführt sind:</span><span class="sxs-lookup"><span data-stu-id="f5e09-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="f5e09-148">Wartungsaktion</span><span class="sxs-lookup"><span data-stu-id="f5e09-148">Remediation action</span></span> |<span data-ttu-id="f5e09-149">Erforderliche Rollen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f5e09-149">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="f5e09-150">Microsoft Defender für die Endpunkt Sanierung (Geräte)</span><span class="sxs-lookup"><span data-stu-id="f5e09-150">Microsoft Defender for Endpoint remediation (devices)</span></span> |<span data-ttu-id="f5e09-151">Sicherheitsadministratorrolle in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com))</span><span class="sxs-lookup"><span data-stu-id="f5e09-151">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="f5e09-152">--- oder ---</span><span class="sxs-lookup"><span data-stu-id="f5e09-152">--- or ---</span></span><br/><span data-ttu-id="f5e09-153">In Microsoft Defender für Endpoint zugewiesene Rolle "aktive Behebungsaktionen"</span><span class="sxs-lookup"><span data-stu-id="f5e09-153">Active remediation actions role assigned in Microsoft Defender for Endpoint</span></span> <br/> <br/> <span data-ttu-id="f5e09-154">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="f5e09-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="f5e09-155">- [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="f5e09-155">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="f5e09-156">- [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="f5e09-156">- [Create and manage roles for role-based access control (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="f5e09-157">Microsoft Defender für Office 365 Sanierung (Office-Inhalte und e-Mail)</span><span class="sxs-lookup"><span data-stu-id="f5e09-157">Microsoft Defender for Office 365 remediation (Office content and email)</span></span>  |<span data-ttu-id="f5e09-158">Sicherheitsadministratorrolle in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com))</span><span class="sxs-lookup"><span data-stu-id="f5e09-158">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="f5e09-159">--- und ---</span><span class="sxs-lookup"><span data-stu-id="f5e09-159">--- and ---</span></span> <br/><span data-ttu-id="f5e09-160">Dem Security & Compliance Center zugewiesene Rolle "Search and Purge" ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="f5e09-160">Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="f5e09-161">**Wichtig** : Wenn Sie die Sicherheits Administrator Rolle nur im Security & Compliance Center zugewiesen haben, können Sie nicht auf das Action Center oder die Microsoft 365 Defender-Funktionen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f5e09-161">**IMPORTANT** : If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="f5e09-162">Ihnen muss die Sicherheitsadministratorrolle in Azure Active Directory oder im Microsoft 365 Admin Center zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="f5e09-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="f5e09-163">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="f5e09-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="f5e09-164">- [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="f5e09-164">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="f5e09-165">- [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="f5e09-165">- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="f5e09-166">Benutzer, denen in Azure Active Directory die Rolle Globaler Administrator zugewiesen ist, können alle ausstehenden Aktionen im Info-Center genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="f5e09-166">Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="f5e09-167">Als bewährte Methode sollte Ihre Organisation jedoch die Anzahl der Personen einschränken, denen die Rolle des globalen Administrators zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f5e09-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="f5e09-168">Es wird empfohlen, die oben aufgeführten Rollen Sicherheitsadministrator, Aktive Wartungsaktionen und Suchen und Löschen für Info-Center-Berechtigungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e09-168">We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5e09-169">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5e09-169">Next steps</span></span> 

- [<span data-ttu-id="f5e09-170">Genehmigen oder Ablehnen ausstehender Aktionen im Anschluss an eine automatisierte Untersuchung</span><span class="sxs-lookup"><span data-stu-id="f5e09-170">Approve or reject pending actions following an automated investigation</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="f5e09-171">Anzeigen der Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="f5e09-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)

