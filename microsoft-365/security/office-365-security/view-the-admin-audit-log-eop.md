---
title: Anzeigen des Administratorüberwachungsprotokolls in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratoren können erfahren, wie Sie das Administrator-Überwachungsprotokoll in eigenständiger Exchange Online Schutz (EoP) anzeigen und durchsuchen.
ms.openlocfilehash: 171f3ec531b232ca796232ab26caefbee8afc75c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653497"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="0b47a-103">Anzeigen des Administratorüberwachungsprotokolls in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="0b47a-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="0b47a-104">In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer können Sie die Exchange-Verwaltungskonsole (EAC) oder die eigenständige EoP-PowerShell verwenden, um nach Einträgen im Administrator-Überwachungsprotokoll zu suchen und diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0b47a-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="0b47a-105">Das administratorüberwachungsprotokoll zeichnet bestimmte Aktionen auf der Grundlage von eigenständigen EoP PowerShell-Cmdlets auf, die von Administratoren und Benutzern ausgeführt wurden, denen Administratorrechte zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="0b47a-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="0b47a-106">Mit Einträgen im Administrator-Überwachungsprotokoll erhalten Sie Informationen dazu, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, wer das Cmdlet ausgeführt hat und welche Objekte betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="0b47a-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0b47a-107">Die Administrator Überwachungsprotokollierung ist standardmäßig aktiviert und kann nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0b47a-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="0b47a-108">Das administratorüberwachungsprotokoll zeichnet keine Aktionen basierend auf Cmdlets auf, die mit dem Verb **Get**, der **Suche**oder dem **Test**beginnen.</span><span class="sxs-lookup"><span data-stu-id="0b47a-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="0b47a-109">Die Überwachungsprotokolleinträge werden 90 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="0b47a-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="0b47a-110">Wenn ein Eintrag älter als 90 Tage ist, wird er gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0b47a-110">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b47a-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="0b47a-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b47a-112">Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0b47a-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="0b47a-113">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="0b47a-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0b47a-114">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0b47a-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="0b47a-115">Insbesondere benötigen Sie die Überwachungsprotokolle oder die Rolle "Überwachungsprotokolle nur anzeigen", die standardmäßig den Rollengruppen ComplianceManagement, Mitglied (globale Administratoren) und SecurityAdministrator zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="0b47a-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="0b47a-116">Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="0b47a-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="0b47a-117">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="0b47a-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="0b47a-118">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="0b47a-118">Having problems?</span></span> <span data-ttu-id="0b47a-119">Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="0b47a-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="0b47a-120">Anzeigen des administratorüberwachungsprotokolls mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="0b47a-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="0b47a-121">Wechseln Sie in der Exchange- **Verwaltungskonsole zu Compliance Management** \> **Auditing**, und wählen Sie dann **Administrator-Überwachungsprotokollbericht ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="0b47a-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="0b47a-122">Wählen Sie auf der Seite nach **Änderungen an Administratorrollengruppen suchen** , die geöffnet wird, ein **Start Datum** und ein **Enddatum** aus (der Standardbereich ist die letzten zwei Wochen), und wählen Sie dann **Suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="0b47a-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="0b47a-123">Sämtliche Konfigurationsänderungen, die im angegebenen Zeitraum erfolgt sind, werden angezeigt und können anhand der folgenden Informationen sortiert werden:</span><span class="sxs-lookup"><span data-stu-id="0b47a-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="0b47a-124">**Date**: das Datum und die Uhrzeit, zu der die Konfigurationsänderung vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="0b47a-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="0b47a-125">Datum und Uhrzeit werden im UTC-Format (Coordinated Universal Time, koordinierte Weltzeit) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0b47a-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="0b47a-126">**Cmdlet**: der Name des Cmdlets, das zum vornehmen der Konfigurationsänderung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0b47a-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="0b47a-127">**User**: der Name des Benutzerkontos des Benutzers, der die Konfigurationsänderung vorgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="0b47a-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="0b47a-p107">Es können bis zu 5000 Einträge auf mehreren Seiten angezeigt werden. Geben Sie einen kürzeren Datumsbereich ein, wenn Sie Ihre Ergebnisse eingrenzen möchten. Wenn Sie ein einzelnes Suchergebnis auswählen, werden im Detailbereich die folgenden weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0b47a-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="0b47a-131">**Objekt geändert**: das Objekt, das vom Cmdlet geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="0b47a-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="0b47a-132">**Parameter (Parameter: Wert)**: die verwendeten Cmdlet-Parameter und der mit dem Parameter angegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="0b47a-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="0b47a-133">Wenn Sie einen bestimmten Überwachungsprotokolleintrag drucken möchten, klicken Sie im Detailbereich auf die Schaltfläche **Drucken**.</span><span class="sxs-lookup"><span data-stu-id="0b47a-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="0b47a-134">Verwenden eigenständiger EoP PowerShell zum Anzeigen des administratorüberwachungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="0b47a-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="0b47a-135">Sie können eigenständige EoP PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen, die die von Ihnen angegebenen Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0b47a-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="0b47a-136">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="0b47a-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="0b47a-137">**Anmerkungen**:</span><span class="sxs-lookup"><span data-stu-id="0b47a-137">**Notes**:</span></span>

