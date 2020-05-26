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
ms.openlocfilehash: bbef6729680db2c9a6aec4caa9036ec23fad6949
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327606"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="14a09-103">Veröffentlichungshinweise zur Datenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="14a09-103">Data classification release notes</span></span>

<span data-ttu-id="14a09-104">Lesen Sie diese Versionshinweise, damit Sie diese Datenklassifizierung optimal nutzen können.</span><span class="sxs-lookup"><span data-stu-id="14a09-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="14a09-105">Anzahl der Exchange-Postfächer</span><span class="sxs-lookup"><span data-stu-id="14a09-105">Exchange mailbox count</span></span>

<span data-ttu-id="14a09-106">Beim Ausführen eines Drilldowns in Exchange-Postfächer wird ein kleiner QuickInfo-Tipp angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14a09-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="14a09-107">Dadurch wird darauf hingewiesen, dass die für den vertraulichen Informationstyp, die Vertraulichkeitsbezeichnung und die Aufbewahrungsbezeichnung angezeigte Gesamtzahl möglicherweise nicht genau mit der Anzahl von Elementen übereinstimmt, die im Postfach zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="14a09-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="14a09-108">Der Grund dafür ist, dass der Drilldown in den Ordner die Live-Ansichten von Inhalten abruft, die klassifiziert sind, während die Gesamtzahl berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="14a09-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="14a09-109">Rendern von verschlüsselten Dokumenten</span><span class="sxs-lookup"><span data-stu-id="14a09-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="14a09-110">Verschlüsselte SharePoint-, Exchange- und OneDrive-Dateien werden im Inhalts-Explorer nicht gerendert.</span><span class="sxs-lookup"><span data-stu-id="14a09-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="14a09-111">Hierbei handelt es sich um ein heikles Problem, das einen Kompromiss zwischen der Notwendigkeit des Anzeigens von Dateiinhalten im Inhalts-Explorer und der Notwendigkeit der Verschlüsselung von Inhalten erfordert.</span><span class="sxs-lookup"><span data-stu-id="14a09-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="14a09-112">Mit den Berechtigungen, die von den Rollengruppen **Inhalts-Explorer-Listenanzeige** und **Inhalts-Explorer-Listenanzeige** gewährt werden, werden eine Listenansicht der Dateien, die Dateimetadaten sowie ein Link angezeigt, mit dem Sie über den Webclient auf den Inhalt zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="14a09-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="14a09-113">Unterstützte Zeichen in den Namen von Aufbewahrungsbezeichnungen in der SharePoint-Suche</span><span class="sxs-lookup"><span data-stu-id="14a09-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="14a09-114">Die SharePoint-Suche unterstützt keine Namen von Aufbewahrungsbezeichnungen, die `-` oder `_` enthalten.</span><span class="sxs-lookup"><span data-stu-id="14a09-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="14a09-115">`Label-MIP` und `Label_MIP` werden beispielsweise nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="14a09-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="14a09-116">Diese Zeichen werden von der SharePoint-Suche nicht in Namen von Aufbewahrungsbezeichnungen und Namen von Typen vertraulicher Informationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="14a09-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="14a09-117">OneDrive bleibt in der Vorschauphase</span><span class="sxs-lookup"><span data-stu-id="14a09-117">OneDrive remains in preview</span></span>

<span data-ttu-id="14a09-118">Wir haben uns Ihr wertvolles Feedback zur OneDrive-Integration während unseres Vorschauprogramms angehört.</span><span class="sxs-lookup"><span data-stu-id="14a09-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="14a09-119">Während wir die Einzelheiten bearbeiten, können Sie auf inkonsistente Daten/Flüsse stoßen.</span><span class="sxs-lookup"><span data-stu-id="14a09-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="14a09-120">Wir werden weiterhin OneDrive in der Vorschauphase präsentieren, bis alle Fehlerkorrekturen umgesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="14a09-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="14a09-121">Wir wissen Ihre anhaltende Unterstützung diesbezüglich zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="14a09-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="14a09-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14a09-122">See also</span></span>

- [<span data-ttu-id="14a09-123">Erste Schritte mit der Datenklassifizierung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="14a09-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="14a09-124">Beschriftungs-Aktivität anzeigen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="14a09-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="14a09-125">Anzeigen von beschriftetem Inhalt (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="14a09-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="14a09-126">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="14a09-126">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="14a09-127">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="14a09-127">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="14a09-128">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="14a09-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)