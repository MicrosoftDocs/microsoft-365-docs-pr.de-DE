---
title: Zugreifen auf lokale Ressourcen von einem azure AD-verbundenen Gerät in Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Erfahren Sie, wie Sie zugriff auf lokale Ressourcen wie Branchen-Apps, Dateifreigaben und Drucker von einem Azure Active Directory verbundenen Windows 10 Gerät erhalten.
ms.openlocfilehash: 71d60e0187c917dffb7390afcedf22dc73f44008
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393457"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Zugreifen auf lokale Ressourcen von einem Azure AD-verbundenen Gerät in Microsoft 365 Business Premium

Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.

Jedes Windows 10 Gerät, das Azure Active Directory beigetreten ist, hat Zugriff auf alle cloudbasierten Ressourcen, z. B. Ihre Microsoft 365-Apps, und kann durch Microsoft 365 Business Premium geschützt werden. Sie können auch den Zugriff auf lokale Ressourcen wie Branchen-Apps, Dateifreigaben und Drucker zulassen. Um den Zugriff zuzulassen, verwenden Sie [Azure AD Verbinden,](/azure/active-directory/connect/active-directory-aadconnect) um Ihr lokales Active Directory mit Azure Active Directory zu synchronisieren.

Weitere Informationen finden Sie unter ["Einführung in die Geräteverwaltung" in Azure Active Directory.](/azure/active-directory/device-management-introduction)
Die Schritte werden auch in den folgenden Abschnitten zusammengefasst.

## <a name="run-azure-ad-connect"></a>Ausführen von Azure AD-Verbinden

Führen Sie die folgenden Schritte aus, um den Azure AD-Geräten Ihrer Organisation den Zugriff auf lokale Ressourcen zu ermöglichen.

1. Um Ihre Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory in Azure Active Directory zu synchronisieren, führen Sie den Assistenten für die Verzeichnissynchronisierung und azure AD-Verbinden aus, wie unter Einrichten der [Verzeichnissynchronisierung für Office 365](../enterprise/set-up-directory-synchronization.md)beschrieben.

2. Stellen Sie nach Abschluss der Verzeichnissynchronisierung sicher, dass die Windows 10 Geräte Ihrer Organisation in Azure AD eingebunden sind. Dieser Schritt wird auf jedem Windows 10 Gerät einzeln ausgeführt. Weitere Informationen finden Sie unter ["Einrichten Windows Geräte für Microsoft 365 Business Premium Benutzer".](set-up-windows-devices.md)

3. Sobald die Windows 10 Geräte mit Azure AD verbunden sind, muss jeder Benutzer seine Geräte neu starten und sich mit seiner Microsoft 365 Business Premium Anmeldeinformationen anmelden. Alle Geräte haben jetzt auch Zugriff auf lokale Ressourcen.

Es sind keine zusätzlichen Schritte erforderlich, um Zugriff auf lokale Ressourcen für in Azure AD eingebundene Geräte zu erhalten. Diese Funktionalität ist in Windows 10 integriert.

Wenn Sie planen, sich beim AADJ-Gerät mit Ausnahme der Kennwortmethode wie PIN/Bio-Metrik über die WHFB-Anmeldeinformationen anzumelden und dann auf lokale Ressourcen (Freigaben, Drucker usw.) zuzugreifen, folgen Sie [diesem Artikel.](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)

Wenn Ihre Organisation nicht bereit ist, in der oben beschriebenen Azure AD-verbundenen Gerätekonfiguration bereitzustellen, sollten Sie die Einrichtung einer [in Azure AD eingebundenen Hybridgerätekonfiguration](manage-windows-devices.md)in Betracht ziehen.

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Überlegungen beim Verknüpfen Windows Geräten mit Azure AD

Wenn das Windows Gerät, dem Sie Azure-AD beigetreten sind, zuvor in die Domäne oder in eine Arbeitsgruppe eingebunden war, beachten Sie die folgenden Einschränkungen:

- Wenn ein Gerät mit Azure AD verknüpft wird, wird ein neuer Benutzer erstellt, ohne auf ein vorhandenes Profil zu verweisen. Profile müssen manuell migriert werden. Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen und Startmenü Einstellungen. Ein optimaler Ansatz besteht darin, ein Drittanbietertool zu finden, um vorhandene Dateien und Einstellungen dem neuen Profil zuzuordnen.

- Wenn das Gerät Gruppenrichtlinienobjekte (Group Policy Objects, GPO) verwendet, verfügen einige Gruppenrichtlinienobjekte möglicherweise nicht über einen vergleichbare [Konfigurationsdienstanbieter (Configuration Service Provider,](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) CSP) in Intune. Führen Sie das [MMAT-Tool](https://www.microsoft.com/download/details.aspx?id=45520) aus, um vergleichbare CSPs für vorhandene Gruppenrichtlinienobjekte zu finden.

- Benutzer können sich möglicherweise nicht bei Anwendungen authentifizieren, die von der Active Directory-Authentifizierung abhängig sind. Bewerten Sie die Legacy-App, und erwägen Sie nach Möglichkeit eine Aktualisierung auf eine App, die moderne Authentifizierung verwendet.

- Die Active Directory-Druckerermittlung funktioniert nicht. Sie können direkte Druckerpfade für alle Benutzer bereitstellen oder [universelles Drucken](/universal-print/)verwenden.

### <a name="related-articles"></a>Verwandte Artikel

[Voraussetzungen für Azure AD Verbinden](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
