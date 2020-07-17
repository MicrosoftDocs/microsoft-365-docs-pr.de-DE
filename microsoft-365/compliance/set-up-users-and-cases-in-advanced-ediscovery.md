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
description: Informationen zum Konfigurieren von Benutzerrollen, Erstellen von Fällen und Zuweisen von Benutzern zu Fällen in Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e24354960b517815bef3cf498822d6ce9fd9dbe
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936742"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="77c14-103">Einrichten von Benutzern und Fällen in Advanced eDiscovery (klassisch)</span><span class="sxs-lookup"><span data-stu-id="77c14-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="77c14-104">In diesem Thema wird beschrieben, wie Sie Benutzer und Fälle für Advanced eDiscovery (Classic) einrichten.</span><span class="sxs-lookup"><span data-stu-id="77c14-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="77c14-105">Während wir weiterhin in neuere Versionen von Advanced eDiscovery investieren, kündigen wir jetzt die Deaktivierung von Advanced eDiscovery (auch bekannt als *Advanced eDiscovery (Classic)* oder *Advanced eDiscovery v1.0*) an.</span><span class="sxs-lookup"><span data-stu-id="77c14-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="77c14-106">Wenn Sie noch mit Advanced eDiscovery v1.0 arbeiten, wechseln Sie so bald wie möglich zu [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (auch bekannt als *Advanced eDiscovery-Lösung in Microsoft 365*).</span><span class="sxs-lookup"><span data-stu-id="77c14-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="77c14-107">Advanced eDiscovery 2.0 enthält ähnliche Funktionen wie Advanced eDiscovery v1.0, bietet aber auch viele neue Funktionen wie z. B. Verwahrerverwaltung, Kommunikationsverwaltung und Prüfungssätze.</span><span class="sxs-lookup"><span data-stu-id="77c14-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="77c14-108">Um mehr über die Deaktivierung von Advanced eDiscovery v1.0 zu erfahren, siehe [Deaktivierung von veralteten eDiscovery-Tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). </span><span class="sxs-lookup"><span data-stu-id="77c14-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="requirements-to-set-up-users-and-cases"></a><span data-ttu-id="77c14-109">Anforderungen zum Einrichten von Benutzern und Fällen</span><span class="sxs-lookup"><span data-stu-id="77c14-109">Requirements to set up users and cases</span></span>

<span data-ttu-id="77c14-110">Vor dem Einrichten von Fällen und Benutzern in Advanced eDiscovery ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="77c14-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="77c14-111">Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="77c14-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="77c14-112">Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="77c14-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="77c14-113">Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="77c14-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="77c14-114">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security &amp; Compliance Center sein, um einen eDiscovery-Fall zu erstellen und ihm Mitglieder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="77c14-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="77c14-115">Um sich selbst der eDiscovery-Manager-Rollengruppe im Security Compliance Center hinzufügen zu können &amp; , müssen Sie ein globaler Administrator in Ihrer Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="77c14-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="77c14-116">Wenn Sie kein globaler Administrator sind, müssen Sie einen globalen Administrator bitten, Sie zur eDiscovery-Manager-Rollengruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="77c14-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="77c14-117">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="77c14-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="77c14-118">Berechtigungen im Microsoft 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="77c14-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="77c14-119">Zuweisen von eDiscovery-Berechtigungen im Microsoft 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="77c14-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="77c14-120">Schritt 1: Zuweisen von eDiscovery-Berechtigungen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="77c14-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="77c14-121">Der erste Schritt besteht darin, Benutzern die Anforderungs Berechtigungen im Security &amp; Compliance Center zuzuweisen, damit Sie als Mitglied eines eDiscovery-Falls hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="77c14-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="77c14-122">Nachdem ein Benutzer als Mitglied eines Falls im Security Compliance Center hinzugefügt wurde &amp; , kann er auf den Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="77c14-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="77c14-123">Wenn Sie einem Benutzer die erforderlichen Berechtigungen zuweisen möchten, damit diese als Mitglied eines eDiscovery-Falls hinzugefügt werden können, lesen Sie Schritt 1 in [eDiscovery-Fällen im Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="77c14-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="77c14-124">Schritt 2: Erstellen eines eDiscovery-Falls und Hinzufügen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="77c14-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="77c14-125">Der nächste Schritt ist das Erstellen eines neuen eDiscovery-Falls im Security & Compliance Center und das Hinzufügen von Mitgliedern.</span><span class="sxs-lookup"><span data-stu-id="77c14-125">The next step is to create a new eDiscovery case in the Security & Compliance Center and add members.</span></span> <span data-ttu-id="77c14-126">Mitglieder der Anfrage können dann auf den Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="77c14-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="77c14-127">Informationen zum Erstellen eines neuen eDiscovery-Falls finden Sie in Schritt 3 unter [Erste Schritte mit der Haupt-eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span><span class="sxs-lookup"><span data-stu-id="77c14-127">To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span></span>

2. <span data-ttu-id="77c14-128">Informationen zum Hinzufügen von Mitgliedern zu einem eDiscovery-Fall finden Sie in Schritt 4 unter [Erste Schritte mit der Haupt-eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span><span class="sxs-lookup"><span data-stu-id="77c14-128">To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span></span>

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="77c14-129">Schritt 3: Wechseln Sie zu einem Fall in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="77c14-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="77c14-130">Nachdem Sie einen eDiscovery-Fall erstellt und Mitglieder hinzugefügt haben, können Sie (oder ein beliebiges Mitglied des Falles) auf den entsprechenden Fall in Advanced eDiscovery zugreifen.</span><span class="sxs-lookup"><span data-stu-id="77c14-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="77c14-131">Informationen zum Zugriff auf einen Fall in Advanced eDiscovery finden Sie unter [zugreifen auf einen Fall in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="77c14-131">To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77c14-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77c14-132">See also</span></span>

[<span data-ttu-id="77c14-133">Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="77c14-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="77c14-134">Vorbereiten von Daten für Advanced eDiscovery (klassisch)</span><span class="sxs-lookup"><span data-stu-id="77c14-134">Preparing data for Advanced eDiscovery (classic)</span></span>](prepare-data-for-advanced-ediscovery.md)
 
