---
title: Exportieren von Case-Daten in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel erfahren Sie, wie Sie Inhalte aus einer Überprüfungsgruppe für Präsentationen oder externe Reviews in einem erweiterten eDiscovery-Fall exportieren oder herunterladen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 114264f342a51f3ce68696f321cf7c6e929dc6d1
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726475"
---
# <a name="export-case-data-in-advanced-ediscovery"></a><span data-ttu-id="4bf7d-103">Exportieren von Case-Daten in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4bf7d-103">Export case data in Advanced eDiscovery</span></span>

<span data-ttu-id="4bf7d-104">Es gibt drei Möglichkeiten zum Exportieren von Daten aus einer Überprüfungsgruppe:</span><span class="sxs-lookup"><span data-stu-id="4bf7d-104">There are three ways to export data from a review set:</span></span>

<span data-ttu-id="4bf7d-105">**Download:** Laden Sie (mithilfe eines Browsers) eine kleine Gruppe von systemeigenen Dateien herunter.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-105">**Download:** Download (by using a browser) a small set of native files.</span></span> <span data-ttu-id="4bf7d-106">Dies ist die schnellste Möglichkeit, eine kleine Gruppe von Daten zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-106">This is the quickest way to export a small set of data.</span></span> <span data-ttu-id="4bf7d-107">Bei dieser Methode werden die systemeigenen Dateinamen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-107">This method preserves the native file names.</span></span>

<span data-ttu-id="4bf7d-108">**Export:** Passen Sie an, welche Daten exportiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-108">**Export:** Customize what data is exported.</span></span> <span data-ttu-id="4bf7d-109">Dies umfasst das Exportieren von Datei Metadaten, systemeigenen Dateien, Textdateien und behandelten Dokumenten, die in einer PDF-Datei gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-109">This includes exporting file metadata, native files, text files, and redacted documents that have been saved to a PDF file.</span></span> <span data-ttu-id="4bf7d-110">Nachdem die exportierten Daten in einen Azure-Speicherort hochgeladen wurden, können Sie Sie auf einen lokalen Computer herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-110">After the exported data is uploaded to an Azure Storage location, you can download it to a local computer.</span></span> <span data-ttu-id="4bf7d-111">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="4bf7d-111">For more information, see:</span></span>

- [<span data-ttu-id="4bf7d-112">Exportieren von Dokumenten aus einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="4bf7d-112">Export documents from a review set</span></span>](export-documents-from-review-set.md)

- [<span data-ttu-id="4bf7d-113">Herunterladen von Exportaufträgen</span><span class="sxs-lookup"><span data-stu-id="4bf7d-113">Download export jobs</span></span>](download-export-jobs.md)

<span data-ttu-id="4bf7d-114">**Zu einem anderen Überprüfungs Satzes hinzufügen:** Kopieren von Daten aus einem Überprüfungs Satzes in einen anderen Überprüfungs.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-114">**Add to another review set:** Copy data from one review set to a different review set.</span></span> <span data-ttu-id="4bf7d-115">Weitere Informationen finden Sie unter [Hinzufügen von Daten aus einer Überprüfungsgruppe zu einem anderen Überprüfungs Satzes](add-data-to-review-set-from-another-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="4bf7d-115">For more information, see [Add data from one review set to another review set](add-data-to-review-set-from-another-review-set.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4bf7d-116">In Microsoft 365 werden Daten gehasht, und diese Hashwerte werden in der Ausgabedatei zu Überprüfungszwecken bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-116">In Microsoft 365, data is hashed and those hashes are provided in the output file for verification purposes.</span></span> <span data-ttu-id="4bf7d-117">Dies wird durch Überwachungsprotokolle und Berichtsfunktionen wie Sammlungs Statistiken, Laden von Berichten und Exportieren von Berichten (einschließlich der Export Lade Datei) ergänzt.</span><span class="sxs-lookup"><span data-stu-id="4bf7d-117">This is supplemented by audit logs and reporting functionality, such as collection statistics, load set reports, and export reports (including the export load file).</span></span>
