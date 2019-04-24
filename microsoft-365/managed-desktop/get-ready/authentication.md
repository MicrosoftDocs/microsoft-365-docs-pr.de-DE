---
title: Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass eine Azure AD mit der lokalen AD kommunizieren kann, um die Authentifizierung bereitzustellen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276916"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop

In Microsoft Managed Desktop werden Geräte automatisch mit Azure Active Directory (Azure AD) verbunden. Wenn Sie also ein lokales Active Directory verwenden, müssen Sie einige Dinge überprüfen, um sicherzustellen, dass mit Azure AD verbundene Geräte mit Ihrem lokalen Active Directory kommunizieren können. 

> [!NOTE]  
> *Hybrid* Azure AD Join wird von Microsoft Managed Desktop nicht unterstützt.

Mit Azure Active Directory können Ihre Benutzer die Vorteile des einmaligen Anmeldens (Single Sign-on, SSO) nutzen, d. h., Sie müssen in der Regel nicht bei jeder Verwendung von Ressourcen Anmeldeinformationen angeben.

Informationen zum Hinzufügen von Azure Active Directory finden Sie unter [How to: Plan your Azure AD Join Implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Hintergrundinformationen zum einmaligen Anmelden (Single Sign-on, SSO) auf Geräten, die mit Azure AD verbunden sind, finden Sie unter [Funktionsweise von SSO zu lokalen Ressourcen auf mit Azure AD verbundene Geräte](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


In diesem Thema werden die Dinge erläutert, die Sie überprüfen müssen, um sicherzustellen, dass apps und andere Ressourcen, die von der lokalen Active Directory-Konnektivität abhängig sind, reibungslos mit Microsoft Managed Desktop funktionieren.


## <a name="single-sign-on-for-on-premises-resources"></a>Einmaliges Anmelden für lokale Ressourcen

Einmaliges Anmelden (Single Sign-on, SSO) mithilfe von UPN und Kennwort ist auf Microsoft-Desktop Geräten standardmäßig aktiviert. Ihre Benutzer können aber auch Windows Hello for Business verwenden, was einige zusätzliche Setupschritte erfordert. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Einmaliges Anmelden mithilfe von UPN und Kennwort

In den meisten Organisationen können Benutzer mithilfe von SSO mithilfe von UPN und Kennwort auf verwalteten Desktop Geräten von Microsoft authentifizieren. Sie sollten jedoch Folgendes überprüfen, um sicherzustellen, dass dies funktioniert:

- Vergewissern Sie sich, dass Azure AD Connect eingerichtet ist und einen lokalen Active Directory-Server mit Windows Server 2008 R2 oder höher verwendet.
- Vergewissern Sie sich, dass Azure AD Connect eine unterstützte Version ausführt und diese drei Attribute mit Azure AD synchronisiert werden: 
    - DNS-Domänenname des lokalen Active Directory (in dem sich die Endbenutzer befinden)
    - NetBIOS des lokalen Active Directory (in dem sich die Endbenutzer befinden)
    - SAM-Konto Name des Benutzers


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Einmaliges Anmelden mithilfe von Windows Hello for Business

Microsoft Managed Desktop-Geräte bieten ihren Benutzern außerdem eine schnelle, kennwortlos-Erfahrung, indem Sie Windows Hello for Business verwenden. Wenn Sie sicherstellen möchten, dass Windows Hello for Business funktioniert, ohne dass Ihre Benutzer den entsprechenden UPN und das Kennwort angeben müssen, besuchen Sie [configure Azure AD Joined Devices for on-premises Single-Sign on using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) , um die Anforderungen zu überprüfen und dann Führen Sie die dort aufgeführten Schritte aus.


## <a name="apps-and-resources-that-use-authentication"></a>Apps und Ressourcen, die die Authentifizierung verwenden

Ausführliche Informationen zum Einrichten von Apps für die Verwendung mit Azure Active Directory finden Sie Untergrund Legendes zu [Anwendungen und Ressourcen](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) im Azure-Inhaltssatz. Zusammenfassung:


- Wenn Sie **Cloud-basierte apps**verwenden, wie beispielsweise solche, die dem Azure AD-App-Katalog hinzugefügt werden, benötigen die meisten keine weiteren Vorbereitungen für die Arbeit mit Microsoft Managed Desktop. Allerdings können alle Win32-apps, die den Web Account Manager (WAM) nicht verwenden, Benutzer weiterhin zur Authentifizierung auffordern.

- Bei apps, die **lokal gehostet**werden, müssen Sie diese apps der Liste der vertrauenswürdigen Websites in Ihrem Browser hinzufügen. Dadurch kann die Windows-Authentifizierung nahtlos ausgeführt werden, ohne dass Benutzer zur Eingabe von Anmeldeinformationen aufgefordert werden. Informationen hierzu finden Sie unter [vertrauenswürdige Websites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in der [Referenz zu konfigurierbaren Einstellungen](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Wenn Sie Active Directory-Verbunddienste verwenden, überprüfen Sie, ob SSO aktiviert ist, indem Sie die Schritte unter [überprüfen und Verwalten des einmaligen Anmeldens mit AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))ausführen. 

- Für apps, die **lokal sind und ältere Protokolle verwenden**, ist kein zusätzliches Setup erforderlich, solange die Geräte über Zugriff auf einen lokalen Domänencontroller zur Authentifizierung verfügen. Zur Bereitstellungeines sicheren Zugriffs für diese Anwendungen sollten Sie jedoch den Azure AD-Anwendungs Proxy bereitstellen. Weitere Informationen finden Sie unter [Remote Zugriff auf lokale Anwendungen über Azure Active Directory Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Apps, die **lokal ausgeführt werden und auf der Computerauthentifizierung basieren** , werden nicht unterstützt, daher sollten Sie diese mit neueren Versionen ersetzen.

### <a name="network-shares-that-use-authentication"></a>Netzwerkfreigaben, die die Authentifizierung verwenden

Es ist keine zusätzliche Installation erforderlich, damit Benutzer auf Netzwerkfreigaben zugreifen können, solange die Geräte über einen UNC-Pfad Zugriff auf einen lokalen Domänencontroller haben.

### <a name="printers"></a>Drucker

Microsoft Managed Desktop-Geräte können keine Verbindung zu Druckern herstellen, die in Ihrem lokalen Active Directory veröffentlicht werden, es sei denn, Sie haben [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)konfiguriert.

Drucker können zwar nicht automatisch in einer Cloud-Umgebung ermittelt werden, Ihre Benutzer verwenden jedoch lokale Drucker mithilfe des Drucker Pfads oder des Druckerwarte Schlangen Pfads, sofern die Geräte über Zugriff auf einen lokalen Domänencontroller verfügen.

<!--add fuller material on printers when available-->