- <span data-ttu-id="0b47a-138">Sie können den Parameter _para_ meters nur zusammen mit dem _Cmdlets_ -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b47a-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="0b47a-139">Der Parameter _ObjectIDs_ filtert die Ergebnisse nach dem Objekt, das vom Cmdlet geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="0b47a-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="0b47a-140">Ein gültiger Wert hängt davon ab, wie das Objekt im Überwachungsprotokoll dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0b47a-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="0b47a-141">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0b47a-141">For example:</span></span>

  - <span data-ttu-id="0b47a-142">Name</span><span class="sxs-lookup"><span data-stu-id="0b47a-142">Name</span></span>
  - <span data-ttu-id="0b47a-143">Kanonischer Distinguished Name (beispielsweise contoso.com/users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="0b47a-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="0b47a-144">Sie müssen wahrscheinlich andere Filterparameter für dieses Cmdlet verwenden, um die Ergebnisse einzugrenzen und die Objekttypen zu identifizieren, an denen Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="0b47a-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="0b47a-145">Der Parameter _userids_ filtert die Ergebnisse des Benutzers, der die Änderung vorgenommen hat (der das Cmdlet ausgeführt hat).</span><span class="sxs-lookup"><span data-stu-id="0b47a-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="0b47a-146">Wenn Sie für die Parameter _StartDate_ und _EndDate_ einen Datum/Uhrzeit-Wert ohne Zeitzone angeben, wird der Wert in koordinierter Weltzeit (Coordinated Universal Time, UTC) angegeben.</span><span class="sxs-lookup"><span data-stu-id="0b47a-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="0b47a-147">Verwenden Sie eine der folgenden Optionen, um einen Datum/Uhrzeit-Wert für diesen Parameter anzugeben:</span><span class="sxs-lookup"><span data-stu-id="0b47a-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="0b47a-148">Datum/Uhrzeit-Wert in UTC, z. B.: "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="0b47a-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="0b47a-149">Geben Sie den Wert für Datum/Uhrzeit als Formel an, die das Datum/die Uhrzeit in Ihrer lokalen Zeitzone in UTC konvertiert: beispielsweise `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="0b47a-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="0b47a-150">Weitere Informationen finden Sie unter [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="0b47a-150">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="0b47a-151">Das Cmdlet gibt standardmäßig maximal 1.000 Protokolleinträge zurück.</span><span class="sxs-lookup"><span data-stu-id="0b47a-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="0b47a-152">Verwenden Sie den _resultse_ -Parameter, um bis zu 250.000 Protokolleinträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0b47a-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="0b47a-153">Oder verwenden Sie den Wert `Unlimited` , um alle Einträge zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0b47a-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="0b47a-154">In diesem Beispiel wird eine Suche nach allen Überwachungsprotokolleinträgen ausgeführt, welche die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="0b47a-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="0b47a-155">**Start Datum**: 4. August 2019</span><span class="sxs-lookup"><span data-stu-id="0b47a-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="0b47a-156">**Ende Datum**: 3. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="0b47a-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="0b47a-157">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="0b47a-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="0b47a-158">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="0b47a-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="0b47a-159">Anzeigen der Details von Überwachungsprotokolleinträgen</span><span class="sxs-lookup"><span data-stu-id="0b47a-159">View details of audit log entries</span></span>

<span data-ttu-id="0b47a-160">Das Cmdlet **Search-AdminAuditLog** gibt die Felder zurück, die im Abschnitt [Überwachungsprotokoll Inhalt](#audit-log-contents) weiter unten in diesem Thema beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0b47a-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="0b47a-161">Von den vom Cmdlet zurückgegebenen Feldern enthalten zwei Felder, **CmdletParameters** und **ModifiedProperties**, zusätzliche Informationen, die standardmäßig nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0b47a-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="0b47a-162">Führen Sie die folgenden Schritte aus, um die Inhalte der Felder **CmdletParameters** und **ModifiedProperties** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0b47a-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="0b47a-163">Legen Sie die Suchkriterien fest, führen Sie das Cmdlet **Search-AdminAuditLog** aus, und speichern Sie die Ergebnisse über den folgenden Befehl in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="0b47a-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="0b47a-164">Jeder Überwachungsprotokolleintrag wird als Arrayelement in der Variablen gespeichert `$Results` .</span><span class="sxs-lookup"><span data-stu-id="0b47a-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="0b47a-165">Zur Auswahl eines Arrayelements geben Sie den Arrayelementindex an.</span><span class="sxs-lookup"><span data-stu-id="0b47a-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="0b47a-166">Arrayelementindizes beginnen für das erste Arrayelement bei 0.</span><span class="sxs-lookup"><span data-stu-id="0b47a-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="0b47a-167">Verwenden Sie beispielsweise den folgenden Befehl, um das fünfte Arrayelement (mit dem Index 4) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0b47a-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="0b47a-p115">Der oben stehende Befehl gibt den im Arrayelement 4 gespeicherten Protokolleintrag zurück. Zum Anzeigen der Felder **CmdletParameters** und **ModifiedProperties** für diesen Protokolleintrag verwenden Sie die folgenden Befehle.</span><span class="sxs-lookup"><span data-stu-id="0b47a-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="0b47a-170">Um die Inhalte der Felder **CmdletParameters** und **ModifiedParameters** in einem anderen Protokolleintrag anzuzeigen, ändern Sie den Arrayelementindex.</span><span class="sxs-lookup"><span data-stu-id="0b47a-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="0b47a-171">Inhalte des Überwachungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="0b47a-171">Audit log contents</span></span>

<span data-ttu-id="0b47a-172">Jeder Überwachungsprotokolleintrag enthält die Informationen, die in der folgenden Tabelle beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="0b47a-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="0b47a-173">Das Überwachungsprotokoll enthält mindestens einen Überwachungsprotokolleintrag.</span><span class="sxs-lookup"><span data-stu-id="0b47a-173">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="0b47a-174">Feld</span><span class="sxs-lookup"><span data-stu-id="0b47a-174">Field</span></span>|<span data-ttu-id="0b47a-175">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b47a-175">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="0b47a-176">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="0b47a-177">Dieses Feld enthält das Objekt, das von dem im Feld angegebenen Cmdlet geändert wurde `CmdletName` .</span><span class="sxs-lookup"><span data-stu-id="0b47a-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="0b47a-178">Dieses Feld enthält den Namen des Cmdlets, das vom Benutzer im Feld ausgeführt wurde `Caller` .</span><span class="sxs-lookup"><span data-stu-id="0b47a-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="0b47a-179">Dieses Feld enthält die Parameter, die beim Ausführen des Cmdlets im `CmdletName` Feld angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="0b47a-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="0b47a-180">In diesem Feld wird auch, falls vorhanden, der in diesem Parameter angegebene Wert gespeichert, er wird jedoch nicht in der Standardausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b47a-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="0b47a-181">Dieses Feld enthält die Eigenschaften, die für das Objekt in dem Feld geändert wurden `ObjectModified` .</span><span class="sxs-lookup"><span data-stu-id="0b47a-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="0b47a-182">In diesem Feld werden auch der alte Wert der Eigenschaft und der neue gespeicherte Wert gespeichert, sie werden jedoch nicht in der Standardausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b47a-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="0b47a-183">Dieses Feld enthält das Benutzerkonto des Benutzers, der das Cmdlet im Feld ausgeführt hat `CmdletName` .</span><span class="sxs-lookup"><span data-stu-id="0b47a-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="0b47a-184">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="0b47a-185">Dieses Feld gibt an, ob das Cmdlet im `CmdletName` Feld erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="0b47a-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="0b47a-186">Der Wert ist entweder `True` oder `False` .</span><span class="sxs-lookup"><span data-stu-id="0b47a-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="0b47a-187">Dieses Feld enthält die Fehlermeldung, die generiert wird, wenn das Cmdlet im `CmdletName` Feld nicht erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0b47a-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="0b47a-188">Dieses Feld enthält das Datum und die Uhrzeit, zu der das Cmdlet im `CmdletName` Feld ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="0b47a-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="0b47a-189">Datum und Uhrzeit werden im UTC-Format (Coordinated Universal Time, koordinierte Weltzeit) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0b47a-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="0b47a-190">Dieses Feld gibt den Server an, auf dem das im Feld angegebene Cmdlet `CmdletName` ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="0b47a-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="0b47a-191">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="0b47a-192">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="0b47a-193">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="0b47a-194">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="0b47a-195">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="0b47a-196">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="0b47a-197">Dieses Feld wird intern von EoP verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b47a-197">This field is used internally by EOP.</span></span>|
|
