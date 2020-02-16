---
title: Schützen Ihrer Administratorkonten
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Erfahren Sie, wie Sie Ihre Administratorkonten einrichten und schützen.
ms.openlocfilehash: b74d9d2d69549bcaa476a346ba2a61fc24e0b3f3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080577"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="ec502-103">Schützen Ihrer Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="ec502-103">Protect your administrator accounts</span></span>

<span data-ttu-id="ec502-104">Da Administratorkonten mit erhöhten Rechten ausgestattet sind, sind Sie wertvolle Ziele für Hacker und Cyber-Kriminelle.</span><span class="sxs-lookup"><span data-stu-id="ec502-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="ec502-105">Inhalt dieses Artikels</span><span class="sxs-lookup"><span data-stu-id="ec502-105">This article describes:</span></span>

- <span data-ttu-id="ec502-106">Einrichten eines zusätzlichen Administratorkontos für Notfälle.</span><span class="sxs-lookup"><span data-stu-id="ec502-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="ec502-107">Wie diese Konten geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="ec502-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="ec502-108">Wenn Sie sich für Microsoft 365 Business registrieren und Ihre Informationen eingeben, werden Sie automatisch zum globalen Administrator. Ein globaler Administrator hat die ultimative Kontrolle über Benutzerkonten und alle anderen Einstellungen im Microsoft Admin Center, aber es gibt viele verschiedene Arten von Administratorkonten mit unterschiedlichem Zugriffs Grad.</span><span class="sxs-lookup"><span data-stu-id="ec502-108">When you sign up for Microsoft 365 Business and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="ec502-109">Unter Informationen zu [Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) finden Sie Informationen zu den verschiedenen Zugriffsebenen für jede Art von Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="ec502-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="ec502-110">Erstellen zusätzlicher Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="ec502-110">Create additional admin accounts</span></span>

<span data-ttu-id="ec502-111">Verwenden Sie Administratorkonten nur für die Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="ec502-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="ec502-112">Administratoren sollten über ein separates Benutzerkonto für die regelmäßige Verwendung von Office-Apps verfügen und bei Bedarf nur Ihr Administratorkonto verwenden, um Konten und Geräte zu verwalten, sowie bei der Arbeit an anderen Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="ec502-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="ec502-113">Es empfiehlt sich auch, die Microsoft 365 Business License aus den Administratorkonten zu entfernen, damit Sie nicht dafür bezahlen müssen.</span><span class="sxs-lookup"><span data-stu-id="ec502-113">It's also a good idea to remove the Microsoft 365 Business license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="ec502-114">Sie möchten mindestens ein zusätzliches globales Administratorkonto einrichten, um Administratorzugriff auf einen anderen vertrauenswürdigen Mitarbeiter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ec502-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="ec502-115">Sie können auch separate Administratorkonten für die Benutzerverwaltung erstellen (diese Rolle wird als **Benutzer Verwaltungs Administrator**bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="ec502-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="ec502-116">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ec502-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ec502-117">So erstellen Sie zusätzliche Administratorkonten:</span><span class="sxs-lookup"><span data-stu-id="ec502-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="ec502-118">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Admin Center</a> , und wählen Sie dann **Benutzer** \> **aktive Benutzer** im linken Navigationsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="ec502-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Wählen Sie Benutzer und dann aktive Benutzer im linken Navigationsbereich aus.](../media/Activeusers.png)

2. <span data-ttu-id="ec502-120">Wählen Sie auf der Seite **aktive Benutzer** oben auf der Seite **einen Benutzer hinzufügen** aus, und geben Sie im Bereich **neuer Benutzer** den Namen und andere Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="ec502-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="ec502-121">Erweitern Sie den Abschnitt **Rollen** , und wählen Sie **globaler Administrator** aus, um diesem Benutzer den globalen Administratorzugriff zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="ec502-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="ec502-122">Sie können auch **benutzerdefinierten Administrator** auswählen und eine der Rollen auswählen, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ec502-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="ec502-123">Geben Sie eine Alternative e-Mail in das Textfeld **Alternative e-Mail-Adresse** ein.</span><span class="sxs-lookup"><span data-stu-id="ec502-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="ec502-124">Sie können diese Adresse verwenden, um Ihre Kennwortinformationen wiederherzustellen, wenn Sie gesperrt werden. Für globale Administratoren wird auch eine Abrechnungs Anweisung an diese Adresse gesendet.</span><span class="sxs-lookup"><span data-stu-id="ec502-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![Auswählen der Administratorrolle](../media/adminroles.png)
    
