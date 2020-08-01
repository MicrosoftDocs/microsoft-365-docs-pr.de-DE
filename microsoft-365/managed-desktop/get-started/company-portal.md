---
title: Installieren des InTune-Unternehmensportals auf Geräten
description: Informationen zum Installieren der Unternehmensportal-App auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Unternehmens Portal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 371656168f32db86ff32f187736d59dbd5dbe749
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529695"
---
# <a name="install-intune-company-portal-on-on-devices"></a>Installieren des Intune Company Portals auf Geräten

Microsoft Managed Desktop erfordert, dass IT-Administratoren das InTune-Unternehmens Portal für Ihre Benutzer mit Microsoft Managed Desktop-Geräten installieren. Hier finden Sie einige Vorteile für Ihre Organisation:
- Benutzer verfügen über eine Stelle zum Durchsuchen und Installieren verfügbarer Anwendungen. 
- IT-Administratoren können Anwendungen nach Kategorien für Ihre Benutzer organisieren.  
- Einige Anwendungen (wie Microsoft Project und Microsoft Visio) erfordern ein Unternehmens Portal für die Bereitstellung mit Microsoft Managed Desktop.
- IT-Administratoren können das Unternehmens Portal für Ihre Organisation anpassen. Dies umfasst Marken Bilder, das Hinzufügen von lokalen Support Kontakten und vieles mehr. Weitere Informationen finden Sie unter [Konfigurieren der Microsoft InTune-Unternehmens Portal-App](https://docs.microsoft.com/intune/company-portal-app).   

In diesem Thema wird der Prozess für die Bereitstellung des InTune-Unternehmensportals für Ihre Microsoft Managed Desktop-Benutzer dokumentiert. Der Gesamtprozess sieht wie folgt aus:
1. Erwerben des Unternehmensportals von Microsoft Store for Business und Synchronisieren mit InTune
2. Zuweisen eines Unternehmensportals zu Benutzern
3. Kommunizieren von Änderungen an Ihre Benutzer

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Schritt 1: Unternehmens Portal aus Microsoft Store for Business erwerben und mit InTune synchronisieren
Informationen zum Kauf der apps und zur Synchronisierung mit InTune finden Sie unter [Microsoft Store for Business-Apps](deploy-apps.md#msfb-apps) in *Deploy Apps to Microsoft Managed Desktop Devices*.

Dieses Thema enthält Informationen zu folgenden Themen: 
- Erwerben des Unternehmensportals von Microsoft Store for Business 
- Erzwingen der Synchronisierung zwischen InTune und Microsoft Store for Business
- Überprüfen der aktiven Synchronisierung zwischen InTune und Microsoft Store for Business 

## <a name="step-2---assign-company-portal-to-your-users"></a>Schritt 2: Zuweisen eines Unternehmensportals zu Benutzern
Übermitteln Sie eine Supportanfrage an Microsoft Managed Desktop Operations über das Verwaltungsportal von Microsoft Managed Desktop. Fordern Sie in der Supportanforderung an, dass das Unternehmens Portal Ihren Benutzern zugewiesen wird. Microsoft Managed Desktop stellt das Unternehmens Portal für Ihren Mandanten bereit und installiert die APP auf Microsoft Managed Desktop-Geräten in Ihrer Organisation.

Weitere Informationen zum Senden von Supportanforderungen mit Microsoft Managed Desktop finden Sie unter [Administrator Unterstützung für Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="step-3---communicate-change-to-your-users"></a>Schritt 3 – kommunizieren von Änderungen an Ihre Benutzer
Als IT-Administrator für Ihre Organisation ist es wichtig, dass Ihre Benutzer wissen, wie Sie das Unternehmens Portal in Ihrer Organisation verwenden können. Microsoft Managed Desktop empfiehlt Folgendes:
- Schritte zum Installieren von Anwendungen aus dem Unternehmens Portal. Weitere Informationen finden Sie unter [Installieren und Freigeben von apps auf Ihrem Gerät](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).
- Vorgehensweise Senden von Anforderungen an IT-Administratoren für Anwendungen, die derzeit nicht verfügbar sind. Weitere Informationen finden Sie unter [Anfordern einer APP für Arbeit oder Schule](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal](add-admin-contacts.md)
2. [Bedingten Zugriff anpassen](conditional-access.md)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. Bereitstellen des InTune-Unternehmensportals (in diesem Thema)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Bereitstellen von Apps](deploy-apps.md)
