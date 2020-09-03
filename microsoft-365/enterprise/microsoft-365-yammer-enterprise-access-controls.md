---
title: Microsoft 365 jammern von Unternehmens Zugriffs Steuerelementen
ms.author: robmazz
author: robmazz
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
description: Dieser Artikel enthält eine kurze Zusammenfassung über das Jammern von Enterprise-Zugriffs Steuerelementen in der Produktionsumgebung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332664"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="40eb2-103">Jammern von Enterprise-Zugriffs Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="40eb2-103">Yammer enterprise access controls</span></span> 

<span data-ttu-id="40eb2-104">Der physische und logische Zugriff auf die Produktionsumgebung jammern ist auf eine kleine Gruppe von Personen (Infrastruktur und Betrieb) beschränkt.</span><span class="sxs-lookup"><span data-stu-id="40eb2-104">Physical and logical access to the Yammer production environment is restricted to a small set of people (infrastructure and operations).</span></span> <span data-ttu-id="40eb2-105">Wie bei anderen Microsoft 365-Ingenieuren haben Jammer Techniker keine ständigen Zugriff auf Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="40eb2-105">As with other Microsoft 365 engineers, Yammer engineers have zero standing access to customer data.</span></span> <span data-ttu-id="40eb2-106">Der Zugriff muss mithilfe eines Genehmigungs basierten Just-in-Time-Zugriffs Steuerungssystems angefordert werden, ähnlich wie Lockbox mit einer begrenzten Anzahl von genehmigenden Personen.</span><span class="sxs-lookup"><span data-stu-id="40eb2-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox with a limited number of approvers.</span></span> <span data-ttu-id="40eb2-107">Genehmigende Personen überprüfen die Anforderung (beispielsweise überprüfen, ob die Anforderung aufgrund von Bedarf, Geschäftsfall, Zeit usw. legitim ist), und genehmigen oder verweigern die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="40eb2-107">Approvers verify the request (for example, they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="40eb2-108">Wenn die Anforderung genehmigt wird, wird der JIT-Zugriff für eine definierte und beschränkte Zeit gewährt.</span><span class="sxs-lookup"><span data-stu-id="40eb2-108">If the request is approved, JIT access is granted for a defined and limited time.</span></span> <span data-ttu-id="40eb2-109">Nach Überschreiten der Zugriffszeit läuft der Zugriff automatisch ab.</span><span class="sxs-lookup"><span data-stu-id="40eb2-109">After access time is exceeded, the access automatically expires.</span></span>

<span data-ttu-id="40eb2-110">Wie bei anderen Microsoft 365-Diensten verwendet jeder Zugriff auf die Produktionsumgebung von jammern mehrstufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="40eb2-110">As with other Microsoft 365 services, all access to the Yammer production environment uses multi-factor authentication.</span></span> <span data-ttu-id="40eb2-111">Der gesamte Zugriffs-und Befehlsverlauf wird einem Benutzer zugeschrieben und regelmäßig vom Sicherheitsteam "jammern" protokolliert und überprüft.</span><span class="sxs-lookup"><span data-stu-id="40eb2-111">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="40eb2-112">Weitere Informationen zur Verwaltung und Verwaltung von jammern finden Sie unter [jammern der Administratorhilfe](https://docs.microsoft.com/yammer/yammer-landing-page).</span><span class="sxs-lookup"><span data-stu-id="40eb2-112">For more information about Yammer administration and management, see [Yammer admin help](https://docs.microsoft.com/yammer/yammer-landing-page).</span></span>