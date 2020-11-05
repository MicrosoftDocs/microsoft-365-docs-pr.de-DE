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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie einen Administratorrollengruppen Bericht in eigenständigen Exchange Online Schutz (EoP) ausführen. Dieser Bericht protokolliert, wenn ein Administrator Mitglieder aus Administratorrollengruppen hinzugefügt oder entfernt.
ms.openlocfilehash: 95b216b41d1c83ba36bcc00e1f571e08c8bd1f73
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920620"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="6cc8d-104">Ausführen eines Administrator-Rollengruppenberichts in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="6cc8d-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6cc8d-105">In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer, wenn ein Administrator Mitglieder aus administrativen Rollengruppen hinzufügt oder diese entfernt, protokolliert der Dienst jedes Vorkommen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="6cc8d-106">Weitere Informationen zu Rollengruppen in eigenständigen EoP finden Sie unter [Permissions in Standalone EoP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="6cc8d-107">Wenn Sie einen Administratorrollengruppen Bericht im Exchange Admin Center (EAC) ausführen, werden Einträge als Suchergebnisse angezeigt und umfassen die betroffenen Rollengruppen, die die Rollengruppenmitgliedschaft geändert haben und wann und welche Mitgliedschafts Aktualisierungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="6cc8d-108">Mithilfe dieses Berichts können Sie Änderungen an den Administratorberechtigungen überwachen, die den Benutzern in der Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6cc8d-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="6cc8d-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6cc8d-110">Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="6cc8d-111">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="6cc8d-112">Insbesondere benötigen Sie die Überwachungsprotokolle oder View-Only Überwachungsprotokoll Rolle, die standardmäßig den Rollengruppen ComplianceManagement, Mitglied (globale Administratoren) und SecurityAdministrator zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="6cc8d-113">Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="6cc8d-114">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Artikel gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-114">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="6cc8d-115">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="6cc8d-115">Having problems?</span></span> <span data-ttu-id="6cc8d-116">Bitten Sie im [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)-Forum um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="6cc8d-117">Ausführen eines Administrator-Rollengruppenberichts mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="6cc8d-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="6cc8d-118">Führen Sie den Bericht Administratorrollengruppe aus, um die Änderungen an Verwaltungsrollengruppen innerhalb eines bestimmten Zeitrahmens zu finden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-118">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="6cc8d-119">Wechseln Sie in der Exchange- **Verwaltungskonsole zu Compliance Management** \> **Auditing** , und wählen Sie dann **Administratorrollengruppen Bericht ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-119">In the EAC, go to **Compliance management** \> **Auditing** , and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="6cc8d-120">Konfigurieren Sie auf der Seite nach **Änderungen an Administratorrollengruppen suchen** , die geöffnet wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="6cc8d-121">**Start Datum** und **Enddatum** : Geben Sie einen Datumsbereich ein.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-121">**Start date** and **End date** : Enter a date range.</span></span> <span data-ttu-id="6cc8d-122">Standardmäßig sucht der Bericht nach Änderungen, die innerhalb der letzten zwei Wochen an Administratorrollengruppen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="6cc8d-123">**Auswählen von Rollengruppen** : Standardmäßig werden alle Rollengruppen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-123">**Select role groups** : By default, all role groups are searched.</span></span> <span data-ttu-id="6cc8d-124">Klicken Sie auf **Rollengruppen auswählen** , um die Ergebnisse nach bestimmten Rollengruppen zu filtern.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="6cc8d-125">Wählen Sie im daraufhin angezeigten Dialogfeld eine Rollengruppe aus, und klicken Sie auf **Add->**.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="6cc8d-126">Wiederholen Sie diesen Schritt so oft wie nötig, und klicken Sie dann auf **OK** , wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="6cc8d-127">Wenn Sie fertig sind, klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="6cc8d-p108">Wenn Änderungen gefunden werden, die mit den angegebenen Kriterien übereinstimmen, werden sie im Ergebnisbereich angezeigt. Klicken Sie auf eine Rollengruppe in den Suchergebnissen, um die Änderungen im Detailbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6cc8d-130">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="6cc8d-130">How do you know this worked?</span></span>

