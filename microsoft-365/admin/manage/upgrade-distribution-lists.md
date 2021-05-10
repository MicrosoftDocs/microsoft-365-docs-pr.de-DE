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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Erfahren Sie, wie Sie eine oder mehrere Verteilerlisten auf Microsoft 365 Gruppen in Outlook aktualisieren und wie Sie PowerShell verwenden, um mehrere Verteilerlisten gleichzeitig zu aktualisieren.
ms.openlocfilehash: 72a98cdfda441dc71fcc5ae21f0042dafef3aefb
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297080"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e10b2-103">Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="e10b2-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="e10b2-104">Sie können Verteilerlisten auf Microsoft 365 Gruppen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="e10b2-104">You can upgrade distribution lists to Microsoft 365 Groups in Outlook.</span></span> <span data-ttu-id="e10b2-105">Dies ist eine hervorragende Möglichkeit, um den Verteilerlisten Ihrer Organisation alle Features und Funktionen von Microsoft 365 zu geben.</span><span class="sxs-lookup"><span data-stu-id="e10b2-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="e10b2-106">Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten</span><span class="sxs-lookup"><span data-stu-id="e10b2-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="e10b2-107">Sie können ein Upgrade für eine einzelne Verteilerliste oder für mehrere Verteilerlisten gleichzeitig ausführen.</span><span class="sxs-lookup"><span data-stu-id="e10b2-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e10b2-108">Aktualisieren Sie eine oder mehrere Verteilerlistengruppen auf Microsoft 365 Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="e10b2-108">Upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="e10b2-109">Sie müssen ein globaler Administrator oder Exchange administrator sein, um eine Verteilerlistengruppe aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="e10b2-109">You must be a global admin or Exchange admin to upgrade a distribution list group.</span></span> <span data-ttu-id="e10b2-110">Zum Upgrade auf Microsoft 365 Gruppen muss die Verteilerlistengruppe über einen Besitzer mit einem Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="e10b2-110">To upgrade to Microsoft 365 Groups, the distribution list group must have an owner with a mailbox.</span></span>

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e10b2-111">Verwenden Sie die neue EAC, um eine oder mehrere Verteilerlistengruppen auf Microsoft 365 gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="e10b2-111">Use the new EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="e10b2-112">Wechseln Sie zum neuen [Exchange Admin Center,](https://admin.exchange.microsoft.com)und navigieren Sie zu  \> **Empfängergruppen**.</span><span class="sxs-lookup"><span data-stu-id="e10b2-112">Go to the new [Exchange admin center](https://admin.exchange.microsoft.com), and navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="e10b2-113">Wählen Sie auf der Seite Gruppen die Verteilerlistengruppe (auch Verteilergruppe **genannt)** aus, die Sie auf Microsoft 365 Gruppe **aktualisieren** möchten.</span><span class="sxs-lookup"><span data-stu-id="e10b2-113">Select the distribution list group (also called a **distribution group**) that you want to upgrade to Microsoft 365 group from the **Groups** page.</span></span>

3. <span data-ttu-id="e10b2-114">Wählen Sie **auf der Toolleiste** die Verteilergruppe Upgrade aus.</span><span class="sxs-lookup"><span data-stu-id="e10b2-114">Select the **Upgrade distribution group** from the tool bar.</span></span>

4. <span data-ttu-id="e10b2-115">Klicken Sie im Dialogfeld **Bereit zum Upgrade?** auf **Upgrade**.</span><span class="sxs-lookup"><span data-stu-id="e10b2-115">In the dialog box **Ready to upgrade?**, click **Upgrade**.</span></span> <span data-ttu-id="e10b2-116">Der Prozess beginnt sofort.</span><span class="sxs-lookup"><span data-stu-id="e10b2-116">The process begins immediately.</span></span> <span data-ttu-id="e10b2-117">Je nach Größe und Anzahl der Verteilerlistengruppen, die Sie aktualisieren, kann der Vorgang Minuten oder Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="e10b2-117">Depending on the size and number of distribution list groups you're upgrading, the process can take minutes or hours.</span></span>

