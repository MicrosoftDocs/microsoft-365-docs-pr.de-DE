---
title: Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Sie können die Standardgröße von PST-Dateien ändern, die beim Exportieren von eDiscovery-Suchergebnissen auf Ihren Computer heruntergeladen werden.
ms.openlocfilehash: 9deb90e688617981499bee286b95a0442fa1a1b4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595932"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="0c991-103">Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen</span><span class="sxs-lookup"><span data-stu-id="0c991-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="0c991-104">Wenn Sie das e-Mail-Ergebnis einer eDiscovery-Suche mithilfe des Office 365 eDiscovery-Exporttools aus den verschiedenen Microsoft eDiscovery-Tools exportieren, beträgt die Standardgröße einer PST-Datei, die exportiert werden kann, 10 GB.</span><span class="sxs-lookup"><span data-stu-id="0c991-104">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="0c991-105">Wenn Sie diese Standardgröße ändern möchten, können Sie die Windows-Registrierung auf dem Computer bearbeiten, mit dem Sie die Suchergebnisse exportieren.</span><span class="sxs-lookup"><span data-stu-id="0c991-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="0c991-106">Ein Grund hierfür ist, dass eine PST-Datei auf Wechselmedien, einer solchen DVD, einer CD oder einem USB-Laufwerk angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c991-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0c991-107">Das Office 365 eDiscovery-Export Tool wird verwendet, um die Suchergebnisse zu exportieren, wenn Sie das Tool für die Inhaltssuche im Security and Compliance Center, in-Place eDiscovery in Exchange Online und im eDiscovery Center in SharePoint Online verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c991-107">The Office 365 eDiscovery Export tool is used to export the search results when using the Content Search tool in the security and compliance center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="0c991-108">Erstellen einer Registrierungseinstellung zum Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen</span><span class="sxs-lookup"><span data-stu-id="0c991-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="0c991-109">Führen Sie das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse einer eDiscovery-Suche exportieren.</span><span class="sxs-lookup"><span data-stu-id="0c991-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="0c991-110">Schließen Sie das Office 365 eDiscovery-Export Tool, wenn es geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="0c991-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="0c991-111">Speichern Sie den folgenden Text in einer Fenster Registrierungsdatei unter Verwendung eines filename-Suffixes von. reg; Beispiel: PstExportSize. reg.</span><span class="sxs-lookup"><span data-stu-id="0c991-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="0c991-112">Im obigen Beispiel ist der `PstSizeLimitInBytes` Wert auf 1.073.741.824 Byte oder ungefähr 1 GB festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0c991-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="0c991-113">Hier sind einige weitere Beispielwerte für die `PstSizeLimitInBytes` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="0c991-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="0c991-114">**Größe in GB (ca.)**</span><span class="sxs-lookup"><span data-stu-id="0c991-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="0c991-115">**Größe in Bytes**</span><span class="sxs-lookup"><span data-stu-id="0c991-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0c991-116">0,7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="0c991-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="0c991-117">751619277</span><span class="sxs-lookup"><span data-stu-id="0c991-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="0c991-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="0c991-118">2 GB</span></span>  <br/> |<span data-ttu-id="0c991-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="0c991-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="0c991-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="0c991-120">4 GB</span></span>  <br/> |<span data-ttu-id="0c991-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="0c991-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="0c991-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="0c991-122">8 GB</span></span>  <br/> |<span data-ttu-id="0c991-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="0c991-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="0c991-124">Ändern Sie `PstSizeLimitInBytes` den Wert in die gewünschte maximale Größe einer PST-Datei, wenn Sie Suchergebnisse exportieren, und speichern Sie dann die Datei.</span><span class="sxs-lookup"><span data-stu-id="0c991-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="0c991-125">Klicken oder Doppelklicken Sie in Windows-Explorer auf die reg-Datei, die Sie in den vorherigen Schritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0c991-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="0c991-126">Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja** , damit der Registrierungs-Editor die Änderung vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="0c991-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="0c991-127">Wenn Sie aufgefordert werden, den Vorgang fortzusetzen, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0c991-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="0c991-128">Der Registrierungs-Editor zeigt eine Meldung an, die besagt, dass die Einstellung der Registrierung erfolgreich hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="0c991-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="0c991-129">Sie können die Schritte 3-6 wiederholen, um den Wert `PstSizeLimitInBytes` für die Registrierungseinstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0c991-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="0c991-130">Häufig gestellte Fragen zum Ändern der Standardgröße von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen</span><span class="sxs-lookup"><span data-stu-id="0c991-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="0c991-131">**Warum ist die Standardgröße 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="0c991-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="0c991-132">Die Standardgröße von 10 GB basierte auf dem Kundenfeedback; 10 GB ist ein gutes Gleichgewichtzwischen der optimalen Menge an Inhalten in einer einzelnen PST-Datei und einer minimalen Wahrscheinlichkeit von Beschädigung von Dateien.</span><span class="sxs-lookup"><span data-stu-id="0c991-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="0c991-133">**Sollte ich die Standardgröße von PST-Dateien vergrößern oder verkleinern?**</span><span class="sxs-lookup"><span data-stu-id="0c991-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="0c991-134">Kunden neigen dazu, die Größenbeschränkung so zu verringern, dass die Suchergebnisse auf Wechseldatenträgern angepasst werden, die Sie physisch an andere Standorte in Ihrer Organisation versenden können.</span><span class="sxs-lookup"><span data-stu-id="0c991-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="0c991-135">Es wird nicht empfohlen, dass Sie die Standardgröße vergrößern, da PST-Dateien mit mehr als 10 GB möglicherweise zu Problemen mit der Beschädigung kommen.</span><span class="sxs-lookup"><span data-stu-id="0c991-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="0c991-136">**Auf welchem Computer muss ich diese Funktion ausführen?**</span><span class="sxs-lookup"><span data-stu-id="0c991-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="0c991-137">Sie müssen die Registrierungseinstellung auf einem lokalen Computer ändern, auf dem Sie das Office 365 eDiscovery-Export Tool ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c991-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="0c991-138">**Muss ich den Computer neu starten, nachdem ich diese Einstellung geändert habe?**</span><span class="sxs-lookup"><span data-stu-id="0c991-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="0c991-139">Nein, Sie müssen den Computer nicht neu starten.</span><span class="sxs-lookup"><span data-stu-id="0c991-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="0c991-140">Wenn das Office 365 eDiscovery-Export Tool jedoch aktiv ist, müssen Sie es schließen und neu starten, nachdem Sie diese Einstellung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="0c991-140">But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="0c991-141">**Wird ein vorhandener Registrierungsschlüssel bearbeitet oder wird ein neuer Schlüssel erstellt?**</span><span class="sxs-lookup"><span data-stu-id="0c991-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="0c991-142">Ein neuer Registrierungsschlüssel wird erstellt, wenn Sie die reg-Datei zum ersten Mal ausführen, die Sie in diesem Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0c991-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="0c991-143">Anschließend wird die Einstellung jedes Mal bearbeitet, wenn Sie die reg-Bearbeitungs Datei ändern und erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c991-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
