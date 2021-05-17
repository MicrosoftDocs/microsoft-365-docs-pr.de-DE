---
title: Beheben von Problemen mit freigegebenen Postfächern
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Probieren Sie diese Lösungen aus, wenn Probleme mit freigegebenen Postfächern auftreten.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926486"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="e840b-103">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="e840b-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="e840b-104">Wenn beim Erstellen oder Verwenden eines freigegebenen Postfachs Fehlermeldungen angezeigt werden, versuchen Sie diese möglichen Lösungen.</span><span class="sxs-lookup"><span data-stu-id="e840b-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="e840b-105">Fehler beim Erstellen freigegebener Postfächer</span><span class="sxs-lookup"><span data-stu-id="e840b-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="e840b-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="e840b-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="e840b-107">Wenn die Fehlermeldung angezeigt wird, wird die Proxyadresse "smtp:<freigegebener Postfachname" bereits von den Proxyadressen oder **\> LegacyExchangeDN von " \<name> verwendet. Wählen Sie eine andere Proxyadresse** aus, d. h. Sie versuchen, dem freigegebenen Postfach einen Namen zu geben, der bereits verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e840b-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="e840b-108">Beispiel: Sie möchten freigegebenen Postfächern die Namen "info@domaene1" und "info@domaene2" geben.</span><span class="sxs-lookup"><span data-stu-id="e840b-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="e840b-109">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="e840b-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="e840b-110">Verwenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e840b-110">Use Windows PowerShell.</span></span> <span data-ttu-id="e840b-111">Anweisungen zum Erstellen freigegebener Postfächer mit demselben Alias in verschiedenen Domänen finden Sie in diesem [Blogbeitrag.](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="e840b-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="e840b-112">Nennen Sie das zweite freigegebene Postfach etwas anders als am Anfang, um den Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="e840b-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="e840b-113">Benennen Sie dann im Admin Center das freigegebene Postfach in das um, was es sein soll.</span><span class="sxs-lookup"><span data-stu-id="e840b-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="e840b-114">Fehler beim Nichtzugriff auf Sendeberechtigungen bei Verwendung eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="e840b-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="e840b-115">Wenn Sie ein freigegebenes Postfach erstellt haben und dann versuchen, eine Nachricht davon zu senden, erhalten Sie möglicherweise dies:</span><span class="sxs-lookup"><span data-stu-id="e840b-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="e840b-116">**Diese Nachricht konnte nicht gesendet werden. Sie haben nicht die Berechtigung, die Nachricht im Namen des angegebenen Benutzers zu senden.**</span><span class="sxs-lookup"><span data-stu-id="e840b-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="e840b-117">Diese Meldung wird angezeigt, Microsoft 365 beim Auftreten eines Replikationslatenzproblems angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e840b-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="e840b-118">Sie sollte in etwa einer Stunde entfernt werden, wenn die Informationen zu Ihrem neuen freigegebenen Postfach (oder hinzugefügten Benutzer) in allen unseren Rechenzentren repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="e840b-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="e840b-119">Warten Sie eine Stunde, und versuchen Sie dann erneut, eine Nachricht zu senden.</span><span class="sxs-lookup"><span data-stu-id="e840b-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e840b-120">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e840b-120">Related articles</span></span>

[<span data-ttu-id="e840b-121">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="e840b-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="e840b-122">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="e840b-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="e840b-123">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="e840b-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="e840b-124">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="e840b-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="e840b-125">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="e840b-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

