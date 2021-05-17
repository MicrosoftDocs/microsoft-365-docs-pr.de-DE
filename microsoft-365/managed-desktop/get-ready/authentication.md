---
title: Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass ein Azure AD mit lokalem AD kommunizieren kann, um die Authentifizierung zu ermöglichen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574595"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop

In Microsoft Managed Desktop werden Geräte automatisch mit Azure Active Directory (Azure AD) verbunden. Aus diesem Grund müssen Sie, wenn Sie ein lokales Active Directory verwenden, einige Dinge überprüfen, um sicherzustellen, dass Mit Azure AD verbundene Geräte mit Ihrem lokalen Active Directory kommunizieren können. 

> [!NOTE]  
> *Hybrid* Der Azure AD-Beitritt wird von der Microsoft Managed Desktop.

Azure Active Directory können Ihre Benutzer die Vorteile von Single Sign-On (SSO) nutzen, was bedeutet, dass sie in der Regel nicht jedes Mal Anmeldeinformationen bereitstellen müssen, wenn sie Ressourcen verwenden.

Informationen zum Beitreten Azure Active Directory finden Sie unter [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan). Hintergrundinformationen zu single Sign-On (SSO) auf Geräten, die Azure AD beigetreten sind, finden Sie unter Funktionsweise von [SSO](/azure/active-directory/devices/azuread-join-sso#how-it-works)zu lokalen Ressourcen auf Azure AD-geräten.


In diesem Artikel werden die Dinge erläutert, die Sie überprüfen müssen, um sicherzustellen, dass Apps und andere Ressourcen, die von der lokalen Active Directory-Konnektivität abhängen, problemlos mit Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Einzelne Sign-On für lokale Ressourcen

Single Sign-On (SSO) mithilfe von UPN und Kennwort ist standardmäßig auf Microsoft Managed Desktop aktiviert. Ihre Benutzer können jedoch auch Windows Hello for Business verwenden, was einige zusätzliche Setupschritte erfordert. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Einzelne Sign-On mithilfe von UPN und Kennwort

In den meisten Organisationen können Ihre Benutzer SSO verwenden, um sich über UPN und Kennwort auf Microsoft Managed Desktop authentifizieren. Um jedoch sicherzustellen, dass diese Funktion funktioniert, sollten Sie die folgenden Punkte überprüfen:

- Vergewissern Sie sich, dass Azure AD Verbinden eingerichtet ist und einen lokalen Active Directory-Server mit Windows Server 2008 R2 oder höher verwendet.
- Vergewissern Sie sich, dass Azure AD Verbinden eine unterstützte Version ausgeführt wird und für die Synchronisierung dieser drei Attribute mit Azure AD festgelegt ist: 
    - DNS-Domänenname des lokalen Active Directory (in dem sich die Benutzer befinden)
    - NetBIOS Ihres lokalen Active Directory (in dem sich die Benutzer befinden)
    - Sam-Kontoname des Benutzers


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Einzelne Sign-On mithilfe von Windows Hello for Business

Microsoft Managed Desktop bieten Ihren Benutzern auch eine schnelle, kennwortlose Benutzererfahrung, indem Sie Windows Hello for Business verwenden. Um sicherzustellen, dass Windows Hello for Business funktioniert, ohne dass Ihre Benutzer den entsprechenden UPN und ein Kennwort angeben müssen, besuchen Sie Configure Azure AD joined [devices for On-premises Single-Sign On using Windows Hello for Business,](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) um die Anforderungen zu überprüfen, und führen Sie dann die dort bereitgestellten Schritte aus.


## <a name="apps-and-resources-that-use-authentication"></a>Apps und Ressourcen, die die Authentifizierung verwenden

Ausführliche [Anleitungen zum](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) Einrichten von Apps für die Arbeit mit Apps finden Sie unter Verstehen von Überlegungen zu Anwendungen und Ressourcen im Azure-Inhaltssatz Azure Active Directory. Zusammenfassend:


- Wenn Sie **cloudbasierte** Apps verwenden, z. B. apps, die dem Azure AD-App-Katalog hinzugefügt wurden, benötigen die meisten keine weitere Vorbereitung für die Arbeit mit Microsoft Managed Desktop. Win32-Apps, die den Web Account Manager (WAM) nicht verwenden, können benutzer jedoch weiterhin zur Authentifizierung anforderen.

- Bei apps, die lokal gehostet **werden,** müssen Sie diese Apps der Liste vertrauenswürdiger Websites in Ihren Browsern hinzufügen. Dieser Schritt ermöglicht Windows nahtlose Authentifizierung, ohne dass Benutzer zur Eingabe von Anmeldeinformationen aufgefordert werden. Informationen zum Hinzufügen von Apps finden Sie unter [Vertrauenswürdige Websites](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) unter [Configurable settings reference](../working-with-managed-desktop/config-setting-ref.md).

- Wenn Sie Active Directory-Verbunddienste verwenden, überprüfen Sie mithilfe der Schritte unter [Verify and manage single sign-on with AD FS,](/previous-versions/azure/azure-services/jj151809(v=azure.100))ob SSO aktiviert ist. 

- Für apps, die lokal sind und ältere Protokolle verwenden, ist kein **zusätzliches** Setup erforderlich, solange die Geräte Zugriff auf einen lokalen Domänencontroller haben, um sich zu authentifizieren. Um sicheren Zugriff für diese Anwendungen zu ermöglichen, sollten Sie jedoch Azure AD Application Proxy bereitstellen. Weitere Informationen finden Sie unter Remotezugriff auf lokale Anwendungen über [Azure Active Directory Anwendungsproxy .](/azure/active-directory/manage-apps/application-proxy)

- Apps, die **lokal ausgeführt werden und auf** der Computerauthentifizierung beruhen, werden nicht unterstützt. Sie sollten daher erwägen, sie durch neuere Versionen zu ersetzen.

### <a name="network-shares-that-use-authentication"></a>Netzwerkfreigaben, die die Authentifizierung verwenden

Es ist kein zusätzliches Setup erforderlich, damit Benutzer auf Netzwerkfreigaben zugreifen können, solange die Geräte über einen UNC-Pfad Zugriff auf einen lokalen Domänencontroller haben.

### <a name="printers"></a>Drucker

Microsoft Managed Desktop geräte können keine Verbindung mit Druckern herstellen, die in Ihrem lokalen Active Directory veröffentlicht werden, es sei denn, Sie haben [Hybrid Cloud Print konfiguriert.](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Während Drucker nicht automatisch in einer cloudbasierten Umgebung erkannt werden können, können Ihre Benutzer lokale Drucker mithilfe des Druckerpfads oder des Druckerwarteschlangenpfads verwenden, solange die Geräte Zugriff auf einen lokalen Domänencontroller haben.

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a>Schritte für die ersten Schritte

1. Überprüfen [Sie Voraussetzungen für Microsoft Managed Desktop](prerequisites.md).
2. Verwenden [Sie Die Bereitschaftsbewertungstools](readiness-assessment-tool.md).
3. [Voraussetzungen für Gastkonten](guest-accounts.md)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des zugriffs auf lokale Ressourcen für Microsoft Managed Desktop](authentication.md) (Dieser Artikel)
7. [Apps im Microsoft Managed Desktop](apps.md)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md)
