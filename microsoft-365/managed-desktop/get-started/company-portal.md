---
title: Installieren des Intune-Unternehmensportals auf Geräten
description: Informationen zum Installieren der Unternehmensportal-App auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Unternehmensportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939284"
---
# <a name="install-intune-company-portal-on-devices"></a>Installieren des Intune-Unternehmensportals auf Geräten

Microsoft Managed Desktop erfordert, dass die IT-Administratoren das Intune-Unternehmensportal für ihre Benutzer mit Microsoft Managed Desktop-Geräten installieren. Hier sind einige Vorteile für Ihre Organisation:
- Benutzer haben einen Ort, um verfügbare Anwendungen zu durchsuchen und zu installieren. 
- IT-Administratoren können Anwendungen nach Kategorien für ihre Benutzer organisieren.  
- Für einige Anwendungen (z. B. Microsoft Project und Microsoft Visio) muss das Unternehmensportal mit Microsoft Managed Desktop bereitgestellt werden.
- IT-Administratoren können das Unternehmensportal für ihre Organisation anpassen. Dies umfasst die Markenbilderstellung, das Hinzufügen lokaler Supportkontakte und vieles mehr. Weitere Informationen finden Sie unter [Konfigurieren der Microsoft Intune-Unternehmensportal-App.](https://docs.microsoft.com/intune/company-portal-app)   

In diesem Thema wird der Prozess für die Bereitstellung des Intune-Unternehmensportals für Ihre Microsoft Managed Desktop-Benutzer dokumentiert. Der gesamte Prozess sieht wie hier aussieht:
1. Erwerben des Unternehmensportals aus dem Microsoft Store für Unternehmen und Synchronisieren mit Intune
2. Zuweisen des Unternehmensportals zu Ihren Benutzern
3. Kommunizieren von Änderungen an Ihre Benutzer

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Schritt 1: Erwerben des Unternehmensportals aus dem Microsoft Store für Unternehmen und Synchronisieren mit Intune
Informationen zum Kauf der Apps und zum Synchronisieren mit Intune finden Sie im [Microsoft Store für](deploy-apps.md#msfb-apps) Unternehmen unter "Bereitstellen von Apps auf Microsoft Managed *Desktop-Geräten".*

Dieses Thema enthält Informationen zu: 
- Erwerben des Unternehmensportals aus dem Microsoft Store für Unternehmen 
- Erzwingen der Synchronisierung zwischen Intune und dem Microsoft Store für Unternehmen
- Überprüfen der aktiven Synchronisierung zwischen Intune und dem Microsoft Store für Unternehmen 

## <a name="step-2---assign-company-portal-to-your-users"></a>Schritt 2: Zuweisen des Unternehmensportals zu Ihren Benutzern
Nach der Registrierung bei Microsoft Managed Desktop stellt Microsoft Managed Desktop Operations automatisch das Unternehmensportal für Ihren Mandanten zur Verfügung und installiert die App auf Microsoft Managed Desktop-Geräten in Ihrer Organisation.

## <a name="step-3---communicate-change-to-your-users"></a>Schritt 3: Kommunizieren von Änderungen an Die Benutzer
Als IT-Administrator für Ihre Organisation ist es wichtig, Ihren Benutzern die Verwendung des Unternehmensportals in Ihrer Organisation zu ermöglichen. Microsoft Managed Desktop empfiehlt Folgendes:
- Schritte zum Installieren von Anwendungen über das Unternehmensportal. Weitere Informationen finden Sie unter ["Installieren und Freigeben von Apps auf Ihrem Gerät".](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)
- Informationen zum Senden von Anforderungen an IT-Administratoren für Anwendungen, die derzeit nicht verfügbar sind. Weitere Informationen finden Sie unter [Anfordern einer App für Arbeit oder Schule.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte für die ersten Schritte mit Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal](add-admin-contacts.md)
2. [Bedingten Zugriff anpassen](conditional-access.md)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. Bereitstellen des Intune-Unternehmensportals (dieses Thema)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Bereitstellen von Apps](deploy-apps.md)
