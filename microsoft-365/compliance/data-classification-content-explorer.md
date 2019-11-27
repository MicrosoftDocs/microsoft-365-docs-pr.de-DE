---
title: Verwenden des Daten Inhalts-Explorers zur Datenklassifizierung (Vorschau)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Mit dem Inhalts-Explorers zur Datenklassifizierung können Sie beschriftete Elemente systemintern anzeigen.
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268523"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="c361f-103">Verwenden des Daten Inhalts-Explorers zur Datenklassifizierung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c361f-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="c361f-104">Mit dem Inhalts-Explorers zur Datenklassifizierung können Sie die Elemente, die auf der Übersichtsseite zusammengefasst wurden, systemintern anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c361f-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="c361f-105">Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="c361f-105">Content explorer</span></span>

<span data-ttu-id="c361f-106">Der Inhalts-Explorer ist eine aktuelle Momentaufnahme der Elemente mit einer Vertraulichkeitsbezeichnung, einer Aufbewahrungsbezeichnung oder von Elementen, die in Ihrer Organisation als vertraulicher Informationstyp klassifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="c361f-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![Screenshot des erweiterten Inhalts-Explorers](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="c361f-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c361f-108">Permissions</span></span>

<span data-ttu-id="c361f-109">Es gibt zwei Rollen, die den Zugriff auf den Inhalts-Explorer gewähren:</span><span class="sxs-lookup"><span data-stu-id="c361f-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="c361f-110">**Inhalts Explorer-Listenanzeige**: Mit der Mitgliedschaft in dieser Rolle können Sie jedes Element und dessen Position anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c361f-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="c361f-111">**Inhalts-Explorer-Inhaltsanzeige**: Mit der Mitgliedschaft in dieser Rolle können Sie die Inhalte aller Elemente in der Liste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c361f-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="c361f-112">Das Konto, das Sie für den Zugriff auf den Inhalts-Explorer verwenden, muss eine oder beide Rollen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c361f-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="c361f-113">Hierbei handelt es sich um unabhängige Rollen, die nicht kumulativ sind.</span><span class="sxs-lookup"><span data-stu-id="c361f-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="c361f-114">Wenn Sie beispielsweise einem Konto die Möglichkeit geben möchten, nur die Elemente und deren Speicherorte anzuzeigen, erteilen Sie Inhalts-Explorer-Listenanzeige-Rechte.</span><span class="sxs-lookup"><span data-stu-id="c361f-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="c361f-115">Wenn Sie möchten, dass dasselbe Konto auch in der Lage ist, die Inhalte der Elemente in der Liste anzuzeigen, erteilen Sie zusätzlich Inhalts-Explorer-Inhaltsanzeige-Rechte.</span><span class="sxs-lookup"><span data-stu-id="c361f-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="c361f-116">Verwendung des Inhalts-Explorers</span><span class="sxs-lookup"><span data-stu-id="c361f-116">How to use content explorer</span></span>

1. <span data-ttu-id="c361f-117">Öffnen Sie **Microsoft 365 Compliance Center**  > **Datenklassifizierung** > **Inhalts-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c361f-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="c361f-118">Wenn Sie den Namen der Bezeichnung oder den Typ vertraulicher Informationen kennen, können Sie ihn in das Suchfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="c361f-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="c361f-119">Alternativ können Sie auch nach dem Element suchen, indem Sie den Beschriftungstyp erweitern und die Bezeichnung in der Liste auswählen. Nachfolgend wird ein Element aus dem Bereich der Aufbewahrungsbezeichnung der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c361f-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="c361f-120">Wählen Sie unter **Alle Standorte** einen Standort aus, und gliedern Sie die Ordnerstruktur bis zu dem Element weiter auf.</span><span class="sxs-lookup"><span data-stu-id="c361f-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="c361f-121">Doppelklicken Sie, um das Element systemintern im Inhalts-Explorer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c361f-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="c361f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c361f-122">See also</span></span>

- [<span data-ttu-id="c361f-123">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c361f-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="c361f-124">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c361f-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="c361f-125">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="c361f-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="c361f-126">Übersicht über Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c361f-126">Overview of retention policies</span></span>](retention-policies.md)
