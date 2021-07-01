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
ms.openlocfilehash: 7ec4ec0d47668c21824d8e01e3845d637b9b0922
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228135"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="62469-103">Deaktivieren von grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="62469-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="62469-104">Um grundlegende Mobilität und Sicherheit effektiv zu deaktivieren, entfernen Sie gruppen von Sicherheitsgruppen definierte Personen aus den Geräteverwaltungsrichtlinien oder entfernen die Richtlinien selbst.</span><span class="sxs-lookup"><span data-stu-id="62469-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="62469-105">Entfernen Sie Benutzergruppen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen.</span><span class="sxs-lookup"><span data-stu-id="62469-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="62469-106">Deaktivieren Sie die grundlegende Mobilität und Sicherheit für alle Benutzer, indem Sie alle Geräterichtlinien für grundlegende Mobilität und Sicherheit entfernen.</span><span class="sxs-lookup"><span data-stu-id="62469-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="62469-107">Diese Optionen entfernen die Basic Mobility and Security-Erzwingung für Geräte in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="62469-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="62469-108">Leider können Sie die Grundlegende Mobilität und Sicherheit nicht einfach "aufheben", nachdem Sie sie eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="62469-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62469-109">Beachten Sie die Auswirkungen auf die Geräte der Benutzer, wenn Sie Benutzersicherheitsgruppen aus Richtlinien entfernen oder die Richtlinien selbst entfernen.</span><span class="sxs-lookup"><span data-stu-id="62469-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="62469-110">Beispielsweise können E-Mail-Profile und zwischengespeicherte E-Mails je nach Gerät entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="62469-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="62469-111">Weitere Informationen finden Sie unter  [Was geschieht, wenn Sie eine Richtlinie löschen oder einen Benutzer aus der Richtlinie entfernen?](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="62469-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="62469-112">Entfernen von Benutzersicherheitsgruppen aus grundlegenden Mobilitäts- und Sicherheitsgeräterichtlinien</span><span class="sxs-lookup"><span data-stu-id="62469-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="62469-113">In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="62469-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="62469-114">Wählen Sie eine Geräterichtlinie und dann **"Richtlinie bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="62469-114">Select a device policy, and select **Edit policy**.</span></span>

3. <span data-ttu-id="62469-115">Wählen Sie auf der Seite  **"Bereitstellung"** die   Option **"Entfernen" aus.**</span><span class="sxs-lookup"><span data-stu-id="62469-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="62469-116">Wählen Sie unter  **"Gruppen"** eine Sicherheitsgruppe aus.</span><span class="sxs-lookup"><span data-stu-id="62469-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="62469-117">Wählen Sie  **"Entfernen"** und dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="62469-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="62469-118">Entfernen grundlegender Mobilitäts- und Sicherheitsgeräterichtlinien</span><span class="sxs-lookup"><span data-stu-id="62469-118">Remove Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="62469-119">In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="62469-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="62469-120">Wählen Sie eine Geräterichtlinie und dann  **"Richtlinie löschen"** aus.</span><span class="sxs-lookup"><span data-stu-id="62469-120">Select a device policy, and then select  **Delete policy**.</span></span>

3. <span data-ttu-id="62469-121">Wählen Sie im Dialogfeld "Warnung" die Option **"Ja"** aus.</span><span class="sxs-lookup"><span data-stu-id="62469-121">In the Warning dialog box, select **Yes**.</span></span>

> [!NOTE]
> <span data-ttu-id="62469-122">Weitere Schritte zum Aufheben der Blockierung von Geräten, wenn sich Ihre Unternehmensgeräte weiterhin in einem blockierten Zustand befinden, finden Sie im Blogbeitrag ["Entfernen der Zugriffssteuerung aus Verwaltung mobiler Geräte für Office 365."](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="62469-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
