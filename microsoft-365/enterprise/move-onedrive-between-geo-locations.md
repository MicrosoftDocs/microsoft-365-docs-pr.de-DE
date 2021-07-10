---
title: Verschieben einer OneDrive-Website an einen anderen geografischen Standort
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Hier finden Sie Informationen zum Verschieben eines OneDrive-Standorts an einen anderen geografischen Standort, einschließlich der Planung von Websiteverschiebungen und der Kommunikation von Erwartungen an die Benutzer.
ms.openlocfilehash: 9e75c8e4102f82d4ab6e0f99ea26e1c0ad8b4bab
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362246"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="b5e41-103">Verschieben einer OneDrive-Website an einen anderen geografischen Standort</span><span class="sxs-lookup"><span data-stu-id="b5e41-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="b5e41-104">Mit OneDrive Geografische Verschiebung können Sie die OneDrive eines Benutzers an einen anderen geografischen Standort verschieben.</span><span class="sxs-lookup"><span data-stu-id="b5e41-104">With OneDrive geo move, you can move a user's OneDrive to a different geo location.</span></span> <span data-ttu-id="b5e41-105">OneDrive Verschiebung des geografischen Standorts erfolgt durch den SharePoint Onlineadministrator oder den Microsoft 365 globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="b5e41-105">OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator.</span></span> <span data-ttu-id="b5e41-106">Bevor Sie mit einer OneDrive Verschiebung des geografischen Standorts beginnen, müssen Sie den Benutzer benachrichtigen, dessen OneDrive verschoben wird, und empfehlen Sie, alle Dateien für die Dauer der Verschiebung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-106">Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move.</span></span> <span data-ttu-id="b5e41-107">(Wenn der Benutzer während der Verschiebung ein Dokument mithilfe des Office-Clients geöffnet hat, muss das Dokument nach Abschluss der Verschiebung am neuen Speicherort gespeichert werden.) Die Verschiebung kann nach Bedarf für eine zukünftige Zeit geplant werden.</span><span class="sxs-lookup"><span data-stu-id="b5e41-107">(If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="b5e41-108">Der OneDrive Dienst verwendet Azure Blob Storage zum Speichern von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="b5e41-108">The OneDrive service uses Azure Blob Storage to store content.</span></span> <span data-ttu-id="b5e41-109">Das Storage Blob, das dem OneDrive des Benutzers zugeordnet ist, wird innerhalb von 40 Tagen nach dem Zielort von der Quelle an den geografischen Zielstandort verschoben, OneDrive für den Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b5e41-109">The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user.</span></span> <span data-ttu-id="b5e41-110">Der Zugriff auf die OneDrive des Benutzers wird wiederhergestellt, sobald das Ziel OneDrive verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b5e41-110">The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="b5e41-111">Während OneDrive Geo-Verschiebungsfensters (ca. 2-6 Stunden) ist die OneDrive des Benutzers auf schreibgeschützt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b5e41-111">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="b5e41-112">Der Benutzer kann weiterhin über die OneDrive-Synchronisation-App oder seine OneDrive-Website in SharePoint Online auf seine Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-112">The user can still access their files via the OneDrive sync app or their OneDrive site in SharePoint Online.</span></span> <span data-ttu-id="b5e41-113">Nachdem OneDrive Verschiebung des geografischen Standorts abgeschlossen ist, wird der Benutzer automatisch mit seiner OneDrive am geografischen Zielstandort verbunden, wenn er im Microsoft 365 App-Startfeld zu OneDrive navigiert.</span><span class="sxs-lookup"><span data-stu-id="b5e41-113">After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher.</span></span> <span data-ttu-id="b5e41-114">Die Synchronisierungs-App beginnt automatisch mit der Synchronisierung vom neuen Speicherort aus.</span><span class="sxs-lookup"><span data-stu-id="b5e41-114">The sync app will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="b5e41-115">Für die Vorgehensweisen in diesem Artikel ist das [Microsoft SharePoint Online PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=35588) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5e41-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="b5e41-116">Kommunikation mit Benutzern</span><span class="sxs-lookup"><span data-stu-id="b5e41-116">Communicating to your users</span></span>

