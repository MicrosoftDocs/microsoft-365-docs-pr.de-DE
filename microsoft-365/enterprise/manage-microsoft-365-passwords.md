---
title: Verwalten Microsoft 365 Benutzerkontenkennwörtern
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Erfahren Sie mehr über die Verwaltung Microsoft 365 Benutzerkontenkennwörtern.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905092"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Verwalten Microsoft 365 Benutzerkontenkennwörtern

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können Microsoft 365 Benutzerkontenkennwörtern abhängig von Ihrer Identitätskonfiguration auf verschiedene Weise verwalten. Sie können Benutzerkonten im [Microsoft 365 Admin Center,](../admin/add-users/index.yml)in Active Directory Domain Services (AD DS) oder im Azure Active Directory (Azure AD) Admin Center verwalten.

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Planen, wo und wie Sie Ihre Benutzerkontenkennwörter verwalten

Wo und wie Sie Ihre Benutzerkonten verwalten können, hängt vom Identitätsmodell ab, das Sie für Ihre Microsoft 365. Die beiden Modelle sind nur cloud- und hybrid.
  
### <a name="cloud-only"></a>Rein cloudbasiert

Sie verwalten Benutzerkontenkennwörter in:

- [Das Microsoft 365 Admin Center](../admin/add-users/index.yml)
- Azure AD Admin Center
    
### <a name="hybrid"></a>Hybrid

Bei hybrider Identität werden Kennwörter in AD DS gespeichert, sodass Sie lokale AD DS-Tools zum Verwalten von Benutzerkontenkennwörtern verwenden müssen. Selbst bei Verwendung der Kennworthashsynchronisierung (Password Hash Synchronization, PHS), in der Azure AD eine Hashversion der bereits in AD DS hashierten Version speichert, müssen Sie und Benutzer ihre Kennwörter in AD DS verwalten.

Mit [dem Kennwortrückschreiben](#pw_writeback)können Ihre Benutzer ihre AD DS-Kennwörter über Azure AD ändern.

## <a name="prevent-bad-passwords"></a>Verhindern unsicherer Kennwörter

Alle Benutzer Ihrer Organisation sollten bei der Erstellung der Kennwörter für ihre Benutzerkonten die [Kennwortrichtlinien von Microsoft](https://www.microsoft.com/research/publication/password-guidance) anwenden.

Verwenden Sie den Azure AD-Kennwortschutz, der sowohl eine Liste global gesperrter Kennwörter als auch eine von Ihnen definierte optionale benutzerdefinierte Liste gesperrter Kennwörter verwendet, um Benutzer daran zu hindern, einfach zu erratende Kennwörter zu erstellen. Hier können Sie beispielsweise Ausdrücke angeben, die für Ihre Organisation spezifisch sind, z. B.:

- Markennamen
- Produktnamen
- Standorte (z. B. Firmenhauptsitz)
- Unternehmensspezifische interne Begriffe
- Abkürzungen, die eine bestimmte Bedeutung im Unternehmen haben

Sie können ungültige Kennwörter [in der Cloud und](/azure/active-directory/authentication/concept-password-ban-bad) für Ihren lokalen AD [DS verbieten.](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)

## <a name="simplify-user-sign-in"></a>Vereinfachen der Benutzeranmeldung

Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) funktioniert mit PHS und Pass-Through Authentication (PTA), um Ihren Benutzern die Anmeldung bei Diensten zu ermöglichen, die Azure AD-Benutzerkonten verwenden, ohne ihre Kennwörter und in vielen Fällen ihre Benutzernamen eingeben zu müssen. Damit können Benutzer einfacher auf cloudbasierte Anwendungen wie Office 365 zugreifen, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver notwendig sind.

Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect. Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Vereinfachen von Kennwortupdates für AD DS

Mit dem Kennwortrückschreiben können Sie Benutzern das Zurücksetzen ihrer Kennwörter über Azure AD ermöglichen, das dann in AD DS repliziert wird. Benutzer müssen nicht auf ihre lokale AD DS zugreifen, um ihre Kennwörter zu aktualisieren. Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.

Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Azure AD Identity Protection, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein hohes Risiko einer Kontogefährdung besteht.

Weitere Informationen und Hinweise zur Konfiguration finden Sie unter [Azure AD SSPR mit Kennwortrückschreiben](/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Führen Sie ein Upgrade auf die neueste Version von Azure AD Connect durch, um das bestmögliche Benutzererlebnis und die Verfügbarkeit neuer Features sicherzustellen, sobald diese veröffentlicht werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Vereinfachen der Kennwortzurücksetzung

Mit der Self-Service Password Reset (SSPR) können Benutzer ihre Kennwörter oder Konten zurücksetzen oder entsperren. Um über eine fehlerhafte oder missbräuchliche Nutzung informiert zu werden, können Sie die ausführliche Berichterstellung verwenden, bei der der Benutzerzugriff auf das System nachverfolgt wird. Sie müssen das [Kennwortrückschreiben aktivieren,](#pw_writeback) bevor Sie Kennwortzurücksetzungen bereitstellen können.

Lesen Sie die [Anweisungen zum Rollout der Kennwortzurücksetzung](/azure/active-directory/authentication/howto-sspr-deployment).