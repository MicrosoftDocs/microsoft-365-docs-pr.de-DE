---
title: Entfernen der Lizenz aus einem freigegebenen Postfach
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Entfernen Sie eine Lizenz aus einem freigegebenen Postfach, um es einem anderen Benutzer zuzuweisen, oder geben Sie die Lizenz zurück, damit Sie nicht dafür bezahlen. '
ms.date: 05/11/2021
ms.openlocfilehash: dd2d99d762a4a68a9b0400353d64dabb536a891c
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821428"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="60153-103">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="60153-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="60153-104">Für freigegebene Postfächer ist in der Regel keine Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="60153-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="60153-105">Folgen Sie diesen Anweisungen, um eine Lizenz aus einem freigegebenen Postfach zu entfernen, damit Sie sie einem Benutzer zuweisen oder die Lizenz zurückgeben können, damit Sie keine Lizenz bezahlen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="60153-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="60153-106">In den folgenden Szenarien ist eine Lizenz erforderlich:</span><span class="sxs-lookup"><span data-stu-id="60153-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="60153-107">Das freigegebene Postfach verfügt über mehr als 50 GB Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="60153-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="60153-108">Das freigegebene Postfach verwendet die direkte Archivierung.</span><span class="sxs-lookup"><span data-stu-id="60153-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="60153-109">Das freigegebene Postfach befindet sich in der Beweissicherung für juristische Zwecke.</span><span class="sxs-lookup"><span data-stu-id="60153-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="60153-110">Dem freigegebenen Postfach ist eine Microsoft Defender-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="60153-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="60153-111">Entfernen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="60153-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="60153-112">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="60153-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="60153-113">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="60153-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="60153-114">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="60153-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

   > [!NOTE]
   > <span data-ttu-id="60153-115">Sie müssen die Lizenz von der Seite "Aktive Benutzer" entfernen.</span><span class="sxs-lookup"><span data-stu-id="60153-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="60153-116">Sie können die Lizenz nicht von der Seite "Freigegebenes Postfach" entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="60153-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="60153-117">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="60153-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="60153-118">Erweitern Sie auf der Registerkarte **"Lizenzen und Apps"** die Option **"Lizenzen",** und deaktivieren Sie das Kontrollkästchen für die Lizenz, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="60153-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="60153-119">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="60153-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="60153-120">Wenn Sie zur Seite **"Aktive Benutzer"** zurückkehren, wird der Status des **freigegebenen Postfachs nicht lizenziert.**</span><span class="sxs-lookup"><span data-stu-id="60153-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="60153-121">Sie bezahlen weiterhin für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="60153-121">You're still paying for the license.</span></span> <span data-ttu-id="60153-122">Um die Zahlung zu beenden, [entfernen Sie die Lizenz aus Ihrem Abonnement.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="60153-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="60153-123">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="60153-123">Related content</span></span>

<span data-ttu-id="60153-124">[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="60153-124">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="60153-125">[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="60153-125">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="60153-126">[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="60153-126">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="60153-127">[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="60153-127">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="60153-128">[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="60153-128">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>
