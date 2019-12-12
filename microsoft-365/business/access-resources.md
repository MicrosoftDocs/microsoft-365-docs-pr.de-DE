---
title: Zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Hier erfahren Sie, wie Sie Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker aus einem Azure-Active Directory, dem Windows 10-Gerät beigetreten ist.
ms.openlocfilehash: 89ac38f3da9cbdd3ff1a5eb33dc129d2e83521c7
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967161"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business

Jedes Windows 10-Gerät, das Azure Active Directory beigetreten ist, hat Zugriff auf alle cloudbasierten Ressourcen wie Ihre Office 365-apps und kann von Microsoft 365 Business geschützt werden. Sie können auch Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker gewähren. Um den Zugriff zuzulassen, verwenden Sie [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) , um Ihre lokale Active Directory mit Azure Active Directory zu synchronisieren. 

Weitere Informationen finden Sie unter [Einführung in die Geräteverwaltung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
Die Schritte sind auch in den folgenden Abschnitten zusammengefasst.

> [!IMPORTANT]
> Dieses Verfahren gilt nur für OAuth und NTLM. Kerberos wird nicht unterstützt.
 
## <a name="run-azure-ad-connect"></a>Ausführen Azure AD Connect

Führen Sie die folgenden Schritte aus, um die Azure AD verbundenen Geräte Ihrer Organisation für den Zugriff auf lokale Ressourcen zu aktivieren.
  
1. Führen Sie den Assistenten für die Verzeichnissynchronisierung aus, und Azure AD Connect wie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)beschrieben, um Ihre Benutzer, Gruppen und Kontakte von der lokalen Active Directory in Azure Active Directory zu synchronisieren.
    
2. Nachdem die Verzeichnissynchronisierung abgeschlossen ist, stellen Sie sicher, dass die Windows 10-Geräte Ihrer Organisation Azure AD verbunden sind. Dieser Schritt wird auf jedem Windows 10-Gerät einzeln ausgeführt. Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business-Benutzer](set-up-windows-devices.md) . 
    
3. Nachdem die Windows 10-Geräte Azure AD beigetreten sind, müssen alle Benutzer ihre Geräte neu starten und sich mit Ihren Microsoft 365-Geschäfts Anmeldeinformationen anmelden. Alle Geräte haben jetzt auch Zugriff auf lokale Ressourcen.
    
Es sind keine weiteren Schritte erforderlich, um Zugriff auf lokale Ressourcen für Azure AD verbundene Geräte zu erhalten. Diese Funktionalität ist in Windows 10 integriert. 

Wenn Sie Pläne zur Anmeldung auf dem AADJ-Gerät als Kenn Wort Methode wie PIN/Bio-Metric über WHFB Credential Login haben und dann auf lokale Ressourcen (Freigaben, Drucker.. usw.), bitte beachten Siehttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Wenn Ihre Organisation nicht bereit ist, die oben beschriebene Bereitstellung in der Azure AD beigefügten Gerätekonfiguration vorzulegen, sollten Sie die [Konfiguration einer hybriden Azure AD verbundenen Gerätekonfiguration](manage-windows-devices.md)in prüfen.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Überlegungen beim Beitritt von Windows-Geräten zu Azure AD

Wenn das Windows-Gerät, das Sie Azure-AD beigetreten sind, zuvor einer Domäne beigetreten war oder sich in einer Arbeitsgruppe befand, sollten Sie die folgenden Einschränkungen in Frage stellen:
  
- Wenn ein Gerät Azure AD Beitritt, wird ein neuer Benutzer erstellt, ohne auf ein vorhandenes Profil zu verweisen. Profile müssen manuell migriert werden. Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen und Start Menü Einstellungen. Ein optimaler Ansatz besteht darin, ein Drittanbietertool zu finden, um vorhandene Dateien und Einstellungen dem neuen Profil zuzuordnen.

- Wenn das Gerät Gruppenrichtlinienobjekte (Group Policy Objects, GPO) verwendet, verfügen einige GPOs möglicherweise nicht über einen vergleichbaren [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in InTune. Führen Sie das [FMAT-Tool](https://www.microsoft.com/download/details.aspx?id=45520) aus, um vergleichbare Kryptografiedienstanbieter für vorhandene GPOs zu finden.

- Benutzer können sich nicht bei Anwendungen authentifizieren, die von der Active Directory-Authentifizierung abhängen. Bewerten Sie die Legacy-APP, und aktualisieren Sie diese in einer APP, die eine moderne Authentifizierung verwendet, wenn möglich.

- Active Directory Druckersuche funktioniert nicht. Sie können direkte Druckerpfade für alle Benutzer bereitstellen oder [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)verwenden.
