---
title: Durchführen einer internen Administratorübernahme
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Erfahren Sie, wie Sie Ihren E-Mail- und Domänenbesitz überprüfen, um einen nicht verwalteten Mandanten zu übernehmen, der durch eine Self-Service-Benutzerregistrierung in einem Microsoft 365.
ms.openlocfilehash: c37bf153edf39f53b5c10f020b0cbb8d630eb4a6
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593933"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="aa81a-103">Durchführen einer internen Administratorübernahme</span><span class="sxs-lookup"><span data-stu-id="aa81a-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="aa81a-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="aa81a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="aa81a-105">Wenn Sie ein Administrator sind und einen nicht verwalteten Mandanten übernehmen möchten, der durch eine Self-Service-Benutzer-Anmeldung erstellt wurde, können Sie dies mit einer internen Administratorübernahme tun.</span><span class="sxs-lookup"><span data-stu-id="aa81a-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="aa81a-106">Eine Self-Service-Anmeldung für jeden Clouddienst, der Azure AD verwendet, fügt den Benutzer einem nicht verwalteten Azure AD-Verzeichnis oder einem "Schatten" hinzu und erstellt einen nicht verwalteten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="aa81a-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="aa81a-107">Ein nicht verwalteter Mandant ist ein Verzeichnis ohne globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="aa81a-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="aa81a-108">Informationen dazu, ob ein Mandant verwaltet oder nicht verwaltet wird, finden Sie unter [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="aa81a-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="aa81a-109">Schritt 1: Überprüfen Ihrer E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="aa81a-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="aa81a-110">Wenn self-service in Ihrem Mandanten aktiviert ist, können Benutzer kostenlose Dienste, z. B. Power BI, selbst abonnieren.</span><span class="sxs-lookup"><span data-stu-id="aa81a-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="aa81a-111">Bei diesen Schritten wird davon ausgegangen, dass ein Self-Service-Benutzerabonnement den nicht verwalteten Mandanten erstellt hat, den Sie als Administrator übernehmen möchten. Im ersten Schritt erstellen Sie einen Benutzerkontext im nicht verwalteten Mandanten, indem Sie Power BI verwenden, um den Administratorübernahmepfad zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="aa81a-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="aa81a-112">Um sich für Power BI zu registrieren, wechseln Sie zur [Power BI-Website,](https://powerbi.com) und wählen Sie **kostenlose** Testversion starten (im Feld Freigeben mit  >   Power BI Pro aus).</span><span class="sxs-lookup"><span data-stu-id="aa81a-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="aa81a-113">Registrieren Sie sich mit einem Benutzerkonto, das den Domänennamen Ihrer Organisation verwendet (z. B. `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="aa81a-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="aa81a-114">Wenn Ihr Konto bereits verwendet wird, melden Sie sich mit Ihrem aktuellen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="aa81a-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="aa81a-115">Überprüfen Sie Ihre E-Mail auf den **Überprüfungscode,** und geben Sie den Code ein, um Ihre E-Mail-Adresse zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="aa81a-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="aa81a-116">Schritt 2: Erstellen eines neuen Kontos</span><span class="sxs-lookup"><span data-stu-id="aa81a-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="aa81a-117">Wenn Sie den Überprüfungscode eingeben, werden Sie auf eine Seite gebracht, auf der Sie ein neues Konto erstellen können.</span><span class="sxs-lookup"><span data-stu-id="aa81a-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="aa81a-118">Füllen Sie die Felder Benutzername und Kennwort mit dem Konto aus, das Sie verwenden möchten, und wählen Sie **dann Start aus.**</span><span class="sxs-lookup"><span data-stu-id="aa81a-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="aa81a-119">Schritt 3: Überprüfen des Domänenbesitzes und Administrator werden</span><span class="sxs-lookup"><span data-stu-id="aa81a-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="aa81a-120">Der **Assistent Zum Administrator werden** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="aa81a-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="aa81a-121">Wenn der Assistent nicht gestartet wird, suchen Sie nach der **Kachel Administrator,** und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="aa81a-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="aa81a-122">Wählen **Sie Ja aus, ich möchte der Administrator sein.**</span><span class="sxs-lookup"><span data-stu-id="aa81a-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="aa81a-123">Vergewissern Sie sich, dass Sie derEn Domänen besitzen, die Sie übernehmen möchten, indem Sie Ihrer Domänenregistrierungsstelle einen TXT-Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aa81a-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="aa81a-124">Der Assistent gibt Ihnen den hinzuzufügende TXT-Eintrag sowie einen Link zur Website Ihrer Registrierungsstelle sowie einen Link zu schrittweisen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="aa81a-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="aa81a-125">Nachdem Sie den TXT-Eintrag zur Registrierungswebsite hinzugefügt haben, kehren Sie zum Assistenten zurück, und wählen Sie **Ok aus, ich habe den Eintrag hinzugefügt.**</span><span class="sxs-lookup"><span data-stu-id="aa81a-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="aa81a-126">Die Übernahme des Schatten-Mandanten wirkt sich nicht auf vorhandene Informationen oder Dienste aus.</span><span class="sxs-lookup"><span data-stu-id="aa81a-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="aa81a-127">Wenn sich jedoch Benutzer in der Domäne für Dienste angemeldet haben, für die eine Lizenz erforderlich ist, werden Sie aufgefordert, Lizenzen für sie zu erwerben, wenn Sie die Administratorrolle übernehmen.</span><span class="sxs-lookup"><span data-stu-id="aa81a-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="aa81a-128">Sie können Lizenzen erwerben oder entfernen, sobald der Administratoreinrichtungsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="aa81a-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="aa81a-129">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="aa81a-129">Related content</span></span>

<span data-ttu-id="aa81a-130">YouTube: [3 Schritte zum Ausführen einer Übernahme](https://www.youtube.com/watch?v=xt5EsrQBZZk) von IT-Administratoren für Power BI und Microsoft 365 (Video)</span><span class="sxs-lookup"><span data-stu-id="aa81a-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span></span>

<span data-ttu-id="aa81a-131">[Admin-Übernahme in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="aa81a-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>

<span data-ttu-id="aa81a-132">[Verwenden der Self-Service-Anmeldung in Ihrer Organisation](self-service-sign-up.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="aa81a-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>
  
<span data-ttu-id="aa81a-133">[Grundlegendes zur Power BI Dienstadministratorrolle](/power-bi/service-admin-role) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="aa81a-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>