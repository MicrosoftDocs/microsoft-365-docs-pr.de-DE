---
title: Einrichten von Benutzern und Fällen in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Informationen zum Konfigurieren von Benutzerrollen, Erstellen von Fällen und Zuweisen von Benutzern zu Fällen in Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: e53d304445aa7d171766d38496d95a0d6cb47792
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081914"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="a2564-103">Einrichten von Benutzern und Fällen in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a2564-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="a2564-104">In diesem Thema wird beschrieben, wie Sie Benutzer und Fälle für Office 365 Advanced eDiscovery einrichten.</span><span class="sxs-lookup"><span data-stu-id="a2564-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2564-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a2564-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="a2564-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a2564-107">Prerequisites</span></span>

<span data-ttu-id="a2564-108">Vor dem Einrichten von Fällen und Benutzern in Advanced eDiscovery ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="a2564-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="a2564-109">Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a2564-109">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="a2564-110">Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a2564-110">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="a2564-111">Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="a2564-111">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="a2564-112">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Office 365 Security &amp; Compliance Center sein, um einen eDiscovery-Fall zu erstellen und ihm Mitglieder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a2564-112">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="a2564-113">Um sich selbst der eDiscovery-Manager-Rollengruppe im &amp; Security Compliance Center hinzufügen zu können, müssen Sie ein globaler Administrator in Ihrer Office 365 Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="a2564-113">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="a2564-114">Wenn Sie kein globaler Administrator sind, müssen Sie einen globalen Administrator bitten, Sie zur eDiscovery-Manager-Rollengruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a2564-114">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="a2564-115">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a2564-115">For more information, see:</span></span>
    
  - [<span data-ttu-id="a2564-116">Berechtigungen im Microsoft 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a2564-116">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="a2564-117">Zuweisen von eDiscovery-Berechtigungen im Microsoft 365 &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a2564-117">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="a2564-118">Schritt 1: Zuweisen von eDiscovery-Berechtigungen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="a2564-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="a2564-119">Der erste Schritt besteht darin, Benutzern die Anforderungs Berechtigungen im Security &amp; Compliance Center zuzuweisen, damit Sie als Mitglied eines eDiscovery-Falls hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="a2564-119">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="a2564-120">Nachdem ein Benutzer als Mitglied eines Falls im Security &amp; Compliance Center hinzugefügt wurde, kann er auf den Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a2564-120">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="a2564-121">Wenn Sie einem Benutzer die erforderlichen Berechtigungen zuweisen möchten, damit diese als Mitglied eines eDiscovery-Falls hinzugefügt werden können, lesen Sie Schritt 1 in [eDiscovery- &amp; Fällen im Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="a2564-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="a2564-122">Schritt 2: Erstellen eines eDiscovery-Falls und Hinzufügen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="a2564-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="a2564-123">Der nächste Schritt ist das Erstellen eines neuen eDiscovery-Falls im Security &amp; Compliance Center und das Hinzufügen von Mitgliedern.</span><span class="sxs-lookup"><span data-stu-id="a2564-123">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="a2564-124">Mitglieder der Anfrage können dann auf den Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a2564-124">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="a2564-125">Informationen zum Erstellen eines neuen eDiscovery-Falls finden Sie unter Schritt 2 in [eDiscovery-Fällen im &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="a2564-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="a2564-126">Informationen zum Hinzufügen von Mitgliedern zu einem eDiscovery-Fall finden Sie unter Schritt 3 in [eDiscovery- &amp; Fällen im Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="a2564-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="a2564-127">Schritt 3: Wechseln Sie zu einem Fall in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a2564-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="a2564-128">Nachdem Sie einen eDiscovery-Fall erstellt und Mitglieder hinzugefügt haben, können Sie (oder ein beliebiges Mitglied des Falles) auf den entsprechenden Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a2564-128">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="a2564-129">Informationen zum Zugriff auf einen Fall in Advanced eDiscovery finden Sie unter Schritt 8 in [eDiscovery-Fällen im &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="a2564-129">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a2564-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2564-130">See also</span></span>

[<span data-ttu-id="a2564-131">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a2564-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a2564-132">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="a2564-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
