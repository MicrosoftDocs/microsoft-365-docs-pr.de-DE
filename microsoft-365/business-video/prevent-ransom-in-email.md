---
title: Erstellen von E-Mail-Regeln für Ransomware
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie E-Mail-Regeln erstellen, um Ransomware zu verhindern.
ms.openlocfilehash: 3b45af71aa26beb31e21f5db662091f46343f97d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926114"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="a9253-103">Erstellen von E-Mail-Regeln, um Ransomware zu verhindern</span><span class="sxs-lookup"><span data-stu-id="a9253-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="a9253-104">Microsoft 365 schützt Ihr Unternehmen vor Ransomware, indem es verhindert, dass potenziell gefährliche Dateien wie JavaScript, Batch und ausführbare Dateien in Outlook geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="a9253-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="a9253-105">Führen Sie die folgenden Schritte aus, um diese Schutzebene durch Hinzufügen von Regeln zu erhöhen, die zusätzliche Dateitypen blockieren oder warnen.</span><span class="sxs-lookup"><span data-stu-id="a9253-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="a9253-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="a9253-106">Try it!</span></span>

1. <span data-ttu-id="a9253-107">Wählen Sie im Admin Center unter Admin Center [https://admin.microsoft.com](https://admin.microsoft.com) **Exchange** **aus.**</span><span class="sxs-lookup"><span data-stu-id="a9253-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="a9253-108">Wählen Sie im Menü auf der linken Seite den **Nachrichtenfluss aus.**</span><span class="sxs-lookup"><span data-stu-id="a9253-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="a9253-109">Wählen Sie auf der Registerkarte "Regeln" den Pfeil neben dem Pluszeichen (+) aus, und wählen Sie dann **"Neue Regel erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a9253-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="a9253-110">Geben Sie **auf der Seite "Neue** Regel" einen Namen für die Regel ein, scrollen Sie nach unten, und wählen Sie dann **"Weitere Optionen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a9253-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="a9253-111">Under **Apply this rule if**, select Any **attachment**, and then select file extension includes **these words**.</span><span class="sxs-lookup"><span data-stu-id="a9253-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="a9253-112">Geben Sie in das Feld **unter**"Wörter oder Ausdrücke angeben" die Dateierweiterungen ein, auf die die Regel angewendet werden soll, z. B. Dateierweiterungen, die Makros enthalten können.</span><span class="sxs-lookup"><span data-stu-id="a9253-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="a9253-113">Verwenden Sie das Pluszeichen (+), um sie eins nach dem anderen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a9253-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="a9253-114">Weitere Informationen zu Dateitypen finden Sie unter ["Schutz vor Ransomware".](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)</span><span class="sxs-lookup"><span data-stu-id="a9253-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="a9253-115">Scrollen Sie nach unten, um Ihre Liste zu überprüfen, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="a9253-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="a9253-116">On the **new rule** page, choose **add condition**, and then choose a condition under Do **the following**.</span><span class="sxs-lookup"><span data-stu-id="a9253-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="a9253-117">Sie haben viele Regeloptionen zur Auswahl, aber in diesem Beispiel wird der Empfänger mit einer **Nachricht benachrichtigt.**</span><span class="sxs-lookup"><span data-stu-id="a9253-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="a9253-118">Geben Sie den Nachrichtentext für Ihre Benachrichtigung ein, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="a9253-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="a9253-119">Optional: Wählen Sie auf der **Seite** "Neue Regel" die Option "Ausnahme hinzufügen" **aus,** und geben Sie alle Details für Ausnahmen zu Ihrer Regel ein, z. B. Nachrichten von vertrauenswürdigen Absendern.</span><span class="sxs-lookup"><span data-stu-id="a9253-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="a9253-120">Wählen Sie auf der Seite "Neue Regel" die Option **"Speichern"** aus, und überprüfen Sie die bereitgestellten Regelzusammenfassungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="a9253-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>