---
title: Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: b16ba88cd4984754f92fac2917f0f2b393600692
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082528"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="f7c9d-103">Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="f7c9d-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="f7c9d-104">[Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) schützt Ihre Organisation vor bösartigen Dateien in Dokumentbibliotheken und Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="f7c9d-105">Wenn eine bösartige Datei erkannt wird, wird diese Datei blockiert, sodass niemand Sie öffnen, kopieren, weiterleiten oder freigeben kann, bis weitere Aktionen vom Sicherheitsteam der Organisation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="f7c9d-106">In diesem Artikel erfahren Sie, wie Sie Informationen zu erkannten Dateien anzeigen und welche Aktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="f7c9d-107">Damit Sie die in diesem Artikel beschriebenen Aufgaben ausführen können, müssen Sie über die erforderlichen [Berechtigungen für das Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)verfügen.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="f7c9d-108">Anzeigen von Berichten mit Informationen zu erkannten Dateien</span><span class="sxs-lookup"><span data-stu-id="f7c9d-108">View reports with information about detected files</span></span>

<span data-ttu-id="f7c9d-109">Zum Anzeigen des Status und detaillierter Informationen zu Dateien, die von Office 365 ATP erkannt wurden, können Sie den Threat Protection-Statusbericht verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="f7c9d-110">Wählen Sie im [Office 365 &amp; Security Compliance Center](https://protection.office.com)die Option **Reports** \> **Dashboard** \> **Threat Protection Status**aus.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="f7c9d-111">Wählen Sie in der oberen rechten Ecke des Berichts die Option **Details-Tabelle anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="f7c9d-112">Zeigt die Liste der Dateien an, die im Bericht erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="f7c9d-113">Wählen Sie ein Element in der Liste aus, um detaillierte Informationen anzuzeigen, einschließlich der ausgeführten Aktionen, des Datei namens, des Dateipfads und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="f7c9d-114">Klicken Sie auf die Registerkarte **Erweiterte Analyse** , um Informationen wie beobachtetes Verhalten und Analysedetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="f7c9d-115">Anzeigen und Ausführen von Aktionen für Dateien in der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="f7c9d-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="f7c9d-116">Wählen Sie im Office 365 &amp; Security Compliance Center die Option **Threat Management** \> **Review** \> **Quarantine**aus.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="f7c9d-117">Ändern Sie in der oberen linken Ecke den Filter von **e-Mail** in **Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="f7c9d-118">Wählen Sie ein Element in der Liste aus, um detaillierte Informationen anzuzeigen, einschließlich der URL der Datei.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="f7c9d-119">Wählen Sie eine verfügbare Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="f7c9d-120">Wählen **Sie &amp; Release Report** aus, um die Datei zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="f7c9d-121">Wählen Sie **Bericht an Microsoft senden** aus, um die Datei als falsch positiv an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="f7c9d-122">Wählen Sie **Datei herunterladen** aus, um die Datei weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="f7c9d-123">Klicken Sie auf **Löschen** , um die Datei aus der Liste der isolierten Elemente zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-123">Choose **Delete** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="f7c9d-124">Wenn Sie diese Option auswählen, müssen Sie die Datei auch in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams aus der entsprechenden Bibliothek löschen.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-124">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="f7c9d-125">Mit dieser Option wird das Öffnen oder Freigeben einer Datei nicht aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-125">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="f7c9d-126">Wählen Sie **Schließen** aus, um die Details für ein ausgewähltes Element zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f7c9d-126">Choose **Close** to close the details for a selected item.</span></span> 
  
  

