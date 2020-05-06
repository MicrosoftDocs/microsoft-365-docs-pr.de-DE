---
title: DSGVO für Project Server
description: Erfahren Sie, wie Sie mit Anforderungen der Datenschutz-Grundverordnung (DSGVO) in einer lokalen Project Server-Instanz umgehen.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3a7eb291d0da72adf171594aac307ec0ad91829d
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036238"
---
# <a name="gdpr-for-project-server"></a><span data-ttu-id="fd431-103">DSGVO für Project Server</span><span class="sxs-lookup"><span data-stu-id="fd431-103">GDPR for Project Server</span></span>

<span data-ttu-id="fd431-p101">Project Server verwendet benutzerdefinierte Skripts zum Exportieren und Bearbeiten von Benutzerdaten in Project Web App. Die grundlegende Vorgehensweise sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="fd431-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="fd431-106">Suchen Sie die Project Web App-Websites in Ihrer Farm.</span><span class="sxs-lookup"><span data-stu-id="fd431-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="fd431-107">Suchen Sie auf jeder Website die Projekte, die den Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="fd431-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="fd431-108">Exportieren und überprüfen Sie die Arten von Daten, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="fd431-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="fd431-109">Bearbeiten Sie die Daten bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="fd431-109">Redact data as needed.</span></span>

<span data-ttu-id="fd431-110">In den folgenden Artikeln werden diese Schritte ausführlich beschrieben:</span><span class="sxs-lookup"><span data-stu-id="fd431-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="fd431-111">Exportieren von Benutzerdaten aus Project Server</span><span class="sxs-lookup"><span data-stu-id="fd431-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="fd431-112">Löschen von Benutzerdaten aus Project Server</span><span class="sxs-lookup"><span data-stu-id="fd431-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="fd431-p102">Beachten Sie, dass Project Server auf SharePoint Server aufbaut und Ereignisse in SharePoint-ULS-Protokollen und in der Verwendungsdatenbank protokolliert. Weitere Informationen finden Sie unter [DSGVO für SharePoint Server](gdpr-for-sharepoint-server.md).</span><span class="sxs-lookup"><span data-stu-id="fd431-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>
