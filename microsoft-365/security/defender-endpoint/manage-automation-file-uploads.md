---
title: Verwalten von automatischen Dateiuploads
description: Aktivieren der Inhaltsanalyse und Konfigurieren der Dateierweiterung und E-Mail-Anlagenerweiterungen, die zur Analyse übermittelt werden
keywords: Automatisierung, Datei, Uploads, Inhalt, Analyse, Datei, Erweiterung, E-Mail, Anlage
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b7d330388dd698cb524c1f4a8edaf9039ba4d16e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454829"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="2bb5c-104">Verwalten von automatischen Dateiuploads</span><span class="sxs-lookup"><span data-stu-id="2bb5c-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2bb5c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2bb5c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2bb5c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2bb5c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bb5c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bb5c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2bb5c-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="2bb5c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2bb5c-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="2bb5c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="2bb5c-110">Aktivieren Sie die Funktion für die Inhaltsanalyse, damit bestimmte Dateien und E-Mail-Anlagen automatisch zur zusätzlichen Untersuchung in die Cloud hochgeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="2bb5c-111">Identifizieren Sie die Dateien und E-Mail-Anlagen, indem Sie die Dateierweiterungsnamen und die Namen der E-Mail-Anlagenerweiterung angeben.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="2bb5c-112">Wenn Sie beispielsweise *exe* und *bat* als Datei- oder Anlagenerweiterungsnamen hinzufügen, werden alle Dateien oder Anlagen mit diesen Erweiterungen automatisch zur zusätzlichen Überprüfung während der automatisierten Untersuchung an die Cloud gesendet.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="2bb5c-113">Fügen Sie Dateierweiterungsnamen und Namen von Anlagenerweiterungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="2bb5c-114">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpoints**  >  **Rules**  >  **Automation uploads** aus.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-114">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Automation uploads**.</span></span>

2. <span data-ttu-id="2bb5c-115">Umschalten der Inhaltsanalyseeinstellung zwischen **"Ein"** und **"Aus".**</span><span class="sxs-lookup"><span data-stu-id="2bb5c-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="2bb5c-116">Konfigurieren Sie die folgenden Erweiterungsnamen und separaten Erweiterungsnamen mit einem Komma:</span><span class="sxs-lookup"><span data-stu-id="2bb5c-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="2bb5c-117">**Dateierweiterungsnamen** – Verdächtige Dateien mit Ausnahme von E-Mail-Anlagen werden zur zusätzlichen Überprüfung übermittelt.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="2bb5c-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2bb5c-118">Related topics</span></span>
- [<span data-ttu-id="2bb5c-119">Verwalten von automatischen Ordnerausschlüssen</span><span class="sxs-lookup"><span data-stu-id="2bb5c-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
