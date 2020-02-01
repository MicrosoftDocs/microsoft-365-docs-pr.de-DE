---
title: Konfigurieren der Antispamrichtlinien
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Die Spamfilterung wird durch die standardmäßigen Antispamrichtlinien automatisch unternehmensweit aktiviert (Verbindungsfilter, Spamfilter und ausgehende Spamnachrichten). Als Administrator können Sie die standardmäßigen Antispamrichtlinien zwar nicht löschen, aber anzeigen und bearbeiten, sodass Sie sie optimal an die Anforderungen Ihrer Organisation anpassen können. Für eine höhere Granularität können Sie auch benutzerdefinierte Richtlinien erstellen und diese bestimmten Benutzern, Gruppen oder Domänen in Ihrer Organisation zuweisen. Standardmäßig haben die benutzerdefinierten Richtlinien Vorrang vor den Standardrichtlinien. Sie können die Prioritäten Ihrer Richtlinien jedoch verändern.
ms.openlocfilehash: 2ee5833bf476123a84411a7ad645b9f8c5d0b2b8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599582"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="c31d3-106">Konfigurieren der Antispamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c31d3-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="c31d3-p102">Die Spamfilterung wird durch die standardmäßigen Antispamrichtlinien automatisch unternehmensweit aktiviert (Verbindungsfilter, Spamfilter und ausgehende Spamnachrichten). Als Administrator können Sie die standardmäßigen Antispamrichtlinien zwar nicht löschen, aber anzeigen und bearbeiten, sodass Sie sie optimal an die Anforderungen Ihrer Organisation anpassen können. Für eine höhere Granularität können Sie auch benutzerdefinierte Richtlinien erstellen und diese bestimmten Benutzern, Gruppen oder Domänen in Ihrer Organisation zuweisen. Standardmäßig haben die benutzerdefinierten Richtlinien Vorrang vor den Standardrichtlinien. Sie können die Prioritäten Ihrer Richtlinien jedoch verändern.</span><span class="sxs-lookup"><span data-stu-id="c31d3-p102">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam). As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization. For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization. By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="c31d3-111">Weitere Informationen zum Konfigurieren der Antispamrichtlinien finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c31d3-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="c31d3-112">Konfigurieren der Verbindungsfilterrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c31d3-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="c31d3-113">Konfigurieren von Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c31d3-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="c31d3-114">Für Kunden der eigenständigen EOP-Lösung: Standardmäßig leiten die EOP-Inhaltsfilter als Spam erkannte Nachrichten an den Junk-E-Mail-Ordner der einzelnen Empfänger weiter.</span><span class="sxs-lookup"><span data-stu-id="c31d3-114">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder.</span></span> <span data-ttu-id="c31d3-115">Um jedoch sicherzustellen, dass die Aktion **Nachricht in Junk-e-Mail-Ordner verschieben** mit lokalen Postfächern funktioniert, müssen Sie zwei Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln) auf Ihren lokalen Servern konfigurieren, um von EoP hinzugefügte Spam Kopfzeilen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="c31d3-115">However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="c31d3-116">Weitere Informationen finden Sie unter [Sicherstellen, dass Spam an die Junk-E-Mail-Ordner der einzelnen Benutzer geleitet wird](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="c31d3-116">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="c31d3-117">Konfigurieren der Richtlinie für ausgehende Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="c31d3-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

