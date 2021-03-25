---
title: Verwalten von Automatisierungsdateiuploads
description: Aktivieren der Inhaltsanalyse und Konfigurieren der Dateierweiterung und der E-Mail-Anlagenerweiterungen, die zur Analyse übermittelt werden
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
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068872"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="b5b6e-104">Verwalten von Automatisierungsdateiuploads</span><span class="sxs-lookup"><span data-stu-id="b5b6e-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5b6e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b5b6e-105">**Applies to:**</span></span>
- [<span data-ttu-id="b5b6e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b5b6e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b5b6e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5b6e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b5b6e-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b5b6e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b5b6e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b5b6e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="b5b6e-110">Aktivieren Sie die Inhaltsanalysefunktion, damit bestimmte Dateien und E-Mail-Anlagen automatisch zur zusätzlichen Überprüfung in die Cloud hochgeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="b5b6e-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="b5b6e-111">Identifizieren Sie die Dateien und E-Mail-Anlagen, indem Sie die Dateinamenerweiterungsnamen und E-Mail-Anlagenerweiterungsnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="b5b6e-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="b5b6e-112">Wenn Sie beispielsweise *exe* und *bat* als Datei- oder Anlagenerweiterungsnamen hinzufügen, werden alle Dateien oder Anlagen mit diesen Erweiterungen automatisch zur weiteren Überprüfung während der automatisierten Untersuchung an die Cloud gesendet.</span><span class="sxs-lookup"><span data-stu-id="b5b6e-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="b5b6e-113">Fügen Sie Dateinamen und Anlagenerweiterungsnamen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b5b6e-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="b5b6e-114">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Automatisierungsdateiuploads aus.**</span><span class="sxs-lookup"><span data-stu-id="b5b6e-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="b5b6e-115">Umschalten der Inhaltsanalyseeinstellung zwischen **Ein** und **Aus**.</span><span class="sxs-lookup"><span data-stu-id="b5b6e-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="b5b6e-116">Konfigurieren Sie die folgenden Erweiterungsnamen und separaten Erweiterungsnamen mit einem Komma:</span><span class="sxs-lookup"><span data-stu-id="b5b6e-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="b5b6e-117">**Dateinamenerweiterungsnamen** – Verdächtige Dateien mit Ausnahme von E-Mail-Anlagen werden zur weiteren Überprüfung übermittelt.</span><span class="sxs-lookup"><span data-stu-id="b5b6e-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="b5b6e-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b5b6e-118">Related topics</span></span>
- [<span data-ttu-id="b5b6e-119">Verwalten von Ausschlüssen für Automatisierungsordner</span><span class="sxs-lookup"><span data-stu-id="b5b6e-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
