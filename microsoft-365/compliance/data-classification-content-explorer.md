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
ms.openlocfilehash: 9e9ad76d2bdd7f74368121346f7e04d1208803ff
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818857"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="17e37-103">Verwenden des Daten Inhalts-Explorers zur Datenklassifizierung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="17e37-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="17e37-104">Mit dem Inhalts-Explorers zur Datenklassifizierung können Sie die Elemente, die auf der Übersichtsseite zusammengefasst wurden, systemintern anzeigen.</span><span class="sxs-lookup"><span data-stu-id="17e37-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="17e37-105">Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="17e37-105">Content explorer</span></span>

<span data-ttu-id="17e37-106">Der Inhalts-Explorer zeigt eine aktuelle Momentaufnahme der Elemente mit einer Vertraulichkeitsbezeichnung, einer Aufbewahrungsbezeichnung oder von Elementen, die in Ihrer Organisation als vertraulicher Informationstyp klassifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="17e37-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="17e37-107">Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="17e37-107">Sensitive information types</span></span>

<span data-ttu-id="17e37-108">Mithilfe einer [DLP-Richtlinie](data-loss-prevention-policies.md) können vertrauliche Informationen geschützt werden, die als **vertraulicher Informationstyp** definiert sind.</span><span class="sxs-lookup"><span data-stu-id="17e37-108">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="17e37-109">Microsoft 365 umfasst [Definitionen für viele gängige Typen vertraulicher Informationen](what-the-sensitive-information-types-look-for.md) in vielen verschiedenen Regionen, die für Sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="17e37-109">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> <span data-ttu-id="17e37-110">Beispielsweise Kreditkartennummern, Bankkontonummern, Personalausweisnummern und Windows Live ID-Dienstnummern.</span><span class="sxs-lookup"><span data-stu-id="17e37-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="17e37-111">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="17e37-111">Sensitivity labels</span></span>

<span data-ttu-id="17e37-112">Eine [Vertraulichkeitsbezeichnung](sensitivity-labels.md) ist einfach ein Tag, das den Wert des Elements für Ihre Organisation angibt.</span><span class="sxs-lookup"><span data-stu-id="17e37-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="17e37-113">Sie kann manuell oder automatisch angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17e37-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="17e37-114">Sobald sie angewendet wurde, wird sie in das Dokument eingebettet und mit diesem überall hin weitergebenen.</span><span class="sxs-lookup"><span data-stu-id="17e37-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="17e37-115">Eine Vertraulichkeitsbezeichnung aktiviert verschiedene Schutzmaßnahmen, z. B. ein obligatorisches Wasserzeichen oder die Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="17e37-115">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="17e37-116">Mit aktiviertem Endpunktschutz können Sie sogar verhindern, dass ein Element die Kontrolle Ihrer Organisation verlässt.</span><span class="sxs-lookup"><span data-stu-id="17e37-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="17e37-117">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="17e37-117">Retention labels</span></span>

<span data-ttu-id="17e37-118">Mithilfe einer [Aufbewahrungbezeichnung](labels.md) können Sie festlegen, wie lange ein entsprechend gekennzeichnetes Element aufbewahrt wird, und welche Schritte vor dem Löschen ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="17e37-118">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="17e37-119">Aufbewahrungbezeichnungen können manuell oder automatisch über Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17e37-119">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="17e37-120">Sie können Ihre Organisation dabei unterstützen, rechtliche und behördliche Vorschriften einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="17e37-120">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![Screenshot des erweiterten Inhalts-Explorers](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="17e37-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="17e37-122">Permissions</span></span>

<span data-ttu-id="17e37-123">Es gibt zwei Rollen, die den Zugriff auf den Inhalts-Explorer gewähren:</span><span class="sxs-lookup"><span data-stu-id="17e37-123">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="17e37-124">**Inhalts Explorer-Listenanzeige**: Mit der Mitgliedschaft in dieser Rolle können Sie jedes Element und dessen Position anzeigen.</span><span class="sxs-lookup"><span data-stu-id="17e37-124">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="17e37-125">**Inhalts-Explorer-Inhaltsanzeige**: Mit der Mitgliedschaft in dieser Rolle können Sie die Inhalte aller Elemente in der Liste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="17e37-125">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="17e37-126">Das Konto, das Sie für den Zugriff auf den Inhalts-Explorer verwenden, muss eine oder beide Rollen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="17e37-126">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="17e37-127">Hierbei handelt es sich um unabhängige Rollen, die nicht kumulativ sind.</span><span class="sxs-lookup"><span data-stu-id="17e37-127">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="17e37-128">Wenn Sie beispielsweise einem Konto die Möglichkeit geben möchten, nur die Elemente und deren Speicherorte anzuzeigen, erteilen Sie Inhalts-Explorer-Listenanzeige-Rechte.</span><span class="sxs-lookup"><span data-stu-id="17e37-128">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="17e37-129">Wenn Sie möchten, dass dasselbe Konto auch in der Lage ist, die Inhalte der Elemente in der Liste anzuzeigen, erteilen Sie zusätzlich Inhalts-Explorer-Inhaltsanzeige-Rechte.</span><span class="sxs-lookup"><span data-stu-id="17e37-129">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="17e37-130">Verwendung des Inhalts-Explorers</span><span class="sxs-lookup"><span data-stu-id="17e37-130">How to use content explorer</span></span>

1. <span data-ttu-id="17e37-131">Öffnen Sie **Microsoft 365 Compliance Center**  > **Datenklassifizierung** > **Inhalts-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="17e37-131">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="17e37-132">Wenn Sie den Namen der Bezeichnung oder den Typ vertraulicher Informationen kennen, können Sie ihn in das Suchfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="17e37-132">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="17e37-133">Alternativ können Sie auch nach dem Element suchen, indem Sie den Beschriftungstyp erweitern und die Bezeichnung in der Liste auswählen. Nachfolgend wird ein Element aus dem Bereich der Aufbewahrungsbezeichnung der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17e37-133">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="17e37-134">Wählen Sie unter **Alle Standorte** einen Standort aus, und gliedern Sie die Ordnerstruktur bis zu dem Element weiter auf.</span><span class="sxs-lookup"><span data-stu-id="17e37-134">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="17e37-135">Doppelklicken Sie, um das Element systemintern im Inhalts-Explorer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="17e37-135">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="17e37-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17e37-136">See also</span></span>

- [<span data-ttu-id="17e37-137">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="17e37-137">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="17e37-138">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="17e37-138">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="17e37-139">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="17e37-139">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="17e37-140">Übersicht über Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="17e37-140">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="17e37-141">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="17e37-141">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
