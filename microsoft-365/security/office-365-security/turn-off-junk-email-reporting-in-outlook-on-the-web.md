---
title: Deaktivieren der Junk-E-Mail-Berichterstattung in Outlook im Web
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Als Office 365 Administrator können Sie die Möglichkeit deaktivieren, dass Personen e-Mails als Junk-e-Mails melden.
ms.openlocfilehash: de0e5d1aa51ececafc0d344b9907f6751a613370
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441172"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="1fa66-103">Deaktivieren der Junk-E-Mail-Berichterstattung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="1fa66-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="1fa66-104">Sie können Junk-e-Mails, Phishing-und nicht-Junk-Nachrichten zur Analyse mithilfe der Optionen für Junk-e-Mail-Berichte im Outlook im Internet (früher als Outlook Web App bezeichnet) senden, wie in [melden von Junk-e-Mails und Phishing-Scams in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1fa66-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="1fa66-105">Wenn Sie diese Optionen nicht verwenden möchten, können Administratoren Sie über das Cmdlet "Cmdlet [festlegen-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) " deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1fa66-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1fa66-106">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="1fa66-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="1fa66-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa66-107"></span></span>

- <span data-ttu-id="1fa66-108">Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten</span><span class="sxs-lookup"><span data-stu-id="1fa66-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="1fa66-109">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1fa66-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="1fa66-110">Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Outlook im webpostfach-Richtlinien" im Thema [Berechtigungen für Outlook im Internet](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) .</span><span class="sxs-lookup"><span data-stu-id="1fa66-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in the [Outlook on the web permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 

- <span data-ttu-id="1fa66-111">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1fa66-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="1fa66-112">Deaktivieren von Junk-, Phishing-und nicht-Junk-Berichten an Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fa66-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="1fa66-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa66-113"></span></span>

<span data-ttu-id="1fa66-114">Führen Sie zunächst den folgenden Befehl aus, um die Namen der verfügbaren Outlook im webpostfach-Richtlinien abzurufen:</span><span class="sxs-lookup"><span data-stu-id="1fa66-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="1fa66-115">Verwenden Sie als nächstes die folgende Syntax, um Junk-und nicht-Junk-Berichte an Microsoft in Outlook im Internet zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="1fa66-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="1fa66-116">In diesem Beispiel wird die Berichterstellung in der standardmäßigen Outlook-Webanwendung-Postfachrichtlinie deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="1fa66-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="1fa66-117">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) und [Sets-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span><span class="sxs-lookup"><span data-stu-id="1fa66-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1fa66-118">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="1fa66-118">How do you know this worked?</span></span>
<span data-ttu-id="1fa66-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa66-119"></span></span>

<span data-ttu-id="1fa66-120">Führen Sie **Get-OwaMailboxPolicy** aus, um die Parameterwerte zu überprüfen, und öffnen Sie dann Outlook im Internet für einen betroffenen Benutzer (auf den die Outlook im WebPost Fach Richtlinie angewendet wurde), und stellen Sie sicher, dass die Optionen zum Melden von Junk-, Phishing-und nicht-Junk-e-Mails nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1fa66-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="1fa66-121">Sie können Nachrichten weiterhin als Junk, Phishing und nicht als Junk markieren, aber Sie können Sie nicht melden.</span><span class="sxs-lookup"><span data-stu-id="1fa66-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
