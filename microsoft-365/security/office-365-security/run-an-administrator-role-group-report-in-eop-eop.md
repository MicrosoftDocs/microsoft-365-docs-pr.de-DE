---
title: Ausführen eines Administrator-Rollengruppenberichts in EOP
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie einen Administratorrollengruppen Bericht in Exchange Online Protection (EoP) ausführen.
ms.openlocfilehash: d3c4db8079a71ba054f323617d3ade65083a3a04
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034456"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="0f194-103">Ausführen eines Administrator-Rollengruppenberichts in EOP</span><span class="sxs-lookup"><span data-stu-id="0f194-103">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="0f194-104">Wenn ein Administrator Mitglieder zu Administratorrollengruppen hinzufügt oder diese entfernt, protokolliert Exchange Online Protection (EoP) jedes Vorkommen.</span><span class="sxs-lookup"><span data-stu-id="0f194-104">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="0f194-105">Wenn Sie einen Administratorrollengruppen Bericht im Exchange Admin Center (EAC) ausführen, werden Einträge als Suchergebnisse angezeigt und umfassen die betroffenen Rollengruppen, die die Rollengruppenmitgliedschaft geändert haben und wann und welche Mitgliedschafts Aktualisierungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="0f194-105">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="0f194-106">Mithilfe dieses Berichts können Sie Änderungen an den Administratorberechtigungen überwachen, die den Benutzern in der Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="0f194-106">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0f194-107">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="0f194-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0f194-108">Geschätzte Zeit bis zum Abschließen des Vorgangs: 2 Minuten</span><span class="sxs-lookup"><span data-stu-id="0f194-108">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="0f194-109">Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0f194-109">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="0f194-p102">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Berichte" im Thema [Featureberechtigungen in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0f194-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="0f194-112">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="0f194-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="0f194-113">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="0f194-113">Having problems?</span></span> <span data-ttu-id="0f194-114">Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="0f194-114">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="0f194-115">Ausführen eines Administrator-Rollengruppenberichts mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="0f194-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="0f194-116">Führen Sie den Bericht Administratorrollengruppe aus, um die Änderungen an Verwaltungsrollengruppen in Ihrer Organisation innerhalb eines bestimmten Zeitrahmens zu finden.</span><span class="sxs-lookup"><span data-stu-id="0f194-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="0f194-117">Wählen Sie in der Exchange-Verwaltungskonsole **Verwaltung der Richtlinientreue** \> **Überwachung** aus, und klicken Sie anschließend auf **Administrator-Rollengruppenbericht ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0f194-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="0f194-p104">Legen Sie **Startdatum** und **Enddatum** fest. Standardmäßig sucht der Bericht nach Änderungen, die innerhalb der letzten zwei Wochen an Administratorrollengruppen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="0f194-p104">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="0f194-p105">Um die Änderungen für eine bestimmte Rollengruppe anzuzeigen, klicken Sie auf **Rollengruppen auswählen**. Wählen Sie im nachfolgenden Dialogfeld die Rollengruppe (oder -gruppen) aus, und klicken Sie auf **OK**. Sie können das Feld auch leer lassen, um nach allen geänderten Rollengruppen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0f194-p105">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="0f194-123">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="0f194-123">Click **Search**.</span></span>

<span data-ttu-id="0f194-p106">Wenn Änderungen gefunden werden, die mit den angegebenen Kriterien übereinstimmen, werden sie im Ergebnisbereich angezeigt. Klicken Sie auf eine Rollengruppe in den Suchergebnissen, um die Änderungen im Detailbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0f194-p106">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0f194-126">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="0f194-126">How do you know this worked?</span></span>

<span data-ttu-id="0f194-p107">Wenn Sie einen Administrator-Rollengruppenbericht erfolgreich ausgeführt haben, werden die Rollengruppen, die innerhalb des Datumsbereichs geändert wurden, im Suchergebnisbereich angezeigt. Wenn keine Ergebnisse angezeigt werden, wurden im angegebenen Datumsbereich keine Änderungen an Rollengruppen vorgenommen. Wenn Sie davon ausgehen, dass Ergebnisse angezeigt werden sollten, ändern Sie den Datumsbereich, und führen Sie den Bericht erneut aus.</span><span class="sxs-lookup"><span data-stu-id="0f194-p107">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="0f194-130">Überwachen von Änderungen an der Rollengruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="0f194-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="0f194-p108">Wenn einer Rollengruppe Mitglieder hinzugefügt oder daraus entfernt werden, wird in den im Detailbereich angezeigten Suchergebnissen angegeben, dass die Rollengruppenmitgliedschaft aktualisiert wurde, und die aktuellen Mitglieder werden aufgelistet. In den Ergebnissen ist nicht angegeben, welcher Benutzer hinzugefügt oder entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="0f194-p108">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="0f194-p109">Wenn Sie ermitteln möchten, ob ein Benutzer hinzugefügt oder entfernt wurde, müssen zwei separate Einträge im Bericht verglichen werden. Sehen Sie sich beispielsweise die folgenden Protokolleinträge für die Rollengruppe **HelpDesk** an:</span><span class="sxs-lookup"><span data-stu-id="0f194-p109">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="0f194-135">1/27/2018 4:43 Uhr</span><span class="sxs-lookup"><span data-stu-id="0f194-135">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="0f194-136">Administrator</span><span class="sxs-lookup"><span data-stu-id="0f194-136">Administrator</span></span> <br> <span data-ttu-id="0f194-137">Aktualisierte Mitglieder: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="0f194-137">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="0f194-138">2/06/2018 10:09 Uhr</span><span class="sxs-lookup"><span data-stu-id="0f194-138">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="0f194-139">Administrator</span><span class="sxs-lookup"><span data-stu-id="0f194-139">Administrator</span></span> <br> <span data-ttu-id="0f194-140">Aktualisierte Mitglieder: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="0f194-140">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="0f194-141">2/19/2018 2:12 Uhr</span><span class="sxs-lookup"><span data-stu-id="0f194-141">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="0f194-142">Administrator</span><span class="sxs-lookup"><span data-stu-id="0f194-142">Administrator</span></span> <br> <span data-ttu-id="0f194-143">Aktualisierte Mitglieder: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="0f194-143">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="0f194-144">In diesem Beispiel wurden mit dem Administratorbenutzerkonto folgende Änderungen vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="0f194-144">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="0f194-145">Am 2/06/2018 wurde der Benutzer tonip hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0f194-145">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="0f194-146">Am 2/19/2018 wurde der Benutzer pilarp entfernt.</span><span class="sxs-lookup"><span data-stu-id="0f194-146">On 2/19/2018, they removed the user pilarp.</span></span>
