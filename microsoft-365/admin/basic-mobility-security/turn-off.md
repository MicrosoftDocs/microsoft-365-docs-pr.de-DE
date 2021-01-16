---
title: Deaktivieren von Basic Mobility and Security
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
description: Entfernen Sie Gruppen oder Richtlinien, um "Basic Mobility and Security" zu deaktivieren.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876840"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="384f1-103">Deaktivieren von Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="384f1-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="384f1-104">Um basic Mobility and Security effektiv zu deaktivieren, entfernen Sie gruppen von Personen, die von Sicherheitsgruppen definiert sind, aus den Geräteverwaltungsrichtlinien oder entfernen die Richtlinien selbst.</span><span class="sxs-lookup"><span data-stu-id="384f1-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="384f1-105">Entfernen Sie Benutzergruppen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen.</span><span class="sxs-lookup"><span data-stu-id="384f1-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="384f1-106">Deaktivieren Sie "Basic Mobility and Security" für alle Benutzer, indem Sie alle Richtlinien für Grundlegende Mobilität und Sicherheit entfernen.</span><span class="sxs-lookup"><span data-stu-id="384f1-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="384f1-107">Diese Optionen entfernen die Erzwingung von Basic Mobility and Security für Geräte in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="384f1-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="384f1-108">Leider können Sie die Grundlegende Mobilität und Sicherheit nicht einfach "entsprovisionen", nachdem Sie sie eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="384f1-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="384f1-109">Beachten Sie die Auswirkungen auf die Geräte der Benutzer, wenn Sie Benutzersicherheitsgruppen aus Richtlinien entfernen oder die Richtlinien selbst entfernen.</span><span class="sxs-lookup"><span data-stu-id="384f1-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="384f1-110">Je nach Gerät können beispielsweise E-Mail-Profile und zwischengespeicherte E-Mails entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="384f1-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="384f1-111">Weitere Informationen finden Sie unter Was geschieht, wenn Sie eine Richtlinie löschen oder  [einen Benutzer aus der Richtlinie entfernen?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="384f1-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="384f1-112">Entfernen von Benutzersicherheitsgruppen aus den Geräterichtlinien für grundlegende Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="384f1-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="384f1-113">In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="384f1-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="384f1-114">Wählen Sie eine Geräterichtlinie aus, und wählen Sie **"Richtlinie bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="384f1-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="384f1-115">Wählen Sie  **auf der Seite "Bereitstellung"**   **"Entfernen" aus.**</span><span class="sxs-lookup"><span data-stu-id="384f1-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="384f1-116">Wählen  **Sie unter "Gruppen"** eine Sicherheitsgruppe aus.</span><span class="sxs-lookup"><span data-stu-id="384f1-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="384f1-117">Wählen Sie  **"Entfernen"** und **"Speichern" aus.**</span><span class="sxs-lookup"><span data-stu-id="384f1-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="384f1-118">Entfernen grundlegender Mobilitäts- und Sicherheitsgeräterichtlinien</span><span class="sxs-lookup"><span data-stu-id="384f1-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="384f1-119">In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="384f1-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="384f1-120">Wählen Sie eine Geräterichtlinie aus, und wählen Sie dann  **"Richtlinie löschen" aus.**</span><span class="sxs-lookup"><span data-stu-id="384f1-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="384f1-121">Wählen Sie im Dialogfeld "Warnung" die Option **"Ja" aus.**</span><span class="sxs-lookup"><span data-stu-id="384f1-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="384f1-122">Weitere Schritte zum Aufheben der Blockierung von Geräten, wenn geräte in Ihrer Organisation weiterhin blockiert sind, finden Sie im Blogbeitrag ["Removing Access Control from Mobile Device Management for Office 365 "Removing Access Control from Mobile Device Management for Office 365".](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="384f1-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
