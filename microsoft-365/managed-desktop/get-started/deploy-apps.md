---
title: Bereitstellen von apps auf Geräten
description: Informationen zum Hinzufügen und Bereitstellen von apps auf Microsoft Managed Desktop-Geräten.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, apps, Branchenanwendungen, Lob-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5f1e2bd2440b5c38c958d3182684e87643f2e853
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012026"
---
# <a name="deploy-apps-to-devices"></a>Bereitstellen von apps auf Geräten
Ein Teil des onboardings für Microsoft Managed Desktop umfasst das Hinzufügen und Bereitstellen von apps auf den Geräten Ihrer Benutzer. Nachdem Sie das Microsoft Managed Desktop Portal verwendet haben, können Sie Ihre apps hinzufügen und bereitstellen. 

Der Gesamtprozess sieht wie folgt aus:
1. [Hinzufügen von apps zu Microsoft Managed Desktop Portal](#1) -Dies kann vorhandene Branchen-Apps oder Apps aus dem Microsoft Store for Business sein, die Sie mit InTune synchronisiert haben. 
2. [Erstellen von Azure Active Directory (AD)-Gruppen für die APP-Zuweisung](#2) -Sie verwenden diese Gruppen zum Verwalten der APP-Zuweisung.
3. [Zuweisen von apps zu Benutzern](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Schritt 1: Hinzufügen von apps zu Microsoft Managed Desktop Portal
Sie können [Win32-oder Windows MSI-basierte apps](#lob-apps)oder [Microsoft Store for Business-Apps](#msfb-apps) zu Microsoft Managed Desktop hinzufügen und diese dann auf Microsoft Managed Desktop-Geräten bereitstellen.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32-oder Windows MSI-basierte apps auf Microsoft Managed Desktop

Sie können Ihre Branchen-apps zu Microsoft Managed Desktop Portal hinzufügen. Informationen zu den Anforderungen für apps, die auf Microsoft Managed Desktop-Geräten installiert sind, finden Sie unter [Microsoft Managed Desktop App Requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

In diesem Verfahren wählen Sie aus, welche App-Art Sie hinzufügen möchten, und konfigurieren und laden dann die APP-Quelle. 

**So fügen Sie Ihre Branchen-APP oder Windows-APP zu einem Microsoft Managed Desktop-Portal hinzu**

Sie können sich bei Microsoft Managed Desktop Portal anmelden oder sich bei InTune anmelden und dann nach Microsoft Managed Desktop suchen. Wir zeigen, dass Sie sich bei Microsoft Managed Desktop Portal anmelden. 

1.  Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an. 
2.  Wählen Sie unter **Inventar**die Option **apps**aus.
3.  Wählen Sie in der Arbeitsauslastung von apps die Option **Hinzufügen**aus.
4.  Wählen Sie unter **app hinzufügen**die Option **Branchen-App** oder **Windows-app (Win32)** aus.
    - Wenn Sie die Branchen **-App**ausgewählt haben, finden Sie unter [Hinzufügen einer Windows-Branchen-APP zu Microsoft InTune](https://docs.microsoft.com/intune/lob-apps-windows) Anweisungen zum Hinzufügen und Konfigurieren von Branchen-apps.
    - Wenn Sie **Windows-app (Win32)** ausgewählt haben, finden Sie unter [Win32 App Management](https://docs.microsoft.com/intune/apps-win32-app-management) Anweisungen zum Hinzufügen und Konfigurieren von Windows-apps.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store for Business-Apps
Wenn Sie sich nicht bei Microsoft Store for Business angemeldet haben, können Sie sich anmelden, wenn Sie apps kaufen. Nachdem Sie Ihre apps haben, können Sie Sie mit dem Microsoft Managed Desktop synchronisieren. 

**So kaufen Sie Apps aus dem Microsoft Store for Business**

1. Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.
2. Wählen Sie **für meine Gruppe Shop**aus.
3. Verwenden Sie die Suche, um die gewünschte APP zu finden, und wählen Sie die APP aus.
4. Wählen Sie auf den Produkt Details **die Option App abrufen**aus. Microsoft Store fügt die APP den **Produkten #a0 Diensten** für Ihre Organisation hinzu.

**So erzwingen Sie eine Synchronisierung zwischen InTune und Microsoft Store for Business**
1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) als InTune-Administrator oder globaler Administrator für Ihren Mandanten an.
2. Wählen Sie **alle Dienste #a0 InTune**aus. InTune befindet sich im Abschnitt Überwachung + Verwaltung.
3. Wählen Sie im Bereich InTune die Option **Client apps**aus, und wählen Sie dann **Microsoft Store for Business**aus.
4. Wählen Sie **aktivieren** aus, um Ihren Microsoft Store for Business-Apps mit InTune zu synchronisieren.
    - Wenn Sie noch nicht angemeldet sind, registrieren und Ihr Microsoft Store for Business-Konto mit InTune verknüpfen
    - Wählen Sie die Sprache aus, in der Apps aus dem Microsoft Store for Business in ihrer InTune-Konsole angezeigt werden.
    - Wählen Sie **Sync** aus, um Ihren Microsoft Store for Business-Apps mit InTune zu synchronisieren.
    - Stellen Sie sicher, dass die Synchronisierung zwischen Microsoft Store for Business und InTune aktiv ist (nächster Schritt). 

**So stellen Sie sicher, dass eine Synchronisierung zwischen InTune und Microsoft Store for Business aktiv ist**
1. Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.
2. Wählen Sie **Manage**aus.
3. Wählen Sie **Einstellungen** aus, und wählen Sie dann **verteilen**aus.
4. Überprüfen Sie unter **Verwaltungstools**, ob InTune aufgeführt ist und ob der Status **aktiv**ist.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Schritt 2: Erstellen von Azure Ad Gruppen

Erstellen Sie für jede APP drei Azure Ad Gruppen. In dieser Tabelle werden die Gruppen beschrieben, die Sie benötigen (verfügbar, erforderlich und Uninstall). 

Zuordnungstyp "App" |   Gruppenverwendung   | Beispiel Azure Ad Name
--- | --- | ---
Available |  Die APP wird über die APP oder Website des Unternehmensportals verfügbar sein. | MMD – *App-Name* – verfügbar
Erforderlich |  Die APP wird auf Geräten in den ausgewählten Gruppen installiert. | MMD – *App-Name* – erforderlich
Uninstall |  Die APP wird auf den Geräten in den ausgewählten Gruppen deinstalliert. | MMD – *App-Name* – deinstallieren

Fügen Sie Ihre Benutzer zu diesen Gruppen hinzu, um entweder die app verfügbar zu machen, die APP zu installieren oder die APP von Ihrem von Microsoft verwalteten Desktop Gerät zu entfernen. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Schritt 3: Zuweisen von apps zu Benutzern

**So weisen Sie die APP Ihren Benutzern zu**

1. Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.
2. Wählen Sie im Bereich verwalteter Desktop die Option **apps**aus.
3. Wählen Sie in der Arbeitsauslastung Apps die APP aus, der Sie Benutzer zuweisen möchten, und wählen Sie **Benutzergruppen zuweisen**aus.
4. Wählen Sie für die jeweilige APP einen Zuordnungstyp (verfügbar, erforderlich, deinstallieren) aus, und weisen Sie die entsprechende Gruppe zu.
5. Wählen Sie im Bereich apps zuweisen die Option **OK**aus.


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator Kontakten im Administratorportal](add-admin-contacts.md)
2. [Anpassen des bedingten Zugriffs](conditional-access.md)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Bereitstellen des InTune-Unternehmensportals](company-portal.md)
5. [Aktivieren des Enterprise-Status-Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. Bereitstellen von apps (dieses Thema)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
