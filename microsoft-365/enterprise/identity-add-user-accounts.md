---
title: 'Schritt 4: Hinzufügen von Benutzerkonten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Fügen Sie Benutzerkonten und Gruppen entweder direkt in der Cloud oder über die Synchronisierung mit Ihrem lokalen Verzeichnis hinzu.
ms.openlocfilehash: ce831a6866f61342f6eb93836d44637742007c03
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082015"
---
# <a name="step-4-add-your-user-accounts"></a><span data-ttu-id="4cff9-103">Schritt 4: Hinzufügen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="4cff9-103">Step 4: Add your user accounts</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a><span data-ttu-id="4cff9-104">Erstellen von Benutzerkonten für reine Cloudidentität</span><span class="sxs-lookup"><span data-stu-id="4cff9-104">Create your user accounts for cloud-only identity</span></span>

<span data-ttu-id="4cff9-105">Für reine Cloudidentität erstellen Sie Ihre Benutzer und Gruppen in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="4cff9-105">For cloud-only identity, create your users and groups in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="4cff9-106">Sie können Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="4cff9-106">You can use:</span></span>

- <span data-ttu-id="4cff9-107">Das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="4cff9-107">Microsoft Office 365 admin center</span></span>
- <span data-ttu-id="4cff9-108">Das Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="4cff9-108">The Azure portal</span></span>
- <span data-ttu-id="4cff9-109">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="4cff9-109">Azure Powershell</span></span>

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a><span data-ttu-id="4cff9-110">Synchronisieren von Identitäten für die Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="4cff9-110">Synchronize identities for hybrid identity</span></span>

<span data-ttu-id="4cff9-111">*Dieser Schritt ist erforderlich für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4cff9-111">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4cff9-112">In diesem Abschnitt synchronisieren Sie Ihre lokalen Active Directory Domain Services (AD DS) mit dem Azure AD-Mandanten, der von Ihren Office 365- Microsoft Intune- und anderen, in Microsoft 365 Enterprise-Abonnements enthaltenen cloudbasierten Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4cff9-112">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure AD tenant used by Office 365, Microsoft Intune, and other cloud-based services included with Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="4cff9-113">Azure AD Connect ist das unterstützte Microsoft-Tool, das Sie durch die Synchronisierung nur der Identitäten führt, die Sie aus AD DS -Umgebungen mit einer oder mehreren Gesamtstrukturen wirklich für Ihren Azure AD-Mandanten benötigen.</span><span class="sxs-lookup"><span data-stu-id="4cff9-113">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="4cff9-114">In der folgenden Abbildung ist der grundlegende Prozess für die Azure AD Connect-Synchronisierung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4cff9-114">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Wie Azure AD Connect Ihr lokales Verzeichnis mit Azure AD synchronisiert](./media/identity-add-user-accounts/azure-ad-connect.png)

