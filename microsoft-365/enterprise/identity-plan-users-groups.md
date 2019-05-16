---
title: 'Schritt 1: Planen von Benutzern und Gruppen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Planen von Satz von Benutzern und Gruppen, die für Ihr Unternehmen arbeiten werden.
ms.openlocfilehash: 1f879c789e6b531dec7163fa252e0f85459c823d
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072175"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="d2249-103">Schritt 1: Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="d2249-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="d2249-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d2249-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d2249-p101">In diesem Schritt erstellen Sie Ihre Identitätsinfrastruktur, die Benutzer, Gruppen und Gruppenmitgliedschaften mit Sicherheitsfunktionen in der richtigen Konfiguration verwendet. Dadurch können Sie:</span><span class="sxs-lookup"><span data-stu-id="d2249-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="d2249-107">die Kontrolle darüber behalten, wer Zugriff auf Ressourcen in Ihrer Umgebung hat.</span><span class="sxs-lookup"><span data-stu-id="d2249-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="d2249-108">den Zugriff durch Steuerelemente sichern, die starke Sicherheiten im Bezug auf die Identität bieten (Benutzer sind die, die sie behaupten, zu sein), und über sichere Geräte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d2249-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="d2249-109">Ressourcen in Ihrer Umgebung entsprechende Berechtigungen bereitstellen, um das Risiko für potenziellen Schaden und Datenverlust zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="d2249-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="d2249-110">Ihre Umgebung auf abweichendes Benutzerverhalten überwachen und automatisch Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="d2249-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="d2249-111">Planen Ihres primären Identitätsanbieter</span><span class="sxs-lookup"><span data-stu-id="d2249-111">Plan your primary identity provider</span></span>

<span data-ttu-id="d2249-p102">Um Ihre Identitätsinfrastruktur zu erstellen, müssen Sie einen primären Identitätsanbieter festlegen. Dieser Dienst speichert Benutzerkonten und deren Attribute, Gruppen und Mitgliedschaften und unterstützt deren kontinuierliche Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="d2249-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="d2249-114">Wenn Ihre Organisation Microsoft 365 Enterprise einführt, ist Ihr primärer Identitätsanbieter entweder:</span><span class="sxs-lookup"><span data-stu-id="d2249-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="d2249-115">**Active Directory Domain Services (AD DS)**, ein Intranet-Identitätsanbieter, der auf Computern mit Windows-Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="d2249-115">**Active Directory Domain Services (AD DS)**, an intranet identity provider hosted on computers running Windows Server.</span></span> <span data-ttu-id="d2249-116">Dieser wird in der Regel von Organisationen genutzt, die über einen vorhandenen lokalen Identitätsanbieter verfügen.</span><span class="sxs-lookup"><span data-stu-id="d2249-116">This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="d2249-117">**Azure Active Directory (Azure AD**), ein cloudbasierter „Identity as a Service“(IDaaS)-Anbieter, der eine Vielzahl von Funktionen zum Verwalten und Schützen Ihre Umgebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d2249-117">**Azure Active Directory (Azure AD)**, a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment.</span></span> <span data-ttu-id="d2249-118">Dies wird normalerweise von Organisationen genutzt, die über keine vorhandene lokale Infrastruktur verfügen.</span><span class="sxs-lookup"><span data-stu-id="d2249-118">This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="d2249-119">Wenn Ihre Organisation über einen vorhandenen lokalen Identitätsanbieter verfügt, müssen Sie Ihre Benutzerkonten und Gruppen von AD DS mit Azure AD synchronisieren, um einen nahtlosen Zugriff auf die cloudbasierten Dienste von Microsoft 365 Enterprise zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d2249-119">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from AD DS to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="d2249-120">Sie können auch Azure AD verwenden, um Gruppen zu erstellen und zu verwalten, die nur in der Microsoft Cloud vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d2249-120">You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="d2249-121">Nachdem Sie Ihre Benutzer und Gruppen in Azure AD haben, können Sie:</span><span class="sxs-lookup"><span data-stu-id="d2249-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="d2249-122">alle Azure AD-Konten für all Ihre Cloudanwendungen verwalten.</span><span class="sxs-lookup"><span data-stu-id="d2249-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="d2249-123">denselben Satz Steuerelemente zum Schützen des Zugriffs auf Anwendungen in Ihrer gesamten Umgebung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2249-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="d2249-124">mit externen Partnern zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d2249-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="d2249-125">abweichendes Kontoverhalten, z. B. verdächtige Anmeldeversuche, überwachen und automatisch eingreifen.</span><span class="sxs-lookup"><span data-stu-id="d2249-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="d2249-126">Befolgen Sie die Anweisungen in den nächsten beiden Abschnitten, um Ihre Benutzerkonten und Gruppen zu planen und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d2249-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="d2249-127">Kategorisieren Ihrer Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2249-127">Categorize your users</span></span>
<span data-ttu-id="d2249-p106">Benutzer in Unternehmen können auf verschiedene Weise kategorisiert werden. Einige sind beispielsweise Mitarbeiter und haben einen permanenten Status. Einige sind Lieferanten, Auftragnehmer oder Partner, die über einen temporären Status verfügen. Einige sind externe Benutzer, die keine Benutzerkonten haben, denen aber trotzdem Zugriff auf bestimmte Dienste und Ressourcen zur Unterstützung der Interaktion und Zusammenarbeit gewährt werden muss. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d2249-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="d2249-133">Mandantenkonten stellen Benutzer in Ihrem Unternehmen dar, die Sie für Clouddienste lizenzieren.</span><span class="sxs-lookup"><span data-stu-id="d2249-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="d2249-134">Business-to-Business(B2B)-Konten stellen Benutzer außerhalb Ihres Unternehmens dar, die Sie zur Zusammenarbeit einladen.</span><span class="sxs-lookup"><span data-stu-id="d2249-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="d2249-p107">Nehmen Sie eine Bestandsaufnahme der Arten von Benutzern in Ihrem Unternehmen vor. Was sind die Gruppierungen? Beispielsweise können Sie Benutzer nach hoher Funktion oder nach dem Zweck für Ihr Unternehmen gruppieren.</span><span class="sxs-lookup"><span data-stu-id="d2249-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="d2249-p108">Darüber hinaus können einige Clouddienste für Benutzer außerhalb Ihres Unternehmens ohne Benutzerkonten freigegeben werden. Sie müssen diese Benutzergruppen ebenfalls identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d2249-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a><span data-ttu-id="d2249-140">Planung für AD DS und Azure Active Directory-Gruppen</span><span class="sxs-lookup"><span data-stu-id="d2249-140">Plan for AD DS and Azure AD groups</span></span>

