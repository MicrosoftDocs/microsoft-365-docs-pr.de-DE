---
title: Anzeigen des Administratorüberwachungsprotokolls in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratoren können erfahren, wie Sie das Administrator-Überwachungsprotokoll in eigenständigem Exchange Online Protection (EOP) anzeigen und durchsuchen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286477"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="fe5e9-103">Anzeigen des Administratorüberwachungsprotokolls in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="fe5e9-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="fe5e9-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="fe5e9-104">**Applies to**</span></span>
- [<span data-ttu-id="fe5e9-105">Exchange Online Protection als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="fe5e9-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fe5e9-106">In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie das Exchange Admin Center (EAC) oder die eigenständige EOP PowerShell verwenden, um Einträge im Administrator-Überwachungsprotokoll zu suchen und diese ein- und auszusuchen.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="fe5e9-107">Im Administrator-Überwachungsprotokoll werden bestimmte Aktionen aufgezeichnet, die auf eigenständigen EOP -PowerShell-Cmdlets basieren, die von Administratoren und Benutzern durchgeführt werden, denen Administratorrechte zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="fe5e9-108">Einträge im Administrator-Überwachungsprotokoll enthalten Informationen dazu, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, wer das Cmdlet ausgeführt hat und welche Objekte betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fe5e9-109">Die Administratorüberwachungsprotokollierung ist standardmäßig aktiviert und kann nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="fe5e9-110">Im Administrator-Überwachungsprotokoll werden keine Aktionen aufgezeichnet, die auf Cmdlets basieren, die mit den Verben **Get,** **Search** oder **Test beginnen.**</span><span class="sxs-lookup"><span data-stu-id="fe5e9-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="fe5e9-111">Die Überwachungsprotokolleinträge werden 90 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="fe5e9-112">Wenn ein Eintrag älter als 90 Tage ist, wird er gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fe5e9-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="fe5e9-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fe5e9-114">Informationen zum Öffnen des Exchange Admin Centers finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="fe5e9-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="fe5e9-115">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="fe5e9-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fe5e9-116">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="fe5e9-117">Insbesondere benötigen Sie die  Rolle **"Überwachungsprotokolle"** oder "Überwachungsprotokolle nur anzeigen", die standardmäßig den Rollengruppen "Organisationsverwaltung", "Complianceverwaltung" und "Sicherheitsadministrator" zugewiesen sind.   </span><span class="sxs-lookup"><span data-stu-id="fe5e9-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="fe5e9-118">Weitere Informationen finden Sie unter "Berechtigungen [in EOP als eigenständige](feature-permissions-in-eop.md) Lösung", und ändern Sie mithilfe der EAC die Liste der Mitglieder in [Rollengruppen.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="fe5e9-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="fe5e9-119">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="fe5e9-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="fe5e9-120">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="fe5e9-120">Having problems?</span></span> <span data-ttu-id="fe5e9-121">Bitten Sie im [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)-Forum um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="fe5e9-122">Anzeigen des Administrator-Überwachungsprotokolls mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="fe5e9-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="fe5e9-123">Wechseln Sie in der EAC zu **Überwachung** der Verwaltung der Richtlinienverwaltung, und wählen Sie dann \>  **"Administratorüberwachungsprotokollbericht ausführen" aus.**</span><span class="sxs-lookup"><span data-stu-id="fe5e9-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="fe5e9-124">Wählen Sie **auf** der Seite "Nach Änderungen an Administrator-Rollengruppen suchen", die geöffnet wird, ein **Startdatum** und ein **Enddatum** aus (der Standardbereich ist die letzten zwei Wochen), und wählen Sie dann **Suche aus.**</span><span class="sxs-lookup"><span data-stu-id="fe5e9-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="fe5e9-125">Sämtliche Konfigurationsänderungen, die im angegebenen Zeitraum erfolgt sind, werden angezeigt und können anhand der folgenden Informationen sortiert werden:</span><span class="sxs-lookup"><span data-stu-id="fe5e9-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="fe5e9-126">**Datum**: Datum und Uhrzeit der Konfigurationsänderung.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="fe5e9-127">Datum und Uhrzeit werden im UTC-Format (Coordinated Universal Time, koordinierte Weltzeit) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="fe5e9-128">**Cmdlet:** Der Name des Cmdlets, das zum Ändern der Konfiguration verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="fe5e9-129">**Benutzer:** Der Name des Benutzerkontos des Benutzers, der die Konfigurationsänderung vorgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="fe5e9-p107">Es können bis zu 5000 Einträge auf mehreren Seiten angezeigt werden. Geben Sie einen kürzeren Datumsbereich ein, wenn Sie Ihre Ergebnisse eingrenzen möchten. Wenn Sie ein einzelnes Suchergebnis auswählen, werden im Detailbereich die folgenden weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fe5e9-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="fe5e9-133">**Objekt geändert:** Das Objekt, das vom Cmdlet geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="fe5e9-134">**Parameter (Parameter:Wert):** Die verwendeten Cmdlet-Parameter und alle mit dem Parameter angegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="fe5e9-135">Wenn Sie einen bestimmten Überwachungsprotokolleintrag drucken möchten, klicken Sie im Detailbereich auf die Schaltfläche **Drucken**.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="fe5e9-136">Verwenden der eigenständigen EOP PowerShell zum Anzeigen des Administrator-Überwachungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="fe5e9-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="fe5e9-137">Sie können die eigenständige EOP PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen, die den von Ihnen angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="fe5e9-138">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="fe5e9-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="fe5e9-139">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="fe5e9-139">**Notes**:</span></span>

- <span data-ttu-id="fe5e9-140">Sie können den Parameter _"Parameters"_ nur zusammen mit dem _Parameter "Cmdlets"_ verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="fe5e9-141">Der _Parameter "ObjectIds"_ filtert die Ergebnisse nach dem Objekt, das vom Cmdlet geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="fe5e9-142">Ein gültiger Wert hängt davon ab, wie das Objekt im Überwachungsprotokoll dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="fe5e9-143">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fe5e9-143">For example:</span></span>

  - <span data-ttu-id="fe5e9-144">Name</span><span class="sxs-lookup"><span data-stu-id="fe5e9-144">Name</span></span>
  - <span data-ttu-id="fe5e9-145">Kanonischer Distinguished Name (z. B. contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="fe5e9-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="fe5e9-146">Wahrscheinlich müssen Sie andere Filterparameter für dieses Cmdlet verwenden, um die Ergebnisse einengt und die Objekttypen zu identifizieren, die Sie interessieren.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="fe5e9-147">Der _Parameter "UserIds"_ filtert die Ergebnisse nach dem Benutzer, der die Änderung vorgenommen hat (der das Cmdlet verwendet hat).</span><span class="sxs-lookup"><span data-stu-id="fe5e9-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="fe5e9-148">Wenn Sie _für die Parameter "StartDate"_ und _"EndDate"_ einen Datums-/Uhrzeitwert ohne Zeitzone angeben, wird der Wert in koordinierter Weltzeit (Coordinated Universal Time, UTC) angegeben.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="fe5e9-149">Verwenden Sie eine der folgenden Optionen, um einen Datum/Uhrzeit-Wert für diesen Parameter anzugeben:</span><span class="sxs-lookup"><span data-stu-id="fe5e9-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="fe5e9-150">Datum/Uhrzeit-Wert in UTC, z. B.: "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="fe5e9-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="fe5e9-151">Geben Sie den Wert für Datum/Uhrzeit als Formel an, die Datum/Uhrzeit in Ihrer lokalen Zeitzone in UTC konvertiert: z. B. `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="fe5e9-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="fe5e9-152">Weitere Informationen finden Sie unter [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="fe5e9-152">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="fe5e9-153">Das Cmdlet gibt standardmäßig maximal 1.000 Protokolleinträge zurück.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="fe5e9-154">Verwenden Sie _den Parameter "ResultSize",_ um bis zu 250.000 Protokolleinträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="fe5e9-155">Oder verwenden Sie den `Unlimited` Wert, um alle Einträge zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="fe5e9-156">In diesem Beispiel wird eine Suche nach allen Überwachungsprotokolleinträgen ausgeführt, welche die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="fe5e9-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="fe5e9-157">**Startdatum:** 4. August 2019</span><span class="sxs-lookup"><span data-stu-id="fe5e9-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="fe5e9-158">**Enddatum:** 3. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="fe5e9-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="fe5e9-159">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="fe5e9-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="fe5e9-160">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="fe5e9-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="fe5e9-161">Anzeigen der Details von Überwachungsprotokolleinträgen</span><span class="sxs-lookup"><span data-stu-id="fe5e9-161">View details of audit log entries</span></span>

<span data-ttu-id="fe5e9-162">Das **Cmdlet Search-AdminAuditLog** gibt die Felder zurück, die weiter unten in diesem Artikel im Abschnitt ["Überwachungsprotokollinhalte"](#audit-log-contents) beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="fe5e9-163">Von den vom Cmdlet zurückgegebenen Feldern enthalten die beiden Felder **CmdletParameters** und **ModifiedProperties** zusätzliche Informationen, die standardmäßig nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="fe5e9-164">Führen Sie die folgenden Schritte aus, um die Inhalte der Felder **CmdletParameters** und **ModifiedProperties** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="fe5e9-165">Legen Sie die Suchkriterien fest, führen Sie das Cmdlet **Search-AdminAuditLog** aus, und speichern Sie die Ergebnisse über den folgenden Befehl in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="fe5e9-166">Jeder Überwachungsprotokolleintrag wird als Arrayelement in der Variablen `$Results` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="fe5e9-167">Zur Auswahl eines Arrayelements geben Sie den Arrayelementindex an.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="fe5e9-168">Arrayelementindizes beginnen für das erste Arrayelement bei 0.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="fe5e9-169">Verwenden Sie beispielsweise den folgenden Befehl, um das fünfte Arrayelement (mit dem Index 4) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="fe5e9-p115">Der oben stehende Befehl gibt den im Arrayelement 4 gespeicherten Protokolleintrag zurück. Zum Anzeigen der Felder **CmdletParameters** und **ModifiedProperties** für diesen Protokolleintrag verwenden Sie die folgenden Befehle.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="fe5e9-172">Um die Inhalte der Felder **CmdletParameters** und **ModifiedParameters** in einem anderen Protokolleintrag anzuzeigen, ändern Sie den Arrayelementindex.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="fe5e9-173">Inhalte des Überwachungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="fe5e9-173">Audit log contents</span></span>

<span data-ttu-id="fe5e9-174">Jeder Überwachungsprotokolleintrag enthält die Informationen, die in der folgenden Tabelle beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="fe5e9-175">Das Überwachungsprotokoll enthält mindestens einen Überwachungsprotokolleintrag.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="fe5e9-176">Feld</span><span class="sxs-lookup"><span data-stu-id="fe5e9-176">Field</span></span>|<span data-ttu-id="fe5e9-177">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe5e9-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="fe5e9-178">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="fe5e9-179">Dieses Feld enthält das Objekt, das durch das im Feld angegebene Cmdlet geändert `CmdletName` wurde.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="fe5e9-180">Dieses Feld enthält den Namen des Cmdlets, das vom Benutzer im Feld ausgeführt `Caller` wurde.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="fe5e9-181">Dieses Feld enthält die Parameter, die angegeben wurden, als das Cmdlet im `CmdletName` Feld ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="fe5e9-182">In diesem Feld wird auch, falls vorhanden, der in diesem Parameter angegebene Wert gespeichert, er wird jedoch nicht in der Standardausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="fe5e9-183">Dieses Feld enthält die Eigenschaften, die für das Objekt im Feld geändert `ObjectModified` wurden.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="fe5e9-184">In diesem Feld werden auch der alte Wert der Eigenschaft und der neue gespeicherte Wert gespeichert, sie werden jedoch nicht in der Standardausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="fe5e9-185">Dieses Feld enthält das Benutzerkonto des Benutzers, der das Cmdlet im Feld verwendet `CmdletName` hat.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="fe5e9-186">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="fe5e9-187">Dieses Feld gibt an, ob das Cmdlet im `CmdletName` Feld erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="fe5e9-188">Der Wert ist entweder `True` oder `False` .</span><span class="sxs-lookup"><span data-stu-id="fe5e9-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="fe5e9-189">Dieses Feld enthält die Fehlermeldung, die generiert wird, wenn das Cmdlet im Feld `CmdletName` nicht erfolgreich abgeschlossen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="fe5e9-190">Dieses Feld enthält Datum und Uhrzeit der Ausführung des Cmdlets im `CmdletName` Feld.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="fe5e9-191">Datum und Uhrzeit werden im UTC-Format (Coordinated Universal Time, koordinierte Weltzeit) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="fe5e9-192">Dieses Feld gibt den Server an, auf dem das im Feld angegebene Cmdlet `CmdletName` ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="fe5e9-193">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="fe5e9-194">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="fe5e9-195">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="fe5e9-196">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="fe5e9-197">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="fe5e9-198">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="fe5e9-199">Dieses Feld wird intern von EOP verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe5e9-199">This field is used internally by EOP.</span></span>|
|
