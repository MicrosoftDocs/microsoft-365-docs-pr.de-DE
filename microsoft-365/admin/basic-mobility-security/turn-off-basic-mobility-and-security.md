---
title: Deaktivieren der grundlegenden Mobilität und Sicherheit
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
description: Entfernen Sie Gruppen oder Richtlinien, um die grundlegende Mobilität und Sicherheit zu deaktivieren.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336886"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="e02bb-103">Deaktivieren der grundlegenden Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e02bb-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="e02bb-104">Um die grundlegende Mobilität und Sicherheit effektiv zu deaktivieren, entfernen Sie Gruppen von Personen, die von Sicherheitsgruppen definiert wurden, aus den Geräteverwaltungsrichtlinien oder entfernen die Richtlinien selbst.</span><span class="sxs-lookup"><span data-stu-id="e02bb-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="e02bb-105">Entfernen Sie Gruppen von Benutzern, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen.</span><span class="sxs-lookup"><span data-stu-id="e02bb-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="e02bb-106">Deaktivieren Sie die grundlegenden Mobilitäts-und Sicherheitseinstellungen für alle, indem Sie alle grundlegenden Mobilitäts-und Sicherheitsgeräte Richtlinien entfernen.</span><span class="sxs-lookup"><span data-stu-id="e02bb-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="e02bb-107">Diese Optionen entfernen grundlegende Mobilitäts-und Sicherheitsvorkehrungen für Geräte in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e02bb-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="e02bb-108">Leider können Sie die grundlegende Mobilität und Sicherheit nicht einfach "aufheben", nachdem Sie Sie eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="e02bb-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="e02bb-109">Beachten Sie die Auswirkungen auf die Geräte der Benutzer, wenn Sie Benutzersicherheitsgruppen aus Richtlinien entfernen oder die Richtlinien selbst entfernen.</span><span class="sxs-lookup"><span data-stu-id="e02bb-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="e02bb-110">Beispielsweise können e-Mail-Profile und zwischengespeicherte e-Mails je nach Gerät entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="e02bb-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="e02bb-111">Weitere Informationen finden Sie unter  [Was geschieht, wenn Sie eine Richtlinie löschen oder einen Benutzer aus der Richtlinie entfernen?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="e02bb-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="e02bb-112">Entfernen von Benutzersicherheitsgruppen aus grundlegenden Mobilitäts-und Sicherheitsgeräte Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e02bb-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="e02bb-113">Geben Sie im Browsertyp Folgendes ein:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="e02bb-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="e02bb-114">Wählen Sie eine Geräterichtlinie aus, und wählen Sie **Richtlinie bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="e02bb-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="e02bb-115">Wählen Sie auf der Seite  **Bereitstellung** die   Option **Entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="e02bb-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="e02bb-116">Wählen Sie unter  **Gruppen**eine Sicherheitsgruppe aus.</span><span class="sxs-lookup"><span data-stu-id="e02bb-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="e02bb-117">Wählen Sie  **Entfernen**aus, und wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="e02bb-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="e02bb-118">Entfernen grundlegender Mobilitäts-und Sicherheitsgeräte Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e02bb-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="e02bb-119">Geben Sie im Browsertyp Folgendes ein:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="e02bb-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="e02bb-120">Wählen Sie eine Geräterichtlinie aus, und wählen Sie dann  **Richtlinie löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="e02bb-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="e02bb-121">Wählen Sie im Dialogfeldwarnung die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="e02bb-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="e02bb-122">Weitere Schritte zum Entsperren von Geräten, wenn sich Ihre Organisations Geräte noch im Status "blockiert" befinden, finden Sie im Blogbeitrag [Entfernen der Zugriffssteuerung von der Verwaltung mobiler Geräte für Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="e02bb-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
