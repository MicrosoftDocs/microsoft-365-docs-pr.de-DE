---
title: Erstellen von e-Mail-Regeln für Ransomware
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie e-Mail-Regeln zum Verhindern von Ransomware erstellen.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701933"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="1c4dd-103">Erstellen von e-Mail-Regeln zum Verhindern von Ransomware</span><span class="sxs-lookup"><span data-stu-id="1c4dd-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="1c4dd-104">Microsoft 365 hilft, Ihr Unternehmen vor Ransomware zu schützen, indem verhindert wird, dass potenziell gefährliche Dateien wie JavaScript, Batch und ausführbare Dateien in Outlook geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="1c4dd-105">Führen Sie die folgenden Schritte aus, um diesen Schutzgrad zu verbessern, indem Sie Regeln hinzufügen, mit denen Sie zusätzliche Dateitypen blockieren oder warnen.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="1c4dd-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="1c4dd-106">Try it!</span></span>

1. <span data-ttu-id="1c4dd-107">Wählen Sie im Admin Center [https://admin.microsoft.com](https://admin.microsoft.com) unter **Admin** Centers die Option **Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="1c4dd-108">Wählen Sie im Menü auf der linken Seite **Nachrichtenfluss** aus.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="1c4dd-109">Klicken Sie auf der Registerkarte Regeln auf den Pfeil neben dem Pluszeichen (+), und wählen Sie dann **neue Regel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="1c4dd-110">Geben Sie auf der Seite **neue Regel** einen Namen für die Regel ein, Scrollen Sie nach unten, und wählen Sie dann **Weitere Optionen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="1c4dd-111">Wählen Sie unter **diese Regel anwenden, wenn** **eine Anlage** aus, und wählen Sie dann **Dateierweiterung enthält diese Wörter** aus.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="1c4dd-112">Geben Sie im Feld unter **Geben Sie Wörter oder Ausdrücke angeben** die Dateierweiterungen ein, auf die die Regel angewendet werden soll, beispielsweise Dateierweiterungen, die Makros enthalten können.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="1c4dd-113">Verwenden Sie das Pluszeichen (+), um Sie einzeln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="1c4dd-114">Erfahren Sie mehr über Dateitypen, indem Sie [Protect gegen Ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)lesen.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="1c4dd-115">Scrollen Sie nach unten, um Ihre Liste zu überprüfen, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="1c4dd-116">Wählen Sie auf der Seite **neue Regel** die Option **Bedingung hinzufügen** aus, und wählen Sie dann unter **gehen Sie folgendermaßen** eine Bedingung aus.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="1c4dd-117">Sie haben viele Regeloptionen, aus denen Sie auswählen können, in diesem Beispiel wird **der Empfänger jedoch mit einer Nachricht benachrichtigt**.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="1c4dd-118">Geben Sie den Nachrichtentext für Ihre Benachrichtigung ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="1c4dd-119">Optional: Wählen Sie auf der Seite **neue Regel** die Option **Ausnahme hinzufügen** aus, und geben Sie alle Details für Ausnahmen für Ihre Regel ein, beispielsweise Nachrichten von vertrauenswürdigen Absendern.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="1c4dd-120">Wählen Sie auf der Seite neue Regel die Option **Speichern** aus, und überprüfen Sie die bereitgestellten Informationen zur Regel Zusammenfassung.</span><span class="sxs-lookup"><span data-stu-id="1c4dd-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>