<span data-ttu-id="6cc8d-p109">Wenn Sie einen Administrator-Rollengruppenbericht erfolgreich ausgeführt haben, werden die Rollengruppen, die innerhalb des Datumsbereichs geändert wurden, im Suchergebnisbereich angezeigt. Wenn keine Ergebnisse angezeigt werden, wurden im angegebenen Datumsbereich keine Änderungen an Rollengruppen vorgenommen. Wenn Sie davon ausgehen, dass Ergebnisse angezeigt werden sollten, ändern Sie den Datumsbereich, und führen Sie den Bericht erneut aus.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="6cc8d-134">Überwachen von Änderungen an der Rollengruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="6cc8d-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="6cc8d-p110">Wenn einer Rollengruppe Mitglieder hinzugefügt oder daraus entfernt werden, wird in den im Detailbereich angezeigten Suchergebnissen angegeben, dass die Rollengruppenmitgliedschaft aktualisiert wurde, und die aktuellen Mitglieder werden aufgelistet. In den Ergebnissen ist nicht angegeben, welcher Benutzer hinzugefügt oder entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="6cc8d-p111">Wenn Sie ermitteln möchten, ob ein Benutzer hinzugefügt oder entfernt wurde, müssen zwei separate Einträge im Bericht verglichen werden. Sehen Sie sich beispielsweise die folgenden Protokolleinträge für die Rollengruppe **HelpDesk** an:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="6cc8d-139">1/27/2018 4:43 Uhr</span><span class="sxs-lookup"><span data-stu-id="6cc8d-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="6cc8d-140">Administrator</span><span class="sxs-lookup"><span data-stu-id="6cc8d-140">Administrator</span></span> <br> <span data-ttu-id="6cc8d-141">Aktualisierte Mitglieder: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="6cc8d-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="6cc8d-142">2/06/2018 10:09 Uhr</span><span class="sxs-lookup"><span data-stu-id="6cc8d-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="6cc8d-143">Administrator</span><span class="sxs-lookup"><span data-stu-id="6cc8d-143">Administrator</span></span> <br> <span data-ttu-id="6cc8d-144">Aktualisierte Mitglieder: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="6cc8d-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="6cc8d-145">2/19/2018 2:12 Uhr</span><span class="sxs-lookup"><span data-stu-id="6cc8d-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="6cc8d-146">Administrator</span><span class="sxs-lookup"><span data-stu-id="6cc8d-146">Administrator</span></span> <br> <span data-ttu-id="6cc8d-147">Aktualisierte Mitglieder: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="6cc8d-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="6cc8d-148">In diesem Beispiel wurden mit dem Administratorbenutzerkonto folgende Änderungen vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="6cc8d-149">Am 2/06/2018 wurde der Benutzer tonip hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-149">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="6cc8d-150">Am 2/19/2018 wurde der Benutzer pilarp entfernt.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="6cc8d-151">Verwenden eigenständiger Exchange Online PowerShell zum Suchen nach Überwachungsprotokolleinträgen</span><span class="sxs-lookup"><span data-stu-id="6cc8d-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="6cc8d-152">Sie können Exchange Online PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen, die die von Ihnen angegebenen Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="6cc8d-153">Eine Liste der Suchkriterien finden Sie unter Search [-AdminAuditLog Suchkriterien](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="6cc8d-154">Bei diesem Verfahren wird das Cmdlet **Search-AdminAuditLog** verwendet, und es werden Suchergebnisse in Exchange Online PowerShell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="6cc8d-155">Dieses Cmdlet kann verwendet werden, wenn eine Ergebnismenge zurückgegeben werden muss, die die im Cmdlet **New-AdminAuditLogSearch** oder in den Überwachungsberichten der Exchange-Verwaltungskonsole definierten Grenzwerte überschreitet.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="6cc8d-156">Verwenden Sie die folgende Syntax, um das Überwachungsprotokoll anhand angegebener Kriterien zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="6cc8d-157">Das Cmdlet **Search-AdminAuditLog** gibt standardmäßig maximal 1.000 Protokolleinträge zurück.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="6cc8d-158">Verwenden Sie den _resultse_ -Parameter, um bis zu 250.000 Protokolleinträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="6cc8d-159">Oder verwenden Sie den Wert `Unlimited` , um alle Einträge zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="6cc8d-160">In diesem Beispiel wird eine Suche nach allen Überwachungsprotokolleinträgen ausgeführt, welche die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="6cc8d-161">**Start Datum** : 08/04/2018</span><span class="sxs-lookup"><span data-stu-id="6cc8d-161">**Start date** : 08/04/2018</span></span>
- <span data-ttu-id="6cc8d-162">**End-Datum** : 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="6cc8d-162">**End date** : 10/03/2018</span></span>
- <span data-ttu-id="6cc8d-163">**Benutzer-IDs** : `davids` , `chrisd` , `kima`</span><span class="sxs-lookup"><span data-stu-id="6cc8d-163">**User IDs** : `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="6cc8d-164">**Cmdlets** : **festlegen-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-164">**Cmdlets** : **Set-Mailbox**</span></span>
- <span data-ttu-id="6cc8d-165">**Parameter** : _ProhibitSendQuota_ , _ProhibitSendReceiveQuota_ , _IssueWarningQuota_ , _MaxSendSize_ , _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="6cc8d-165">**Parameters** : _ProhibitSendQuota_ , _ProhibitSendReceiveQuota_ , _IssueWarningQuota_ , _MaxSendSize_ , _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="6cc8d-p114">In diesem Beispiel werden Änderungen an einem bestimmten Postfach ermittelt. Dies ist bei der Problembehebung nützlich, oder wenn Sie Informationen für eine Untersuchung bereitstellen müssen. Die folgenden Kriterien werden verwendet:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="6cc8d-169">**Start Datum** : 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="6cc8d-169">**Start date** : 05/01/2018</span></span>
- <span data-ttu-id="6cc8d-170">**End-Datum** : 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="6cc8d-170">**End date** : 10/03/2018</span></span>
- <span data-ttu-id="6cc8d-171">**Objekt-ID** : contoso.com/users/DavidS</span><span class="sxs-lookup"><span data-stu-id="6cc8d-171">**Object ID** : contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="6cc8d-172">Wenn Ihre Suchvorgänge viele Protokolleinträge zurückgeben, wird empfohlen, dass Sie das in **verwenden Exchange Online PowerShell bereitgestellte Verfahren verwenden, um nach Überwachungsprotokolleinträgen zu suchen und Ergebnisse an einen Empfänger** weiter unten in diesem Artikel zu senden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="6cc8d-173">Bei dieser Vorgehensweise wird eine XML-Datei als E-Mail-Anlage an die angegebenen Empfänger gesendet, sodass die relevanten Daten einfacher extrahiert werden können.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="6cc8d-174">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="6cc8d-175">Anzeigen der Details von Überwachungsprotokolleinträgen</span><span class="sxs-lookup"><span data-stu-id="6cc8d-175">View details of audit log entries</span></span>

<span data-ttu-id="6cc8d-176">Das Cmdlet **Search-AdminAuditLog** gibt die in [Überwachungsprotokoll Inhalt](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)beschriebenen Felder zurück.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="6cc8d-177">Zwei der zurückgegebenen Felder, **CmdletParameters** und **ModifiedProperties** , enthalten zusätzliche Informationen, die standardmäßig nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties** , contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="6cc8d-178">Führen Sie die folgenden Schritte aus, um die Inhalte der Felder **CmdletParameters** und **ModifiedProperties** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="6cc8d-179">Sie können auch das Verfahren in Verwenden von **Exchange Online PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen und Ergebnisse an einen Empfänger** weiter unten in diesem Artikel zu senden, um eine XML-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="6cc8d-180">In dieser Vorgehensweise werden die folgenden Konzepte verwendet:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="6cc8d-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="6cc8d-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="6cc8d-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="6cc8d-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="6cc8d-183">Legen Sie die Suchkriterien fest, führen Sie das Cmdlet **Search-AdminAuditLog** aus, und speichern Sie die Ergebnisse über den folgenden Befehl in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="6cc8d-184">Jeder Überwachungsprotokolleintrag wird als Arrayelement in der Variablen gespeichert `$Results` .</span><span class="sxs-lookup"><span data-stu-id="6cc8d-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="6cc8d-185">Zur Auswahl eines Arrayelements geben Sie den Arrayelementindex an.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="6cc8d-186">Arrayelementindizes beginnen für das erste Arrayelement bei 0.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="6cc8d-187">Verwenden Sie beispielsweise den folgenden Befehl, um das fünfte Arrayelement (mit dem Index 4) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="6cc8d-p119">Der oben stehende Befehl gibt den im Arrayelement 4 gespeicherten Protokolleintrag zurück. Zum Anzeigen der Felder **CmdletParameters** und **ModifiedProperties** für diesen Protokolleintrag verwenden Sie die folgenden Befehle.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="6cc8d-190">Um die Inhalte der Felder **CmdletParameters** und **ModifiedParameters** in einem anderen Protokolleintrag anzuzeigen, ändern Sie den Arrayelementindex.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