1. <span data-ttu-id="4cff9-116">Azure AD Connect, das auf einem Server ausgeführt wird, fragt AD DS auf Änderungen in Konten, Gruppen und Kontakten ab.</span><span class="sxs-lookup"><span data-stu-id="4cff9-116">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="4cff9-117">Azure AD Connect sendet diese Änderungen an den Azure AD-Mandanten Ihres Microsoft 365-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="4cff9-117">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="4cff9-p103">Die erste Entscheidung in Ihrer Identitätshybridlösung ist Ihre Authentifizierungsanforderung. Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="4cff9-p103">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="4cff9-p104">Bei der **verwalteten Authentifizierung** verarbeitet Azure AD den Authentifizierungsprozess für die Benutzeranmeldung. Es gibt zwei Methoden für die verwaltete Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="4cff9-p104">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="4cff9-122">**Kennworthashsynchronisierung (Password Hash Sync, PHS)** [Empfohlen und für einige Premiumfunktionen erforderlich].</span><span class="sxs-lookup"><span data-stu-id="4cff9-122">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="4cff9-123">Dies ist die einfachste Methode, um die Authentifizierung für lokale Verzeichnisobjekte in Azure AD zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4cff9-123">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="4cff9-124">Azure AD Connect extrahiert das Kennwort mit Hash aus AD DS, führt eine zusätzliche Sicherheitsverarbeitung für den Kennworthash durch und synchronisiert es mit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4cff9-124">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password, and saves it in Azure AD.</span></span> <span data-ttu-id="4cff9-125">Weitere Informationen finden Sie unter [Implementieren der Kennworthashsynchronisierung mit der Azure AD Connect-Synchronisierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="4cff9-125">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="4cff9-126">Die **Pass-Through-Authentifizierung (PTA)** bietet eine einfache Kennwortüberprüfungslösung für auf Azure AD basierende Dienste.</span><span class="sxs-lookup"><span data-stu-id="4cff9-126">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="4cff9-127">PTA verwendet einen Agent, der auf einem oder mehreren lokalen Servern ausgeführt wird, um die Benutzerauthentifizierungen direkt mit Ihren lokalen AD DS zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4cff9-127">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="4cff9-128">Weitere Informationen finden Sie unter [Benutzeranmeldung mit der Azure Active Directory-Passthrough-Authentifizierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="4cff9-128">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="4cff9-p107">Bei der **Verbundauthentifizierung** wird der Authentifizierungsprozess über einen Identitätsverbundserver wie die Active Directory-Verbunddienste (AD FS) an einen anderen Identitätsanbieter weitergeleitet, wenn der Benutzer sich anmelden möchte. Der Identitätsanbieter kann weitere Authentifizierungsmethoden bereitstellen, z. B. Smartcard-basierte Authentifizierung. Weitere Informationen finden Sie unter [Wählen der richtigen Authentifizierungsmethode für Ihre Azure Active Directory-Hybrididentitätslösung](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span><span class="sxs-lookup"><span data-stu-id="4cff9-p107">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="4cff9-132">Schauen Sie sich dieses Video an, um eine Übersicht über die Identitätsmodelle und Authentifizierung für Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4cff9-132">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="4cff9-133"><p> </p></span><span class="sxs-lookup"><span data-stu-id="4cff9-133"></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="4cff9-134">Nachdem Sie Ihre Identitätshybridlösung ermittelt haben, laden Sie das [IdFix-Tool für die Fehlerbehebung bei der Verzeichnissynchronisierung herunter](https://www.microsoft.com/download/details.aspx?id=36832) und führen es aus, um Ihre AD DS auf Probleme zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="4cff9-134">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="4cff9-135">Beheben Sie alle vom IdFix-Tool erkannten Probleme, und lesen Sie dann [Implementieren der Kennworthashsynchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization). Dort finden Sie eine Anleitung zur Installation des Azure AD Connect-Tools und zur Konfiguration der Verzeichnissynchronisierung zwischen Ihren lokalen AD DS und dem Azure AD-Mandanten für Ihr Microsoft 365-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="4cff9-135">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span> <span data-ttu-id="4cff9-136">Nach dem Start der Synchronisierung werden die Benutzerkonten und Gruppen im lokalen Identitätsanbieter (z. B. AD DS) beibehalten.</span><span class="sxs-lookup"><span data-stu-id="4cff9-136">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="4cff9-137">Microsoft stellt eine Reihe von Empfehlungen für [Identität und Gerätezugriff](microsoft-365-policies-configurations.md) bereit, um sicherzustellen, dass die Mitarbeiter sicher und produktiv arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="4cff9-137">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="4cff9-138">Empfohlene Anforderungen für Hybridumgebungen finden Sie in der Spalte **Active Directory mit Kennworthashsynchronisierung** unter [Voraussetzungen](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="4cff9-138">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="4cff9-139">Empfohlene Anforderungen nur für Cloudumgebungen finden Sie in der Spalte **Nur Cloud** unter [Voraussetzungen](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="4cff9-139">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="4cff9-140">Sobald Ihre lokalen Benutzer und Gruppen in Azure AD vorhanden sind, können Sie mit dem Zuweisen von Lizenzen und der Verwendung von Produktivitätsarbeitslasten wie OneDrive for Business oder Exchange Online beginnen.</span><span class="sxs-lookup"><span data-stu-id="4cff9-140">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using Exchange Online.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4cff9-142">Testumgebungsanleitung: Kennworthashsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="4cff9-142">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="4cff9-143">Testumgebungsanleitung: Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4cff9-143">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="4cff9-144">Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sync) für diesen Abschnitt anschauen.</span><span class="sxs-lookup"><span data-stu-id="4cff9-144">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="4cff9-145">Überwachen des Synchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="4cff9-145">Monitor synchronization health</span></span>

<span data-ttu-id="4cff9-146">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4cff9-146">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4cff9-147">In diesem Abschnitt installieren Sie einen Azure AD Connect Health-Agent auf den einzelnen lokalen AD DS-Domänencontrollern, um die Identitätsinfrastruktur und die von Azure AD Connect bereitgestellten Synchronisierungsdienste zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="4cff9-147">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="4cff9-148">Die Überwachungsinformationen werden in einem Azure AD Connect Health-Portal verfügbar gemacht, wo Sie Warnungen, Leistungsüberwachungsdaten, Nutzungsanalysen und andere Informationen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="4cff9-148">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Komponenten von Azure AD Connect Health](./media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

<span data-ttu-id="4cff9-150">Die wichtigste Entwurfsentscheidung hinsichtlich der Verwendung von Azure AD Connect Health basiert auf der Art und Weise, wie Sie Azure AD Connect verwenden:</span><span class="sxs-lookup"><span data-stu-id="4cff9-150">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="4cff9-151">Wenn Sie die **verwaltete Authentifizierung** verwenden, beginnen Sie mit [Verwenden von Azure AD Connect Health mit Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), um Informationen zur Funktionsweise und Konfiguration von Azure AD Connect Health zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4cff9-151">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="4cff9-152">Wenn Sie nur die Namen der Konten und Gruppen mithilfe der **Verbundauthentifizierung** mit Active Directory-Verbunddiensten (AD FS) synchronisieren, beginnen Sie mit [Verwenden von Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), um Informationen zur Funktionsweise und zur Konfiguration von Azure AD Connect Health zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4cff9-152">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="4cff9-153">Wenn Sie diesen Abschnitt abgeschlossen haben, verfügen Sie über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4cff9-153">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="4cff9-154">Der Azure AD Connect Health-Agent ist auf jedem Ihrer lokalen Identitätsanbieterserver installiert.</span><span class="sxs-lookup"><span data-stu-id="4cff9-154">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="4cff9-155">Das Azure AD Connect Health-Portal zeigt den aktuellen Status Ihrer lokalen Infrastruktur und der Synchronisierungsaktivitäten mit dem Azure AD-Mandanten für Ihr Microsoft 365-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="4cff9-155">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="4cff9-156">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-sync-health) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="4cff9-156">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="4cff9-157">Vereinfachen der Kennwortaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="4cff9-157">Simplify password updates</span></span>

<span data-ttu-id="4cff9-158">*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4cff9-158">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4cff9-159">In diesem Abschnitt können Sie können Sie festlegen, dass Benutzer ihre Kennwörter über Azure Active Directory (Azure AD) zurücksetzen können, das dann in Ihre lokalen Active Directory Domain Services (AD DS) repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="4cff9-159">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="4cff9-160">Dieser Vorgang wird als Rückschreiben des Kennworts bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4cff9-160">This process is known as password writeback.</span></span> <span data-ttu-id="4cff9-161">Mit der Kennwortrückschreibung brauchen Benutzer ihre Kennwörter nicht mehr über den lokalen AD-DS zu aktualisieren, auf dem ihre Benutzerkonten und Attribute gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4cff9-161">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="4cff9-162">Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.</span><span class="sxs-lookup"><span data-stu-id="4cff9-162">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="4cff9-163">Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Azure AD Identity Protection, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein hohes Risiko einer Kontogefährdung besteht.</span><span class="sxs-lookup"><span data-stu-id="4cff9-163">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="4cff9-164">Weitere Informationen und Hinweise zur Konfiguration finden Sie unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="4cff9-164">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="4cff9-p111">Führen Sie ein Upgrade auf die neueste Version von Azure AD Connect durch, um das bestmögliche Benutzererlebnis und die Verfügbarkeit neuer Features sicherzustellen, sobald diese veröffentlicht werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="4cff9-p111">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4cff9-168">Testumgebungsanleitung: Rückschreiben des Kennworts</span><span class="sxs-lookup"><span data-stu-id="4cff9-168">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="4cff9-169">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-pw-writeback) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="4cff9-169">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="4cff9-170">Verwenden von Gruppen zur Verwaltung</span><span class="sxs-lookup"><span data-stu-id="4cff9-170">Use groups for easier management</span></span>](identity-use-group-management.md) |
