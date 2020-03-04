---
title: Verwenden des Daten Inhalts-Explorers zur Datenklassifizierung (Vorschau)
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 205ec6b4f2049e18ee95f25505d8a58d7eb7ac77
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409690"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="5ceac-103">Verwenden des Daten Inhalts-Explorers zur Datenklassifizierung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="5ceac-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="5ceac-104">Mit dem Inhalts-Explorers zur Datenklassifizierung können Sie die Elemente, die auf der Übersichtsseite zusammengefasst wurden, systemintern anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ceac-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5ceac-105">Prerequisites</span></span>

<span data-ttu-id="5ceac-106">Jedem Konto, das auf den Aktivitäten-Explorer zugreift und diesen verwendet, muss eine Lizenz aus einem dieser Abonnements zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="5ceac-106">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="5ceac-107">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5ceac-107">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="5ceac-108">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5ceac-108">Office 365 (E5)</span></span>
- <span data-ttu-id="5ceac-109">Advanced Compliance (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="5ceac-109">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="5ceac-110">Advanced Threat Intelligence (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="5ceac-110">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="content-explorer"></a><span data-ttu-id="5ceac-111">Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="5ceac-111">Content explorer</span></span>

<span data-ttu-id="5ceac-112">Der Inhalts-Explorer zeigt eine aktuelle Momentaufnahme der Elemente mit einer Vertraulichkeitsbezeichnung, einer Aufbewahrungsbezeichnung oder von Elementen, die in Ihrer Organisation als vertraulicher Informationstyp klassifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="5ceac-112">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="5ceac-113">Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="5ceac-113">Sensitive information types</span></span>

<span data-ttu-id="5ceac-114">Mithilfe einer [DLP-Richtlinie](data-loss-prevention-policies.md) können vertrauliche Informationen geschützt werden, die als **vertraulicher Informationstyp** definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5ceac-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="5ceac-115">Microsoft 365 umfasst [Definitionen für viele gängige Typen vertraulicher Informationen](what-the-sensitive-information-types-look-for.md) in vielen verschiedenen Regionen, die für Sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5ceac-115">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="5ceac-116">Beispielsweise Kreditkartennummern, Bankkontonummern, Personalausweisnummern und Windows Live ID-Dienstnummern.</span><span class="sxs-lookup"><span data-stu-id="5ceac-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="5ceac-117">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5ceac-117">Sensitivity labels</span></span>

<span data-ttu-id="5ceac-118">Eine [Vertraulichkeitsbezeichnung](sensitivity-labels.md) ist einfach ein Tag, das den Wert des Elements für Ihre Organisation angibt.</span><span class="sxs-lookup"><span data-stu-id="5ceac-118">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="5ceac-119">Sie kann manuell oder automatisch angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ceac-119">It can be applied manually, or automatically.</span></span> <span data-ttu-id="5ceac-120">Sobald sie angewendet wurde, wird sie in das Dokument eingebettet und mit diesem überall hin weitergebenen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-120">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="5ceac-121">Eine Vertraulichkeitsbezeichnung aktiviert verschiedene Schutzmaßnahmen, z. B. ein obligatorisches Wasserzeichen oder die Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="5ceac-121">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="5ceac-122">Mit aktiviertem Endpunktschutz können Sie sogar verhindern, dass ein Element die Kontrolle Ihrer Organisation verlässt.</span><span class="sxs-lookup"><span data-stu-id="5ceac-122">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="5ceac-123">Vertraulichkeitsbezeichnungen müssen für Dateien in SharePoint und OneDrive aktiviert sein, damit die entsprechenden Daten in der Datenklassifizierungsseite eingeblendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5ceac-123">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="5ceac-124">Weitere Informationen finden Sie unter [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="5ceac-124">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="5ceac-125">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5ceac-125">Retention labels</span></span>

<span data-ttu-id="5ceac-126">Mithilfe einer [Aufbewahrungbezeichnung](labels.md) können Sie festlegen, wie lange ein entsprechend gekennzeichnetes Element aufbewahrt wird, und welche Schritte vor dem Löschen ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-126">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="5ceac-127">Aufbewahrungbezeichnungen können manuell oder automatisch über Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ceac-127">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="5ceac-128">Sie können Ihre Organisation dabei unterstützen, rechtliche und behördliche Vorschriften einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="5ceac-128">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![Screenshot des erweiterten Inhalts-Explorers](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="5ceac-130">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5ceac-130">Permissions</span></span>

<span data-ttu-id="5ceac-131">Es gibt zwei Rollen, die den Zugriff auf den Inhalts-Explorer gewähren:</span><span class="sxs-lookup"><span data-stu-id="5ceac-131">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="5ceac-132">**Inhalts Explorer-Listenanzeige**: Durch die Mitgliedschaft in dieser Rollengruppe können Sie jedes Element und dessen Speicherort anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-132">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="5ceac-133">Die Rolle `data classification list viewer` wurde dieser Rollengruppe bereits zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-133">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="5ceac-134">**Inhalts-Explorer-Inhaltsanzeige**: Durch die Mitgliedschaft in dieser Rollengruppe können Sie die Inhalte aller Elemente in der Liste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-134">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="5ceac-135">Die Rolle `data classification content viewer` wurde dieser Rollengruppe bereits zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-135">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="5ceac-136">Das Konto, das Sie für den Zugriff auf den Inhalts-Explorer verwenden, muss einer oder beiden Rollengruppen angehören.</span><span class="sxs-lookup"><span data-stu-id="5ceac-136">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="5ceac-137">Hierbei handelt es sich um unabhängige Rollengruppen, die nicht kumulativ sind.</span><span class="sxs-lookup"><span data-stu-id="5ceac-137">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="5ceac-138">Wenn Sie beispielsweise einem Konto die Möglichkeit geben möchten, nur die Elemente und deren Speicherorte anzuzeigen, erteilen Sie Inhalts-Explorer-Listenanzeige-Rechte.</span><span class="sxs-lookup"><span data-stu-id="5ceac-138">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="5ceac-139">Wenn Sie möchten, dass dasselbe Konto auch in der Lage ist, die Inhalte der Elemente in der Liste anzuzeigen, erteilen Sie zusätzlich Inhalts-Explorer-Inhaltsanzeige-Rechte.</span><span class="sxs-lookup"><span data-stu-id="5ceac-139">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="5ceac-140">Sie können auch eine oder beide Rollen einer benutzerdefinierten Rollengruppe zuweisen, um den Zugriff auf den Inhalts-Explorer anzupassen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-140">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="5ceac-141">Ein globaler Administrator, ein Compliance-Administrator oder ein Datenadministrator kann die erforderliche Rollengruppenmitgliedschaft Inhalts-Explorer-Listenanzeige und Inhalts-Explorer-Inhaltsanzeige zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-141">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="5ceac-142">Verwendung des Inhalts-Explorers</span><span class="sxs-lookup"><span data-stu-id="5ceac-142">How to use content explorer</span></span>

1. <span data-ttu-id="5ceac-143">Öffnen Sie **Microsoft 365 Compliance Center**  > **Datenklassifizierung** > **Inhalts-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="5ceac-143">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="5ceac-144">Wenn Sie den Namen der Bezeichnung oder den Typ vertraulicher Informationen kennen, können Sie ihn in das Suchfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="5ceac-144">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="5ceac-145">Alternativ können Sie auch nach dem Element suchen, indem Sie den Beschriftungstyp erweitern und die Bezeichnung in der Liste auswählen. Nachfolgend wird ein Element aus dem Bereich der Aufbewahrungsbezeichnung der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ceac-145">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="5ceac-146">Wählen Sie unter **Alle Standorte** einen Standort aus, und gliedern Sie die Ordnerstruktur bis zu dem Element weiter auf.</span><span class="sxs-lookup"><span data-stu-id="5ceac-146">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="5ceac-147">Doppelklicken Sie, um das Element systemintern im Inhalts-Explorer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5ceac-147">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ceac-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ceac-148">See also</span></span>

- [<span data-ttu-id="5ceac-149">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5ceac-149">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="5ceac-150">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5ceac-150">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="5ceac-151">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="5ceac-151">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="5ceac-152">Übersicht über Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5ceac-152">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="5ceac-153">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="5ceac-153">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
