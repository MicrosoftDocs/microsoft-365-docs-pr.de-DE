---
title: Verwalten von Kennwörtern für Microsoft 365-Benutzerkonten
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
description: In diesem Artikel erfahren Sie, wie Sie Kennwörter für Microsoft 365-Benutzerkonten verwalten.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328509"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Verwalten von Kennwörtern für Microsoft 365-Benutzerkonten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können die Kennwörter von Microsoft 365-Benutzerkonten in Abhängigkeit von Ihrer Identitäts Konfiguration auf verschiedene Arten verwalten. Sie können Benutzerkonten im [Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory-Domänendienste (AD DS) oder im Azure Active Directory (Azure AD) Admin Center verwalten.

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Planen, wo und wie Sie die Kennwörter für Benutzerkonten verwalten können

Wo und wie Sie Ihre Benutzerkonten verwalten können, hängt vom Identitätsmodell ab, das Sie für Ihre Microsoft 365 verwenden möchten. Die beiden Modelle sind nur in der Cloud und Hybrid.
  
### <a name="cloud-only"></a>Rein cloudbasiert

Sie verwalten Kennwörter für Benutzerkonten in:

- [Das Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- Das Azure AD Admin Center
    
### <a name="hybrid"></a>Hybrid

Bei der Hybrid Identität werden Kennwörter in AD DS gespeichert, sodass Sie lokale AD DS-Tools zum Verwalten von Kennwörtern für Benutzerkonten verwenden müssen. Selbst bei Verwendung der Kenn Wort Hash Synchronisierung (Password Hash Synchronization, PHS), in der Azure AD eine gehashte Version der bereits gehashten Version in AD DS speichert, müssen Sie und die Benutzer ihre Kennwörter in AD DS verwalten.

Mit dem [Kenn Wort](#pw_writeback)Rückschreiben können Ihre Benutzer Ihre AD DS Kennwörter über Azure AD ändern.

## <a name="prevent-bad-passwords"></a>Verhindern unsicherer Kennwörter

Alle Benutzer Ihrer Organisation sollten bei der Erstellung der Kennwörter für ihre Benutzerkonten die [Kennwortrichtlinien von Microsoft](https://www.microsoft.com/research/publication/password-guidance) anwenden.

Verwenden Sie den Azure AD-Kennwortschutz, der sowohl eine Liste global gesperrter Kennwörter als auch eine von Ihnen definierte optionale benutzerdefinierte Liste gesperrter Kennwörter verwendet, um Benutzer daran zu hindern, einfach zu erratende Kennwörter zu erstellen. Hier können Sie beispielsweise Ausdrücke angeben, die für Ihre Organisation spezifisch sind, z. B.:

- Markennamen
- Produktnamen
- Standorte (z. B. Firmenhauptsitz)
- Unternehmensspezifische interne Begriffe
- Abkürzungen, die eine bestimmte Bedeutung im Unternehmen haben

Sie können ungültige Kennwörter [in der Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) und für Ihre [lokale AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)verbieten.

## <a name="simplify-user-sign-in"></a>Vereinfachen der Benutzeranmeldung

Azure AD nahtloses einmaliges Anmelden (Azure AD nahtloses SSO) funktioniert mit der PHS-und der Pass-Through-Authentifizierung (PTA), damit sich Ihre Benutzer bei Diensten anmelden können, die Azure AD Benutzerkonten verwenden, ohne Ihre Kennwörter und in vielen Fällen Ihre Benutzernamen eingeben zu müssen. Damit können Benutzer einfacher auf cloudbasierte Anwendungen wie Office 365 zugreifen, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver notwendig sind.

Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect. Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Vereinfachen der Kennwortaktualisierung auf AD DS

Mit dem Kenn Wort Rückschreiben können Sie Benutzern das Zurücksetzen Ihrer Kennwörter über Azure AD gestatten, das dann in AD DS repliziert wird. Benutzer müssen nicht auf Ihre lokalen AD DS zugreifen, um Ihre Kennwörter zu aktualisieren. Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.

Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Azure AD Identity Protection, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein hohes Risiko einer Kontogefährdung besteht.

Weitere Informationen und Hinweise zur Konfiguration finden Sie unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Führen Sie ein Upgrade auf die neueste Version von Azure AD Connect durch, um das bestmögliche Benutzererlebnis und die Verfügbarkeit neuer Features sicherzustellen, sobald diese veröffentlicht werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Vereinfachen der Kennwortzurücksetzung

Self-Service Password Reset (SSPR) ermöglicht Benutzern das Zurücksetzen oder entsperren ihrer Kennwörter oder Konten. Um über eine fehlerhafte oder missbräuchliche Nutzung informiert zu werden, können Sie die ausführliche Berichterstellung verwenden, bei der der Benutzerzugriff auf das System nachverfolgt wird. Sie müssen das [Kenn Wort](#pw_writeback) Rückschreiben aktivieren, bevor Sie das Zurücksetzen von Kennwörtern bereitstellen können.

Lesen Sie die [Anweisungen zum Rollout der Kennwortzurücksetzung](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

