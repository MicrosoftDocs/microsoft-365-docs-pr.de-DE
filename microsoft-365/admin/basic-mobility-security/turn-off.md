---
title: Deaktivieren von grundlegender Mobilität und Sicherheit
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Entfernen Sie Gruppen oder Richtlinien, um grundlegende Mobilität und Sicherheit zu deaktivieren.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023869"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="7e9ad-103">Deaktivieren von grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7e9ad-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="7e9ad-104">Um grundlegende Mobilität und Sicherheit effektiv zu deaktivieren, entfernen Sie Gruppen von Personen, die von Sicherheitsgruppen definiert sind, aus den Geräteverwaltungsrichtlinien, oder entfernen Sie die Richtlinien selbst.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="7e9ad-105">Entfernen Sie Benutzergruppen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="7e9ad-106">Deaktivieren Sie grundlegende Mobilität und Sicherheit für alle Benutzer, indem Sie alle Geräterichtlinien für Grundlegende Mobilität und Sicherheit entfernen.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="7e9ad-107">Mit diesen Optionen wird die Erzwingung von Basic Mobility and Security für Geräte in Ihrer Organisation entfernt.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="7e9ad-108">Leider können Sie grundlegende Mobilität und Sicherheit nach der Einrichtung nicht einfach "unprovision".</span><span class="sxs-lookup"><span data-stu-id="7e9ad-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="7e9ad-109">Beachten Sie die Auswirkungen auf die Geräte von Benutzern, wenn Sie Benutzersicherheitsgruppen aus Richtlinien entfernen oder die Richtlinien selbst entfernen.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="7e9ad-110">Je nach Gerät können beispielsweise E-Mail-Profile und zwischengespeicherte E-Mails entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="7e9ad-111">Weitere Informationen finden Sie unter Was geschieht, wenn Sie eine Richtlinie löschen oder  [einen Benutzer aus der Richtlinie entfernen?](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7e9ad-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="7e9ad-112">Entfernen von Benutzersicherheitsgruppen aus Geräterichtlinien für grundlegende Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7e9ad-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="7e9ad-113">In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="7e9ad-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="7e9ad-114">Wählen Sie eine Geräterichtlinie aus, und wählen Sie **Richtlinie bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="7e9ad-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="7e9ad-115">Wählen Sie  **auf der** Seite Bereitstellung die Option   Entfernen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7e9ad-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="7e9ad-116">Wählen  **Sie unter Gruppen** eine Sicherheitsgruppe aus.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="7e9ad-117">Wählen  **Sie Entfernen** aus, und wählen Sie Speichern **aus.**</span><span class="sxs-lookup"><span data-stu-id="7e9ad-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="7e9ad-118">Entfernen grundlegender Mobilitäts- und Sicherheitsgeräterichtlinien</span><span class="sxs-lookup"><span data-stu-id="7e9ad-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="7e9ad-119">In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="7e9ad-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="7e9ad-120">Wählen Sie eine Geräterichtlinie aus, und wählen Sie dann  **Richtlinie löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="7e9ad-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="7e9ad-121">Wählen Sie im Dialogfeld Warnung ja **aus.**</span><span class="sxs-lookup"><span data-stu-id="7e9ad-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="7e9ad-122">Weitere Schritte zum Aufheben der Blockierung von Geräten, wenn sich Ihre Organisationsgeräte weiterhin in einem blockierten Zustand befinden, finden Sie im Blogbeitrag Entfernen der Zugriffssteuerung aus der Verwaltung mobiler [Geräte für Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="7e9ad-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
