---
title: Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass ein Azure AD mit dem lokalen AD kommunizieren kann, um die Authentifizierung zu ermöglichen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c1732dc17188427f9a181d1c47abe71bb8f39584
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841411"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop

In Microsoft Managed Desktop werden Geräte automatisch mit Azure Active Directory (Azure AD) verbunden. Wenn Sie ein lokales Active Directory verwenden, müssen Sie daher einige Dinge überprüfen, um sicherzustellen, dass mit Azure AD verbundene Geräte mit Ihrem lokalen Active Directory kommunizieren können. 

> [!NOTE]  
> *Hybrid* Der Beitritt zu Azure AD wird von Microsoft Managed Desktop nicht unterstützt.

Mit Azure Active Directory können Benutzer die Vorteile von single Sign-On (SSO) nutzen, was bedeutet, dass sie in der Regel nicht jedes Mal Anmeldeinformationen angeben müssen, wenn sie Ressourcen verwenden.

Informationen zum Beitritt zu Azure Active Directory finden Sie unter [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Hintergrundinformationen zu einmaligem Sign-On (Single Sign-On, SSO) auf Geräten, die mit Azure AD verbunden sind, finden Sie unter Funktionsweise von SSO zu lokalen Ressourcen auf Geräten, die mit Azure AD verbunden [sind.](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)


In diesem Artikel werden die Dinge erläutert, die Sie überprüfen müssen, um sicherzustellen, dass Apps und andere Ressourcen, die von der lokalen Active Directory-Konnektivität abhängen, mit Microsoft Managed Desktop reibungslos funktionieren.


## <a name="single-sign-on-for-on-premises-resources"></a>Einzelne Sign-On für lokale Ressourcen

Single Sign-On (SSO) mithilfe von UPN und Kennwort ist auf Microsoft Managed Desktop Devices standardmäßig aktiviert. Ihre Benutzer können jedoch auch Windows Hello for Business verwenden, was einige zusätzliche Einrichtungsschritte erfordert. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Einzelne Sign-On mithilfe von UPN und Kennwort

In den meisten Organisationen können Ihre Benutzer SSO verwenden, um sich über UPN und Kennwort auf Microsoft Managed Desktop Devices zu authentifizieren. Um jedoch sicherzustellen, dass diese Funktion funktioniert, sollten Sie folgendes überprüfen:

- Vergewissern Sie sich, dass Azure AD Connect eingerichtet ist und einen lokalen Active Windows Server 2008 R2 oder höher verwendet.
- Vergewissern Sie sich, dass Azure AD Connect eine unterstützte Version ausgeführt wird und so festgelegt ist, dass diese drei Attribute mit Azure AD synchronisiert werden: 
    - DER DNS-Domänenname des lokalen Active Directory (in dem sich die Benutzer befinden)
    - NetBIOS Ihres lokalen Active Directory (in dem sich die Benutzer befinden)
    - Name des Sam-Kontos des Benutzers


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Einzelne Sign-On mithilfe von Windows Hello for Business

Microsoft Managed Desktop-Geräte bieten Ihren Benutzern auch eine schnelle, kennwortlose Erfahrung, indem Sie Windows Hello for Business verwenden. Um sicherzustellen, dass Windows Hello for Business funktioniert, ohne dass Ihre Benutzer den entsprechenden UPN und das Kennwort angeben müssen, besuchen Sie "Konfigurieren von in Azure AD beigetretenen Geräten für lokales Single-Sign Bei Verwendung von [Windows Hello for Business,](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) um die Anforderungen zu überprüfen, und führen Sie dann die dort bereitgestellten Schritte aus.


## <a name="apps-and-resources-that-use-authentication"></a>Apps und Ressourcen, die die Authentifizierung verwenden

Weitere Informationen [zum Einrichten von](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) Apps für die Arbeit mit Azure Active Directory finden Sie unter "Überlegungen zu Anwendungen und Ressourcen im Azure-Inhaltssatz". Zusammenfassend:


- Wenn Sie **cloudbasierte** Apps verwenden, z. B. Apps, die dem Azure AD-App-Katalog hinzugefügt wurden, benötigen die meisten keine weitere Vorbereitung für die Arbeit mit Microsoft Managed Desktop. Win32-Apps, die web Account Manager (WAM) nicht verwenden, können benutzer jedoch dennoch zur Authentifizierung aufgefordert werden.

- Für Apps, die lokal **gehostet** werden, müssen Sie diese Apps der Liste der vertrauenswürdigen Websites in Ihren Browsern hinzufügen. Dieser Schritt ermöglicht die nahtlose Funktion der Windows-Authentifizierung, ohne dass Benutzer zur Eingabe von Anmeldeinformationen aufgefordert werden. Informationen zum Hinzufügen von Apps finden Sie unter ["Vertrauenswürdige Websites"](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in der Referenz zu [konfigurierbaren Einstellungen.](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)

- Wenn Sie Active Directory-Verbunddienste verwenden, überprüfen Sie mithilfe der Schritte unter Überprüfen und Verwalten des einmaligen Anmeldens mit AD FS, ob SSO [aktiviert ist.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)) 

- Für Apps, die lokal sind und ältere Protokolle verwenden, ist kein **zusätzliches** Setup erforderlich, solange die Geräte Zugriff auf einen lokalen Domänencontroller haben, um sich zu authentifizieren. Um den sicheren Zugriff für diese Anwendungen zu ermöglichen, sollten Sie jedoch Azure AD-Anwendungsproxy bereitstellen. Weitere Informationen finden Sie unter Remotezugriff auf lokale Anwendungen über [den Anwendungsproxy von Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)

- Apps, die **lokal ausgeführt** werden und sich auf die Computerauthentifizierung verlassen, werden nicht unterstützt. Daher sollten Sie erwägen, sie durch neuere Versionen zu ersetzen.

### <a name="network-shares-that-use-authentication"></a>Netzwerkfreigaben, die die Authentifizierung verwenden

Es ist kein zusätzliches Setup erforderlich, damit Benutzer auf Netzwerkfreigaben zugreifen können, solange die Geräte über einen UNC-Pfad Zugriff auf einen lokalen Domänencontroller haben.

### <a name="printers"></a>Drucker

Microsoft Managed Desktop-Geräte können keine Verbindung mit Druckern herstellen, die in Ihrem lokalen Active Directory veröffentlicht werden, es sei denn, Sie haben [Hybrid Cloud Print konfiguriert.](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Drucker können zwar nicht automatisch in einer Nur-Cloud-Umgebung ermittelt werden, Ihre Benutzer können jedoch lokale Drucker verwenden, indem sie den Druckerpfad oder den Druckerwarteschlangenpfad verwenden, solange die Geräte Zugriff auf einen lokalen Domänencontroller haben.

<!--add fuller material on printers when available-->
