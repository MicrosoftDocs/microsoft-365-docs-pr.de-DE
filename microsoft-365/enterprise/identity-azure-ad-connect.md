---
title: 'Schritt 7: Synchronisieren von Identitäten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/15/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zu Identitätsoptionen und zum Konfigurieren von Azure AD Connect, um Ihr lokales Windows Server Active Directory mit Azure AD zu synchronisieren.
ms.openlocfilehash: 97e6b2204fb4fd97d2fc76543a080746bb6dac28
ms.sourcegitcommit: 42645d5b15fd8698d116745f3b0d7943887e5a2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2018
ms.locfileid: "26644226"
---
# <a name="step-7-synchronize-identities"></a><span data-ttu-id="2b102-103">Schritt 7: Synchronisieren von Identitäten</span><span class="sxs-lookup"><span data-stu-id="2b102-103">Step 2: Synchronize identities</span></span>

<span data-ttu-id="2b102-104">*Dieser Schritt ist erforderlich für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2b102-104">*This step is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="2b102-105">In diesem Schritt synchronisieren Sie Ihr lokales Windows Server Azure Active Directory (AD) mit dem Azure Active Directory (AD)-Mandanten, der von Ihren Office 365- und Enterprise Mobility + Security (EMS)-Abonnements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2b102-105">In Step 2, you'll synchronize your on-premises Windows Server Active Directory (AD) with the Azure Active Directory (AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="2b102-106">Azure AD Connect ist das unterstützte Microsoft-Tool, das Sie durch die Synchronisierung nur der Identitäten führt, die Sie aus Windows Server AD-Umgebungen mit einer oder mehreren Gesamtstrukturen wirklich für Ihren Azure AD-Mandanten benötigen.</span><span class="sxs-lookup"><span data-stu-id="2b102-106">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest Windows Server AD environments to your Azure AD tenant.</span></span>

![Wie Azure AD Connect Ihr lokales Verzeichnis mit Azure AD synchronisiert](./media/identity-azure-ad-connect/azure-ad-connect.png)

<span data-ttu-id="2b102-108">*Wie Azure AD Connect Ihr lokales Verzeichnis mit Azure AD synchronisiert*</span><span class="sxs-lookup"><span data-stu-id="2b102-108">*How Azure AD Connect synchronizes your on-premises directory with Azure AD*</span></span>

<span data-ttu-id="2b102-p101">Die erste Entscheidung in Ihrer Identitätshybridlösung ist Ihre Authentifizierungsanforderung. Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2b102-p101">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="2b102-p102">Bei der **verwalteten Authentifizierung** verarbeitet Azure AD den Authentifizierungsprozess für die Benutzeranmeldung. Es gibt zwei Methoden für die verwaltete Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="2b102-p102">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="2b102-p103">**Kennworthashsynchronisierung (PHS)** [Für einige Premiumfunktionen empfohlen und erforderlich]. Dies ist die einfachste Methode zum Aktivieren der Authentifizierung für lokale Verzeichnisobjekte in Azure AD. Azure AD Connect extrahiert das Kennwort mit Hash aus Windows Server AD, führt eine zusätzliche Sicherheitsverarbeitung für das Kennwort aus und speichert es in Azure AD. Weitere Informationen finden Sie unter [Implementieren der Kennworthashsynchronisierung mit der Azure AD Connect-Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span><span class="sxs-lookup"><span data-stu-id="2b102-p103">**Password Hash Sync (PHS)** [Recommended and required for some premium features]. This is the simplest way to enable authentication for on-premises directory objects in Azure AD. Azure AD Connect extracts the hashed password from Active Directory, does extra security processing on the password, and saves it in Azure AD. For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="2b102-p104">Die **Passthrough-Authentifizierung (PTA)** stellt eine einfache Lösung zur Kennwortüberprüfung für Azure AD-basierte Dienste bereit. PTA verwendet einen Agent, der auf einem oder mehreren lokalen Servern ausgeführt wird, um die Benutzerauthentifizierungsmethode direkt mit dem lokalen Windows Server Active Directory zu überprüfen. Weitere Informationen finden Sie unter [Benutzeranmeldung mit der Azure Active Directory-Passthrough-Authentifizierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="2b102-p104">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services. PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises Windows Server AD. For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="2b102-p105">Bei der **Verbundauthentifizierung** wird der Authentifizierungsprozess über einen Identitätsverbundserver wie die Active Directory-Verbunddienste (AD FS) an einen anderen Identitätsanbieter weitergeleitet, wenn der Benutzer sich anmelden möchte. Der Identitätsanbieter kann weitere Authentifizierungsmethoden bereitstellen, z. B. Smartcard-basierte Authentifizierung. Weitere Informationen finden Sie unter [Wählen der richtigen Authentifizierungsmethode für Ihre Azure Active Directory-Hybrididentitätslösung](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span><span class="sxs-lookup"><span data-stu-id="2b102-p105">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="2b102-123">Nachdem Sie Ihre Identitätshybridlösung ermittelt haben, laden Sie das [IdFix-Tool für die Fehlerbehebung bei der Verzeichnissynchronisierung herunter](https://www.microsoft.com/download/details.aspx?id=36832) und führen es aus, um Ihr Windows Server AD auf Probleme zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="2b102-123">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your Windows Server AD for issues.</span></span>