4. <span data-ttu-id="ec502-126">Stellen Sie im Abschnitt **Produktlizenzen** den Selektor für **Microsoft 365 Business** auf **aus** , und legen Sie den **Benutzer ohne Produktlizenz** auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="ec502-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Produktlizenz auswählen](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="ec502-128">Erstellen eines Notfall Administratorkontos</span><span class="sxs-lookup"><span data-stu-id="ec502-128">Create an emergency admin account</span></span>

<span data-ttu-id="ec502-129">Sie sollten auch ein sicherungskonto erstellen, das nicht mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eingerichtet ist, damit Sie sich nicht versehentlich selbst verschließen (beispielsweise wenn Sie Ihr Telefon verlieren, das Sie als zweite Überprüfung verwenden).</span><span class="sxs-lookup"><span data-stu-id="ec502-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="ec502-130">Stellen Sie sicher, dass das Kennwort für dieses Konto ein Ausdruck oder mindestens 16 Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="ec502-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="ec502-131">Dies wird häufig als "Break-Glass-Konto" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ec502-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="ec502-132">Erstellen eines Benutzerkontos für sich selbst</span><span class="sxs-lookup"><span data-stu-id="ec502-132">Create a user account for yourself</span></span>

<span data-ttu-id="ec502-133">Verwenden Sie Ihr Benutzerkonto, um an der Zusammenarbeit mit Ihrer Organisation teilzunehmen, einschließlich der Überprüfung von e-Mails.</span><span class="sxs-lookup"><span data-stu-id="ec502-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="ec502-134">Das heißt, Ihre Administratoranmeldeinformationen ähneln möglicherweise *Alice. Chavez<span></span>@contoso. org* , und Ihr reguläres Benutzerkonto ähnelt *Alice<span></span>@contoso. com*.</span><span class="sxs-lookup"><span data-stu-id="ec502-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="ec502-135">So erstellen Sie ein neues Benutzerkonto:</span><span class="sxs-lookup"><span data-stu-id="ec502-135">To create a new user account:</span></span>
1. <span data-ttu-id="ec502-136">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Admin Center</a> , und wählen Sie dann **Benutzer** \> **aktive Benutzer** im linken Navigationsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="ec502-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="ec502-137">Wählen Sie auf der Seite **aktive Benutzer** oben auf der Seite **einen Benutzer hinzufügen** aus, und geben Sie im Bereich **neuer Benutzer** den Namen und andere Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="ec502-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="ec502-138">Erweitern Sie den Abschnitt **Rollen** , und wählen Sie **Benutzer (kein Administratorzugriff)** aus.</span><span class="sxs-lookup"><span data-stu-id="ec502-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="ec502-139">Stellen Sie im Abschnitt **Produktlizenzen** den Selektor für **Microsoft 365 Business** auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="ec502-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="ec502-140">Registrieren jedes dieser Konten für mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ec502-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="ec502-141">Weitere Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="ec502-141">Additional recommendations</span></span>

- <span data-ttu-id="ec502-142">Stellen Sie sicher, dass auch Administratorkonten für die mehrstufige Authentifizierung eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="ec502-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="ec502-143">In diesem Artikel erfahren Sie, wie Sie die [Richtlinien für bedingten Zugriff konfigurieren](m365-campaigns-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="ec502-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="ec502-144">Schließen Sie vor der Verwendung von Administratorkonten alle nicht verwandten Browsersitzungen und apps, einschließlich persönlicher e-Mail-Konten.</span><span class="sxs-lookup"><span data-stu-id="ec502-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="ec502-145">Sie können auch in privaten oder inkognito-Browserfenstern verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec502-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="ec502-146">Nachdem Sie die Administratoraufgaben abgeschlossen haben, müssen Sie sich bei der Browsersitzung abmelden.</span><span class="sxs-lookup"><span data-stu-id="ec502-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>
