---
title: Funktionsweise von Office 365 ATP-Sicherheits Links
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Das Feature "sichere Links" bietet eine Zeit-für-Mausklick-Überprüfung von Hyperlinks in Office-Dokumenten und e-Mail-Nachrichten. Lesen Sie diesen Artikel, um zu erfahren, wie ATP-sichere Links funktionieren.
ms.openlocfilehash: 7b1c1368b274bbbb6dc7a5b760de4968575962fa
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599202"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="a0a3b-104">Funktionsweise von Office 365 ATP-Sicherheits Links</span><span class="sxs-lookup"><span data-stu-id="a0a3b-104">How Office 365 ATP Safe Links works</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="a0a3b-105">So funktioniert ATP-sichere Links mit URLs in e-Mails</span><span class="sxs-lookup"><span data-stu-id="a0a3b-105">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="a0a3b-106">Auf einer hohen Ebene funktioniert der Schutz für [ATP-sichere Links](atp-safe-links.md) für URLs in e-Mails (in Office 365 gehostet, nicht lokal):</span><span class="sxs-lookup"><span data-stu-id="a0a3b-106">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="a0a3b-107">Personen erhalten e-Mail-Nachrichten, von denen einige URLs enthalten.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-107">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="a0a3b-108">Alle e-Mails werden Exchange Online Schutz durchlaufen, wobei IP-und Briefumschlag Filter, signaturbasierter Malware Schutz, Antispam-und Antischadsoftware-Filter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-108">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="a0a3b-109">E-Mail kommt in Postfächern der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-109">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="a0a3b-110">Ein Benutzer meldet sich bei Office 365 an und wechselt in den e-Mail-Posteingang.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-110">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="a0a3b-111">Der Benutzer öffnet eine e-Mail-Nachricht und klickt auf eine URL in der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-111">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="a0a3b-112">Das Feature "ATP-sichere Links" überprüft die URL unmittelbar vor dem Öffnen der Website.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-112">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="a0a3b-113">Die URL wird als blockiert, bösartig oder sicher identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-113">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="a0a3b-114">Wenn die URL zu einer Website gehört, die in der [Liste benutzerdefinierte blockierte URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md)der Organisation enthalten ist, wird eine [Warn Seite](atp-safe-links-warning-pages.md) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-114">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="a0a3b-115">Wenn die URL zu einer Website gehört, die als bösartig eingestuft wurde, wird eine [Warn Seite](atp-safe-links-warning-pages.md) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-115">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="a0a3b-116">Wenn die URL zu einer herunterladbaren Datei wechselt und die [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) in Ihrer Organisation für die Überprüfung solcher Inhalte konfiguriert sind, wird die herunterladbare Datei überprüft.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-116">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="a0a3b-117">Wenn die URL als sicher eingestuft wird, wird die Website geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-117">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="a0a3b-118">So funktioniert ATP-sichere Links mit URLs in Office-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="a0a3b-118">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="a0a3b-119">Auf einer hohen Ebene funktioniert der Schutz von [ATP-Links](atp-safe-links.md) für URLs in Office 365 ProPlus-oder Business Premium-Anwendungen (aktuelle Versionen von Word, Excel und PowerPoint unter Windows, Mac oder in einem Browser, Office-Apps auf IOS-oder Android-Geräten, Visio unter Windows, OneNote in einem Browser):</span><span class="sxs-lookup"><span data-stu-id="a0a3b-119">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="a0a3b-120">Benutzer haben Office 365 ProPlus oder Business Premium auf Ihrem Computer, Smartphone oder Tablet installiert.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-120">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="a0a3b-121">(Oder Sie verwenden Office in Ihrem Browser.)</span><span class="sxs-lookup"><span data-stu-id="a0a3b-121">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="a0a3b-122">Ein Benutzer öffnet ein Word-, Excel-, PowerPoint-, OneNote-(im Browser) oder Visio (auf dem Desktop) und meldet sich bei Office 365 Enterprise über sein Arbeits-oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-122">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="a0a3b-123">Das Dokument enthält URLs.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-123">The document contains URLs.</span></span>
    
3. <span data-ttu-id="a0a3b-124">Wenn der Benutzer auf eine URL im Dokument klickt, wird der Link vom ATP-Dienst für sichere Links überprüft.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-124">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="a0a3b-125">Wenn die URL zu einer Website gehört, die in der [Liste benutzerdefinierte blockierte URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md)der Organisation enthalten ist, wird der Benutzer zu einer [Warnungsseite](atp-safe-links-warning-pages.md)geleitet.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-125">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="a0a3b-126">Wenn die URL zu einer Website gehört, die als bösartig eingestuft wurde, wird der Benutzer zu einer [Warnungsseite](atp-safe-links-warning-pages.md)geleitet.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-126">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="a0a3b-127">Wenn die URL zu einer herunterladbaren Datei wechselt und die [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) für die Überprüfung solcher Downloads konfiguriert sind, wird die herunterladbare Datei überprüft.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-127">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="a0a3b-128">Wenn die URL als sicher eingestuft wird, wird der Benutzer zur Website geleitet.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-128">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="a0a3b-129">Wenn die URL-Prüfung fehlschlägt, wird der Schutz für sichere Links nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-129">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="a0a3b-130">Auf den Desktop Clients wird der Benutzer gewarnt, bevor er mit der Website fortfahren kann.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-130">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="a0a3b-131">Es kann einige Sekunden zu Beginn jeder Sitzung dauern, um sicherzustellen, dass der Benutzer über ATP-sichere Links für Office Enabled verfügt.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-131">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
