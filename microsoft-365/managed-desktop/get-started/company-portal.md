---
title: Installieren Intune-Unternehmensportal auf Geräten
description: Informationen zum Installieren der Unternehmensportal-App auf Microsoft Managed Desktop Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Unternehmensportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086685"
---
# <a name="install-intune-company-portal-on-devices"></a>Installieren Intune-Unternehmensportal auf Geräten

Microsoft Managed Desktop erfordert, dass IT-Administratoren Intune-Unternehmensportal Benutzer mit Microsoft Managed Desktop installieren. Hier sind einige Vorteile für Ihre Organisation:
- Benutzer haben eine einzige Stelle, um verfügbare Anwendungen zu durchsuchen und zu installieren. 
- IT-Administratoren können Anwendungen nach Kategorien für ihre Benutzer organisieren.  
- Einige Anwendungen (z. B. Microsoft Project und Microsoft Visio) erfordern Unternehmensportal bereitstellung mit Microsoft Managed Desktop.
- IT-Administratoren können Unternehmensportal für ihre Organisation anpassen. Dies umfasst die Markendarstellung, das Hinzufügen lokaler Supportkontakte und vieles mehr. Weitere Informationen finden Sie unter [Konfigurieren der Microsoft Intune Unternehmensportal App.](/intune/company-portal-app)   

In diesem Thema wird der Prozess für die Bereitstellung Intune-Unternehmensportal Benutzer Microsoft Managed Desktop dokumentiert. Der Gesamteindruck sieht wie dies aus:
1. Erwerben Unternehmensportal von Microsoft Store für Unternehmen und Synchronisierung mit Intune
2. Zuweisen Unternehmensportal Benutzern
3. Kommunizieren von Änderungen an Ihre Benutzer

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Schritt 1 – Erwerben Unternehmensportal von Microsoft Store für Unternehmen und Synchronisierung mit Intune
Informationen zum Kauf der Apps und zur Synchronisierung mit Intune finden Sie [unter Microsoft Store für Unternehmen apps](deploy-apps.md#msfb-apps) in Deploy apps to Microsoft Managed Desktop *devices*.

In diesem Thema finden Sie Informationen zu: 
- Erwerben Unternehmensportal von Microsoft Store für Unternehmen 
- Erzwingen der Synchronisierung zwischen Intune und Microsoft Store für Unternehmen
- Überprüfen der aktiven Synchronisierung zwischen Intune und Microsoft Store für Unternehmen 

## <a name="step-2---assign-company-portal-to-your-users"></a>Schritt 2 – Zuweisen Unternehmensportal Benutzern
Nach Der Registrierung in Microsoft Managed Desktop stellen wir automatisch Unternehmensportal Mandanten zur Verfügung und installieren die App auf Microsoft Managed Desktop In Ihrer Organisation.

## <a name="step-3---communicate-change-to-your-users"></a>Schritt 3 – Kommunizieren von Änderungen an Ihre Benutzer
Als IT-Administrator für Ihre Organisation ist es wichtig, Ihren Benutzern zu zeigen, wie sie Unternehmensportal in Ihrer Organisation verwenden. Microsoft Managed Desktop empfiehlt:
- Schritte zum Installieren von Anwendungen aus Unternehmensportal. Weitere Informationen finden Sie unter [Installieren und Freigeben von Apps auf Ihrem Gerät.](/intune-user-help/install-apps-cpapp-windows)
- Senden von Anforderungen an IT-Administratoren für Anwendungen, die derzeit nicht verfügbar sind. Weitere Informationen finden Sie unter [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal](add-admin-contacts.md)
2. [Bedingten Zugriff anpassen](conditional-access.md)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. Bereitstellen Intune-Unternehmensportal (dieses Thema)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Bereitstellen von Apps](deploy-apps.md)
