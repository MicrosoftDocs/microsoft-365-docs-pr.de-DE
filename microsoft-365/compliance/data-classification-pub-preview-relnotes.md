---
title: Veröffentlichungshinweise zur Datenklassifizierung
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
description: Veröffentlichungshinweise für die Datenklassifizierung.
ms.openlocfilehash: 2b9302cfa49f9445d3cbeb5109aef70e0c8d8f7f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663040"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="d8a28-103">Veröffentlichungshinweise zur Datenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="d8a28-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="d8a28-104">Anzahl der Exchange-Postfächer</span><span class="sxs-lookup"><span data-stu-id="d8a28-104">Exchange mailbox count</span></span>

<span data-ttu-id="d8a28-105">Beim Ausführen eines Drilldowns in Exchange-Postfächer wird ein kleiner QuickInfo-Tipp angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8a28-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="d8a28-106">Dadurch wird darauf hingewiesen, dass die für den vertraulichen Informationstyp, die Vertraulichkeitsbezeichnung und die Aufbewahrungsbezeichnung angezeigte Gesamtzahl möglicherweise nicht genau mit der Anzahl von Elementen übereinstimmt, die im Postfach zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="d8a28-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="d8a28-107">Der Grund dafür ist, dass der Drilldown in den Ordner die Live-Ansichten von Inhalten abruft, die klassifiziert sind, während die Gesamtzahl berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="d8a28-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="d8a28-108">Rendern von verschlüsselten Dokumenten</span><span class="sxs-lookup"><span data-stu-id="d8a28-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="d8a28-109">Verschlüsselte SharePoint-, Exchange- und OneDrive-Dateien werden im Inhalts-Explorer nicht gerendert.</span><span class="sxs-lookup"><span data-stu-id="d8a28-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="d8a28-110">Hierbei handelt es sich um ein heikles Problem, das einen Kompromiss zwischen der Notwendigkeit des Anzeigens von Dateiinhalten im Inhalts-Explorer und der Notwendigkeit der Verschlüsselung von Inhalten erfordert.</span><span class="sxs-lookup"><span data-stu-id="d8a28-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="d8a28-111">Mit den Berechtigungen, die von den Rollengruppen **Inhalts-Explorer-Listenanzeige** und **Inhalts-Explorer-Listenanzeige** gewährt werden, werden eine Listenansicht der Dateien, die Dateimetadaten sowie ein Link angezeigt, mit dem Sie über den Webclient auf den Inhalt zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d8a28-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="d8a28-112">Unterstützte Zeichen in den Namen von Aufbewahrungsbezeichnungen in der SharePoint-Suche</span><span class="sxs-lookup"><span data-stu-id="d8a28-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="d8a28-113">Die SharePoint-Suche unterstützt keine Namen von Aufbewahrungsbezeichnungen, die `-` oder `_` enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8a28-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="d8a28-114">`Label-MIP` und `Label_MIP` werden beispielsweise nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d8a28-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="d8a28-115">Diese Zeichen werden von der SharePoint-Suche nicht in Namen von Aufbewahrungsbezeichnungen und Namen von Typen vertraulicher Informationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d8a28-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="d8a28-116">OneDrive bleibt in der Vorschauphase</span><span class="sxs-lookup"><span data-stu-id="d8a28-116">OneDrive remains in preview</span></span>

<span data-ttu-id="d8a28-117">Vielen Dank für Ihr wertvolles Feedback zur OneDrive-Integration während unseres Vorschauprogramms.</span><span class="sxs-lookup"><span data-stu-id="d8a28-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="d8a28-118">Während wir die Einzelheiten bearbeiten, können Sie auf inkonsistente Daten/Flüsse stoßen.</span><span class="sxs-lookup"><span data-stu-id="d8a28-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="d8a28-119">Wir werden OneDrive weiterhin in der Vorschauphase präsentieren, bis alle Fehlerkorrekturen umgesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="d8a28-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="d8a28-120">Wir wissen Ihre fortgesetzte Unterstützung sehr zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="d8a28-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="d8a28-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8a28-121">See also</span></span>

- [<span data-ttu-id="d8a28-122">Erste Schritte mit der Datenklassifizierung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d8a28-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="d8a28-123">Beschriftungs-Aktivität anzeigen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d8a28-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d8a28-124">Anzeigen von beschriftetem Inhalt (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d8a28-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="d8a28-125">Weitere Informationen zu Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d8a28-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="d8a28-126">Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d8a28-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="d8a28-127">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="d8a28-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)