<span data-ttu-id="b5e41-p104">Beim Verschieben von OneDrive-Websites zwischen geografischen Standorten, ist es wichtig, dass Sie Ihren Benutzer kommunizieren, was sie zu erwarten haben. Auf diese Weise werden Verunsicherungen seitens der Benutzer und Anrufe bei Ihrem Help Desk verhindert. Schreiben Sie Ihren Benutzer vor der Verschiebung eine E-Mail, und teilen Sie ihnen die folgenden Informationen mit:</span><span class="sxs-lookup"><span data-stu-id="b5e41-p104">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect. This can help reduce user confusion and calls to your help desk. Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="b5e41-120">Wann die Verschiebung voraussichtlich stattfinden soll und wie lange sie dauern wird.</span><span class="sxs-lookup"><span data-stu-id="b5e41-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="b5e41-121">An welchen geografischen Standort OneDrive verschoben wird sowie die URL zum Zugreifen auf den neuen Standort.</span><span class="sxs-lookup"><span data-stu-id="b5e41-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="b5e41-122">Der Benutzer sollte alle Dateien schließen und während der Verschiebung keine Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="b5e41-123">Dateiberechtigungen und Freigabe werden als Ergebnis der Verschiebung nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="b5e41-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="b5e41-124">Erwartungen im Hinblick auf die [Benutzererfahrung in einer Multi-Geo-Umgebung](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="b5e41-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="b5e41-125">Vergessen Sie nicht, Ihren Benutzer eine E-Mail zu schicken, wenn die Verschiebung erfolgreich abgeschlossen wurde, um sie darüber zu informieren, dass sie ihre Arbeit in OneDrive fortsetzen können.</span><span class="sxs-lookup"><span data-stu-id="b5e41-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="b5e41-126">Planen der Verschiebung von OneDrive-Sites</span><span class="sxs-lookup"><span data-stu-id="b5e41-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="b5e41-p105">Sie können die Verschiebung von OneDrive-Sites im Voraus planen (weiter unten in diesem Artikel beschrieben). Wir empfehlen, zunächst mit einer kleinen Anzahl Benutzer zu beginnen, um die Arbeitsabläufe und Kommunikationsstrategien zu überprüfen. Sobald Sie mit dem Prozess vertraut sind, können Sie die Verschiebungen wie folgt planen:</span><span class="sxs-lookup"><span data-stu-id="b5e41-p105">You can schedule OneDrive site moves in advance (described later in this article). We recommend that you start with a small number of users to validate your workflows and communication strategies. Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="b5e41-130">Sie können bis zu 4.000 Verschiebungen zugleich planen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="b5e41-131">Wenn mit dem Verschieben begonnen wird, können Sie weitere planen, bis zu maximal jeweils 4.000 ausstehenden Verschiebungen in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="b5e41-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="b5e41-132">Die maximale Größe eines OneDrive, das verschoben werden kann, beträgt 1 TB (1 TB).</span><span class="sxs-lookup"><span data-stu-id="b5e41-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="b5e41-133">Verschieben einer OneDrive-Website</span><span class="sxs-lookup"><span data-stu-id="b5e41-133">Moving a OneDrive site</span></span>

