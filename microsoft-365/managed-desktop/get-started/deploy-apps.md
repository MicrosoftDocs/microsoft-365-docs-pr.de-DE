---
title: Stellen Sie Anwendungen auf Geräten bereit
description: Informationen zum Hinzufügen und Bereitstellen von Apps auf Microsoft Managed Desktop-Geräten.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Apps, Branchen-Apps, Branchen-Apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922026"
---
# <a name="deploy-apps-to-devices"></a>Stellen Sie Anwendungen auf Geräten bereit
Ein Teil des Onboardings auf Microsoft Managed Desktop umfasst das Hinzufügen und Bereitstellen von Apps auf den Geräten Ihres Benutzers. Nachdem Sie das Microsoft Managed Desktop-Portal verwendet haben, können Sie Ihre Apps hinzufügen und bereitstellen. 

Der Gesamteindruck sieht wie dies aus:
1. [Hinzufügen von Apps zum Microsoft Managed Desktop-Portal](#1) – Dies kann vorhandene Branchen-Apps (Branchen-Apps) oder Apps aus dem Microsoft Store für Unternehmen sein, die Sie mit Intune synchronisiert haben. 
2. [Erstellen von Azure Active Directory (AD)-Gruppen für](#2) die App-Zuweisung – Sie verwenden diese Gruppen zum Verwalten der App-Zuweisung.
3. [Zuweisen von Apps zu Ihren Benutzern](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Schritt 1: Hinzufügen von Apps zum Microsoft Managed Desktop-Portal
Sie können [Win32- oder Windows MSI-basierte](#lob-apps)Apps oder [Microsoft Store for Business-Apps](#msfb-apps) zu Microsoft Managed Desktop hinzufügen und diese dann auf Microsoft Managed Desktop-Geräten bereitstellen.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32- oder Windows MSI-basierte Apps für Microsoft Managed Desktop

Sie können Ihre Branchen-Apps zum Microsoft Managed Desktop-Portal hinzufügen. Informationen zu den Anforderungen für Apps, die auf Microsoft Managed Desktop-Geräten installiert sind, finden Sie unter [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).

In diesem Verfahren wählen Sie aus, welche Art von App Sie hinzufügen möchten, und konfigurieren und laden die App-Quelle hoch. 

**So fügen Sie Ihre Branchen-App oder Windows-App zum Microsoft Managed Desktop-Portal hinzu**

Sie können sich beim Microsoft Managed Desktop-Portal anmelden oder sich bei Intune anmelden und dann nach Microsoft Managed Desktop suchen. Wir zeigen die Anmeldung beim Microsoft Managed Desktop-Portal. 

1.    Melden Sie sich beim [Microsoft Managed Desktop Admin-Portal an.](https://aka.ms/mmdportal) 
2.    Wählen **Sie unter Inventar** die Option **Apps aus.**
3.    Wählen Sie in der Arbeitsauslastung apps die Option **Hinzufügen aus.**
4.    Wählen **Sie in App** hinzufügen die Option Business-App oder **Windows-App** **(Win32) aus.**
    - Wenn Sie die **Line-of-Business-App** ausgewählt haben, finden Sie unter [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) Anweisungen zum Hinzufügen und Konfigurieren von Line-of-Business-Apps.
    - Wenn Sie **Die Windows-App (Win32)** ausgewählt haben, finden Sie unter [Win32-App-Verwaltung](/intune/apps-win32-app-management) Anweisungen zum Hinzufügen und Konfigurieren von Windows-Apps.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store für Business-Apps
Wenn Sie sich nicht beim Microsoft Store für Unternehmen angemeldet haben, können Sie sich registrieren, wenn Sie Apps kaufen. Nachdem Sie Ihre Apps installiert haben, können Sie sie mit Microsoft Managed Desktop synchronisieren. 

**So kaufen Sie Apps aus dem Microsoft Store für Unternehmen**

1. Melden Sie sich mit Ihrem [Microsoft Store](https://businessstore.microsoft.com) for Business Admin-Konto beim Microsoft Store für Unternehmen an.
2. Wählen **Sie Shop für meine Gruppe aus.**
3. Verwenden Sie Die Suche, um die gesuchte App zu finden, und wählen Sie die App aus.
4. Wählen Sie in den Produktdetails die Option **App erhalten aus.** Microsoft Store fügt die App zu **Ihren Produkten für** Ihre Organisation hinzu.

**So erzwingen Sie eine Synchronisierung zwischen Intune und Microsoft Store für Unternehmen**
1. Melden Sie sich beim [Microsoft Endpoint Manager Admin Center an.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Wählen **Sie Mandantenverwaltungsconnectors**  >  **und Token Microsoft** Store für Unternehmen  >  **aus.**
3. Wählen **Sie Synchronisieren** aus, um die Apps, die Sie aus dem Microsoft Store erworben haben, in Intune zu erhalten.

**So überprüfen Sie, ob eine Synchronisierung zwischen Intune und dem Microsoft Store für Unternehmen aktiv ist**
1. Melden Sie sich mit Ihrem [Microsoft Store](https://businessstore.microsoft.com) for Business Admin-Konto beim Microsoft Store für Unternehmen an.
2. Wählen Sie **Verwalten aus.**
3. Wählen **Sie Einstellungen** aus, und wählen Sie dann Verteilen **aus.**
4. Überprüfen **Sie unter Verwaltungstools,** ob Intune aufgeführt ist und ob der Status **Aktiv ist.**  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Schritt 2: Erstellen von Azure AD-Gruppen

Erstellen Sie drei Azure AD-Gruppen für jede App. In dieser Tabelle sind die benötigten Gruppen (Verfügbar, Erforderlich und Deinstallieren) aufgeführt. 

App-Zuweisungstyp |    Gruppennutzung    | Azure AD-Beispielname
--- | --- | ---
Available |  Die App ist über die App oder Website des Unternehmensportals verfügbar. | MMD – *App-Name* – Verfügbar
Erforderlich |  Die App wird auf Geräten in den ausgewählten Gruppen installiert. | MMD – *App-Name* – Erforderlich
Uninstall |  Die App wird von Geräten in den ausgewählten Gruppen deinstalliert. | MMD – *App-Name* – Deinstallieren

Fügen Sie Ihre Benutzer zu diesen Gruppen hinzu, um die App entweder verfügbar zu machen, die App zu installieren oder die App von ihrem Microsoft Managed Desktop-Gerät zu entfernen. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Schritt 3: Zuweisen von Apps zu Ihren Benutzern

**So weisen Sie die App Ihren Benutzern zu**

1. Melden Sie sich beim [Microsoft Managed Desktop Admin-Portal an.](https://aka.ms/mmdportal)
2. Wählen Sie im Bereich Verwalteter Desktop die Option **Apps aus.**
3. Wählen Sie in der Arbeitslast Apps die App aus, der Sie Benutzer zuweisen möchten, und wählen Sie **Benutzergruppen zuweisen aus.**
4. Wählen Sie für die spezifische App einen Zuweisungstyp (Verfügbar, Erforderlich, Deinstallieren) aus, und weisen Sie die entsprechende Gruppe zu.
5. Wählen Sie im Bereich Apps zuweisen die Option **OK aus.**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal](add-admin-contacts.md)
2. [Bedingten Zugriff anpassen](conditional-access.md)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Intune-Unternehmensportal bereitstellen](company-portal.md)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. Bereitstellen von Apps (in diesem Thema)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->