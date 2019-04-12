---
title: Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass eine Azure AD mit der lokalen AD kommunizieren kann, um die Authentifizierung bereitzustellen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824465"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop

In Microsoft Managed Desktop werden Geräte automatisch mit Azure Active Directory verbunden. Wenn Sie also ein lokales Active Directory verwenden, müssen Sie einige Dinge überprüfen, um sicherzustellen, dass mit Azure AD verbundene Geräte mit Ihrem lokalen Active Directory kommunizieren können. 

> [!NOTE]  
> *Hybrid* Azure AD Join wird von Microsoft Managed Desktop nicht unterstützt.

Azure Active Directory ermöglicht es Ihren Benutzern, einmaliges Anmelden (Single Sign-on, SSO) zu nutzen, was dazu führt, dass Sie nicht jedes Mal, wenn Sie etwas tun möchten, Anmeldeinformationen angeben müssen. Wenn Sie vollständig neu in Azure Active Directory sind, finden Sie unter [How to: Plan your Azure AD Join Implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)--Wenn Sie jedoch auf die Azure Active Directory-Dokumentation verweisen, beachten Sie, dass der *Hybrid* Azure AD Join von Microsoft nicht unterstützt wird. Verwalteter Desktop.


In diesem Thema werden die Dinge erläutert, die Sie überprüfen müssen, um sicherzustellen, dass apps und andere Ressourcen, die von der lokalen Active Directory-Konnektivität abhängig sind, reibungslos mit Microsoft Managed Desktop funktionieren.


> [!IMPORTANT]  
> Damit Benutzer Geräte in Azure Active Directory registrieren und in InTune (erforderlich für Microsoft Managed Desktop) anmelden können, führen Sie die Schritte unter [configure your device settings](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) aus, bevor Sie mit dem Rest dieses Themas fortfahren.


## <a name="single-sign-on-for-on-premises-resources"></a>Einmaliges Anmelden für lokale Ressourcen

Einmaliges Anmelden (Single Sign-on, SSO) für Ihre Geräte mithilfe von UPN oder Kennwörtern (die Standardmethode) sollte bereits standardmäßig funktionieren. Sie können aber auch Windows Hello for Business verwenden, was einige zusätzliche Setupschritte erfordert. Hintergrundinformationen zu SSO finden Sie unter [Funktionsweise von SSO zu lokalen Ressourcen auf mit Azure AD verbundene Geräte](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


### <a name="single-sign-on-by-using-upn-and-passwords"></a>Einmaliges Anmelden mithilfe von UPN und Kennwörtern

Es ist kein spezielles Setup erforderlich, damit Ihre Benutzer sich über UPN und Kennwort authentifizieren können – Sie erhalten dies standardmäßig über Azure. Sie sollten jedoch Folgendes überprüfen, um sicherzustellen, dass dies funktioniert:

- Vergewissern Sie sich, dass Azure Active Directory (AAD) Connect mit einem lokalen Active Directory-Server mit Windows Server 2008 R2 oder höher eingerichtet ist.
- AAD Connect führt eine unterstützte Version aus und wird so festgelegt, dass diese drei Schlüsselattribute mit Azure AD synchronisiert werden: 
    - DNS-Domänenname, in dem der Benutzer in Ihrem lokalen Active Directory vorhanden ist
    - NetBIOS-Domänenname, in dem der Benutzer in Ihrem lokalen Active Directory vorhanden ist
    - SAM-Konto Name des Benutzers


### <a name="sso-by-using-windows-hello-for-business"></a>SSO mithilfe von Windows Hello for Business

Alternativ können Sie Ihren Benutzern eine schnelle, kennwortlos-Erfahrung bieten, indem Sie Windows Hello for Business verwenden. Um dies einzurichten, besuchen Sie [configure Azure AD Joined Devices for on-premises Single-Sign on using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) , um die Anforderungen zu überprüfen, und befolgen Sie dann die dort bereitgestellten Schritte.


## <a name="apps-and-resources-that-use-authentication"></a>Apps und Ressourcen, die die Authentifizierung verwenden

Ausführliche Informationen zum Einrichten von Apps für die Verwendung mit Azure Active Directory finden Sie Untergrund Legendes zu [Anwendungen und Ressourcen](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) im Azure-Inhaltssatz. Zusammenfassung:


- Wenn Sie **Cloud-basierte apps**verwenden, wie beispielsweise solche, die dem Azure AD-App-Katalog hinzugefügt werden, benötigen die meisten keine weiteren Vorbereitungen für die Arbeit mit Microsoft Managed Desktop. Alle Win32-apps, die Web Account Manager (WAM) {verify this Akronym} jedoch nicht verwenden, können Benutzer weiterhin zur Authentifizierung auffordern.

- Bei apps, die **lokal gehostet**werden, müssen Sie diese apps der Liste der vertrauenswürdigen Websites in Ihrem Browser hinzufügen. Dadurch kann die Windows-Authentifizierung nahtlos ausgeführt werden, ohne dass Benutzer zur Eingabe von Anmeldeinformationen aufgefordert werden.

- Wenn Sie Active Directory-Verbunddienste verwenden, führen Sie die Schritte unter [überprüfen und Verwalten des einmaligen Anmeldens mit AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))aus. 

- Für apps, die **lokal sind und ältere Protokolle verwenden**, ist kein zusätzliches Setup erforderlich, solange die Geräte über Zugriff auf einen lokalen Domänencontroller verfügen. Zur Bereitstellungeines sicheren Zugriffs für diese Anwendungen sollten Sie jedoch den Azure AD-Anwendungs Proxy bereitstellen. Weitere Informationen finden Sie unter [Remote Zugriff auf lokale Anwendungen über Azure Active Directory Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Apps, die **lokal ausgeführt werden und auf der Computerauthentifizierung basieren** , werden nicht unterstützt, daher sollten Sie diese mit neueren Versionen ersetzen.

## <a name="network-shares-that-use-authentication"></a>Netzwerkfreigaben, die die Authentifizierung verwenden

Es ist keine zusätzliche Installation erforderlich, damit Benutzer auf Netzwerkfreigaben zugreifen können, solange die Geräte über einen UNC-Pfad Zugriff auf einen lokalen Domänencontroller haben.

## <a name="printers"></a>Drucker

Drucker können in einer Cloud-Umgebung nicht automatisch erkannt werden, aber auch der UNC-Pfad der Drucker kann direkt hinzugefügt werden.

<!--add fuller material on printers when available-->