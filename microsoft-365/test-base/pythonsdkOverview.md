---
title: Testen des Basis-SDK für Python
description: Details zum Verständnis des SDK der Testbasis für Python
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322795"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="338b6-103">Testen des Basis-SDK für Python</span><span class="sxs-lookup"><span data-stu-id="338b6-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="338b6-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="338b6-104">Overview</span></span>
<span data-ttu-id="338b6-105">Das Test Base SDK kann für die Interaktion mit der Azure-Testbasisressource verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="338b6-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="338b6-106">(d. h. Ihr Anwendungspaket verwalten, Paket erstellen, Paket bearbeiten und Paket löschen)</span><span class="sxs-lookup"><span data-stu-id="338b6-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="338b6-107">Mit dem SDK enthalten die Testzusammenfassung und das Analyseergebnis Folgendes: scriptExecution, Zuverlässigkeit, MemoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span><span class="sxs-lookup"><span data-stu-id="338b6-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="338b6-108">Mit dem Test Base SDK können Sie die Testbasis in Ihre CI/CD-Pipeline integrieren.</span><span class="sxs-lookup"><span data-stu-id="338b6-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="338b6-109">Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="338b6-109">Client Library</span></span>

<span data-ttu-id="338b6-110">Installieren Sie das Testbasispaket mit "pip".</span><span class="sxs-lookup"><span data-stu-id="338b6-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="338b6-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="338b6-111">Example</span></span>