<span data-ttu-id="2b102-p106">Beheben Sie alle vom IdFix-Tool erkannten Probleme, und lesen Sie dann [Implementieren der Kennworthashsynchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization). Dort finden Sie eine Anleitung zur Installation des Azure AD Connect-Tools und zur Konfiguration der Verzeichnissynchronisierung zwischen Ihrem lokalen Windows Server AD und dem Azure AD-Mandanten für Ihre Office 365- und EMS-Abonnements. Nach dem Start der Synchronisierung werden die Benutzerkonten und Gruppen im lokalen Identitätsanbieter (z. B. Windows Server AD) beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2b102-p106">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises Windows Server AD and the Azure AD tenant for your Office 365 and EMS subscriptions. After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as Windows Server AD.</span></span>

<span data-ttu-id="2b102-126">Microsoft stellt eine Reihe von Empfehlungen für [Identität und Gerätezugriff](microsoft-365-policies-configurations.md) bereit, um sicherzustellen, dass die Mitarbeiter sicher und produktiv arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="2b102-126">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 
- <span data-ttu-id="2b102-127">Empfohlene Anforderungen für Hybridumgebungen finden Sie in der Spalte **Active Directory mit Kennworthashsynchronisierung** unter [Voraussetzungen](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="2b102-127">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="2b102-128">Empfohlene Anforderungen nur für Cloudumgebungen finden Sie in der Spalte **Nur Cloud** unter [Voraussetzungen](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="2b102-128">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="2b102-p107">Wenn Ihre lokalen Benutzer und Gruppen in Azure AD vorhanden sind, können Sie mit dem Zuweisen von Lizenzen beginnen und Exchange Online verwenden. Informationen zur Einführung von Exchange Online für Ihre Benutzer und zur Migration von lokalen Postfächern finden Sie unter [Bereitstellen von Exchange Online für Microsoft 365 Enterprise](identity-azure-ad-connect.md).</span><span class="sxs-lookup"><span data-stu-id="2b102-p107">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using Exchange Online. To roll out Exchange Online to your users and migrate on-premises mailboxes, see [Deploy Exchange Online for Microsoft 365 Enterprise](identity-azure-ad-connect.md).</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2b102-132">Testumgebungsanleitung: Kennworthashsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="2b102-132">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="2b102-133">Testumgebungsanleitung: Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2b102-133">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="2b102-134">Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sync) für diesen Schritt anschauen.</span><span class="sxs-lookup"><span data-stu-id="2b102-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2b102-135">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="2b102-135">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="2b102-136">Überwachen des Synchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="2b102-136">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |

