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
search.appverid:
- BCS160
- MET150
- MOE150
description: Versuchen Sie diese Lösungen, wenn Probleme mit freigegebenen Postfächern auftreten.
ms.openlocfilehash: c889d3aa2fab8c2dce4cc2a8a00ef49a905363a1
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445507"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="0fc62-103">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="0fc62-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="0fc62-104">Wenn beim Erstellen oder Verwenden eines freigegebenen Postfachs Fehlermeldungen angezeigt werden, versuchen Sie es mit den folgenden Lösungsmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="0fc62-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="0fc62-105">Fehler beim Erstellen freigegebener Postfächer</span><span class="sxs-lookup"><span data-stu-id="0fc62-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="0fc62-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="0fc62-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="0fc62-107">Wenn die Fehlermeldung angezeigt wird, **wird die Proxyadresse "SMTP: <freigegebener Postfachname \> " bereits von den Proxyadressen oder legacyExchangeDN von " \<name> " verwendet. Wählen Sie eine andere Proxyadresse aus**, d. h., Sie versuchen, dem freigegebenen Postfach einen bereits verwendeten Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="0fc62-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="0fc62-108">Beispiel: Sie möchten freigegebenen Postfächern die Namen "info@domaene1" und "info@domaene2" geben.</span><span class="sxs-lookup"><span data-stu-id="0fc62-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="0fc62-109">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="0fc62-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="0fc62-110">Verwenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0fc62-110">Use Windows PowerShell.</span></span> <span data-ttu-id="0fc62-111">In diesem Blogbeitrag finden Sie Anweisungen: [Erstellen freigegebener Postfächer mit gleichem Alias in verschiedenen Domänen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="0fc62-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="0fc62-112">Nennen Sie das zweite freigegebene Postfach etwas anderes als den Anfang, um den Fehler zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="0fc62-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="0fc62-113">Benennen Sie dann im Admin Center das freigegebene Postfach So um, wie es sein soll.</span><span class="sxs-lookup"><span data-stu-id="0fc62-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="0fc62-114">Fehler beim Senden von Berechtigungen bei Verwendung eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="0fc62-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="0fc62-115">Wenn Sie ein freigegebenes Postfach erstellt und anschließend versuchen, eine Nachricht daraus zu senden, erhalten Sie möglicherweise Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0fc62-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="0fc62-116">**Diese Nachricht konnte nicht gesendet werden. Sie verfügen nicht über die Berechtigung, die Nachricht im Namen des angegebenen Benutzers zu senden.**</span><span class="sxs-lookup"><span data-stu-id="0fc62-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="0fc62-117">Diese Meldung wird angezeigt, wenn bei Microsoft 365 ein Problem mit der Replikationswartezeit auftritt.</span><span class="sxs-lookup"><span data-stu-id="0fc62-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="0fc62-118">Es sollte in einer Stunde oder so verschwinden, wenn die Informationen zu Ihrem neuen freigegebenen Postfach (oder hinzugefügter Benutzer) in allen unseren Rechenzentren repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="0fc62-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="0fc62-119">Warten Sie eine Stunde, und versuchen Sie dann erneut, eine Nachricht zu senden.</span><span class="sxs-lookup"><span data-stu-id="0fc62-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0fc62-120">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0fc62-120">Related articles</span></span>

[<span data-ttu-id="0fc62-121">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="0fc62-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="0fc62-122">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="0fc62-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="0fc62-123">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="0fc62-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="0fc62-124">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="0fc62-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="0fc62-125">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="0fc62-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

