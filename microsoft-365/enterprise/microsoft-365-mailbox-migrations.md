---
title: Microsoft 365-Postfachmigrationen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Dieser Artikel enthält eine kurze Zusammenfassung über Microsoft 365-Postfachmigrationen und eine Liste der für Migrationen verwendeten Cmdlets.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a31eda9c33aa12e4f7c1fe3da4580eba9e1698a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690612"
---
# <a name="microsoft-365-mailbox-migrations"></a><span data-ttu-id="6cd8a-103">Microsoft 365-Postfachmigrationen</span><span class="sxs-lookup"><span data-stu-id="6cd8a-103">Microsoft 365 mailbox migrations</span></span>

<span data-ttu-id="6cd8a-104">Bei einer Exchange-basierten hybridbereitstellung können Kunden wahlweise lokale Exchange-Postfächer in eine [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) Organisation verschieben oder Exchange Online Postfächer in eine [lokale Exchange-](https://docs.microsoft.com/Exchange/exchange-server) Organisation verschieben.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="6cd8a-105">Migrationsbatches werden beim Verschieben von Postfächern zwischen lokalen und Exchange Online Organisationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span>

<span data-ttu-id="6cd8a-106">Kunden können Statistiken und andere Informationen zu Postfachmigrationen mit den folgenden Cmdlets überprüfen:</span><span class="sxs-lookup"><span data-stu-id="6cd8a-106">Customers can review statistics and other information about mailbox migrations with the following cmdlets:</span></span>

- <span data-ttu-id="6cd8a-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps): stellt Standardstatistiken für ein Benutzerpostfach bereit, das den Status, die Postfachgröße, die Archiv Postfachgröße und den abgeschlossenen Prozentsatz enthält.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps): Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size, and percentage complete.</span></span>
- <span data-ttu-id="6cd8a-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
): enthält eine Zusammenfassungsliste der Postfachobjekte und-Attribute in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
): Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="6cd8a-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps): enthält eine Liste vorhandener e-Mail-aktivierter Objekte wie Postfächer, e-Mail-Benutzer, Kontakte und Verteilergruppen.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps): Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts, and distribution groups.</span></span>
- <span data-ttu-id="6cd8a-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps): bietet einen detaillierten Status einer laufenden Postfachmigration.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps): Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="6cd8a-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps): enthält Informationen über die Benutzer der Post Fach Verlagerung und-Migration.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps): Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="6cd8a-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps): enthält Informationen zum Status des aktuellen Migrationsbatches.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps): Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="6cd8a-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps): enthält detaillierte Informationen zum Migrationsstatus für einen bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps): Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="6cd8a-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps): stellt Informationen zu Postfächern bereit, beispielsweise die Größe, die Anzahl der Nachrichten und die Uhrzeit des letzten Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="6cd8a-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps): Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="6cd8a-115">Weitere Informationen zu Cmdlets finden Sie unter [Umzugs-und Migrations-Cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="6cd8a-115">For more information about cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
