---
title: Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Erfahren Sie, wie Sie eine oder mehrere Verteilerlisten auf Microsoft 365 Gruppen in Outlook aktualisieren und wie Sie PowerShell verwenden, um mehrere Verteilerlisten gleichzeitig zu aktualisieren.
ms.openlocfilehash: aef797a2bf052fcc84c9220993c2e6706eae5f61
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391387"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="33ae7-103">Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="33ae7-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="33ae7-104">Sie können Verteilerlisten auf Microsoft 365 Gruppen in Outlook aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="33ae7-104">You can upgrade distribution lists to Microsoft 365 Groups in Outlook.</span></span> <span data-ttu-id="33ae7-105">Dies ist eine großartige Möglichkeit, um den Verteilerlisten Ihrer Organisation alle Features und Funktionen von Microsoft 365-Gruppen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="33ae7-106">Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten</span><span class="sxs-lookup"><span data-stu-id="33ae7-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="33ae7-107">Sie können ein Upgrade für eine einzelne Verteilerliste oder für mehrere Verteilerlisten gleichzeitig ausführen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="33ae7-108">Aktualisieren einer oder mehrerer Verteilerlistengruppen auf Microsoft 365 Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="33ae7-108">Upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="33ae7-109">Sie müssen ein globaler Administrator oder Exchange Administrator sein, um ein Upgrade einer Verteilerlistengruppe durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-109">You must be a global admin or Exchange admin to upgrade a distribution list group.</span></span> <span data-ttu-id="33ae7-110">Um auf Microsoft 365 Gruppen zu aktualisieren, muss die Verteilerlistengruppe über einen Besitzer mit einem Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-110">To upgrade to Microsoft 365 Groups, the distribution list group must have an owner with a mailbox.</span></span>

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="33ae7-111">Verwenden sie das neue EAC, um eine oder viele Verteilerlistengruppen auf Microsoft 365 Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="33ae7-111">Use the new EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="33ae7-112">Wechseln Sie zum neuen [Exchange Admin Center,](https://admin.exchange.microsoft.com)und navigieren Sie zu  \> **Empfängergruppen.**</span><span class="sxs-lookup"><span data-stu-id="33ae7-112">Go to the new [Exchange admin center](https://admin.exchange.microsoft.com), and navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="33ae7-113">Wählen Sie auf der Seite **"Gruppen"** die Verteilerlistengruppe (auch **Verteilergruppe** genannt) aus, die Sie auf Microsoft 365 Gruppe aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="33ae7-113">Select the distribution list group (also called a **distribution group**) that you want to upgrade to Microsoft 365 group from the **Groups** page.</span></span>

3. <span data-ttu-id="33ae7-114">Wählen Sie die **Verteilergruppe "Upgrade"** in der Toolleiste aus.</span><span class="sxs-lookup"><span data-stu-id="33ae7-114">Select the **Upgrade distribution group** from the tool bar.</span></span>

4. <span data-ttu-id="33ae7-115">Klicken Sie im Dialogfeld **Bereit für das Upgrade?** auf **"Upgrade".**</span><span class="sxs-lookup"><span data-stu-id="33ae7-115">In the dialog box **Ready to upgrade?**, click **Upgrade**.</span></span> <span data-ttu-id="33ae7-116">Der Prozess beginnt sofort.</span><span class="sxs-lookup"><span data-stu-id="33ae7-116">The process begins immediately.</span></span> <span data-ttu-id="33ae7-117">Je nach Größe und Anzahl der Verteilerlistengruppen, die Sie aktualisieren, kann der Vorgang Minuten oder Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="33ae7-117">Depending on the size and number of distribution list groups you're upgrading, the process can take minutes or hours.</span></span>

> [!NOTE]
> <span data-ttu-id="33ae7-118">Ein Banner oben zeigt das Upgrade an, z. B. *verteilergruppen wurden aktualisiert. Es dauert 5 Minuten, um die Änderungen widerzuspiegeln. Filtern Sie nach Microsoft 365 Gruppen, um die aktualisierten Distrubtionsgruppen anzuzeigen.*</span><span class="sxs-lookup"><span data-stu-id="33ae7-118">A banner at the top indicates the upgrade, for example, *Distribution group(s) has been upgraded. It will take 5 minutes to reflect the changes. Filter by Microsoft 365 groups to see the upgraded distrubtion groups(s)*.</span></span>

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="33ae7-119">Verwenden des klassischen EAC, um eine oder viele Verteilerlistengruppen auf Microsoft 365 Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="33ae7-119">Use the Classic EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="33ae7-120">Wechseln Sie zum klassischen <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center.</a></span><span class="sxs-lookup"><span data-stu-id="33ae7-120">Go to the Classic <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="33ae7-121">Wechseln Sie im klassischen Exchange Admin  Center zu \> **Empfängergruppen.**</span><span class="sxs-lookup"><span data-stu-id="33ae7-121">In the Classic Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="33ae7-122">Es wird ein Hinweis angezeigt, der angibt, dass Sie Verteilerlisten (auch **verteilergruppen** genannt) haben, die für das Upgrade auf Microsoft 365 Gruppen berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="33ae7-122">You'll see a notice indicating you have distribution lists (also called **distribution groups**) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="33ae7-123">![Wählen Sie die Schaltfläche "Erste Schritte" aus.](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="33ae7-123">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="33ae7-124">Wählen Sie auf **der** Gruppenseite eine oder mehrere Verteilerlisten (auch **Verteilergruppe** genannt) aus.</span><span class="sxs-lookup"><span data-stu-id="33ae7-124">Select one or more distribution lists (also called a **distribution group**) from the **groups** page.</span></span><br/><span data-ttu-id="33ae7-125">![Auswählen einer Verteilergruppe](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="33ae7-125">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="33ae7-126">Wählen Sie das Upgradesymbol aus.</span><span class="sxs-lookup"><span data-stu-id="33ae7-126">Select the upgrade icon.</span></span><br/>![Symbol "Auf Microsoft 365 Gruppen aktualisieren"](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="33ae7-128">Wählen Sie im Dialogfeld "Informationen" die Option **"Ja"** aus, um das Upgrade zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-128">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="33ae7-129">Der Prozess beginnt sofort.</span><span class="sxs-lookup"><span data-stu-id="33ae7-129">The process begins immediately.</span></span> <span data-ttu-id="33ae7-130">Je nach Größe und Anzahl der DLs, die Sie aktualisieren, kann der Vorgang Minuten oder Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="33ae7-130">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="33ae7-131">Wenn für die Verteilerliste kein Upgrade ausgeführt werden kann, wird ein Dialogfeld mit einer entsprechenden Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33ae7-131">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="33ae7-132">Siehe [Welche Verteilerlisten können nicht aktualisiert werden?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="33ae7-132">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="33ae7-133">Wenn Sie mehrere Verteilerlisten aktualisieren, verwenden Sie die Dropdownliste, um zu filtern, welche Verteilerlisten aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33ae7-133">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="33ae7-134">Wenn die Liste nicht abgeschlossen ist, warten Sie eine Weile, und wählen Sie **"Aktualisieren"** aus, um zu sehen, was erfolgreich aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="33ae7-134">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="33ae7-p107">Es wird keine Benachrichtigung ausgegeben, die Sie informiert, wann das Upgrade für alle ausgewählten Verteilerlisten abgeschlossen wurde. Sie können dies jedoch herausfinden, indem Sie die Elemente untersuchen, die unter **Für Upgrade verfügbar** oder **Aktualisierte Verteilerlisten** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="33ae7-p107">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="33ae7-137">Wenn Sie eine DL für das Upgrade ausgewählt haben, diese jedoch weiterhin auf der Seite als für das Upgrade verfügbar angezeigt wird, konnte das Upgrade nicht durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33ae7-137">If you selected a DL for upgrade, but it's still appeared on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="33ae7-138">Lesen Sie in diesem Fall [Wie gehe ich vor, wenn das Upgrade nicht funktioniert?](#what-to-do-if-the-upgrade-doesnt-work)</span><span class="sxs-lookup"><span data-stu-id="33ae7-138">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="33ae7-p109">Wenn Sie die Digest-E-Mails der Gruppen erhalten, wird im unteren Bereich ggf. angeboten, ein Upgrade für alle geeigneten Verteilerlisten auszuführen, deren Besitzer Sie sind. Weitere Informationen zu Digest-E-Mails finden Sie unter [Führen einer Gruppenunterhaltung in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).</span><span class="sxs-lookup"><span data-stu-id="33ae7-p109">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="33ae7-141">Wie gehe ich vor, wenn das Upgrade nicht funktioniert?</span><span class="sxs-lookup"><span data-stu-id="33ae7-141">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="33ae7-142">Verteilerlisten, für die beim Upgrade ein Fehler auftritt, bleiben unverändert.</span><span class="sxs-lookup"><span data-stu-id="33ae7-142">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="33ae7-p110">Wenn für mindestens eine **geeignete** Verteilerliste beim Upgrade ein Fehler auftritt, öffnen Sie ein [Supportticket](../../business-video/get-help-support.md). Das Problem muss an das Gruppenentwicklungsteam eskaliert werden, damit dieses das Problem ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="33ae7-p110">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../../business-video/get-help-support.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="33ae7-145">Es ist möglich, dass die Verteilerliste aufgrund eines Dienstausfalls nicht aktualisiert wurde, aber unwahrscheinlich.</span><span class="sxs-lookup"><span data-stu-id="33ae7-145">It's possible that the distribution list didn't get upgraded because of a service outage, but unlikely.</span></span> <span data-ttu-id="33ae7-146">Wenn Sie möchten, warten Sie eine Weile, und versuchen Sie dann erneut, die DL zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="33ae7-146">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="33ae7-147">Verwenden von PowerShell zum gleichzeitigen Ausführen eines Upgrades mehrerer Verteilerlisten</span><span class="sxs-lookup"><span data-stu-id="33ae7-147">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="33ae7-148">Wenn Sie im Umgang mit PowerShell erfahren sind, können Sie diese Methode anstelle der Benutzeroberfläche verwenden.</span><span class="sxs-lookup"><span data-stu-id="33ae7-148">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="33ae7-149">Wir verfügen über eine Reihe von Cmdlets, die Ihnen beim Upgrade von Verteilerlisten helfen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-149">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="33ae7-150">Siehe unten.</span><span class="sxs-lookup"><span data-stu-id="33ae7-150">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="33ae7-151">Upgrade einer einzelnen DL</span><span class="sxs-lookup"><span data-stu-id="33ae7-151">Upgrade a single DL</span></span>

<span data-ttu-id="33ae7-152">Führen Sie den folgenden Befehl aus, um ein einzelnes DL zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="33ae7-152">To upgrade a single DL, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

<span data-ttu-id="33ae7-153">Wenn Sie beispielsweise eine DL mit SMTP-Adresse dl1@contoso.com aktualisieren möchten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="33ae7-153">For example, if you want to upgrade a DL with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> <span data-ttu-id="33ae7-154">Sie können auch eine einzelne Verteilerliste auf eine Microsoft 365 Gruppe aktualisieren, indem Sie das [PowerShell-Cmdlet "New-UnifiedGroup"](/powershell/module/exchange/new-unifiedgroup) verwenden.</span><span class="sxs-lookup"><span data-stu-id="33ae7-154">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="33ae7-155">Upgrade mehrerer DLs in einem Batch</span><span class="sxs-lookup"><span data-stu-id="33ae7-155">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="33ae7-156">Sie können auch mehrere DLs als Batch übergeben und gemeinsam aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="33ae7-156">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

<span data-ttu-id="33ae7-157">Wenn Sie beispielsweise fünf DLs mit SMTP-Adresse aktualisieren möchten, führen Sie `dl1@contoso.com` `dl2@contoso.com` den folgenden Befehl `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` aus:</span><span class="sxs-lookup"><span data-stu-id="33ae7-157">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="33ae7-158">Aktualisieren aller berechtigten DLs</span><span class="sxs-lookup"><span data-stu-id="33ae7-158">Upgrade all eligible DLs</span></span>

<span data-ttu-id="33ae7-159">Es gibt zwei Möglichkeiten, um alle berechtigten DLs zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="33ae7-159">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="33ae7-160">Das cmdlet Upgrade-DistributionGroup empfängt keine Daten aus der Pipeline. Aus diesem Grund muss der Operator "foreach-object" verwendet {} werden, um erfolgreich ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="33ae7-160">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="33ae7-161">Rufen Sie die berechtigten DLs im Mandanten ab, und aktualisieren Sie sie mithilfe des Upgradebefehls:</span><span class="sxs-lookup"><span data-stu-id="33ae7-161">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="33ae7-162">Rufen Sie die Liste aller DLs ab, und aktualisieren Sie nur die berechtigten DLs:</span><span class="sxs-lookup"><span data-stu-id="33ae7-162">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="33ae7-163">Häufig gestellte Fragen zum Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="33ae7-163">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="33ae7-164">Welche Verteilerlisten können nicht aktualisiert werden?</span><span class="sxs-lookup"><span data-stu-id="33ae7-164">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="33ae7-165">Sie können nur für in der Cloud verwaltete, einfache, nicht geschachtelte Verteilerlisten ein Upgrade ausführen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-165">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="33ae7-166">In der folgenden Tabelle sind Verteilerlisten aufgeführt, die nicht aktualisiert werden **können.**</span><span class="sxs-lookup"><span data-stu-id="33ae7-166">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="33ae7-167">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="33ae7-167">**Property**</span></span>|<span data-ttu-id="33ae7-168">**Geeignet?**</span><span class="sxs-lookup"><span data-stu-id="33ae7-168">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33ae7-169">Lokal verwaltete Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="33ae7-169">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="33ae7-170">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-170">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-p114">Geschachtelte Verteilerliste. Die Verteilerliste hat untergeordnete Gruppen oder ist Mitglied einer anderen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="33ae7-p114">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="33ae7-173">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-173">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-174">Verteilerlisten mit member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="33ae7-174">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="33ae7-175">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-175">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-176">Verteilerliste mit mehr als 100 Besitzern</span><span class="sxs-lookup"><span data-stu-id="33ae7-176">Distribution list that has more than 100 owners</span></span>  <br/> |<span data-ttu-id="33ae7-177">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-177">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-178">Verteilerliste, die nur Mitglieder, aber keinen Besitzer hat</span><span class="sxs-lookup"><span data-stu-id="33ae7-178">Distribution list that only has members but no owner</span></span>  <br/> |<span data-ttu-id="33ae7-179">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-179">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-180">Verteilerliste mit Alias mit Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="33ae7-180">Distribution list that has alias containing special characters</span></span>  <br/> |<span data-ttu-id="33ae7-181">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-181">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-182">Die Verteilerliste ist als Weiterleitungsadresse für das freigegebene Postfach konfiguriert</span><span class="sxs-lookup"><span data-stu-id="33ae7-182">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="33ae7-183">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-183">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-184">Wenn die DL Teil der **Absendereinschränkung** in einer anderen DL ist.</span><span class="sxs-lookup"><span data-stu-id="33ae7-184">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="33ae7-185">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-185">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-186">Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="33ae7-186">Security groups</span></span>  <br/> |<span data-ttu-id="33ae7-187">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-187">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-188">Dynamische Verteilerlisten</span><span class="sxs-lookup"><span data-stu-id="33ae7-188">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="33ae7-189">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-189">No</span></span>  <br/> |
|<span data-ttu-id="33ae7-190">Verteilerlisten, die in **RoomLists** konvertiert wurden</span><span class="sxs-lookup"><span data-stu-id="33ae7-190">Distribution lists that were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="33ae7-191">Nein</span><span class="sxs-lookup"><span data-stu-id="33ae7-191">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="33ae7-192">Überprüfen, welche DLs für ein Upgrade berechtigt sind</span><span class="sxs-lookup"><span data-stu-id="33ae7-192">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="33ae7-193">Wenn Sie überprüfen möchten, ob eine DL berechtigt ist oder nicht, können Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="33ae7-193">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="33ae7-194">Wenn Sie überprüfen möchten, welche DLs für das Upgrade berechtigt sind, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="33ae7-194">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="33ae7-195">Wer kann die Upgradeskripts ausführen?</span><span class="sxs-lookup"><span data-stu-id="33ae7-195">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="33ae7-196">Personen mit globalen Administratorrechten oder Exchange Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="33ae7-196">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="33ae7-197">Warum wird auf der Visitenkarte weiterhin eine Verteilerliste angezeigt?</span><span class="sxs-lookup"><span data-stu-id="33ae7-197">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="33ae7-198">Was soll ich tun, um zu verhindern, dass eine aktualisierte Verteilerliste in meiner Liste mit automatischen Vorschlägen angezeigt wird?</span><span class="sxs-lookup"><span data-stu-id="33ae7-198">What should I do to prevent an upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="33ae7-199">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span><span class="sxs-lookup"><span data-stu-id="33ae7-199">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="33ae7-200">Die Visitenkarte des Empfängers entspricht der Visitenkarte der Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="33ae7-200">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="33ae7-201">Der Grund hierfür liegt im Empfängercache oder "Spitznamen"-Cache von Outlook.</span><span class="sxs-lookup"><span data-stu-id="33ae7-201">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="33ae7-202">Die E-Mail wird erfolgreich an die Gruppe gesendet, kann jedoch zu Verwirrung für den Absender führen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-202">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="33ae7-203">Sie können die Schritte in diesem Artikel ausführen, [Informationen zum Outlook AutoVervollständigen-Liste,](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) um den Cache zurückzusetzen, wodurch dieses Problem behoben wird.</span><span class="sxs-lookup"><span data-stu-id="33ae7-203">You can perform the steps in this article, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="33ae7-204">Für Outlook im Web: Bei Outlook im Web verbleibt der Empfänger der Verteilerliste weiterhin im Cache.</span><span class="sxs-lookup"><span data-stu-id="33ae7-204">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="33ae7-205">Sie können die Schritte unter ["Vorgeschlagenen Namen oder E-Mail-Adresse entfernen" aus der AutoVervollständigen-Liste](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) ausführen, um den Cache zu aktualisieren, um die Visitenkarte der Gruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="33ae7-205">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="33ae7-206">Erhalten neue Gruppenmitglieder in ihrem Posteingang eine Willkommensnachricht?</span><span class="sxs-lookup"><span data-stu-id="33ae7-206">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="33ae7-p118">Nein. Die Einstellung zum Aktivieren von Willkommensnachrichten ist standardmäßig auf FALSE festgelegt. Diese Einstellung wirkt sich auf vorhandene und neue Gruppenmitglieder aus, die beitreten können, nachdem die Migration abgeschlossen wurde. Wenn der Besitzer der Gruppe später Gastbenutzer zulässt, empfangen Gastbenutzer keine Willkommensnachricht in ihrem Posteingang. Gastmitglieder können weiterhin mit der Gruppe zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="33ae7-p118">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="33ae7-212">Was geschieht, wenn eine oder einige der DLs nicht aktualisiert werden?</span><span class="sxs-lookup"><span data-stu-id="33ae7-212">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="33ae7-213">Es gibt einige Fälle, in denen DL zwar berechtigt ist, aber nicht aktualisiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="33ae7-213">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="33ae7-214">Die DL wird nicht aktualisiert und bleibt als DL erhalten.</span><span class="sxs-lookup"><span data-stu-id="33ae7-214">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="33ae7-215">Wenn der Administrator die **Gruppen-E-Mail-Adressrichtlinie** für die Gruppen in einer Organisation angewendet hat und versucht, DLs zu aktualisieren, die die Kriterien nicht erfüllen, wird die DL nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="33ae7-215">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs that doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="33ae7-216">DLs, bei **denen "MemberJoinRestriction"** oder **"MemberDepartRestriction"** auf **"Closed"** festgelegt ist, konnten nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="33ae7-216">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="33ae7-217">Was geschieht mit der Verteilerliste, wenn beim Upgrade aus EAC ein Fehler auftritt?</span><span class="sxs-lookup"><span data-stu-id="33ae7-217">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="33ae7-p120">Das Upgrade erfolgt nur, wenn der Aufruf an den Server übermittelt wird. Wenn beim Upgrade ein Fehler auftritt, bleiben Ihre Verteilerlisten erhalten. Sie funktionieren wie bisher.</span><span class="sxs-lookup"><span data-stu-id="33ae7-p120">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>

## <a name="related-content"></a><span data-ttu-id="33ae7-221">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="33ae7-221">Related content</span></span>

<span data-ttu-id="33ae7-222">[Vergleichen von Gruppen](../create-groups/compare-groups.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="33ae7-222">[Compare groups](../create-groups/compare-groups.md) (article)</span></span>\
<span data-ttu-id="33ae7-223">[Erläutern Microsoft 365 Gruppen für Ihre Benutzer](../create-groups/explain-groups-knowledge-worker.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="33ae7-223">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
[<span data-ttu-id="33ae7-224">Hinzufügen oder Entfernen von Mitgliedern aus Microsoft 365 Gruppen mithilfe des Admin Centers</span><span class="sxs-lookup"><span data-stu-id="33ae7-224">Add or remove members from Microsoft 365 groups using the admin center</span></span>](../create-groups/add-or-remove-members-from-groups.md)
