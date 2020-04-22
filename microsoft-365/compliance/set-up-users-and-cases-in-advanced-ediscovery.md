---
title: Einrichten von Benutzern und Fällen in Advanced eDiscovery
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
description: 'Informationen zum Konfigurieren von Benutzerrollen, Erstellen von Fällen und Zuweisen von Benutzern zu Fällen in Advanced eDiscovery.  '
ms.openlocfilehash: 5c82ad8b630974d3afeb1928f8dd229ffb0dc36a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636069"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="79d36-103">Einrichten von Benutzern und Fällen in Advanced eDiscovery (klassisch)</span><span class="sxs-lookup"><span data-stu-id="79d36-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="79d36-104">In diesem Thema wird beschrieben, wie Sie Benutzer und Fälle für Advanced eDiscovery (Classic) einrichten.</span><span class="sxs-lookup"><span data-stu-id="79d36-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="79d36-105">Da wir weiterhin in neuere Versionen von Advanced eDiscovery investieren, kündigen wir den Ruhestand von Advanced eDiscovery an, auch bekannt als Advanced eDiscovery *(Classic)* oder *Advanced eDiscovery v 1.0*.</span><span class="sxs-lookup"><span data-stu-id="79d36-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="79d36-106">Wenn Sie noch mit Advanced eDiscovery v1.0 arbeiten, wechseln Sie so bald wie möglich zu [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (auch bekannt als *Advanced eDiscovery-Lösung in Microsoft 365*).</span><span class="sxs-lookup"><span data-stu-id="79d36-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="79d36-107">Advanced eDiscovery 2.0 enthält ähnliche Funktionen wie Advanced eDiscovery v1.0, bietet aber auch viele neue Funktionen wie z. B. Verwahrerverwaltung, Kommunikationsverwaltung und Prüfungssätze.</span><span class="sxs-lookup"><span data-stu-id="79d36-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="79d36-108">Um mehr über die Deaktivierung von Advanced eDiscovery v1.0 zu erfahren, siehe [Deaktivierung von veralteten eDiscovery-Tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). </span><span class="sxs-lookup"><span data-stu-id="79d36-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="79d36-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="79d36-109">Prerequisites</span></span>

<span data-ttu-id="79d36-110">Vor dem Einrichten von Fällen und Benutzern in Advanced eDiscovery ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="79d36-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="79d36-111">Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="79d36-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="79d36-112">Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="79d36-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="79d36-113">Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="79d36-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="79d36-114">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security &amp; Compliance Center sein, um einen eDiscovery-Fall zu erstellen und ihm Mitglieder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="79d36-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="79d36-115">Um sich selbst der eDiscovery-Manager-Rollengruppe im &amp; Security Compliance Center hinzufügen zu können, müssen Sie ein globaler Administrator in Ihrer Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="79d36-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="79d36-116">Wenn Sie kein globaler Administrator sind, müssen Sie einen globalen Administrator bitten, Sie zur eDiscovery-Manager-Rollengruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="79d36-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="79d36-117">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="79d36-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="79d36-118">Berechtigungen im Microsoft 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="79d36-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="79d36-119">Zuweisen von eDiscovery-Berechtigungen im Microsoft 365 &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="79d36-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="79d36-120">Schritt 1: Zuweisen von eDiscovery-Berechtigungen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="79d36-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="79d36-121">Der erste Schritt besteht darin, Benutzern die Anforderungs Berechtigungen im Security &amp; Compliance Center zuzuweisen, damit Sie als Mitglied eines eDiscovery-Falls hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="79d36-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="79d36-122">Nachdem ein Benutzer als Mitglied eines Falls im Security &amp; Compliance Center hinzugefügt wurde, kann er auf den Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="79d36-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="79d36-123">Wenn Sie einem Benutzer die erforderlichen Berechtigungen zuweisen möchten, damit diese als Mitglied eines eDiscovery-Falls hinzugefügt werden können, lesen Sie Schritt 1 in [eDiscovery- &amp; Fällen im Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="79d36-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="79d36-124">Schritt 2: Erstellen eines eDiscovery-Falls und Hinzufügen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="79d36-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="79d36-125">Der nächste Schritt ist das Erstellen eines neuen eDiscovery-Falls im Security &amp; Compliance Center und das Hinzufügen von Mitgliedern.</span><span class="sxs-lookup"><span data-stu-id="79d36-125">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="79d36-126">Mitglieder der Anfrage können dann auf den Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="79d36-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="79d36-127">Informationen zum Erstellen eines neuen eDiscovery-Falls finden Sie unter Schritt 2 in [eDiscovery-Fällen im &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="79d36-127">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="79d36-128">Informationen zum Hinzufügen von Mitgliedern zu einem eDiscovery-Fall finden Sie unter Schritt 3 in [eDiscovery- &amp; Fällen im Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="79d36-128">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="79d36-129">Schritt 3: Wechseln Sie zu einem Fall in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="79d36-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="79d36-130">Nachdem Sie einen eDiscovery-Fall erstellt und Mitglieder hinzugefügt haben, können Sie (oder ein beliebiges Mitglied des Falles) auf den entsprechenden Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="79d36-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="79d36-131">Informationen zum Zugriff auf einen Fall in Advanced eDiscovery finden Sie unter Schritt 8 in [eDiscovery-Fällen im &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="79d36-131">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79d36-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79d36-132">See also</span></span>

[<span data-ttu-id="79d36-133">Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="79d36-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="79d36-134">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="79d36-134">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
