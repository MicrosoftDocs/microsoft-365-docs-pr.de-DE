---
title: Einrichten von Benutzern und Fällen in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Informationen zum Konfigurieren von Benutzerrollen, Erstellen von Fällen und Zuweisen von Benutzern zu Fällen in Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 754cc7d73fc3325c2525e3101d1378d55afea4de
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601452"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="92af3-103">Einrichten von Benutzern und Fällen in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="92af3-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="92af3-104">In diesem Thema wird beschrieben, wie Sie Benutzer und Fälle für Office 365 Advanced eDiscovery einrichten.</span><span class="sxs-lookup"><span data-stu-id="92af3-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="92af3-105">Da wir weiterhin in neuere Versionen von Advanced eDiscovery investieren, kündigen wir den Ruhestand Office 365 Advanced eDiscovery (auch bekannt als *Advanced eDiscovery v 1.0*) an.</span><span class="sxs-lookup"><span data-stu-id="92af3-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="92af3-106">Wenn Sie noch Advanced eDiscovery v 1.0 verwenden, wechseln Sie so bald wie möglich zu [Advanced eDiscovery v 2.0](overview-ediscovery-20.md) (auch als *Erweiterte eDiscovery-Lösung in Microsoft 365*bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="92af3-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="92af3-107">Advanced eDiscovery 2,0 enthält ähnliche Funktionen wie in Advanced eDiscovery v 1.0, bietet aber auch viele neue Features wie Depotverwaltung, Kommunikationsverwaltung und Überprüfungs Sätze.</span><span class="sxs-lookup"><span data-stu-id="92af3-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="92af3-108">Weitere Informationen zum Ruhestand von Advanced eDiscovery v 1.0 finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="92af3-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="92af3-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="92af3-109">Prerequisites</span></span>

<span data-ttu-id="92af3-110">Vor dem Einrichten von Fällen und Benutzern in Advanced eDiscovery ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="92af3-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="92af3-111">Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="92af3-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="92af3-112">Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="92af3-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="92af3-113">Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="92af3-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="92af3-114">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Office 365 Security &amp; Compliance Center sein, um einen eDiscovery-Fall zu erstellen und ihm Mitglieder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="92af3-114">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="92af3-115">Um sich selbst der eDiscovery-Manager-Rollengruppe im &amp; Security Compliance Center hinzufügen zu können, müssen Sie ein globaler Administrator in Ihrer Office 365 Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="92af3-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="92af3-116">Wenn Sie kein globaler Administrator sind, müssen Sie einen globalen Administrator bitten, Sie zur eDiscovery-Manager-Rollengruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="92af3-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="92af3-117">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="92af3-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="92af3-118">Berechtigungen im Microsoft 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="92af3-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="92af3-119">Zuweisen von eDiscovery-Berechtigungen im Microsoft 365 &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="92af3-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="92af3-120">Schritt 1: Zuweisen von eDiscovery-Berechtigungen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="92af3-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="92af3-121">Der erste Schritt besteht darin, Benutzern die Anforderungs Berechtigungen im Security &amp; Compliance Center zuzuweisen, damit Sie als Mitglied eines eDiscovery-Falls hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="92af3-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="92af3-122">Nachdem ein Benutzer als Mitglied eines Falls im Security &amp; Compliance Center hinzugefügt wurde, kann er auf den Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="92af3-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="92af3-123">Wenn Sie einem Benutzer die erforderlichen Berechtigungen zuweisen möchten, damit diese als Mitglied eines eDiscovery-Falls hinzugefügt werden können, lesen Sie Schritt 1 in [eDiscovery- &amp; Fällen im Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="92af3-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="92af3-124">Schritt 2: Erstellen eines eDiscovery-Falls und Hinzufügen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="92af3-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="92af3-125">Der nächste Schritt ist das Erstellen eines neuen eDiscovery-Falls im Security &amp; Compliance Center und das Hinzufügen von Mitgliedern.</span><span class="sxs-lookup"><span data-stu-id="92af3-125">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="92af3-126">Mitglieder der Anfrage können dann auf den Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="92af3-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="92af3-127">Informationen zum Erstellen eines neuen eDiscovery-Falls finden Sie unter Schritt 2 in [eDiscovery-Fällen im &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="92af3-127">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="92af3-128">Informationen zum Hinzufügen von Mitgliedern zu einem eDiscovery-Fall finden Sie unter Schritt 3 in [eDiscovery- &amp; Fällen im Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="92af3-128">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="92af3-129">Schritt 3: Wechseln Sie zu einem Fall in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="92af3-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="92af3-130">Nachdem Sie einen eDiscovery-Fall erstellt und Mitglieder hinzugefügt haben, können Sie (oder ein beliebiges Mitglied des Falles) auf den entsprechenden Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="92af3-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="92af3-131">Informationen zum Zugriff auf einen Fall in Advanced eDiscovery finden Sie unter Schritt 8 in [eDiscovery-Fällen im &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="92af3-131">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92af3-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92af3-132">See also</span></span>

[<span data-ttu-id="92af3-133">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="92af3-133">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="92af3-134">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="92af3-134">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
