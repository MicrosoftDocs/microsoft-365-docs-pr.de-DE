---
title: Durchführen einer internen Übernahme durch den Administrator
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Erfahren Sie, wie Sie Ihren E-Mail- und Domänenbesitz überprüfen, um einen nicht verwalteten Mandanten zu übernehmen, der von einer Self-Service-Benutzeranmeldung in Microsoft 365 erstellt wurde.
ms.openlocfilehash: f6378c708e0533c2da2d38bfe5eb8009515423c7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393847"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="04840-103">Durchführen einer internen Übernahme durch den Administrator</span><span class="sxs-lookup"><span data-stu-id="04840-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="04840-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="04840-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="04840-105">Wenn Sie ein Administrator sind und einen nicht verwalteten Mandanten übernehmen möchten, der von einer Self-Service-Benutzeranmeldung erstellt wurde, können Sie dies mit einer internen Administratorübernahme tun.</span><span class="sxs-lookup"><span data-stu-id="04840-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="04840-106">Eine Self-Service-Registrierung für jeden Clouddienst, der Azure AD verwendet, fügt den Benutzer einem nicht verwalteten oder "Schatten" Azure AD-Verzeichnis hinzu und erstellt einen nicht verwalteten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="04840-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="04840-107">Ein nicht verwalteter Mandant ist ein Verzeichnis ohne globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="04840-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="04840-108">Informationen dazu, ob ein Mandant verwaltet oder nicht verwaltet wird, finden Sie unter [Ermitteln des Mandantentyps.](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="04840-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="04840-109">Schritt 1: Überprüfen Ihrer E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="04840-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="04840-110">Wenn Self-Service in Ihrem Mandanten aktiviert ist, können Benutzer kostenlose Dienste wie Power BI selbst abonnieren.</span><span class="sxs-lookup"><span data-stu-id="04840-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="04840-111">Bei diesen Schritten wird davon ausgegangen, dass ein Self-Service-Benutzerabonnement den nicht verwalteten Mandanten erstellt hat, den Sie als Administrator übernehmen möchten. Im ersten Schritt erstellen Sie einen Benutzerkontext im nicht verwalteten Mandanten mithilfe von Power BI, um den Übernahmepfad des Administrators zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="04840-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="04840-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** Start  >  **free trial** (in Share with Power BI Pro box).</span><span class="sxs-lookup"><span data-stu-id="04840-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="04840-113">Registrieren Sie sich mit einem Benutzerkonto, das den Domänennamen Ihrer Organisation verwendet (z. `powerbiadmin@contoso.com` B. ).</span><span class="sxs-lookup"><span data-stu-id="04840-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="04840-114">Wenn Ihr Konto bereits verwendet wird, melden Sie sich mit Ihrem aktuellen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="04840-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="04840-115">Überprüfen Sie Ihre E-Mail auf den **Überprüfungscode,** und geben Sie den Code ein, um Ihre E-Mail-Adresse zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="04840-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="04840-116">Schritt 2: Erstellen eines neuen Kontos</span><span class="sxs-lookup"><span data-stu-id="04840-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="04840-117">Wenn Sie den Überprüfungscode eingeben, werden Sie zu einer Seite gebracht, auf der Sie ein neues Konto erstellen können.</span><span class="sxs-lookup"><span data-stu-id="04840-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="04840-118">Füllen Sie die Benutzernamen- und Kennwortfelder mit dem Konto aus, das Sie verwenden möchten, und wählen Sie dann **Start** aus.</span><span class="sxs-lookup"><span data-stu-id="04840-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="04840-119">Schritt 3: Überprüfen des Domänenbesitzes und Administrator werden</span><span class="sxs-lookup"><span data-stu-id="04840-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="04840-120">Der Assistent **zum Administrator** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="04840-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="04840-121">Wenn der Assistent nicht gestartet wird, suchen Sie nach der **Administratorkachel,** und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="04840-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="04840-122">Wählen Sie **"Ja", ich möchte der Administrator sein.**</span><span class="sxs-lookup"><span data-stu-id="04840-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="04840-123">Stellen Sie sicher, dass Sie die Domäne besitzen, die Sie übernehmen möchten, indem Sie Ihrer Domänenregistrierungsstelle einen TXT-Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="04840-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="04840-124">Der Assistent gibt Ihnen den hinzuzufügenden TXT-Eintrag sowie einen Link zur Website Ihrer Registrierungsstelle sowie einen Link zu schrittweisen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="04840-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="04840-125">Nachdem Sie den TXT-Eintrag zu Ihrer Registrierungsstellenwebsite hinzugefügt haben, kehren Sie zum Assistenten zurück und wählen **Sie "Okay" aus, ich habe den Datensatz hinzugefügt.**</span><span class="sxs-lookup"><span data-stu-id="04840-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="04840-126">Die Übernahme des Schattenmandanten wirkt sich nicht auf vorhandene Informationen oder Dienste aus.</span><span class="sxs-lookup"><span data-stu-id="04840-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="04840-127">Wenn sich benutzer in der Domäne jedoch für Dienste angemeldet haben, die eine Lizenz erfordern, werden Sie aufgefordert, lizenzen für sie zu erwerben, als Teil der Übernahme der Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="04840-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="04840-128">Sie können Lizenzen kaufen oder entfernen, sobald der Administratoreinrichtungsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="04840-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="04840-129">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="04840-129">Related content</span></span>

<span data-ttu-id="04840-130">YouTube: [3 Schritte zum Durchführen einer Übernahme durch IT-Administratoren für Power BI und Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (Video)</span><span class="sxs-lookup"><span data-stu-id="04840-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span></span>\
<span data-ttu-id="04840-131">[Administratorübernahme in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="04840-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>\
<span data-ttu-id="04840-132">[Verwenden der Self-Service-Registrierung in Ihrer Organisation](self-service-sign-up.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="04840-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>\
<span data-ttu-id="04840-133">[Grundlegendes zur Rolle Power BI Dienstadministrator](/power-bi/service-admin-role) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="04840-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>