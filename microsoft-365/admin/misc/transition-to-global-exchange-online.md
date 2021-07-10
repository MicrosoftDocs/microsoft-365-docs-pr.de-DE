---
title: Aktualisieren Der MX-Einträge für den Umstieg auf den globalen Exchange Online Dienst
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie von Microsoft Cloud Deutschland Exchange Online zum globalen Exchange Online dienst wechseln.
ms.openlocfilehash: 93eab2c4e0ab2f841359061ebdca69967d8d7d33
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363871"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="eea31-103">Aktualisieren Der MX-Einträge für den Umstieg auf den globalen Exchange Online Dienst</span><span class="sxs-lookup"><span data-stu-id="eea31-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="eea31-104">Melden Sie sich bei [Microsoft 365 Admin Center](https://admin.microsoft.com)an, und wechseln Sie zu **Einstellungen**  >  **Domänen.**</span><span class="sxs-lookup"><span data-stu-id="eea31-104">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="eea31-105">Der Status wird für jede Domäne auf der rechten Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eea31-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="eea31-106">Wenn die Domänen Ihrer Organisation auf Microsoft Cloud Deutschland Exchange Online verweisen, müssen Sie Ihren MX-Eintrag aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="eea31-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="eea31-107">Klicken Sie auf die Domäne, und klicken Sie dann auf **dns-Fehler erkannt, klicken Sie hier, um anzuzeigen.**</span><span class="sxs-lookup"><span data-stu-id="eea31-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="eea31-108">Auf dieser Seite finden Sie Anweisungen zum Beheben des MX-Eintrags.</span><span class="sxs-lookup"><span data-stu-id="eea31-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="eea31-109">Wenn die Registrierungsstelle Ihrer Domäne [Domänen-Verbinden](../setup/add-domain.md#registrars-with-domain-connect)verwendet, können Sie oben auf "Meine Datensätze korrigieren" klicken.</span><span class="sxs-lookup"><span data-stu-id="eea31-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="eea31-110">Andernfalls können Sie dem Link im Assistenten folgen, um **Schritt-für-Schritt-Anweisungen** für Ihre Registrierungsstelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eea31-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>