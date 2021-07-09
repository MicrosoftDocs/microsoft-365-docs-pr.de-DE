---
title: Fehlermeldung "Postfach nicht gefunden" in Outlook im Web erhalten
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Der Fehler **Postfach konnte nicht gefunden werden** bedeutet, dass das Konto, das Sie für die Verbindung mit Outlook im Web verwendet haben, keine Exchange Online-Lizenz besitzt.
ms.openlocfilehash: 54aa196b0b324054d6220d4437a672a3db2a45ec
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338565"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="b3580-103">Fehlermeldung "Postfach nicht gefunden" in Outlook im Web erhalten?</span><span class="sxs-lookup"><span data-stu-id="b3580-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="b3580-104">Wenn Sie Outlook im Web verwenden und die Fehlermeldung  **Postfach konnte nicht gefunden werden für**  angezeigt wird, verfügt das Konto, das Sie für die Verbindung mit Outlook im Web verwendet haben, nicht über eine Exchange Online-Lizenz und daher ist dem Konto kein Postfach zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b3580-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> 

## <a name="assign-a-license-to-your-account"></a><span data-ttu-id="b3580-105">Eine Lizenz Ihrem Konto zuweisen</span><span class="sxs-lookup"><span data-stu-id="b3580-105">Assign a license to your account</span></span>

<span data-ttu-id="b3580-106">Ihr Administrator kann Ihrem Konto eine Lizenz zuweisen, indem er die folgenden Schritte ausführt:</span><span class="sxs-lookup"><span data-stu-id="b3580-106">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="b3580-107">Öffnen Sie das  [ Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home#/homepage)  und gehen Sie zu  **Aktive Benutzer**  im Abschnitt  **Benutzer**  und wählen Sie den Benutzer aus, bei dem der Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="b3580-107">Open the  [Microsoft 365 admin center](https://admin.microsoft.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
1. <span data-ttu-id="b3580-108">Wechseln Sie auf der sich öffnenden Benutzerseite in den Bereich  **Lizenzen und Apps**, wählen Sie den entsprechenden  **Standortwert**  aus und weisen Sie eine Lizenz zu, die Exchange Online enthält (erweitern Sie die Lizenz, um ihre Details zu sehen).</span><span class="sxs-lookup"><span data-stu-id="b3580-108">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> 
1. <span data-ttu-id="b3580-109">Klicken Sie nach Abschluss des Vorgangs auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="b3580-109">When you're finished, click  **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="b3580-110">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="b3580-110">Related content</span></span>

<span data-ttu-id="b3580-111">[Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer](../email/add-another-email-alias-for-a-user.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="b3580-111">[Add another email alias for a user](../email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="b3580-112">[Konfigurieren der E-Mail-Weiterleitung in Microsoft 365](../email/configure-email-forwarding.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="b3580-112">[Configure email forwarding in Microsoft 365](../email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="b3580-113">[Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="b3580-113">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>