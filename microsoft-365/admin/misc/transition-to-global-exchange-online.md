---
title: Aktualisieren der MX-Einträge für den Übergang zum globalen Exchange Online Dienst
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Übergang von Microsoft Cloud Germany Exchange Online auf den globalen Exchange Online Dienst
ms.openlocfilehash: 41628b3032f5b268d5e32501b393fef31663dfc3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399230"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="fd8a3-103">Aktualisieren der MX-Einträge für den Übergang zum globalen Exchange Online Dienst</span><span class="sxs-lookup"><span data-stu-id="fd8a3-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="fd8a3-104">Melden Sie sich beim [Microsoft 365-Verwaltungsportal](https://admin.microsoft.com)an, und wechseln Sie zu **Einstellungen**  >  **Domänen**</span><span class="sxs-lookup"><span data-stu-id="fd8a3-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="fd8a3-105">Der Status wird für jede Domäne auf der rechten Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd8a3-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="fd8a3-106">Wenn die Domänen Ihrer Organisation auf Microsoft Cloud Deutschland Exchange Online, müssen Sie Ihren MX-Eintrag aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fd8a3-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="fd8a3-107">Klicken Sie auf die Domäne, klicken Sie dann auf **DNS-Fehler erkannt, klicken Sie hier, um anzuzeigen**.</span><span class="sxs-lookup"><span data-stu-id="fd8a3-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="fd8a3-108">Diese Seite enthält Anweisungen, um zu zeigen, wie Sie den MX-Eintrag korrigieren.</span><span class="sxs-lookup"><span data-stu-id="fd8a3-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="fd8a3-109">Wenn die Registrierungsstelle Ihrer Domäne [Domäne Connect](../setup/add-domain.md#registrars-with-domain-connect)verwendet, können Sie oben auf "meine Datensätze korrigieren" klicken.</span><span class="sxs-lookup"><span data-stu-id="fd8a3-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="fd8a3-110">Andernfalls können Sie dem Link im Assistenten folgen, um **schrittweise Anleitungen** für Ihre Registrierungsstelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fd8a3-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>