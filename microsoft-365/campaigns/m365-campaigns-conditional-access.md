---
title: Aktivieren von Sicherheitseinstellungen
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sicherheitseinstellungen Ihre Organisation vor identitätsbezogenen Angriffen schützen können, indem sie vorkonfigurierte Sicherheitseinstellungen bereitstellen.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398291"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="85a64-103">Aktivieren von Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="85a64-103">Turn on security defaults</span></span>

<span data-ttu-id="85a64-104">Sicherheitseinstellungen schützen Ihre Organisation vor identitätsbezogenen Angriffen, indem sie vorkonfigurierte Sicherheitseinstellungen bereitstellen, die Microsoft im Auftrag Ihrer Organisation verwaltet.</span><span class="sxs-lookup"><span data-stu-id="85a64-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="85a64-105">Zu diesen Einstellungen gehört das Aktivieren der mehrstufigen Authentifizierung (MFA) für alle Administratoren und Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="85a64-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="85a64-106">Für die meisten Organisationen bieten Sicherheitseinstellungen ein hohes Maß an zusätzlicher Anmeldesicherheit.</span><span class="sxs-lookup"><span data-stu-id="85a64-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="85a64-107">Weitere Informationen zu Sicherheitseinstellungen und den von ihnen erzwungenen Richtlinien finden Sie unter [Was sind Sicherheitseinstellungen?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="85a64-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="85a64-108">Wenn Ihr Abonnement am oder nach dem 22. Oktober 2019 erstellt wurde, wurden Sicherheitseinstellungen möglicherweise automatisch aktiviert, damit Sie Ihre Einstellungen überprüfen können, um dies &mdash; zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="85a64-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="85a64-109">So aktivieren Sie Sicherheitseinstellungen in Azure Active Directory (Azure AD) oder überprüfen Sie, ob sie bereits aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="85a64-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="85a64-110">Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center mit</a> globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="85a64-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="85a64-111">Wählen Sie im linken Bereich Alle anzeigen **aus,** und wählen Sie dann unter **Admin Center** die **Option Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="85a64-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="85a64-112">Wählen Sie im linken Bereich des **Azure Active Directory Admin Center** die Option **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="85a64-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="85a64-113">Wählen Sie im linken Menü des Dashboards im Abschnitt **Verwalten** die Option **Eigenschaften aus.**</span><span class="sxs-lookup"><span data-stu-id="85a64-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Screenshot des Azure Active Directory Admin Center mit dem Speicherort des Menüelements Eigenschaften.":::

5. <span data-ttu-id="85a64-115">Wählen Sie unten auf der **Seite Eigenschaften** die Option **Sicherheitseinstellungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="85a64-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="85a64-116">Im rechten Bereich wird die Einstellung **Sicherheitseinstellungen aktivieren** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85a64-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="85a64-117">Wenn **Ja** ausgewählt ist, sind die Sicherheitseinstellungen bereits aktiviert, und es sind keine weiteren Aktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85a64-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="85a64-118">Wenn Sicherheitseinstellungen derzeit nicht aktiviert sind, wählen Sie Ja aus, um sie zu aktivieren, und wählen Sie dann **Speichern aus.** </span><span class="sxs-lookup"><span data-stu-id="85a64-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="85a64-119">Wenn Sie Richtlinien für bedingten Zugriff verwendet haben, müssen Sie sie deaktivieren, bevor Sie Sicherheitseinstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="85a64-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="85a64-120">Sie können entweder Sicherheitseinstellungen oder Richtlinien für bedingten Zugriff verwenden, aber Sie können beide nicht gleichzeitig verwenden.</span><span class="sxs-lookup"><span data-stu-id="85a64-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="85a64-121">Erwägen sie die Verwendung von bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="85a64-121">Consider using Conditional Access</span></span>

<span data-ttu-id="85a64-122">Wenn Ihre Organisation komplexe Sicherheitsanforderungen hat oder Sie eine genauere Kontrolle über Ihre Sicherheitsrichtlinien benötigen, sollten Sie die Verwendung von bedingtem Zugriff anstelle von Sicherheitseinstellungen in Betracht ziehen, um eine ähnliche oder höhere Sicherheitslage zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="85a64-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="85a64-123">Mit bedingten Zugriff können Sie Richtlinien erstellen und definieren, die auf Anmeldeereignisse reagieren und zusätzliche Aktionen anfordern, bevor einem Benutzer Zugriff auf eine Anwendung oder einen Dienst gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="85a64-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="85a64-124">Richtlinien für bedingten Zugriff können präzise und spezifisch sein und es Benutzern ermöglichen, jederzeit produktiv zu sein, aber auch Ihre Organisation zu schützen.</span><span class="sxs-lookup"><span data-stu-id="85a64-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="85a64-125">Sicherheitseinstellungen sind für alle Kunden verfügbar, während für bedingten Zugriff eine Lizenz für einen der folgenden Pläne erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="85a64-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="85a64-126">Azure Active Directory Premium P1 oder P2</span><span class="sxs-lookup"><span data-stu-id="85a64-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="85a64-127">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="85a64-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="85a64-128">Microsoft 365 E3 oder E5</span><span class="sxs-lookup"><span data-stu-id="85a64-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="85a64-129">Enterprise Mobilität & Sicherheit E3 oder E5</span><span class="sxs-lookup"><span data-stu-id="85a64-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="85a64-130">Wenn Sie bedingten Zugriff verwenden möchten, um Richtlinien zu konfigurieren, die den durch Sicherheitseinstellungen aktivierten Richtlinien entsprechen, lesen Sie die folgenden schrittweisen Anleitungen:</span><span class="sxs-lookup"><span data-stu-id="85a64-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="85a64-131">MFA für Administratoren erforderlich</span><span class="sxs-lookup"><span data-stu-id="85a64-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="85a64-132">MFA für die Azure-Verwaltung erforderlich</span><span class="sxs-lookup"><span data-stu-id="85a64-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="85a64-133">Blockieren von Legacy-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="85a64-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="85a64-134">MFA für alle Nutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="85a64-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="85a64-135">[Azure AD MFA-Registrierung erforderlich](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) – Erfordert Azure AD Identity Protection, der Teil von Azure Active Directory Premium P2 ist</span><span class="sxs-lookup"><span data-stu-id="85a64-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="85a64-136">Weitere Informationen zum bedingten Zugriff finden Sie unter [Was ist bedingter Zugriff?](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="85a64-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="85a64-137">Weitere Informationen zum Erstellen von Richtlinien für bedingten Zugriff finden Sie unter [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span><span class="sxs-lookup"><span data-stu-id="85a64-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="85a64-138">Wenn Sie über einen Plan oder eine Lizenz verfügen, die bedingten Zugriff bietet, aber noch keine Richtlinien für bedingten Zugriff erstellt haben, können Sie Sicherheitseinstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="85a64-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="85a64-139">Sie müssen jedoch Sicherheitseinstellungen deaktivieren, bevor Sie Richtlinien für bedingten Zugriff verwenden können.</span><span class="sxs-lookup"><span data-stu-id="85a64-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
