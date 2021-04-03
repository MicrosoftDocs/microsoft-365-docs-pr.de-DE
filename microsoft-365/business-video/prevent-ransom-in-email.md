---
title: Erstellen von E-Mail-Regeln für Ransomware
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie E-Mail-Regeln erstellen, um Ransomware zu verhindern.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580498"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="98ebb-103">Erstellen von E-Mail-Regeln zur Verhinderung von Ransomware</span><span class="sxs-lookup"><span data-stu-id="98ebb-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="98ebb-104">Microsoft 365 schützt Ihr Unternehmen vor Ransomware, indem es verhindert, dass potenziell gefährliche Dateien wie JavaScript, Batch und ausführbare Dateien in Outlook geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="98ebb-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="98ebb-105">Führen Sie die folgenden Schritte aus, um dieses Schutzniveau zu erhöhen, indem Sie Regeln hinzufügen, die Sie vor zusätzlichen Dateitypen blockieren oder warnen.</span><span class="sxs-lookup"><span data-stu-id="98ebb-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="98ebb-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="98ebb-106">Try it!</span></span>

1. <span data-ttu-id="98ebb-107">Wählen Sie im Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) Exchange unter Admin Center die Option Exchange **aus.** </span><span class="sxs-lookup"><span data-stu-id="98ebb-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="98ebb-108">Wählen Sie im Menü auf der linken Seite **E-Mail-Fluss aus.**</span><span class="sxs-lookup"><span data-stu-id="98ebb-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="98ebb-109">Wählen Sie auf der Registerkarte Regeln den Pfeil neben dem Pluszeichen (+) aus, und wählen Sie dann **Neue Regel erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="98ebb-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="98ebb-110">Geben Sie **auf** der Seite neue Regel einen Namen für Ihre Regel ein, scrollen Sie nach unten, und wählen Sie **dann Weitere Optionen aus.**</span><span class="sxs-lookup"><span data-stu-id="98ebb-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="98ebb-111">Wählen **Sie unter Diese Regel anwenden, wenn**, alle Anlagen **aus,** und wählen Sie dann **Dateierweiterung mit den folgenden Wörtern aus.**</span><span class="sxs-lookup"><span data-stu-id="98ebb-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="98ebb-112">Geben Sie im Feld unter Angeben von Wörtern oder Ausdrücken die Dateierweiterungen **ein,** auf die die Regel angewendet werden soll, z. B. Dateierweiterungen, die Makros enthalten können.</span><span class="sxs-lookup"><span data-stu-id="98ebb-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="98ebb-113">Verwenden Sie das Pluszeichen (+), um sie eins nach dem anderen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="98ebb-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="98ebb-114">Weitere Informationen zu Dateitypen finden Sie unter [Schützen vor Ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span><span class="sxs-lookup"><span data-stu-id="98ebb-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="98ebb-115">Scrollen Sie nach unten, um Ihre Liste zu überprüfen, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="98ebb-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="98ebb-116">Wählen Sie **auf der** Seite neue Regel **bedingung** hinzufügen aus, und wählen Sie dann eine Bedingung unter Do **the following** aus.</span><span class="sxs-lookup"><span data-stu-id="98ebb-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="98ebb-117">Sie haben viele Regeloptionen zur Auswahl, aber in diesem Beispiel wählen wir den Empfänger mit einer **Nachricht benachrichtigen aus.**</span><span class="sxs-lookup"><span data-stu-id="98ebb-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="98ebb-118">Geben Sie den Nachrichtentext für Ihre Benachrichtigung ein, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="98ebb-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="98ebb-119">Optional: Wählen Sie auf der **Neuen** Regelseite Ausnahme hinzufügen **aus,** und geben Sie alle Details für Ausnahmen zu Ihrer Regel ein, z. B. Nachrichten von vertrauenswürdigen Absendern.</span><span class="sxs-lookup"><span data-stu-id="98ebb-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="98ebb-120">Wählen Sie auf der Seite neue Regel **Speichern** aus, und überprüfen Sie die bereitgestellten Regelzusammenfassungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="98ebb-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>