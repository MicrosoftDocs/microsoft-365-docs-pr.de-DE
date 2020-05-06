---
title: Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen in Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Hier erfahren Sie, wie Sie eine oder mehrere Verteilerlisten auf Microsoft 365-Gruppen in Outlook aktualisieren und wie Sie mithilfe von PowerShell mehrere Verteilerlisten gleichzeitig aktualisieren.
ms.openlocfilehash: 3f364de1e863cef542fb8342e61f537bcd113535
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048173"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="f12b7-103">Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="f12b7-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="f12b7-104">Sie können Verteilerlisten auf Microsoft 365-Gruppen mit Outlook aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f12b7-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="f12b7-105">Dies ist eine hervorragende Möglichkeit, den Verteilerlisten Ihrer Organisation alle Features und Funktionen von Microsoft 365-Gruppen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f12b7-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="f12b7-106">Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten</span><span class="sxs-lookup"><span data-stu-id="f12b7-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/en-us/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="f12b7-107">Sie können ein Upgrade für eine einzelne Verteilerliste oder für mehrere Verteilerlisten gleichzeitig ausführen.</span><span class="sxs-lookup"><span data-stu-id="f12b7-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="f12b7-108">Aktualisieren einer oder mehrerer Verteilerlisten auf Microsoft 365-Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="f12b7-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="f12b7-109">Zum Aktualisieren einer Verteilerliste müssen Sie ein globaler Administrator oder Exchange-Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="f12b7-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="f12b7-110">Um ein Upgrade auf Microsoft 365-Gruppen durchführen zu können, muss eine Verteilergruppe über einen Besitzer mit einem Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="f12b7-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="f12b7-111">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="f12b7-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="f12b7-112">Wechseln Sie im Exchange Admin Center zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="f12b7-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="f12b7-113">Es wird ein Hinweis angezeigt, dass Sie über Verteilerlisten (auch als **Verteilergruppen** bezeichnet) verfügen, die für ein Upgrade auf Microsoft 365-Gruppen geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="f12b7-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="f12b7-114">![Klicken Sie auf die Schaltfläche Erste Schritte](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="f12b7-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="f12b7-115">Wählen Sie eine oder mehrere Verteilerlisten (auch als **Verteilergruppe** bezeichnet) auf der Seite **Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="f12b7-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="f12b7-116">![Auswählen einer Verteilergruppe](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="f12b7-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="f12b7-117">Wählen Sie das Symbol Upgrade aus.</span><span class="sxs-lookup"><span data-stu-id="f12b7-117">Select the upgrade icon.</span></span><br/>![Upgrade auf Microsoft 365 Groups-Symbol](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="f12b7-119">Wählen Sie im Dialogfeldinformationen die Option **Ja** aus, um das Upgrade zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="f12b7-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="f12b7-120">Der Prozess beginnt sofort.</span><span class="sxs-lookup"><span data-stu-id="f12b7-120">The process begins immediately.</span></span> <span data-ttu-id="f12b7-121">Je nach Größe und Anzahl der DLS, die Sie aktualisieren, kann der Vorgang Minuten oder Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="f12b7-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="f12b7-122">Wenn für die Verteilerliste kein Upgrade ausgeführt werden kann, wird ein Dialogfeld mit einer entsprechenden Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f12b7-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="f12b7-123">Anzeigen [, welche Verteilerlisten nicht aktualisiert werden können?](#which-distribution-lists-cannot-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="f12b7-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="f12b7-124">Wenn Sie mehrere Verteilerlisten aktualisieren, verwenden Sie die Dropdownliste, um zu filtern, welche Verteilerlisten aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f12b7-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="f12b7-125">Wenn die Liste nicht vollständig ist, warten Sie eine Weile länger, und wählen Sie dann **Aktualisieren** aus, um zu sehen, was erfolgreich aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f12b7-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="f12b7-p106">Es wird keine Benachrichtigung ausgegeben, die Sie informiert, wann das Upgrade für alle ausgewählten Verteilerlisten abgeschlossen wurde. Sie können dies jedoch herausfinden, indem Sie die Elemente untersuchen, die unter **Für Upgrade verfügbar** oder **Aktualisierte Verteilerlisten** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f12b7-p106">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="f12b7-p107">Wenn Sie eine Verteilerliste für das Upgrade ausgewählt haben, diese aber auf der Seite noch als "Für Upgrade verfügbar" angezeigt wird, ist beim Upgrade ein Fehler aufgetreten. Lesen Sie in diesem Fall [Wie gehe ich vor, wenn das Upgrade nicht funktioniert?](#what-to-do-if-the-upgrade-doesnt-work)</span><span class="sxs-lookup"><span data-stu-id="f12b7-p107">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="f12b7-p108">Wenn Sie die Digest-E-Mails der Gruppen erhalten, wird im unteren Bereich ggf. angeboten, ein Upgrade für alle geeigneten Verteilerlisten auszuführen, deren Besitzer Sie sind. Weitere Informationen zu Digest-E-Mails finden Sie unter [Führen einer Gruppenunterhaltung in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx).</span><span class="sxs-lookup"><span data-stu-id="f12b7-p108">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="f12b7-132">Wie gehe ich vor, wenn das Upgrade nicht funktioniert?</span><span class="sxs-lookup"><span data-stu-id="f12b7-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="f12b7-133">Verteilerlisten, für die beim Upgrade ein Fehler auftritt, bleiben unverändert.</span><span class="sxs-lookup"><span data-stu-id="f12b7-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="f12b7-p109">Wenn für mindestens eine **geeignete** Verteilerliste beim Upgrade ein Fehler auftritt, öffnen Sie ein [Supportticket](../contact-support-for-business-products.md). Das Problem muss an das Gruppenentwicklungsteam eskaliert werden, damit dieses das Problem ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="f12b7-p109">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="f12b7-p110">Es ist möglich, dass für die Verteilerliste aufgrund eines Dienstausfalls kein Upgrade ausgeführt wurde. Dies ist aber ziemlich unwahrscheinlich. Wenn Sie möchten, können Sie auch eine Weile warten und dann erneut versuchen, ein Upgrade für die Verteilerliste auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f12b7-p110">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="f12b7-138">Verwenden von PowerShell zum gleichzeitigen Ausführen eines Upgrades mehrerer Verteilerlisten</span><span class="sxs-lookup"><span data-stu-id="f12b7-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="f12b7-139">Wenn Sie im Umgang mit PowerShell erfahren sind, können Sie diese Methode anstelle der Benutzeroberfläche verwenden.</span><span class="sxs-lookup"><span data-stu-id="f12b7-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="f12b7-140">Wir verfügen über eine Reihe von Cmdlets, mit denen Sie Verteilerlisten aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="f12b7-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="f12b7-141">Siehe unten.</span><span class="sxs-lookup"><span data-stu-id="f12b7-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="f12b7-142">Aktualisieren einer einzelnen DL</span><span class="sxs-lookup"><span data-stu-id="f12b7-142">Upgrade a single DL</span></span>

<span data-ttu-id="f12b7-143">Führen Sie den folgenden Befehl aus, um ein Upgrade für eine einzelne DL auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f12b7-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="f12b7-144">Wenn Sie beispielsweise ein DLS mit einer SMTP-Adresse DL1@contoso.com aktualisieren möchten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f12b7-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="f12b7-145">Sie können auch eine einzelne Verteilerliste auf eine Microsoft 365-Gruppe mithilfe des [New-Unifiedgroup PowerShell-](https://go.microsoft.com/fwlink/?LinkID=786379) Cmdlets aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f12b7-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="f12b7-146">Aktualisieren mehrerer DLS in einem Batch</span><span class="sxs-lookup"><span data-stu-id="f12b7-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="f12b7-147">Sie können auch mehrere DLS als Batch übergeben und diese gemeinsam aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="f12b7-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="f12b7-148">Wenn Sie beispielsweise fünf Verteilerlisten mit SMTP- `dl1@contoso.com` Adressen `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com`aktualisieren möchten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f12b7-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="f12b7-149">Aktualisieren aller berechtigten DLS</span><span class="sxs-lookup"><span data-stu-id="f12b7-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="f12b7-150">Es gibt zwei Möglichkeiten, ein Upgrade aller berechtigten Verteilerlisten durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="f12b7-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="f12b7-151">Das Cmdlet "Upgrade-DistributionGroup" empfängt keine Daten aus der Pipeline, daher ist es erforderlich, dass der "ForEach-{}Object"-Operator zum erfolgreichen ausführen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f12b7-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="f12b7-152">Rufen Sie die berechtigten DLS im Mandanten ab, und aktualisieren Sie Sie mithilfe des Befehls Upgrade:</span><span class="sxs-lookup"><span data-stu-id="f12b7-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="f12b7-153">Rufen Sie die Liste aller DLS ab, und aktualisieren Sie nur die berechtigten DLS:</span><span class="sxs-lookup"><span data-stu-id="f12b7-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="f12b7-154">Häufig gestellte Fragen zum Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="f12b7-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="f12b7-155">Welche Verteilerlisten können nicht aktualisiert werden?</span><span class="sxs-lookup"><span data-stu-id="f12b7-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="f12b7-156">Sie können nur für in der Cloud verwaltete, einfache, nicht geschachtelte Verteilerlisten ein Upgrade ausführen.</span><span class="sxs-lookup"><span data-stu-id="f12b7-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="f12b7-157">In der folgenden Tabelle werden Verteilerlisten aufgelistet, die nicht aktualisiert werden **können** .</span><span class="sxs-lookup"><span data-stu-id="f12b7-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="f12b7-158">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="f12b7-158">**Property**</span></span>|<span data-ttu-id="f12b7-159">**Geeignet?**</span><span class="sxs-lookup"><span data-stu-id="f12b7-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f12b7-160">Lokal verwaltete Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="f12b7-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="f12b7-161">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-161">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-p113">Geschachtelte Verteilerliste. Die Verteilerliste hat untergeordnete Gruppen oder ist Mitglied einer anderen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="f12b7-p113">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="f12b7-164">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-164">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-165">Verteilerlisten mit anderen Mitglied **RecipientTypeDetails** als **User Mailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="f12b7-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="f12b7-166">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-166">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-167">Verteilerliste mit mehr als 100 Besitzern</span><span class="sxs-lookup"><span data-stu-id="f12b7-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="f12b7-168">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-168">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-169">Verteilerliste, die nur Mitglieder aber keinen Besitzer enthält</span><span class="sxs-lookup"><span data-stu-id="f12b7-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="f12b7-170">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-170">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-171">Verteilerliste, die einen Alias mit Sonderzeichen enthält</span><span class="sxs-lookup"><span data-stu-id="f12b7-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="f12b7-172">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-172">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-173">Die Verteilerliste ist als Weiterleitungsadresse für das freigegebene Postfach konfiguriert</span><span class="sxs-lookup"><span data-stu-id="f12b7-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="f12b7-174">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-174">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-175">Wenn die Verteilerliste Teil der **Absender Einschränkung** in einer anderen Verteilerliste ist.</span><span class="sxs-lookup"><span data-stu-id="f12b7-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="f12b7-176">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-176">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-177">Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="f12b7-177">Security groups</span></span>  <br/> |<span data-ttu-id="f12b7-178">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-178">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-179">Dynamische Verteilerlisten</span><span class="sxs-lookup"><span data-stu-id="f12b7-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="f12b7-180">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-180">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-181">Verteilerlisten, die in **RoomLists** konvertiert wurden</span><span class="sxs-lookup"><span data-stu-id="f12b7-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="f12b7-182">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-182">No</span></span>  <br/> |
|<span data-ttu-id="f12b7-183">Verteilerlisten, in denen **MemberJoinRestriction** und/oder **MemberDepartRestriction** **geschlossen** wird</span><span class="sxs-lookup"><span data-stu-id="f12b7-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="f12b7-184">Nein</span><span class="sxs-lookup"><span data-stu-id="f12b7-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="f12b7-185">Wie kann ich überprüfen, welche DLS für ein Upgrade berechtigt sind?</span><span class="sxs-lookup"><span data-stu-id="f12b7-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="f12b7-186">Wenn Sie überprüfen möchten, ob eine DL berechtigt ist, können Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="f12b7-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="f12b7-187">Wenn Sie überprüfen möchten, welche DLS für ein Upgrade geeignet sind, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f12b7-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="f12b7-188">Wer kann die Upgradeskripts ausführen?</span><span class="sxs-lookup"><span data-stu-id="f12b7-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="f12b7-189">Personen mit globaler Administratorrechte oder Exchange-Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="f12b7-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="f12b7-190">Warum wird auf der Visitenkarte weiterhin eine Verteilerliste angezeigt?</span><span class="sxs-lookup"><span data-stu-id="f12b7-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="f12b7-191">Wie kann ich vorgehen, um zu verhindern, dass eine Verteilerliste, für die ein Upgrade ausgeführt wurde, in meiner Vorschlagssuche angezeigt wird?</span><span class="sxs-lookup"><span data-stu-id="f12b7-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="f12b7-192">Für Outlook: Wenn jemand versucht, eine e-Mail in Outlook zu senden, indem er den Microsoft 365-Gruppennamen nach der Migration eingibt, wird der Empfänger als Verteilerliste anstelle der Gruppe aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="f12b7-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="f12b7-193">Die Visitenkarte des Empfängers entspricht der Visitenkarte der Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="f12b7-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="f12b7-194">Der Grund hierfür liegt im Empfängercache oder "Spitznamen"-Cache von Outlook.</span><span class="sxs-lookup"><span data-stu-id="f12b7-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="f12b7-195">Die e-Mail wird erfolgreich an die Gruppe gesendet, kann jedoch zu Verwechslungen mit dem Absender führen.</span><span class="sxs-lookup"><span data-stu-id="f12b7-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="f12b7-196">Sie können die Schritte im Thema [Informationen zur AutoVervollständigen-Liste von Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) ausführen, um den Cache zurückzusetzen und das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="f12b7-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="f12b7-197">Für Outlook im Internet: im Fall von Outlook im Internet verbleiben die Empfänger der Verteilerliste weiterhin im Cache.</span><span class="sxs-lookup"><span data-stu-id="f12b7-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="f12b7-198">Sie können die Schritte unter [Entfernen des vorgeschlagenen namens oder der e-Mail-Adresse aus der Auto Vervollständigen-Liste](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) ausführen, um den Cache zu aktualisieren, um die Gruppen Visitenkarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f12b7-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="f12b7-199">Erhalten neue Gruppenmitglieder in ihrem Posteingang eine Willkommensnachricht?</span><span class="sxs-lookup"><span data-stu-id="f12b7-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="f12b7-p117">Nein. Die Einstellung zum Aktivieren von Willkommensnachrichten ist standardmäßig auf FALSE festgelegt. Diese Einstellung wirkt sich auf vorhandene und neue Gruppenmitglieder aus, die beitreten können, nachdem die Migration abgeschlossen wurde. Wenn der Besitzer der Gruppe später Gastbenutzer zulässt, empfangen Gastbenutzer keine Willkommensnachricht in ihrem Posteingang. Gastmitglieder können weiterhin mit der Gruppe zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f12b7-p117">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="f12b7-205">Was geschieht, wenn ein oder einige der DLS nicht aktualisiert werden?</span><span class="sxs-lookup"><span data-stu-id="f12b7-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="f12b7-206">Es gibt einige Fälle, in denen zwar DL berechtigt ist, aber nicht aktualisiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="f12b7-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="f12b7-207">Die Verteilerliste wird nicht aktualisiert und bleibt als DL erhalten.</span><span class="sxs-lookup"><span data-stu-id="f12b7-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="f12b7-208">Wo Administratoren eine **Gruppen-e-Mail-Adress Richtlinie** für die Gruppen in einer Organisation angewendet haben und versuchen, die Verteilerlisten zu aktualisieren, die die Kriterien nicht erfüllen, wird die Verteilerliste nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f12b7-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="f12b7-209">Verteilerlisten mit **MemberJoinRestriction** oder **MemberDepartRestriction** , die auf **geschlossen**festgelegt wurden, konnten nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f12b7-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="f12b7-210">Was geschieht mit der Verteilerliste, wenn beim Upgrade aus EAC ein Fehler auftritt?</span><span class="sxs-lookup"><span data-stu-id="f12b7-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="f12b7-p119">Das Upgrade erfolgt nur, wenn der Aufruf an den Server übermittelt wird. Wenn beim Upgrade ein Fehler auftritt, bleiben Ihre Verteilerlisten erhalten. Sie funktionieren wie bisher.</span><span class="sxs-lookup"><span data-stu-id="f12b7-p119">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>


