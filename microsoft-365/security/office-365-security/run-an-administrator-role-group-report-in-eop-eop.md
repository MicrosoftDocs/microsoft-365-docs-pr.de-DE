---
title: Ausführen eines Administrator-Rollengruppenberichts in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie einen Administrator-Rollengruppenbericht in eigenständigem Exchange Online Protection (EOP) ausführen. Dieser Bericht protokolliert, wenn ein Administrator Mitglieder zu Administrator-Rollengruppen hinzufügt oder aus diesen entfernt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 507fbe6fb6c99677cf91b6eb824bf110f1c826f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166627"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="076df-104">Ausführen eines Administrator-Rollengruppenberichts in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="076df-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="076df-105">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="076df-105">**Applies to**</span></span>
-  [<span data-ttu-id="076df-106">Exchange Online Protection als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="076df-106">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="076df-107">Wenn ein Administrator in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer Mitglieder zu administrativen Rollengruppen hinzufügt oder aus diesen entfernt, protokolliert der Dienst jedes Vorkommen.</span><span class="sxs-lookup"><span data-stu-id="076df-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="076df-108">Weitere Informationen zu Rollengruppen in eigenständigem EOP finden Sie unter ["Berechtigungen" in EOP als eigenständige Lösung.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="076df-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="076df-109">Wenn Sie einen Administrator-Rollengruppenbericht in der Exchange Admin Center (EAC) ausführen, werden Einträge als Suchergebnisse angezeigt und enthalten die betroffenen Rollengruppen, die Benutzer, die die Rollengruppenmitgliedschaft geändert haben und wann und welche Mitgliedschaftsaktualisierungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="076df-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="076df-110">Mithilfe dieses Berichts können Sie Änderungen an den Administratorberechtigungen überwachen, die den Benutzern in der Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="076df-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="076df-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="076df-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="076df-112">Informationen zum Öffnen des Exchange Admin Centers finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="076df-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="076df-113">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="076df-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="076df-114">Insbesondere benötigen Sie die Rolle **"Überwachungsprotokolle"** oder **"Nur-Anzeige-Überwachungsprotokolle",** die standardmäßig den Rollengruppen "Organisationsverwaltung", "Verwaltung der Richtlinienkonformität" und "Sicherheitsadministrator" zugewiesen sind.  </span><span class="sxs-lookup"><span data-stu-id="076df-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="076df-115">Weitere Informationen finden Sie unter "Berechtigungen [in EOP als eigenständige](feature-permissions-in-eop.md) Lösung", und ändern Sie mithilfe der EAC die Liste der Mitglieder in [Rollengruppen.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="076df-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="076df-116">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="076df-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="076df-117">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="076df-117">Having problems?</span></span> <span data-ttu-id="076df-118">Bitten Sie im [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)-Forum um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="076df-118">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="076df-119">Ausführen eines Administrator-Rollengruppenberichts mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="076df-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="076df-120">Führen Sie den Administrator-Rollengruppenbericht aus, um die Änderungen an Verwaltungsrollegruppen innerhalb eines bestimmten Zeitrahmens zu finden.</span><span class="sxs-lookup"><span data-stu-id="076df-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="076df-121">Wechseln Sie in der EAC zu **Überwachung** der Verwaltung der Richtlinienverwaltung, und wählen Sie dann \>  **"Administrator-Rollengruppenbericht ausführen" aus.**</span><span class="sxs-lookup"><span data-stu-id="076df-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="076df-122">Konfigurieren Sie **auf der Seite "Nach Änderungen an Administrator-Rollengruppen suchen",** die geöffnet wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="076df-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="076df-123">**Startdatum** und **Enddatum**: Geben Sie einen Datumsbereich ein.</span><span class="sxs-lookup"><span data-stu-id="076df-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="076df-124">Standardmäßig sucht der Bericht nach Änderungen, die innerhalb der letzten zwei Wochen an Administratorrollengruppen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="076df-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="076df-125">**Rollengruppen auswählen:** Standardmäßig werden alle Rollengruppen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="076df-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="076df-126">Klicken Sie auf "Rollengruppen auswählen", um die Ergebnisse nach **bestimmten Rollengruppen zu filtern.**</span><span class="sxs-lookup"><span data-stu-id="076df-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="076df-127">Wählen Sie im angezeigten Dialogfeld eine Rollengruppe aus, und klicken **Sie auf "Add->"**.</span><span class="sxs-lookup"><span data-stu-id="076df-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="076df-128">Wiederholen Sie diesen Schritt so oft wie nötig, und klicken Sie dann auf **"OK",** wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="076df-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="076df-129">Wenn Sie fertig sind, klicken Sie auf **"Suchen".**</span><span class="sxs-lookup"><span data-stu-id="076df-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="076df-p108">Wenn Änderungen gefunden werden, die mit den angegebenen Kriterien übereinstimmen, werden sie im Ergebnisbereich angezeigt. Klicken Sie auf eine Rollengruppe in den Suchergebnissen, um die Änderungen im Detailbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="076df-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="076df-132">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="076df-132">How do you know this worked?</span></span>

<span data-ttu-id="076df-p109">Wenn Sie einen Administrator-Rollengruppenbericht erfolgreich ausgeführt haben, werden die Rollengruppen, die innerhalb des Datumsbereichs geändert wurden, im Suchergebnisbereich angezeigt. Wenn keine Ergebnisse angezeigt werden, wurden im angegebenen Datumsbereich keine Änderungen an Rollengruppen vorgenommen. Wenn Sie davon ausgehen, dass Ergebnisse angezeigt werden sollten, ändern Sie den Datumsbereich, und führen Sie den Bericht erneut aus.</span><span class="sxs-lookup"><span data-stu-id="076df-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="076df-136">Überwachen von Änderungen an der Rollengruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="076df-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="076df-p110">Wenn einer Rollengruppe Mitglieder hinzugefügt oder daraus entfernt werden, wird in den im Detailbereich angezeigten Suchergebnissen angegeben, dass die Rollengruppenmitgliedschaft aktualisiert wurde, und die aktuellen Mitglieder werden aufgelistet. In den Ergebnissen ist nicht angegeben, welcher Benutzer hinzugefügt oder entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="076df-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="076df-p111">Wenn Sie ermitteln möchten, ob ein Benutzer hinzugefügt oder entfernt wurde, müssen zwei separate Einträge im Bericht verglichen werden. Sehen Sie sich beispielsweise die folgenden Protokolleinträge für die Rollengruppe **HelpDesk** an:</span><span class="sxs-lookup"><span data-stu-id="076df-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="076df-141">27.01.2018 16:43</span><span class="sxs-lookup"><span data-stu-id="076df-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="076df-142">Administrator</span><span class="sxs-lookup"><span data-stu-id="076df-142">Administrator</span></span> <br> <span data-ttu-id="076df-143">Aktualisierte Mitglieder: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="076df-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="076df-144">06.02.2018 10:09 Uhr</span><span class="sxs-lookup"><span data-stu-id="076df-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="076df-145">Administrator</span><span class="sxs-lookup"><span data-stu-id="076df-145">Administrator</span></span> <br> <span data-ttu-id="076df-146">Aktualisierte Mitglieder: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="076df-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="076df-147">19.02.2018 14:12</span><span class="sxs-lookup"><span data-stu-id="076df-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="076df-148">Administrator</span><span class="sxs-lookup"><span data-stu-id="076df-148">Administrator</span></span> <br> <span data-ttu-id="076df-149">Aktualisierte Mitglieder: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="076df-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="076df-150">In diesem Beispiel wurden mit dem Administratorbenutzerkonto folgende Änderungen vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="076df-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="076df-151">Am 06.02.2018 wurde der Benutzer tonip hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="076df-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="076df-152">Am 19.02.2018 wurde der Benutzer "pilarp" entfernt.</span><span class="sxs-lookup"><span data-stu-id="076df-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="076df-153">Verwenden der eigenständigen Exchange Online PowerShell zum Suchen nach Überwachungsprotokolleinträgen</span><span class="sxs-lookup"><span data-stu-id="076df-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="076df-154">Sie können Exchange Online PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen, die den von Ihnen angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="076df-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="076df-155">Eine Liste der Suchkriterien finden Sie unter [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span><span class="sxs-lookup"><span data-stu-id="076df-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="076df-156">Dieses Verfahren verwendet das **Cmdlet "Search-AdminAuditLog"** und zeigt Suchergebnisse in Exchange Online PowerShell an.</span><span class="sxs-lookup"><span data-stu-id="076df-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="076df-157">Dieses Cmdlet kann verwendet werden, wenn eine Ergebnismenge zurückgegeben werden muss, die die im Cmdlet **New-AdminAuditLogSearch** oder in den Überwachungsberichten der Exchange-Verwaltungskonsole definierten Grenzwerte überschreitet.</span><span class="sxs-lookup"><span data-stu-id="076df-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="076df-158">Verwenden Sie die folgende Syntax, um das Überwachungsprotokoll anhand angegebener Kriterien zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="076df-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="076df-159">Das Cmdlet **Search-AdminAuditLog** gibt standardmäßig maximal 1.000 Protokolleinträge zurück.</span><span class="sxs-lookup"><span data-stu-id="076df-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="076df-160">Verwenden Sie _den Parameter "ResultSize",_ um bis zu 250.000 Protokolleinträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="076df-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="076df-161">Oder verwenden Sie den `Unlimited` Wert, um alle Einträge zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="076df-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="076df-162">In diesem Beispiel wird eine Suche nach allen Überwachungsprotokolleinträgen ausgeführt, welche die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="076df-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="076df-163">**Startdatum:** 04.08.2018</span><span class="sxs-lookup"><span data-stu-id="076df-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="076df-164">**Enddatum:** 03.10.2018</span><span class="sxs-lookup"><span data-stu-id="076df-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="076df-165">**Benutzer-IDs:** `davids` `chrisd` , , `kima`</span><span class="sxs-lookup"><span data-stu-id="076df-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="076df-166">**Cmdlets**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="076df-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="076df-167">**Parameter**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="076df-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="076df-p114">In diesem Beispiel werden Änderungen an einem bestimmten Postfach ermittelt. Dies ist bei der Problembehebung nützlich, oder wenn Sie Informationen für eine Untersuchung bereitstellen müssen. Die folgenden Kriterien werden verwendet:</span><span class="sxs-lookup"><span data-stu-id="076df-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="076df-171">**Startdatum:** 01.05.2018</span><span class="sxs-lookup"><span data-stu-id="076df-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="076df-172">**Enddatum:** 03.10.2018</span><span class="sxs-lookup"><span data-stu-id="076df-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="076df-173">**Objekt-ID:** contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="076df-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="076df-174">Wenn ihre Suche viele Protokolleinträge zurück gibt, wird empfohlen, das unter Exchange **Online PowerShell** beschriebene Verfahren zu verwenden, um nach Überwachungsprotokolleinträgen zu suchen und Ergebnisse später in diesem Artikel an einen Empfänger zu senden.</span><span class="sxs-lookup"><span data-stu-id="076df-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="076df-175">Bei dieser Vorgehensweise wird eine XML-Datei als E-Mail-Anlage an die angegebenen Empfänger gesendet, sodass die relevanten Daten einfacher extrahiert werden können.</span><span class="sxs-lookup"><span data-stu-id="076df-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="076df-176">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="076df-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="076df-177">Anzeigen der Details von Überwachungsprotokolleinträgen</span><span class="sxs-lookup"><span data-stu-id="076df-177">View details of audit log entries</span></span>

<span data-ttu-id="076df-178">Das **Cmdlet Search-AdminAuditLog** gibt die in überwachungsprotokollinhalten [beschriebenen Felder zurück.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="076df-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="076df-179">Zwei der zurückgegebenen Felder, **CmdletParameters** und **ModifiedProperties**, enthalten zusätzliche Informationen, die standardmäßig nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="076df-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="076df-180">Führen Sie die folgenden Schritte aus, um die Inhalte der Felder **CmdletParameters** und **ModifiedProperties** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="076df-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="076df-181">Sie können auch das Verfahren in **Exchange Online PowerShell** verwenden, um nach Überwachungsprotokolleinträgen zu suchen und Ergebnisse später in diesem Artikel an einen Empfänger zu senden, um eine XML-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="076df-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="076df-182">In dieser Vorgehensweise werden die folgenden Konzepte verwendet:</span><span class="sxs-lookup"><span data-stu-id="076df-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="076df-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="076df-183">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="076df-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="076df-184">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="076df-185">Legen Sie die Suchkriterien fest, führen Sie das Cmdlet **Search-AdminAuditLog** aus, und speichern Sie die Ergebnisse über den folgenden Befehl in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="076df-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="076df-186">Jeder Überwachungsprotokolleintrag wird als Arrayelement in der Variablen `$Results` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="076df-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="076df-187">Zur Auswahl eines Arrayelements geben Sie den Arrayelementindex an.</span><span class="sxs-lookup"><span data-stu-id="076df-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="076df-188">Arrayelementindizes beginnen für das erste Arrayelement bei 0.</span><span class="sxs-lookup"><span data-stu-id="076df-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="076df-189">Verwenden Sie beispielsweise den folgenden Befehl, um das fünfte Arrayelement (mit dem Index 4) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="076df-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="076df-p119">Der oben stehende Befehl gibt den im Arrayelement 4 gespeicherten Protokolleintrag zurück. Zum Anzeigen der Felder **CmdletParameters** und **ModifiedProperties** für diesen Protokolleintrag verwenden Sie die folgenden Befehle.</span><span class="sxs-lookup"><span data-stu-id="076df-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="076df-192">Um die Inhalte der Felder **CmdletParameters** und **ModifiedParameters** in einem anderen Protokolleintrag anzuzeigen, ändern Sie den Arrayelementindex.</span><span class="sxs-lookup"><span data-stu-id="076df-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