<span data-ttu-id="d2249-p109">Sie können Gruppen in Azure AD für mehrere Zwecke verwenden, die die Verwaltung Ihrer Cloudumgebung vereinfachen. Für Azure AD-Gruppen können Sie beispielsweise die folgenden Aufgaben durchführen:</span><span class="sxs-lookup"><span data-stu-id="d2249-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="d2249-143">Sie können die gruppenbasierte Lizenzierung verwenden, um Ihren Benutzerkonten Lizenzen für Office 365 and Enterprise Mobility + Security (EMS) automatisch zuzuweisen, sobald diese in Azure AD hinzugefügt werden oder mit AD DS synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d2249-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from AD DS.</span></span> 
- <span data-ttu-id="d2249-144">Sie können bestimmten Gruppen auf Grundlage von Benutzerkontoattributen wie Abteilung Benutzerkonten dynamisch hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d2249-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="d2249-145">Sie können automatisch SaaS-Anwendungen für Benutzer bereitstellen und den Zugriff auf diese Anwendungen mit der mehrstufigen Authentifizierung und anderen Regeln für bedingten Zugriff schützen.</span><span class="sxs-lookup"><span data-stu-id="d2249-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="d2249-p110">Sie können Berechtigungen und Zugriffsebenen für SharePoint Online-Teamwebsites bereitstellen. Azure AD-Gruppen können auch mit bereichsbezogenen Azure Information Protection-Richtlinien zum Schutz von Dateien mit einer Verschlüsselung und Berechtigungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2249-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="d2249-148">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="d2249-148">Results</span></span>

<span data-ttu-id="d2249-149">Wenn Sie diesen Schritt abgeschlossen haben, verfügen Sie über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d2249-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="d2249-150">Eine Liste der Benutzerkonten in Azure AD, die den Mitarbeitern in Ihrer Organisation und den Lieferanten, Vertragsnehmern und Partnern, die für oder mit Ihrer Organisation arbeiten, entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d2249-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="d2249-151">Gruppen und deren Mitgliedschaft bei Azure AD, die den logischen Benutzerkonten und anderen Gruppen für die automatische Lizenzbereitstellung von Sicherheitseinstellungen für Microsoft-Clouddienste entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d2249-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="d2249-152">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-user-groups) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="d2249-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>

<span data-ttu-id="d2249-153">Sobald Ihre Benutzer und Gruppen in Azure AD vorhanden sind, können Sie mit dem Zuweisen von Lizenzen und der Verwendung von Exchange Online beginnen.</span><span class="sxs-lookup"><span data-stu-id="d2249-153">Once your Azure AD users and groups are created, you can start assigning licenses and using Exchange Online.</span></span> <span data-ttu-id="d2249-154">Informationen zur Einführung von Exchange Online bei Ihren Benutzern finden Sie unter [Bereitstellen von Exchange Online für Microsoft 365 Enterprise](exchangeonline-workload.md).</span><span class="sxs-lookup"><span data-stu-id="d2249-154">To roll out Exchange Online to your users, see [Deploy Exchange Online for Microsoft 365 Enterprise](exchangeonline-workload.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="d2249-155">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d2249-155">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="d2249-156">Sichern Ihrer privilegierten Identitäten</span><span class="sxs-lookup"><span data-stu-id="d2249-156">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |

