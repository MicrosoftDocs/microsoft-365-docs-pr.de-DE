---
title: DSGVO für Skype for Business Server
description: Erfahren Sie, wie Sie mit DSGVO-Anforderungen in lokalen Installationen von Skype for Business Server und Lync Server umgehen.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: aa0d66bcf727b7dd3c545384ec3a4838667a9183
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596402"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a><span data-ttu-id="50cec-103">DSGVO für Skype for Business Server und Lync Server</span><span class="sxs-lookup"><span data-stu-id="50cec-103">GDPR for Skype for Business Server and Lync Server</span></span>

<span data-ttu-id="50cec-p101">Die meisten Daten von Skype for Business Server und Lync Server werden in Exchange Server gespeichert. Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="50cec-p101">Most Skype for Business Server and Lync Server data is stored in Exchange Server. This includes:</span></span>

-   <span data-ttu-id="50cec-106">Aufgezeichnete Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="50cec-106">Conversation history</span></span>

-   <span data-ttu-id="50cec-107">Voicemail-Benachrichtigungen und Transkriptionen</span><span class="sxs-lookup"><span data-stu-id="50cec-107">Voicemail notifications and transcriptions</span></span>

-   <span data-ttu-id="50cec-108">Besprechungseinladungen</span><span class="sxs-lookup"><span data-stu-id="50cec-108">Meeting invites</span></span>

<span data-ttu-id="50cec-109">Verwenden Sie die für [DSGVO für Exchange Server](gdpr-for-exchange-server.md) erläuterten Verfahren, um diese Arten von Daten für DSGVO-Anfragen zu finden, zu exportieren oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="50cec-109">Use the procedures outlined for [GDPR for Exchange Server](gdpr-for-exchange-server.md) to find, export, or delete these types of data for GDPR requests.</span></span>

<span data-ttu-id="50cec-p102">Kontaktlisten werden in der SQL Server-Datenbank gespeichert. Sie können auf folgende Weise exportiert werden:</span><span class="sxs-lookup"><span data-stu-id="50cec-p102">Contact lists are stored in the SQL Server database. They can be exported in the following ways:</span></span>

-   <span data-ttu-id="50cec-p103">Endbenutzer selbst können die Kontakte exportieren, indem sie mit der rechten Maustaste auf den Gruppenkopf klicken und "Kopieren" auswählen. Dadurch werden alle Kontakte in dieser Gruppe in die Zwischenablage kopiert und können anschließend in jede beliebige Anwendung eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="50cec-p103">End users themselves can export the contacts by right clicking the group header and selecting Copy. This will copy all the contacts in that group into the clipboard, which can then be pasted into any app.</span></span>

-   <span data-ttu-id="50cec-114">Mit dem Cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) können Sie diese Daten exportieren.</span><span class="sxs-lookup"><span data-stu-id="50cec-114">You can use the [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>

<span data-ttu-id="50cec-p104">In Besprechungen hochgeladene Inhalte (z. B. PowerPoint-Dateien oder Handzettel) oder in einer Besprechung generierte Inhalte (z. B. Whiteboard, Umfragen oder Fragen und Antworten) werden im Filer gespeichert. Diese Inhalte können auch exportiert werden, wenn sich Endbenutzer wieder bei einer Besprechung anmelden, die noch nicht abgelaufen ist, und hochgeladene Inhalte herunterladen oder im Falle von generierten Inhalten Screenshots erstellen.</span><span class="sxs-lookup"><span data-stu-id="50cec-p104">Content uploaded into meetings (such as PowerPoint files or handouts) or content generated in a meeting (such as whiteboard, polls, or Q/A) is stored in the filer. This can also be exported if end users log back into any meeting that has not expired and download any uploaded content or take screenshots in the case of generated content.</span></span>

<span data-ttu-id="50cec-p105">MeetNow-Besprechungen, die sich nicht in Exchange-Kalender und Kontaktliste befinden, und Kontaktrechte (Familie, Kollegen usw.) sind in der Benutzerdatenbank. In Lync Server 2013 und höher können Sie diese Daten mit dem Cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) exportieren.</span><span class="sxs-lookup"><span data-stu-id="50cec-p105">MeetNow meetings that are not in the Exchange Calendar and Contact List and contact rights (family, co-worker, etc.) are in the User Database. In Lync Server 2013 and later, you can use the [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>
