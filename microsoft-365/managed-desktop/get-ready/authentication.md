---
title: Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass eine Azure AD mit lokaler AD kommunizieren kann, um die Authentifizierung bereitzustellen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7181e81a2db94ce26fb8601f8b9156c65084c439
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289579"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop

In Microsoft Managed Desktop werden Geräte automatisch mit Azure Active Directory (Azure AD) verbunden. Wenn Sie also eine lokale Active Directory verwenden, müssen Sie einige Dinge überprüfen, um sicherzustellen, dass die Azure AD verbundenen Geräte mit Ihrer lokalen Active Directory kommunizieren können. 

> [!NOTE]  
> *Hybrid* Azure AD Beitritt wird von Microsoft Managed Desktop nicht unterstützt.

Azure Active Directory ermöglicht Ihren Benutzern die Nutzung von einmaligem Anmelden (Single Sign-on, SSO), was bedeutet, dass Sie in der Regel nicht jedes Mal, wenn Sie Ressourcen verwenden, Anmeldeinformationen bereitstellen müssen.

Informationen zum Verbinden von Azure Active Directory finden Sie unter [How to: Plan your Azure AD Join Implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Hintergrundinformationen zu einmaligem Anmelden (Single Sign-on, SSO) auf Geräten, die Azure AD beigetreten sind, finden Sie unter [How SSO to on-premises Resources Works on Azure AD Joined Devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


In diesem Thema werden die Dinge erläutert, die Sie überprüfen müssen, um sicherzustellen, dass apps und andere Ressourcen, die von der lokalen Active Directory Konnektivität abhängen, reibungslos mit Microsoft Managed Desktop funktionieren.


## <a name="single-sign-on-for-on-premises-resources"></a>Einmaliges Anmelden für lokale Ressourcen

Einmaliges Anmelden (Single Sign-on, SSO) mithilfe von UPN und Kennwort ist auf Microsoft Managed Desktop-Geräten standardmäßig aktiviert. Ihre Benutzer können aber auch Windows Hello for Business verwenden, was einige zusätzliche Setupschritte erfordert. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Einmaliges Anmelden mit UPN und Kennwort

In den meisten Organisationen können Ihre Benutzer SSO verwenden, um sich über UPN und Kennwort auf Microsoft Managed Desktop-Geräten zu authentifizieren. Um jedoch sicherzustellen, dass dies funktioniert, sollten Sie Folgendes überprüfen:

- Stellen Sie sicher, dass Azure AD Connect eingerichtet ist und einen lokalen Active Directory Server mit Windows Server 2008 R2 oder höher verwendet.
- Stellen Sie sicher, dass Azure AD Connect eine unterstützte Version ausführt und diese drei Attribute mit Azure AD synchronisieren: 
    - DNS-Domänenname des lokalen Active Directory (in dem sich die Benutzer befinden)
    - NetBIOS Ihrer lokalen Active Directory (wo sich die Benutzer befinden)
    - SAM-Konto Name des Benutzers


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Einmaliges Anmelden mit Windows Hello for Business

Microsoft Managed Desktop-Geräte bieten ihren Benutzern auch eine schnelle und passive Benutzerfreundlichkeit, indem Sie Windows Hello for Business verwenden. Um sicherzustellen, dass Windows Hello for Business funktioniert, ohne dass Ihre Benutzer den jeweiligen UPN und das Kennwort angeben müssen, besuchen Sie [configure Azure AD Joined Devices for on-premises Single-Signing on using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) , um die Anforderungen zu überprüfen, und befolgen Sie dann die Schritte, die dort vorgesehen sind.


## <a name="apps-and-resources-that-use-authentication"></a>Apps und Ressourcen, die die Authentifizierung verwenden

Ausführliche Anleitungen zum Einrichten von Apps für die Verwendung von Azure Active Directory erhalten Sie Untergrund [Legendes zu den Überlegungen zu Anwendungen und Ressourcen](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) im Azure-inhaltsset. Zusammenfassung:


- Wenn Sie **Cloud-basierte apps**verwenden, wie Sie zum Azure AD-App-Katalog hinzugefügt wurden, benötigen die meisten keine weiteren Vorbereitungen für die Arbeit mit Microsoft Managed Desktop. Allerdings können Win32-apps, die nicht den webaccountmanager (WAM) verwenden, Benutzer weiterhin zur Authentifizierung auffordern.

- Für apps, die **lokal gehostet**werden, müssen Sie diese apps der Liste der vertrauenswürdigen Sites in ihren Browsern hinzufügen. Auf diese Weise kann die Windows-Authentifizierung nahtlos funktionieren, ohne dass Benutzer zur Eingabe von Anmeldeinformationen aufgefordert werden. Verweisen Sie dazu in der [Referenz konfigurierbare Einstellungen](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)auf [vertrauenswürdige Websites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) .

- Wenn Sie Active Directory Verbunddienste verwenden, überprüfen Sie, ob SSO aktiviert ist, indem Sie die Schritte unter [überprüfen und Verwalten von einmaligem Anmelden mit AD FS durchführen](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Für apps, die **lokal sind und ältere Protokolle verwenden**, ist kein zusätzliches Setup erforderlich, solange die Geräte Zugriff auf einen lokalen Domänencontroller haben, der authentifiziert werden soll. Um einen sicheren Zugriff für diese Anwendungen zu gewährleisten, sollten Sie jedoch Azure AD Anwendungs Proxy bereitstellen. Weitere Informationen finden Sie unter [Remote Zugriff auf lokale Anwendungen über den Anwendungs Proxy von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Apps, die **lokal ausgeführt werden und auf der Computerauthentifizierung basieren** , werden nicht unterstützt, daher sollten Sie diese durch neuere Versionen ersetzen.

### <a name="network-shares-that-use-authentication"></a>Netzwerkfreigaben, die die Authentifizierung verwenden

Es ist kein zusätzliches Setup erforderlich, damit Benutzer auf Netzwerkfreigaben zugreifen können, solange die Geräte über einen UNC-Pfad Zugriff auf einen lokalen Domänencontroller haben.

### <a name="printers"></a>Drucker

Microsoft Managed Desktop-Geräte können keine Verbindung mit Druckern herstellen, die in Ihrem lokalen Active Directory veröffentlicht werden, es sei denn, Sie haben [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)konfiguriert.

Während Drucker nicht automatisch in einer nur-Cloud-Umgebung erkannt werden können, können Ihre Benutzer lokale Drucker mithilfe des Drucker Pfads oder des Druckerwarte Schlangen Pfads verwenden, solange die Geräte Zugriff auf einen lokalen Domänencontroller haben.

<!--add fuller material on printers when available-->