<span data-ttu-id="b5e41-134">Um eine OneDrive Geografische Verschiebung durchzuführen, muss der Mandantenadministrator zuerst den bevorzugten Datenspeicherort (Preferred Data Location, PDL) des Benutzers auf den entsprechenden geografischen Standort festlegen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-134">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location.</span></span> <span data-ttu-id="b5e41-135">Nachdem der PDL festgelegt wurde, warten Sie mindestens 24 Stunden, bis das PDL-Update über die geografischen Standorte hinweg synchronisiert wurde, bevor Sie mit der OneDrive Verschiebung des geografischen Standorts beginnen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-135">Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="b5e41-136">Stellen Sie bei Verwendung der Cmdlets zum Verschieben von Geografischen Standorten eine Verbindung mit dem SPO-Dienst am aktuellen OneDrive geografischen Standort des Benutzers her, und verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="b5e41-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="b5e41-137">Beispiel: Um OneDrive des Benutzers "Matt@contosoenergy.onmicrosoft.com" zu verschieben, stellen Sie eine Verbindung zu EUR SharePoint Admin Center her, da sich die OneDrive des Benutzers am geografischen Standort EUR befindet:</span><span class="sxs-lookup"><span data-stu-id="b5e41-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Screenshot des PowerShell-Fensters mit Connect-SPOService-Cmdlet](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="b5e41-139">Überprüfen der Umgebung</span><span class="sxs-lookup"><span data-stu-id="b5e41-139">Validating the environment</span></span>

<span data-ttu-id="b5e41-140">Bevor Sie mit dem Verschieben von geografischen Standorten in OneDrive beginnen, sollten Sie die Umgebung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="b5e41-141">Um sicherzustellen, dass alle geografischen Standorte kompatibel sind, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b5e41-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="b5e41-142">Angezeigt wird eine Liste Ihrer geografischen Standorte und Informationen dazu, ob Inhalte zwischen diesen verschoben werden können, indem die entsprechenden Standorte als "kompatibel" bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b5e41-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="b5e41-143">Wenn der Befehl „Nicht kompatibel“ zurückgibt, versuchen Sie zu einem späteren Zeitpunkt erneut, den Status zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="b5e41-144">Wenn eine OneDrive-Umgebung beispielsweise eine Unterwebsite umfasst, kann sie nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b5e41-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="b5e41-145">Sie können das Start-SPOUserAndContentMove-Cmdlet mit dem -ValidationOnly-Parameter verwenden, um zu überprüfen, ob die OneDrive-Umgebung verschoben werden kann:</span><span class="sxs-lookup"><span data-stu-id="b5e41-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="b5e41-p109">Dieses gibt „Success“ zurück, wenn OneDrive verschoben werden kann, oder „Fail“, wenn die gesetzliche Aufbewahrungspflicht aktiviert ist oder eine Unterwebsite vorhanden ist, die die Verschiebung verhindert. Nachdem Sie überprüft haben, dass die OneDrive-Umgebung verschoben werden kann, können Sie mit der Verschiebung beginnen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-p109">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move. Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="b5e41-148">Starten einer Verschiebung von geografischen Standorten in OneDrive</span><span class="sxs-lookup"><span data-stu-id="b5e41-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="b5e41-149">Um mit der Verschiebung zu beginnen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b5e41-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="b5e41-150">Verwenden Sie die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="b5e41-150">Using these parameters:</span></span>

-   <span data-ttu-id="b5e41-151">_UserPrincipalName_ – Benutzerprinzipalname des Benutzers, dessen OneDrive-Umgebung verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="b5e41-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="b5e41-152">_DestinationDataLocation_ – Geo-Location, wo die OneDrive verschoben werden muss.</span><span class="sxs-lookup"><span data-stu-id="b5e41-152">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved.</span></span> <span data-ttu-id="b5e41-153">Dies sollte mit dem bevorzugten Datenspeicherort des Benutzers übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-153">This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="b5e41-154">Führen Sie zum Beispiel zum Verschieben von OneDrive von matt@contosoenergy.onmicrosoft.com von EUR nach AUS den folgenden Befehl durch:</span><span class="sxs-lookup"><span data-stu-id="b5e41-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Screenshot des PowerShell-Fensters mit dem Start-SPOUserAndContentMove-Cmdlet](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="b5e41-156">Wenn Sie die Verschiebung eines geografischen Standorts zu einem späteren Zeitpunkt durchführen möchten, verwenden Sie einen der folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="b5e41-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="b5e41-p111">_PreferredMoveBeginDate_ – Die Verschiebung beginnt zu diesem Zeitpunkt. Die Zeit muss in koordinierter Weltzeit (UTC) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b5e41-p111">_PreferredMoveBeginDate_ – The move will likely begin at this specified time. Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="b5e41-p112">_PreferredMoveEndDate_ – Die Verschiebung endet basieren auf dem Best-Effort-Prinzip zu diesem Zeitpunkt. Die Zeit muss in koordinierter Weltzeit (UTC) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b5e41-p112">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis. Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="b5e41-161">Abbrechen einer Verschiebung von geografischen Standorten in OneDrive</span><span class="sxs-lookup"><span data-stu-id="b5e41-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="b5e41-162">Sie können die Verschiebung des geografischen Standorts eines OneDrive eines Benutzers beenden, vorausgesetzt, die Verschiebung wird nicht ausgeführt oder mithilfe des Cmdlets abgeschlossen:</span><span class="sxs-lookup"><span data-stu-id="b5e41-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="b5e41-163">Dabei ist _UserPrincipalName_ der Benutzerprinzipalname des Benutzers, dessen OneDrive-Verschiebung beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5e41-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="b5e41-164">Bestimmen des aktuellen Status</span><span class="sxs-lookup"><span data-stu-id="b5e41-164">Determining current status</span></span>

<span data-ttu-id="b5e41-165">Mithilfe des Cmdlets Get-SPOUserAndContentMoveState können Sie den Status eines OneDrive geografischen Standorts in oder aus dem Geografischen Raum überprüfen, mit dem Sie verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b5e41-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="b5e41-166">Die Statuswerte der Verschiebung werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5e41-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b5e41-167">Status</span><span class="sxs-lookup"><span data-stu-id="b5e41-167">Status</span></span></th>
<th align="left"><span data-ttu-id="b5e41-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5e41-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="b5e41-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="b5e41-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="b5e41-170">Die Verschiebung wurde noch nicht begonnen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b5e41-171">InProgress (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="b5e41-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="b5e41-172">Die Verschiebung wird ausgeführt, wenn einer der folgenden Statuswerte angezeigt wird: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span><span class="sxs-lookup"><span data-stu-id="b5e41-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b5e41-173">Success</span><span class="sxs-lookup"><span data-stu-id="b5e41-173">Success</span></span></td>
<td align="left"><span data-ttu-id="b5e41-174">Die Verschiebung wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b5e41-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b5e41-175">Failed</span><span class="sxs-lookup"><span data-stu-id="b5e41-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="b5e41-176">Beim Verschieben ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b5e41-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b5e41-177">Verwenden Sie den Parameter UserPrincipalName, um den Status der Verschiebung eines bestimmten Benutzers zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="b5e41-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="b5e41-178">Verwenden Sie den MoveState-Parameter mit einem der folgenden Werte, um den Status aller Verschiebungen in oder aus dem geografischen Standort zu ermitteln, mit dem Sie verbunden sind: NotStarted, InProgress, Success, Failed, All.</span><span class="sxs-lookup"><span data-stu-id="b5e41-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="b5e41-179">Sie können auch den `-Verbose`-Parameter für weitere ausführliche Beschreibungen des Status der Verschiebung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="b5e41-180">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="b5e41-180">User Experience</span></span>

<span data-ttu-id="b5e41-p113">OneDrive-Benutzer sollten minimale Unterbrechungen feststellen, wenn ihre OneDrive-Umgebung an einen anderen geografischen Standort verschoben wird. Neben einem kurzzeitigen Schreibschutz während des Verschiebevorgangs funktionieren vorhandene Links und Berechtigungen weiterhin wie gewohnt, sobald die Verschiebung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b5e41-p113">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location. Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="users-onedrive"></a><span data-ttu-id="b5e41-183">OneDrive eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="b5e41-183">User's OneDrive</span></span>

<span data-ttu-id="b5e41-184">Während der Verschiebung wird die OneDrive des Benutzers auf schreibgeschützt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b5e41-184">While the move is in progress the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="b5e41-185">Nach Abschluss der Verschiebung wird der Benutzer zu seiner OneDrive am neuen geografischen Standort weitergeleitet, wenn er zu OneDrive Microsoft 365 App-Startfeld oder zu einem Webbrowser navigiert.</span><span class="sxs-lookup"><span data-stu-id="b5e41-185">Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="b5e41-186">Berechtigungen für OneDrive-Inhalte</span><span class="sxs-lookup"><span data-stu-id="b5e41-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="b5e41-187">Benutzer mit Berechtigungen für OneDrive Inhalte haben während und nach abschluss der Verschiebung weiterhin Zugriff auf den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="b5e41-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-app"></a><span data-ttu-id="b5e41-188">OneDrive-Synchronisation-App</span><span class="sxs-lookup"><span data-stu-id="b5e41-188">OneDrive sync app</span></span> 

<span data-ttu-id="b5e41-189">Die OneDrive-Synchronisation-App erkennt die Synchronisierung automatisch und überträgt sie nahtlos an den neuen OneDrive-Speicherort, sobald die OneDrive Geografische Verschiebung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b5e41-189">The OneDrive sync app will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete.</span></span> <span data-ttu-id="b5e41-190">Der Benutzer muss sich nicht erneut anmelden oder eine andere Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="b5e41-190">The user does not need to sign-in again or take any other action.</span></span>  <span data-ttu-id="b5e41-191">(Version 17.3.6943.0625 oder höher der Synchronisierungs-App erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="b5e41-191">(Version 17.3.6943.0625 or later of the sync app required.)</span></span>

<span data-ttu-id="b5e41-192">Wenn ein Benutzer eine Datei aktualisiert, während die OneDrive Verschiebung des geografischen Raumes ausgeführt wird, benachrichtigt die Synchronisierungs-App sie, dass Dateiuploads ausstehen, während die Verschiebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b5e41-192">If a user updates a file while the OneDrive geo move is in progress, the sync app will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="b5e41-193">Freigabelinks</span><span class="sxs-lookup"><span data-stu-id="b5e41-193">Sharing links</span></span> 

<span data-ttu-id="b5e41-194">Nach Abschluss der geografischen Standortverschiebung in OneDrive werden vorhandene Freigabelinks für verschobene Dateien automatisch zu den Dateien an dem neuen geografischen Standort weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b5e41-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="b5e41-195">OneNote-Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="b5e41-195">OneNote Experience</span></span> 

<span data-ttu-id="b5e41-p116">OneNote-Win32-Client und UWP-App werden automatisch erkannt und synchronisieren nahtlos die Notizbücher mit dem neuen geografischen OneDrive-Standort, nachdem die geografische Standortverschiebung von OneDrive abgeschlossen wurde. Der Benutzer muss sich weder erneut anmelden noch eine andere Aktion durchführen. Der einzige für den Benutzer sichtbare Indikator ist, dass beim Synchronisieren des Notizbuchs ein Fehler auftritt, während die geografische Standortverschiebung von OneDrive ausgeführt wird. Diese Erfahrung gilt für die folgenden OneNote-Clientversionen:</span><span class="sxs-lookup"><span data-stu-id="b5e41-p116">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete. The user does not need to sign-in again or take any other action. The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress. This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="b5e41-200">OneNote-Win32 – Version 16.0.8326.2096 (und höher)</span><span class="sxs-lookup"><span data-stu-id="b5e41-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="b5e41-201">OneNote UWP – Version 16.0.8431.1006 (und höher)</span><span class="sxs-lookup"><span data-stu-id="b5e41-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="b5e41-202">Mobile OneNote-App – Version 16.0.8431.1011 (und höher)</span><span class="sxs-lookup"><span data-stu-id="b5e41-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="b5e41-203">Teams-App</span><span class="sxs-lookup"><span data-stu-id="b5e41-203">Teams app</span></span>

<span data-ttu-id="b5e41-p117">Nach Abschluss der geografischen Standortverschiebung von OneDrive haben Benutzer Zugriff auf ihre OneDrive-Dateien in der Teams-App. Darüber hinaus können die über Teams-Chat in OneDrive vor der Verschiebung freigegebenen Dateien weiterhin verwendet werden, sobald die Verschiebung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b5e41-p117">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app. Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-mobile-app-ios"></a><span data-ttu-id="b5e41-206">OneDrive Mobile App (iOS)</span><span class="sxs-lookup"><span data-stu-id="b5e41-206">OneDrive Mobile App (iOS)</span></span> 

<span data-ttu-id="b5e41-207">Nach Abschluss der geografischen Standortverschiebung von OneDrive müssen sich Benutzer abmelden und erneut in der mobilen iOS-App anmelden, damit mit dem neuen OneDrive-Standort synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b5e41-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="b5e41-208">Vorhandene gefolgte Gruppen und Websites</span><span class="sxs-lookup"><span data-stu-id="b5e41-208">Existing followed groups and sites</span></span>

<span data-ttu-id="b5e41-209">Besuchte Websites und Gruppen werden unabhängig vom geografischen Standort im OneDrive des Benutzers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5e41-209">Followed sites and groups will show up in the user's OneDrive regardless of their geo location.</span></span> <span data-ttu-id="b5e41-210">Websites und Gruppen, die an einem anderen geografischen Standort gehostet werden, werden auf einer separaten Registerkarte geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b5e41-210">Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="b5e41-211">Delve Geo-URL-Updates</span><span class="sxs-lookup"><span data-stu-id="b5e41-211">Delve Geo URL updates</span></span>

<span data-ttu-id="b5e41-212">Benutzer werden erst an das Delve Geo gesendet, das ihrem PDL entspricht, nachdem ihre OneDrive in den neuen geografischen Raum verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="b5e41-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>
