---
title: Microsoft verwalteter Desktop Technologien
description: In diesem Thema werden die Technologien und apps im Microsoft verwalteter Desktop verwendet.
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: da0268c6b0eddbd44cf62de2a95b963a443c3278
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867764"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft verwalteter Desktop Technologien

In diesem Thema werden die Technologien und apps im Microsoft verwalteter Desktop verwendet.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 E5-Lizenz (oder äquivalente Berechtigungen) ist erforderlich für Microsoft verwalteter Desktop-Dienst. Im folgenden werden alle Komponenten, die in diese Lizenz und wie Microsoft verwalteter Desktop jeder Komponente mit Microsoft verwalteter Desktop Geräte verwendet enthalten sind.  Bestimmte Funktionen und Aufgaben für jeden dieser Bereiche werden in der gesamten Microsoft verwalteter Desktop Themen ausführlich beschrieben. 

Microsoft 365 E5 3 Komponenten besteht: Office 365 E5, Windows 10 Enterprise und E5, Enterprise Mobilität + E5 Sicherheit.  

## <a name="office-365-e5"></a>Office 365 E5
 |
 --- | ---
Office 365 Standard Suite (64 Bit) * | Die standard-Office-Suite von Anwendungen werden mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype für Unternehmen, OneNote.<br><br>Klicken Sie zum Ausführen der 64-Bit (C2R) vollständige Versionen von Microsoft Project und Microsoft Visio sind nicht in der Office 365 Standard Suite enthalten.  Jedoch seit die Installation dieser Anwendung werden, hängt von der Standardinstallation von Office-Suite, hat Microsoft verwalteter Desktop erstellt Standard Intune Bereitstellungen und Sicherheitsgruppen, die der Kunde verwendet wird, um diese Programme bereitstellen Endbenutzer lizenziert.  
Store-Apps |    Microsoft Sway, Microsoft-Teams, Power BI-Desktop (nicht Pro) nicht mit dem Gerät geliefert wurde. Diese apps stehen zum Download von Microsoft Store.
Win32-Anwendung |    Power BI Pro, Azure Informationen Protection Client und Microsoft Planner sind nicht im Lieferumfang von Gerät und vom Kunden für die Bereitstellung gepackt werden können. 
Webanwendungen |  Yammer, Office Online, Delve, Flow StaffHub, PowerApps sind nicht im Lieferumfang des Geräts. Benutzer können die Webversion dieser Anwendungen mit einem Browser zugreifen.
Skype für Business Online Cloud Nebenstellenanlage | Dieses Feature ist über Office 365 E5 verfügbar. Microsoft verwalteter Desktop wird keinen Aspekt der dieser Dienst nicht konfiguriert werden.

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Anmeldeinformationen Guard |  Microsoft verwalteter Desktop wird Anleitungen und Verwalten von Cloud-Aspekte dieses Features
Gerät Guard (Windows Defender Anwendung Steuerelement)   | Microsoft verwalteten Desktops wird die Richtlinie zu erstellen. Kunden werden Signaturen verwalten.
AppLocker management |  Microsoft verwalteten Desktops wird die Richtlinie zu erstellen. Kunden werden Signaturen verwalten.
Application Virtualization (App-V) |    Microsoft verwalteter Desktop unterstützt diese Art der Bereitstellung nicht, wie es auf Intune nicht unterstützt wird.
Benutzer-Erlebnis Virtualisierung (UE-V) | Dies wird nicht mit Microsoft verwalteter Desktop verwalteten Geräten verwendet.
Verwaltete Benutzer  | Dies ist nicht mit Microsoft verwalteter Desktop verwalteten Geräten verwendet werden. MDM wird als Lösung für die Verwaltung von Geräten verwendet.
Windows Defender Advanced Threat Protection |   Dies wird von Microsoft verwalteten Desktops verwendet, zum Verwalten von Sicherheitsrichtlinien für Geräte. 

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security 

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Alle Aspekte der Enterprise-Mobilität + Sicherheit E3 und AADP können verwendet werden, um MDM-Geräte verwalten
Microsoft Cloud App Security |  Dies ist eine optionale Funktion, die Kunden mit dem Microsoft verwalteter Desktop-Dienst verwenden können.
Azure Informationen Protection P2  |Dies ist eine optionale Funktion, die Kunden mit dem Microsoft verwalteter Desktop-Dienst verwenden können.