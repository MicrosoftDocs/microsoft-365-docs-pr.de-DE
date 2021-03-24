---
title: Überwachungsberichte in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratoren können mehr über die Administratorüberwachungsberichte erfahren, die in Exchange Online Protection (EOP) verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08432f97d196df8b661d63a5d4cdf3680b78e070
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065464"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="94c4d-103">Überwachungsberichte in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="94c4d-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="94c4d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="94c4d-104">**Applies to**</span></span>
-  [<span data-ttu-id="94c4d-105">Exchange Online Protection eigenständig</span><span class="sxs-lookup"><span data-stu-id="94c4d-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="94c4d-106">In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Überwachungsberichte Ihnen bei der Erfüllung gesetzlicher, compliance- und rechtsstreitigkeiten für Ihre Organisation helfen.</span><span class="sxs-lookup"><span data-stu-id="94c4d-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="94c4d-107">Sie können die Überwachungsberichte jederzeit abrufen, um an Ihrer EOP-Konfiguration vorgenommene Änderungen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="94c4d-107">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="94c4d-108">Diese Berichte können Sie zum Behandeln von Konfigurationsproblemen sowie zum Ermitteln der Ursache von Sicherheits- oder Kompatibilitätsproblemen heranziehen.</span><span class="sxs-lookup"><span data-stu-id="94c4d-108">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="94c4d-109">Es stehen zwei Überwachungsberichte in eigenständigem EOP zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="94c4d-109">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="94c4d-110">**Administrator-Rollengruppenbericht:** Mit dem Administratorrollegruppenbericht können Sie anzeigen, wann ein Benutzer einer Administratorrollegruppe hinzugefügt oder aus der Mitgliedschaft entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="94c4d-110">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="94c4d-111">Sie können diesen Bericht verwenden, um Änderungen an administrativen Berechtigungen zu überwachen, die Benutzern in Ihrer Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="94c4d-111">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="94c4d-112">Weitere Informationen finden Sie unter [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span><span class="sxs-lookup"><span data-stu-id="94c4d-112">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="94c4d-113">**Administrator-Überwachungsprotokoll:** Das Administrator-Überwachungsprotokoll zeichnet alle Aktionen (basierend auf eigenständigen EOP PowerShell-Cmdlets) eines Administrators oder eines Benutzers mit Administratorrechten auf.</span><span class="sxs-lookup"><span data-stu-id="94c4d-113">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="94c4d-114">Weitere Informationen finden Sie unter [Anzeigen des Administrator-Überwachungsprotokolls in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span><span class="sxs-lookup"><span data-stu-id="94c4d-114">For more information, see [View the Administrator Audit Log in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>