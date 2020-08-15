---
title: Microsoft 365 Umgang mit Datenbeschädigung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In diesem Artikel werden Datenbeschädigungen in Microsoft 365 und die von Microsoft unternommenen Anstrengungen zum verhindern und Wiederherstellen von Daten erläutert.
ms.openlocfilehash: fabecf8e368813e2f895669edc19c3f74e305c35
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690473"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a><span data-ttu-id="7be43-103">Umgang mit Datenbeschädigung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7be43-103">Dealing with Data Corruption in Microsoft 365</span></span>

<span data-ttu-id="7be43-104">Einer der Herausforderungen bei der Ausführung eines umfangreichen Cloud-Diensts besteht darin, dass angesichts der großen Datenmengen und unabhängigen Systeme Datenbeschädigungen umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="7be43-104">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems.</span></span> <span data-ttu-id="7be43-105">Die Beschädigung von Daten kann durch folgende Ursachen verursacht werden:</span><span class="sxs-lookup"><span data-stu-id="7be43-105">Data corruption can be caused by:</span></span>

- <span data-ttu-id="7be43-106">Anwendungs-oder Infrastrukturfehler, die einen oder alle Anwendungszustände beschädigen</span><span class="sxs-lookup"><span data-stu-id="7be43-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span>
- <span data-ttu-id="7be43-107">Hardware Probleme, die zu Datenverlusten oder zum Lesen von Daten führen können</span><span class="sxs-lookup"><span data-stu-id="7be43-107">Hardware issues that result in lost data or an inability to read data</span></span>
- <span data-ttu-id="7be43-108">Menschliche Betriebsfehler</span><span class="sxs-lookup"><span data-stu-id="7be43-108">Human operational errors</span></span>
- <span data-ttu-id="7be43-109">Böswillige Hacker und verärgerte Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="7be43-109">Malicious hackers and disgruntled employees</span></span>
- <span data-ttu-id="7be43-110">Vorfälle in externen Diensten, die zu einem Datenverlust führen</span><span class="sxs-lookup"><span data-stu-id="7be43-110">Incidents in external services that result in some loss of data</span></span>

<span data-ttu-id="7be43-111">Da höhere Ausfallsicherheit in der Datenintegrität weniger Daten Beschädigungs Vorfälle bedeutet, hat Microsoft in Microsoft 365-Schutzmechanismen integriert, um zu verhindern, dass eine Beschädigung stattfindet, sowie von Systemen und Prozessen, mit denen Daten bei Bedarf wiederhergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="7be43-111">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Microsoft 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does.</span></span> <span data-ttu-id="7be43-112">Checks and Processes sind in den verschiedenen Phasen des Engineering-Release-Prozesses vorhanden, um die Ausfallsicherheit bei Datenbeschädigung zu verbessern, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="7be43-112">Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>

- <span data-ttu-id="7be43-113">System Design</span><span class="sxs-lookup"><span data-stu-id="7be43-113">System Design</span></span>
- <span data-ttu-id="7be43-114">Code Organisation und-Struktur</span><span class="sxs-lookup"><span data-stu-id="7be43-114">Code organization and structure</span></span>
- <span data-ttu-id="7be43-115">Code Überprüfung</span><span class="sxs-lookup"><span data-stu-id="7be43-115">Code review</span></span>
- <span data-ttu-id="7be43-116">Komponententests, Integrationstests und Systemtests</span><span class="sxs-lookup"><span data-stu-id="7be43-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="7be43-117">Trip Wires-Tests/Tore</span><span class="sxs-lookup"><span data-stu-id="7be43-117">Trip wires tests/gates</span></span>

<span data-ttu-id="7be43-118">In Microsoft 365-Produktionsumgebungen stellt die Peer Replikation zwischen Rechenzentren sicher, dass immer mehrere Live Kopien aller Daten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7be43-118">Within Microsoft 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data.</span></span> <span data-ttu-id="7be43-119">Standard Bilder und-Skripts werden verwendet, um verloren gegangene Server wiederherzustellen, und replizierte Daten werden verwendet, um Kundendaten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7be43-119">Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data.</span></span> <span data-ttu-id="7be43-120">Aufgrund der integrierten Überprüfungs-und Prozess Prozesse für die Datensicherheit unterhält Microsoft Sicherungen nur der Dokumentation zum Microsoft 365-Informationssystem (einschließlich sicherheitsbezogener Dokumentation) unter Verwendung der integrierten Replikation in SharePoint Online und unseres internen Code-Repository-Tools Source Depot.</span><span class="sxs-lookup"><span data-stu-id="7be43-120">Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Microsoft 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot.</span></span> <span data-ttu-id="7be43-121">Die Systemdokumentation wird in SharePoint Online gespeichert, und das Quell Depot enthält System-und Anwendungsbilder.</span><span class="sxs-lookup"><span data-stu-id="7be43-121">System documentation is stored in SharePoint Online, and Source Depot contains system and application images.</span></span> <span data-ttu-id="7be43-122">Sowohl SharePoint Online als auch das Quell Depot verwenden die Versionsverwaltung und werden nahezu in Echtzeit repliziert.</span><span class="sxs-lookup"><span data-stu-id="7be43-122">Both SharePoint Online and Source Depot use versioning and are replicated in near real time.</span></span>
