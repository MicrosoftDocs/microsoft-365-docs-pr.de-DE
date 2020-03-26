---
title: Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wo Sie Informationen zu schädlichen Dateien anzeigen können, die in SharePoint, OneDrive oder Teams erkannt wurden, und wie Sie Aktionen für diese Dateien durchführen.
ms.openlocfilehash: 3a14c7d69c7081be6bd08840eb8f52c5e11d4be7
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955555"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="8c9ce-103">Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="8c9ce-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="8c9ce-104">[Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) schützt Ihre Organisation vor bösartigen Dateien in Dokumentbibliotheken und Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="8c9ce-105">Wenn eine bösartige Datei erkannt wird, wird diese Datei blockiert, sodass niemand Sie öffnen, kopieren, weiterleiten oder freigeben kann, bis weitere Aktionen vom Sicherheitsteam der Organisation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="8c9ce-106">In diesem Artikel erfahren Sie, wie Sie Informationen zu erkannten Dateien anzeigen und welche Aktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="8c9ce-107">Damit Sie die in diesem Artikel beschriebenen Aufgaben ausführen können, müssen Sie über die erforderlichen [Berechtigungen für das Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)verfügen.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="8c9ce-108">Anzeigen von Berichten mit Informationen zu erkannten Dateien</span><span class="sxs-lookup"><span data-stu-id="8c9ce-108">View reports with information about detected files</span></span>

<span data-ttu-id="8c9ce-109">Zum Anzeigen des Status und detaillierter Informationen zu Dateien, die von Office 365 ATP erkannt wurden, können Sie den Threat Protection-Statusbericht verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="8c9ce-110">Wählen Sie im [Office 365 &amp; Security Compliance Center](https://protection.office.com)die Option **Reports** \> **Dashboard** \> **Threat Protection Status**aus.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="8c9ce-111">Wählen Sie in der oberen rechten Ecke des Berichts die Option **Details-Tabelle anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="8c9ce-112">Zeigt die Liste der Dateien an, die im Bericht erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="8c9ce-113">Wählen Sie ein Element in der Liste aus, um detaillierte Informationen anzuzeigen, einschließlich der ausgeführten Aktionen, des Datei namens, des Dateipfads und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="8c9ce-114">Klicken Sie auf die Registerkarte **Erweiterte Analyse** , um Informationen wie beobachtetes Verhalten und Analysedetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="8c9ce-115">Anzeigen und Ausführen von Aktionen für Dateien in der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="8c9ce-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="8c9ce-116">Wählen Sie im Office 365 &amp; Security Compliance Center die Option **Threat Management** \> **Review** \> **Quarantine**aus.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="8c9ce-117">(Sie können auch direkt zu [https://protection.office.com/quarantine](https://protection.office.com/quarantine)wechseln.)</span><span class="sxs-lookup"><span data-stu-id="8c9ce-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="8c9ce-118">Ändern Sie in der oberen linken Ecke das Dropdownmenü von **e-Mails** in **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="8c9ce-119">Wenn die Liste der Ergebnisse zu viele Elemente enthält, verwenden Sie die **Filter** Funktionalität, um die Auswahl einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="8c9ce-120">Wählen Sie ein Element in der Liste aus, um detaillierte Informationen anzuzeigen, einschließlich der URL der Datei.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="8c9ce-121">Wählen Sie eine verfügbare Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-121">Choose an available action.</span></span>
    
    - <span data-ttu-id="8c9ce-122">Wählen Sie **Datei freigeben** aus, um die Datei zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-122">Choose **Release file** to unblock the file.</span></span> 

      <span data-ttu-id="8c9ce-123">Wählen Sie **Bericht an Microsoft senden** aus, um die Datei als falsch positiv an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 

    - <span data-ttu-id="8c9ce-124">Wählen Sie **Datei herunterladen** aus, um die Datei weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-124">Choose **Download file** to investigate the file further.</span></span> 

    - <span data-ttu-id="8c9ce-125">Wählen Sie **aus Quarantäne entfernen** aus, um die Datei aus der Liste der isolierten Elemente zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="8c9ce-126">Wenn Sie diese Option auswählen, müssen Sie die Datei auch in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams aus der entsprechenden Bibliothek löschen.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="8c9ce-127">Mit dieser Option wird das Öffnen oder Freigeben einer Datei nicht aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="8c9ce-128">Wählen Sie **Schließen** aus, um die Details für ein ausgewähltes Element zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8c9ce-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