> [!NOTE]
> <span data-ttu-id="e10b2-118">Ein Banner oben zeigt das Upgrade an, z. B. wurde ein Upgrade für *Verteilergruppen durchgeführt. Es dauert 5 Minuten, bis die Änderungen widerspiegelt werden. Filtern Sie nach Microsoft 365 Gruppen, um die aktualisierten Distrubtionsgruppen (en) zu sehen.*</span><span class="sxs-lookup"><span data-stu-id="e10b2-118">A banner at the top indicates the upgrade, for example, *Distribution group(s) has been upgraded. It will take 5 minutes to reflect the changes. Filter by Microsoft 365 groups to see the upgraded distrubtion groups(s)*.</span></span>

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e10b2-119">Verwenden Sie die klassische EAC, um eine oder mehrere Verteilerlistengruppen auf Microsoft 365 gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="e10b2-119">Use the Classic EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="e10b2-120">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">klassischen Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="e10b2-120">Go to the Classic <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="e10b2-121">Wechseln Sie im Exchange Admin Center  zu \> **Empfängergruppen**.</span><span class="sxs-lookup"><span data-stu-id="e10b2-121">In the Classic Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="e10b2-122">Es wird eine Meldung angezeigt, dass Sie Verteilerlisten (auch Verteilergruppen **genannt)** haben, die berechtigt sind, ein Upgrade auf Microsoft 365 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e10b2-122">You'll see a notice indicating you have distribution lists (also called **distribution groups**) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="e10b2-123">![Wählen Sie die Schaltfläche Erste Schritte aus.](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="e10b2-123">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="e10b2-124">Wählen Sie auf der Seite Gruppen eine oder mehrere Verteilerlisten (auch **Verteilergruppe genannt)** aus.</span><span class="sxs-lookup"><span data-stu-id="e10b2-124">Select one or more distribution lists (also called a **distribution group**) from the **groups** page.</span></span><br/><span data-ttu-id="e10b2-125">![Auswählen einer Verteilergruppe](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="e10b2-125">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="e10b2-126">Wählen Sie das Upgradesymbol aus.</span><span class="sxs-lookup"><span data-stu-id="e10b2-126">Select the upgrade icon.</span></span><br/>![Upgrade auf Microsoft 365 Gruppensymbol](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="e10b2-128">Wählen Sie im Dialogfeld Informationen **Ja** aus, um das Upgrade zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="e10b2-128">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="e10b2-129">Der Prozess beginnt sofort.</span><span class="sxs-lookup"><span data-stu-id="e10b2-129">The process begins immediately.</span></span> <span data-ttu-id="e10b2-130">Je nach Größe und Anzahl der DLs, die Sie aktualisieren, kann der Prozess Minuten oder Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="e10b2-130">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="e10b2-131">Wenn für die Verteilerliste kein Upgrade ausgeführt werden kann, wird ein Dialogfeld mit einer entsprechenden Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e10b2-131">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="e10b2-132">Weitere [Informationen finden Sie unter Welche Verteilerlisten können nicht aktualisiert werden?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="e10b2-132">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="e10b2-133">Wenn Sie mehrere Verteilerlisten aktualisieren, verwenden Sie die Dropdownliste, um zu filtern, welche Verteilerlisten aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e10b2-133">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="e10b2-134">Wenn die Liste nicht vollständig ist, warten Sie  etwas länger, und wählen Sie Aktualisieren aus, um zu sehen, was erfolgreich aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e10b2-134">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="e10b2-p107">Es wird keine Benachrichtigung ausgegeben, die Sie informiert, wann das Upgrade für alle ausgewählten Verteilerlisten abgeschlossen wurde. Sie können dies jedoch herausfinden, indem Sie die Elemente untersuchen, die unter **Für Upgrade verfügbar** oder **Aktualisierte Verteilerlisten** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e10b2-p107">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="e10b2-137">Wenn Sie eine DL für das Upgrade ausgewählt haben, sie jedoch weiterhin auf der Seite als Verfügbar für ein Upgrade angezeigt wird, konnte sie nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e10b2-137">If you selected a DL for upgrade, but it's still appeared on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="e10b2-138">Lesen Sie in diesem Fall [Wie gehe ich vor, wenn das Upgrade nicht funktioniert?](#what-to-do-if-the-upgrade-doesnt-work)</span><span class="sxs-lookup"><span data-stu-id="e10b2-138">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="e10b2-p109">Wenn Sie die Digest-E-Mails der Gruppen erhalten, wird im unteren Bereich ggf. angeboten, ein Upgrade für alle geeigneten Verteilerlisten auszuführen, deren Besitzer Sie sind. Weitere Informationen zu Digest-E-Mails finden Sie unter [Führen einer Gruppenunterhaltung in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).</span><span class="sxs-lookup"><span data-stu-id="e10b2-p109">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="e10b2-141">Wie gehe ich vor, wenn das Upgrade nicht funktioniert?</span><span class="sxs-lookup"><span data-stu-id="e10b2-141">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="e10b2-142">Verteilerlisten, für die beim Upgrade ein Fehler auftritt, bleiben unverändert.</span><span class="sxs-lookup"><span data-stu-id="e10b2-142">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="e10b2-p110">Wenn für mindestens eine **geeignete** Verteilerliste beim Upgrade ein Fehler auftritt, öffnen Sie ein [Supportticket](../../business-video/get-help-support.md). Das Problem muss an das Gruppenentwicklungsteam eskaliert werden, damit dieses das Problem ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="e10b2-p110">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../../business-video/get-help-support.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="e10b2-145">Es ist möglich, dass die Verteilerliste aufgrund eines Dienstausfalls nicht aktualisiert wurde, aber unwahrscheinlich.</span><span class="sxs-lookup"><span data-stu-id="e10b2-145">It's possible that the distribution list didn't get upgraded because of a service outage, but unlikely.</span></span> <span data-ttu-id="e10b2-146">Warten Sie, falls sie möchten, eine Weile, und versuchen Sie dann, die DL erneut zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e10b2-146">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="e10b2-147">Verwenden von PowerShell zum gleichzeitigen Ausführen eines Upgrades mehrerer Verteilerlisten</span><span class="sxs-lookup"><span data-stu-id="e10b2-147">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="e10b2-148">Wenn Sie im Umgang mit PowerShell erfahren sind, können Sie diese Methode anstelle der Benutzeroberfläche verwenden.</span><span class="sxs-lookup"><span data-stu-id="e10b2-148">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="e10b2-149">Wir verfügen über eine Reihe von Cmdlets, mit deren Hilfe Sie Verteilerlisten aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="e10b2-149">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="e10b2-150">Siehe unten.</span><span class="sxs-lookup"><span data-stu-id="e10b2-150">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="e10b2-151">Upgrade einer einzelnen DL</span><span class="sxs-lookup"><span data-stu-id="e10b2-151">Upgrade a single DL</span></span>

<span data-ttu-id="e10b2-152">Führen Sie zum Aktualisieren einer einzelnen DL den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e10b2-152">To upgrade a single DL, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="e10b2-153">Wenn Sie z. B. ein Upgrade einer DLs mit SMTP-Dl1@contoso.com möchten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e10b2-153">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="e10b2-154">Mit dem [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell-Cmdlet können Sie auch eine einzelne Verteilerliste auf eine Microsoft 365 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e10b2-154">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="e10b2-155">Upgrade mehrerer DLs in einem Batch</span><span class="sxs-lookup"><span data-stu-id="e10b2-155">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="e10b2-156">Sie können auch mehrere DLs als Batch übergeben und gemeinsam aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="e10b2-156">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="e10b2-157">Wenn Sie beispielsweise fünf DLs mit SMTP-Adresse und , und aktualisieren möchten, führen `dl1@contoso.com` Sie den folgenden Befehl `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` aus:</span><span class="sxs-lookup"><span data-stu-id="e10b2-157">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="e10b2-158">Upgrade aller berechtigten DLs</span><span class="sxs-lookup"><span data-stu-id="e10b2-158">Upgrade all eligible DLs</span></span>

<span data-ttu-id="e10b2-159">Es gibt zwei Möglichkeiten, wie Sie alle berechtigten DLs aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="e10b2-159">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="e10b2-160">Das Upgrade-DistributionGroup-Cmdlet erhält keine Daten von der Pipeline, daher muss es den Operator "foreach-object" verwenden, um {} erfolgreich ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="e10b2-160">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="e10b2-161">Holen Sie sich die berechtigten DLs im Mandanten, und aktualisieren Sie sie mithilfe des Upgradebefehls:</span><span class="sxs-lookup"><span data-stu-id="e10b2-161">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="e10b2-162">Hier erhalten Sie die Liste aller DLs, und aktualisieren Sie nur die berechtigten DLs:</span><span class="sxs-lookup"><span data-stu-id="e10b2-162">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e10b2-163">Häufig gestellte Fragen zum Upgrade von Verteilerlisten Microsoft 365 Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="e10b2-163">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="e10b2-164">Welche Verteilerlisten können nicht aktualisiert werden?</span><span class="sxs-lookup"><span data-stu-id="e10b2-164">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="e10b2-165">Sie können nur für in der Cloud verwaltete, einfache, nicht geschachtelte Verteilerlisten ein Upgrade ausführen.</span><span class="sxs-lookup"><span data-stu-id="e10b2-165">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="e10b2-166">In der folgenden Tabelle sind Verteilerlisten aufgeführt, die **NICHT aktualisiert** werden können.</span><span class="sxs-lookup"><span data-stu-id="e10b2-166">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="e10b2-167">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="e10b2-167">**Property**</span></span>|<span data-ttu-id="e10b2-168">**Geeignet?**</span><span class="sxs-lookup"><span data-stu-id="e10b2-168">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e10b2-169">Lokal verwaltete Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="e10b2-169">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="e10b2-170">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-170">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-p114">Geschachtelte Verteilerliste. Die Verteilerliste hat untergeordnete Gruppen oder ist Mitglied einer anderen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="e10b2-p114">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="e10b2-173">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-173">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-174">Verteilerlisten mit dem Mitglied **RecipientTypeDetails,** mit Ausnahme **von UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="e10b2-174">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="e10b2-175">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-175">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-176">Verteilerliste mit mehr als 100 Besitzern</span><span class="sxs-lookup"><span data-stu-id="e10b2-176">Distribution list that has more than 100 owners</span></span>  <br/> |<span data-ttu-id="e10b2-177">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-177">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-178">Verteilerliste, die nur Mitglieder, aber keinen Besitzer hat</span><span class="sxs-lookup"><span data-stu-id="e10b2-178">Distribution list that only has members but no owner</span></span>  <br/> |<span data-ttu-id="e10b2-179">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-179">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-180">Verteilerliste mit Alias mit Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="e10b2-180">Distribution list that has alias containing special characters</span></span>  <br/> |<span data-ttu-id="e10b2-181">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-181">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-182">Die Verteilerliste ist als Weiterleitungsadresse für das freigegebene Postfach konfiguriert</span><span class="sxs-lookup"><span data-stu-id="e10b2-182">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="e10b2-183">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-183">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-184">Wenn die DL Teil der **Absendereinschränkung** in einer anderen DL ist.</span><span class="sxs-lookup"><span data-stu-id="e10b2-184">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="e10b2-185">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-185">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-186">Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="e10b2-186">Security groups</span></span>  <br/> |<span data-ttu-id="e10b2-187">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-187">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-188">Dynamische Verteilerlisten</span><span class="sxs-lookup"><span data-stu-id="e10b2-188">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="e10b2-189">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-189">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-190">Verteilerlisten, die in **RoomLists konvertiert wurden**</span><span class="sxs-lookup"><span data-stu-id="e10b2-190">Distribution lists that were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="e10b2-191">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-191">No</span></span>  <br/> |
|<span data-ttu-id="e10b2-192">Verteilerlisten, in denen **MemberJoinRestriction** und/oder **MemberDepartRestriction** geschlossen **ist**</span><span class="sxs-lookup"><span data-stu-id="e10b2-192">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="e10b2-193">Nein</span><span class="sxs-lookup"><span data-stu-id="e10b2-193">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="e10b2-194">Überprüfen, welche DLs für ein Upgrade berechtigt sind</span><span class="sxs-lookup"><span data-stu-id="e10b2-194">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="e10b2-195">Wenn Sie überprüfen möchten, ob eine DL berechtigt ist oder nicht, können Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="e10b2-195">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="e10b2-196">Wenn Sie überprüfen möchten, welche DLs für ein Upgrade berechtigt sind, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e10b2-196">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="e10b2-197">Wer kann die Upgradeskripts ausführen?</span><span class="sxs-lookup"><span data-stu-id="e10b2-197">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="e10b2-198">Personen mit globalen Administrator- oder Exchange Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="e10b2-198">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="e10b2-199">Warum wird auf der Visitenkarte weiterhin eine Verteilerliste angezeigt?</span><span class="sxs-lookup"><span data-stu-id="e10b2-199">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="e10b2-200">Was soll ich tun, um zu verhindern, dass eine aktualisierte Verteilerliste in meiner Liste für automatische Vorschläge angezeigt wird?</span><span class="sxs-lookup"><span data-stu-id="e10b2-200">What should I do to prevent an upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="e10b2-201">For Outlook: When someone tries to send an email in Outlook by tipping the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span><span class="sxs-lookup"><span data-stu-id="e10b2-201">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="e10b2-202">Die Visitenkarte des Empfängers entspricht der Visitenkarte der Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="e10b2-202">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="e10b2-203">Der Grund hierfür liegt im Empfängercache oder "Spitznamen"-Cache von Outlook.</span><span class="sxs-lookup"><span data-stu-id="e10b2-203">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="e10b2-204">Die E-Mail wird erfolgreich an die Gruppe gesendet, kann jedoch zu Verwirrung beim Absender führen.</span><span class="sxs-lookup"><span data-stu-id="e10b2-204">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="e10b2-205">Sie können die Schritte in diesem Artikel, Informationen zur liste [Outlook AutoComplete](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) ausführen, um den Cache zurückzusetzen, wodurch dieses Problem behoben wird.</span><span class="sxs-lookup"><span data-stu-id="e10b2-205">You can perform the steps in this article, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="e10b2-206">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span><span class="sxs-lookup"><span data-stu-id="e10b2-206">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="e10b2-207">Sie können die Schritte unter Entfernen des vorgeschlagenen Namens oder der [E-Mail-Adresse](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) aus der Liste der automatischen Vervollständigen ausführen, um den Cache zu aktualisieren, um die Gruppenkontaktkarte zu sehen.</span><span class="sxs-lookup"><span data-stu-id="e10b2-207">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="e10b2-208">Erhalten neue Gruppenmitglieder in ihrem Posteingang eine Willkommensnachricht?</span><span class="sxs-lookup"><span data-stu-id="e10b2-208">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="e10b2-p118">Nein. Die Einstellung zum Aktivieren von Willkommensnachrichten ist standardmäßig auf FALSE festgelegt. Diese Einstellung wirkt sich auf vorhandene und neue Gruppenmitglieder aus, die beitreten können, nachdem die Migration abgeschlossen wurde. Wenn der Besitzer der Gruppe später Gastbenutzer zulässt, empfangen Gastbenutzer keine Willkommensnachricht in ihrem Posteingang. Gastmitglieder können weiterhin mit der Gruppe zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e10b2-p118">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="e10b2-214">Was passiert, wenn eine oder einige der DLs nicht aktualisiert werden?</span><span class="sxs-lookup"><span data-stu-id="e10b2-214">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="e10b2-215">Es gibt einige Fälle, in denen DL zwar berechtigt ist, aber nicht aktualisiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="e10b2-215">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="e10b2-216">Die DL wird nicht aktualisiert und bleibt als DL erhalten.</span><span class="sxs-lookup"><span data-stu-id="e10b2-216">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="e10b2-217">Wenn der Administrator eine **Gruppen-E-Mail-Adressrichtlinie** für die Gruppen in einer Organisation angewendet hat und versucht, DLs zu aktualisieren, die die Kriterien nicht erfüllen, wird die DL nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e10b2-217">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs that doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="e10b2-218">DLs mit **MemberJoinRestriction** oder **MemberDepartRestriction,** die auf **Closed** festgelegt sind, konnten nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e10b2-218">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="e10b2-219">Was geschieht mit der Verteilerliste, wenn beim Upgrade aus EAC ein Fehler auftritt?</span><span class="sxs-lookup"><span data-stu-id="e10b2-219">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="e10b2-p120">Das Upgrade erfolgt nur, wenn der Aufruf an den Server übermittelt wird. Wenn beim Upgrade ein Fehler auftritt, bleiben Ihre Verteilerlisten erhalten. Sie funktionieren wie bisher.</span><span class="sxs-lookup"><span data-stu-id="e10b2-p120">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>
