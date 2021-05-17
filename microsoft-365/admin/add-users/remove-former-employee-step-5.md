---
title: 'Schritt 5: Löschen und Blockieren des mobilen Geräts eines ehemaligen Mitarbeiters'
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
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Führen Sie die folgenden Schritte aus, um den Zugriff auf mobile Geräte eines ehemaligen Mitarbeiters zu blockieren.
ms.openlocfilehash: 1ce12b06b6a0a74615ff8ac43b8f333456a469bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244242"
---
# <a name="step-5---wipe-and-block-a-former-employees-mobile-device"></a><span data-ttu-id="326e6-103">Schritt 5: Löschen und Blockieren des mobilen Geräts eines ehemaligen Mitarbeiters</span><span class="sxs-lookup"><span data-stu-id="326e6-103">Step 5 - Wipe and block a former employee's mobile device</span></span>

<span data-ttu-id="326e6-104">Wenn Ihr ehemaliger Mitarbeiter ein Organisationstelefon hatte, können Sie das Exchange Admin Center verwenden, um dieses Gerät zu löschen und zu blockieren, sodass alle Organisationsdaten vom Gerät entfernt werden und keine Verbindung mehr mit dem Office 365.</span><span class="sxs-lookup"><span data-stu-id="326e6-104">If your former employee had an organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.</span></span> <span data-ttu-id="326e6-105">Wenn Ihre Organisation grundlegende Mobilität und Sicherheit zum Verwalten mobiler Geräte verwendet, können Sie diese Geräte mithilfe von Basic Mobility and Security löschen und blockieren.</span><span class="sxs-lookup"><span data-stu-id="326e6-105">If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices using Basic Mobility and Security.</span></span>

## <a name="wipe-mobile-device-using-the-exchange-admin-center"></a><span data-ttu-id="326e6-106">Wischen des mobilen Geräts mithilfe Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="326e6-106">Wipe mobile device using the Exchange admin center</span></span>

1. <span data-ttu-id="326e6-107">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="326e6-107">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="326e6-108">Navigieren Sie im Exchange Admin Center zu **Empfänger** \> **Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="326e6-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="326e6-109">Wählen Sie den Benutzer aus, und wählen Sie unter **Mobile Geräte** Details **anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="326e6-109">Select the user, and under **Mobile Devices**, select **View details**.</span></span>
4. <span data-ttu-id="326e6-110">Wählen Sie auf der Seite Mobile **Gerätedetails** unter **Mobile** Geräte das mobile Gerät aus, wählen Sie **Wipe Data** Wipe Device aus, und wählen Sie ![ dann Blockieren ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **aus.**</span><span class="sxs-lookup"><span data-stu-id="326e6-110">On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe Data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block**.</span></span>
5. <span data-ttu-id="326e6-111">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="326e6-111">Select **Save**.</span></span>
   > [!TIP]
   > <span data-ttu-id="326e6-112">Stellen Sie sicher, dass Sie den Benutzer aus Ihrem lokalen Blackberry-Enterprise deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="326e6-112">Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service.</span></span> <span data-ttu-id="326e6-113">Sie sollten auch alle Blackberry-Geräte für den Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="326e6-113">You should also disable any Blackberry devices for the user.</span></span> <span data-ttu-id="326e6-114">Weitere Informationen zum Deaktivieren des Benutzers finden Sie im Blackberry Business Cloud Services Administration Guide.</span><span class="sxs-lookup"><span data-stu-id="326e6-114">Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.</span></span>
