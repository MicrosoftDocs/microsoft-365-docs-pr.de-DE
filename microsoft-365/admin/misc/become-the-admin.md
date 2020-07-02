---
title: Ausführen einer internen Übernahme durch den Administrator
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Erfahren Sie, wie Sie überprüfen, ob Ihr e-Mail-und Domänenbesitz einen nicht verwalteten Mandanten in Microsoft 365 übernimmt.
ms.openlocfilehash: 1eb54a6c34c9700bda09a660c71d2b1222fcdb8c
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022157"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="fa46e-103">Ausführen einer internen Übernahme durch den Administrator</span><span class="sxs-lookup"><span data-stu-id="fa46e-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="fa46e-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="fa46e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="fa46e-105">Wenn Sie ein Administrator sind und einen nicht verwalteten Mandanten übernehmen möchten, der von einer Self-Service-Benutzeranmeldung erstellt wurde, können Sie dies mit einer internen Übernahme durch den Administrator tun.</span><span class="sxs-lookup"><span data-stu-id="fa46e-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="fa46e-106">Eine Self-Service-Registrierung für einen beliebigen cloudbasierten Dienst, der Azure AD verwendet, fügt den Benutzer einem nicht verwalteten oder "Shadow"-Azure AD Verzeichnis hinzu und erstellt einen nicht verwalteten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="fa46e-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="fa46e-107">Ein nicht verwalteter Mandant ist ein Verzeichnis ohne globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="fa46e-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="fa46e-108">Informationen zum ermitteln, ob ein Mandant verwaltet oder nicht verwaltet wird, finden Sie unter [bestimmen des Mandanten Typs](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="fa46e-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="fa46e-109">Schritt 1: Überprüfen Ihrer e-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="fa46e-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="fa46e-110">Wenn Self-Service in Ihrem Mandanten aktiviert ist, können Benutzer kostenlos Dienste wie Power BI selbst abonnieren.</span><span class="sxs-lookup"><span data-stu-id="fa46e-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="fa46e-111">Bei diesen Schritten wird davon ausgegangen, dass ein Self-Service-Benutzer Abonnement den nicht verwalteten Mandanten erstellt hat, den Sie als Administrator übernehmen möchten. Im ersten Schritt erstellen Sie einen Benutzerkontext im nicht verwalteten Mandanten, indem Sie Power BI verwenden, um den Übernahme Pfad des Administrators zu illustrieren.</span><span class="sxs-lookup"><span data-stu-id="fa46e-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="fa46e-112">Wenn Sie sich für Power BI registrieren möchten, wechseln Sie zur [Power BI-Website](https://powerbi.com) , **und wählen Sie ﻿kostenlose**  >  **Testversion** starten (in Freigabe mit Power BI pro Box) aus.</span><span class="sxs-lookup"><span data-stu-id="fa46e-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="fa46e-113">Registrieren Sie sich mit einem Benutzerkonto, das den Domänennamen Ihrer Organisation (like `powerbiadmin@contoso.com` ) verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa46e-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="fa46e-114">Wenn Ihr Konto bereits verwendet wird, melden Sie sich mit Ihrem aktuellen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="fa46e-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="fa46e-115">Überprüfen Sie Ihre e-Mails auf den **Verifizierungscode** , und geben Sie den Code zum Überprüfen Ihrer e-Mail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="fa46e-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="fa46e-116">Schritt 2: Erstellen eines neuen Kontos</span><span class="sxs-lookup"><span data-stu-id="fa46e-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="fa46e-117">Wenn Sie den Überprüfungscode eingeben, werden Sie auf eine Seite gebracht, auf der Sie ein neues Konto erstellen können.</span><span class="sxs-lookup"><span data-stu-id="fa46e-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="fa46e-118">Geben Sie die Felder Benutzername und Kennwort mit dem Konto ein, das Sie verwenden möchten, und wählen Sie dann **Start**aus.</span><span class="sxs-lookup"><span data-stu-id="fa46e-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="fa46e-119">Schritt 3: Überprüfen des Domänenbesitzes und als Administrator</span><span class="sxs-lookup"><span data-stu-id="fa46e-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="fa46e-120">Der Assistent zum Ausführen **des Administrators** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fa46e-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="fa46e-121">Wenn der Assistent nicht gestartet wird, suchen Sie nach der **Administrator** Kachel, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="fa46e-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="fa46e-122">Wählen Sie **Ja aus, ich möchte der Administrator sein**.</span><span class="sxs-lookup"><span data-stu-id="fa46e-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="fa46e-123">Stellen Sie sicher, dass Sie die Domäne besitzen, die Sie übernehmen möchten, indem Sie Ihrer Domänenregistrierungsstelle einen TXT-Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa46e-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="fa46e-124">Der Assistent gibt Ihnen den TXT-Eintrag, der hinzugefügt werden soll, sowie einen Link zur Website Ihrer Registrierungsstelle sowie einen Link zu Schritt-für-Schritt-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fa46e-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="fa46e-125">Nachdem Sie den TXT-Eintrag zur Registrierungsstelle hinzugefügt haben, kehren Sie zum Assistenten zurück, und wählen Sie **OK, ich habe den Eintrag hinzugefügt**.</span><span class="sxs-lookup"><span data-stu-id="fa46e-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fa46e-126">Die Übernahme des Shadow-Mandanten wirkt sich nicht auf vorhandene Informationen oder Dienste aus.</span><span class="sxs-lookup"><span data-stu-id="fa46e-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="fa46e-127">Wenn sich jedoch Benutzer in der Domäne für Dienste angemeldet haben, für die eine Lizenz erforderlich ist, werden Sie aufgefordert, Lizenzen für Sie im Rahmen der Übernahme der Administratorrolle zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="fa46e-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="fa46e-128">Sie können Lizenzen kaufen oder entfernen, nachdem der Administrator Einrichtungsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="fa46e-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="fa46e-129">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="fa46e-129">Related articles</span></span>

<span data-ttu-id="fa46e-130">YouTube: [3 Schritte zum Ausführen einer Übernahme durch IT-Administratoren für Power BI und Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="fa46e-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="fa46e-131">Übernahme von Administratoren in Azure AD</span><span class="sxs-lookup"><span data-stu-id="fa46e-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="fa46e-132">Abrufen von Hilfe zu Domänen</span><span class="sxs-lookup"><span data-stu-id="fa46e-132">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="fa46e-133">Verwenden von Self-Service-Registrierung in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="fa46e-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="fa46e-134">Grundlegendes zur Rolle des Power BI-Dienstadministrators</span><span class="sxs-lookup"><span data-stu-id="fa46e-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

