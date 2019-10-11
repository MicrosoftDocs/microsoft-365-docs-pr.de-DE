---
title: 'Ausführen eines Administrator-Rollengruppenberichts in EOP '
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Administratoren können erfahren, wie Sie einen Administratorrollengruppen Bericht in Exchange Online Protection (EoP) ausführen. Dieser Bericht protokolliert, wenn ein Administrator Mitglieder zu Administratorrollengruppen hinzufügt oder diese entfernt, protokolliert Microsoft Exchange Online Schutz (EoP) jedes Vorkommen.
ms.openlocfilehash: 59557f6fab2281cd36569b40afcf3e0225bd9347
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441402"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="003e1-104">Ausführen eines Administrator-Rollengruppenberichts in EOP</span><span class="sxs-lookup"><span data-stu-id="003e1-104">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="003e1-105">Wenn ein Administrator Mitglieder zu Administratorrollengruppen hinzufügt oder diese entfernt, protokolliert Exchange Online Protection (EoP) jedes Vorkommen.</span><span class="sxs-lookup"><span data-stu-id="003e1-105">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="003e1-106">Wenn Sie einen Administratorrollengruppen Bericht im Exchange Admin Center (EAC) ausführen, werden Einträge als Suchergebnisse angezeigt und umfassen die betroffenen Rollengruppen, die die Rollengruppenmitgliedschaft geändert haben und wann und welche Mitgliedschafts Aktualisierungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="003e1-106">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="003e1-107">Mithilfe dieses Berichts können Sie Änderungen an den Administratorberechtigungen überwachen, die den Benutzern in der Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="003e1-107">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="003e1-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="003e1-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="003e1-109">Geschätzte Zeit bis zum Abschließen des Vorgangs: 2 Minuten</span><span class="sxs-lookup"><span data-stu-id="003e1-109">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="003e1-110">Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="003e1-110">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="003e1-p103">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Berichte" im Thema [Featureberechtigungen in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="003e1-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="003e1-113">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="003e1-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="003e1-114">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="003e1-114">Having problems?</span></span> <span data-ttu-id="003e1-115">Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="003e1-115">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="003e1-116">Ausführen eines Administrator-Rollengruppenberichts mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="003e1-116">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="003e1-117">Führen Sie den Bericht Administratorrollengruppe aus, um die Änderungen an Verwaltungsrollengruppen in Ihrer Organisation innerhalb eines bestimmten Zeitrahmens zu finden.</span><span class="sxs-lookup"><span data-stu-id="003e1-117">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="003e1-118">Wählen Sie in der Exchange-Verwaltungskonsole **Verwaltung der Richtlinientreue** \> **Überwachung** aus, und klicken Sie anschließend auf **Administrator-Rollengruppenbericht ausführen**.</span><span class="sxs-lookup"><span data-stu-id="003e1-118">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="003e1-p105">Legen Sie **Startdatum** und **Enddatum** fest. Standardmäßig sucht der Bericht nach Änderungen, die innerhalb der letzten zwei Wochen an Administratorrollengruppen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="003e1-p105">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="003e1-p106">Um die Änderungen für eine bestimmte Rollengruppe anzuzeigen, klicken Sie auf **Rollengruppen auswählen**. Wählen Sie im nachfolgenden Dialogfeld die Rollengruppe (oder -gruppen) aus, und klicken Sie auf **OK**. Sie können das Feld auch leer lassen, um nach allen geänderten Rollengruppen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="003e1-p106">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="003e1-124">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="003e1-124">Click **Search**.</span></span>

<span data-ttu-id="003e1-p107">Wenn Änderungen gefunden werden, die mit den angegebenen Kriterien übereinstimmen, werden sie im Ergebnisbereich angezeigt. Klicken Sie auf eine Rollengruppe in den Suchergebnissen, um die Änderungen im Detailbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="003e1-p107">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="003e1-127">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="003e1-127">How do you know this worked?</span></span>

<span data-ttu-id="003e1-p108">Wenn Sie einen Administrator-Rollengruppenbericht erfolgreich ausgeführt haben, werden die Rollengruppen, die innerhalb des Datumsbereichs geändert wurden, im Suchergebnisbereich angezeigt. Wenn keine Ergebnisse angezeigt werden, wurden im angegebenen Datumsbereich keine Änderungen an Rollengruppen vorgenommen. Wenn Sie davon ausgehen, dass Ergebnisse angezeigt werden sollten, ändern Sie den Datumsbereich, und führen Sie den Bericht erneut aus.</span><span class="sxs-lookup"><span data-stu-id="003e1-p108">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="003e1-131">Überwachen von Änderungen an der Rollengruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="003e1-131">Monitor changes to role group membership</span></span>

<span data-ttu-id="003e1-p109">Wenn einer Rollengruppe Mitglieder hinzugefügt oder daraus entfernt werden, wird in den im Detailbereich angezeigten Suchergebnissen angegeben, dass die Rollengruppenmitgliedschaft aktualisiert wurde, und die aktuellen Mitglieder werden aufgelistet. In den Ergebnissen ist nicht angegeben, welcher Benutzer hinzugefügt oder entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="003e1-p109">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="003e1-p110">Wenn Sie ermitteln möchten, ob ein Benutzer hinzugefügt oder entfernt wurde, müssen zwei separate Einträge im Bericht verglichen werden. Sehen Sie sich beispielsweise die folgenden Protokolleinträge für die Rollengruppe **HelpDesk** an:</span><span class="sxs-lookup"><span data-stu-id="003e1-p110">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="003e1-136">1/27/2018 4:43 Uhr</span><span class="sxs-lookup"><span data-stu-id="003e1-136">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="003e1-137">Administrator</span><span class="sxs-lookup"><span data-stu-id="003e1-137">Administrator</span></span> <br> <span data-ttu-id="003e1-138">Aktualisierte Mitglieder: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="003e1-138">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="003e1-139">2/06/2018 10:09 Uhr</span><span class="sxs-lookup"><span data-stu-id="003e1-139">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="003e1-140">Administrator</span><span class="sxs-lookup"><span data-stu-id="003e1-140">Administrator</span></span> <br> <span data-ttu-id="003e1-141">Aktualisierte Mitglieder: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="003e1-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="003e1-142">2/19/2018 2:12 Uhr</span><span class="sxs-lookup"><span data-stu-id="003e1-142">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="003e1-143">Administrator</span><span class="sxs-lookup"><span data-stu-id="003e1-143">Administrator</span></span> <br> <span data-ttu-id="003e1-144">Aktualisierte Mitglieder: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="003e1-144">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="003e1-145">In diesem Beispiel wurden mit dem Administratorbenutzerkonto folgende Änderungen vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="003e1-145">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="003e1-146">Am 2/06/2018 wurde der Benutzer tonip hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="003e1-146">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="003e1-147">Am 2/19/2018 wurde der Benutzer pilarp entfernt.</span><span class="sxs-lookup"><span data-stu-id="003e1-147">On 2/19/2018, they removed the user pilarp.</span></span>
