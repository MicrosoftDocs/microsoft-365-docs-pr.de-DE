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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Beim Einrichten freigegebener Postfächer können Fehler auftreten. Probieren Sie diese Lösungen aus, wenn Probleme mit freigegebenen Postfächern auftreten.
ms.openlocfilehash: ae76bc1cb97c44087be57adc7791ea8814b94b40
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393943"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="04b36-104">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="04b36-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="04b36-105">Wenn beim Erstellen oder Verwenden eines freigegebenen Postfachs Fehlermeldungen angezeigt werden, probieren Sie diese möglichen Lösungen aus.</span><span class="sxs-lookup"><span data-stu-id="04b36-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="04b36-106">Fehler beim Erstellen freigegebener Postfächer</span><span class="sxs-lookup"><span data-stu-id="04b36-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="04b36-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="04b36-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="04b36-108">Wenn die Fehlermeldung angezeigt **wird, wird die Proxyadresse "smtp:<freigegebener Postfachname" \> bereits von den Proxyadressen oder LegacyExchangeDN von " \<name> verwendet. Wählen Sie eine andere Proxyadresse** aus. Dies bedeutet, dass Sie versuchen, dem freigegebenen Postfach einen Namen zu geben, der bereits verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="04b36-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="04b36-109">Beispiel: Sie möchten freigegebenen Postfächern die Namen "info@domaene1" und "info@domaene2" geben.</span><span class="sxs-lookup"><span data-stu-id="04b36-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="04b36-110">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="04b36-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="04b36-111">Verwenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04b36-111">Use Windows PowerShell.</span></span> <span data-ttu-id="04b36-112">Anweisungen finden Sie in diesem Blogbeitrag: [Erstellen freigegebener Postfächer mit demselben Alias in verschiedenen Domänen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="04b36-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="04b36-113">Benennen Sie das zweite freigegebene Postfach anders als zu Beginn, um den Fehler zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="04b36-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="04b36-114">Benennen Sie dann im Admin Center das freigegebene Postfach in das gewünschte Postfach um.</span><span class="sxs-lookup"><span data-stu-id="04b36-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="04b36-115">Fehler beim Nichtbeachten von Sendeberechtigungen bei Verwendung eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="04b36-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="04b36-116">Wenn Sie ein freigegebenes Postfach erstellt und dann versuchen, eine Nachricht daraus zu senden, erhalten Sie möglicherweise Folgendes:</span><span class="sxs-lookup"><span data-stu-id="04b36-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="04b36-117">**Diese Nachricht konnte nicht gesendet werden. Sie verfügen nicht über die Berechtigung, die Nachricht im Auftrag des angegebenen Benutzers zu senden.**</span><span class="sxs-lookup"><span data-stu-id="04b36-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="04b36-118">Diese Meldung wird angezeigt, wenn bei Microsoft 365 ein Replikationslatenzproblem auftritt.</span><span class="sxs-lookup"><span data-stu-id="04b36-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="04b36-119">Sie sollte in etwa einer Stunde entfernt sein, wenn die Informationen zu Ihrem neuen freigegebenen Postfach (oder dem hinzugefügten Benutzer) in allen unseren Rechenzentren repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="04b36-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="04b36-120">Warten Sie eine Stunde, und versuchen Sie es dann erneut, um eine Nachricht zu senden.</span><span class="sxs-lookup"><span data-stu-id="04b36-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="04b36-121">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="04b36-121">Related content</span></span>

<span data-ttu-id="04b36-122">[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="04b36-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="04b36-123">[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="04b36-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="04b36-124">[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="04b36-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="04b36-125">[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="04b36-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="04b36-126">[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="04b36-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

