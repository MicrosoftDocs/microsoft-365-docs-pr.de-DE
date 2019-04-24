---
title: Microsoft Managed Desktop-Technologien
description: In diesem Thema werden die Technologien und apps aufgelistet, die in Microsoft Managed Desktop verwendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 843a8cd066bbaf87a8b2b7cc74d8817207e47153
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283467"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-Technologien

In diesem Thema werden die Technologien und apps aufgelistet, die in Microsoft Managed Desktop verwendet werden.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise Licensing ist für alle Microsoft Managed Desktop-Benutzer erforderlich. Weitere Informationen zu den Lizenzierungsanforderungen für den Dienst finden Sie unter [vorausSetzungen für Microsoft Managed Desktop](../get-ready/prerequisites.md).

Nachfolgend finden Sie alle Komponenten, die in den erforderlichen Enterprise-Lizenzen enthalten sind und wie der Dienst die einzelnen Komponenten mit Microsoft Managed Desktop-Geräten verwendet. Bestimmte Rollen und Verantwortlichkeiten für die einzelnen Bereiche werden im Thema Microsoft Managed Desktop ausführlich beschrieben. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64bit) * | Die standardmäßige Office-Suite von Anwendungen wird mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Die 64bit-Click to Run (C2R)-Vollversionen von Microsoft Project und Microsoft Visio sind nicht in der Office 365 Standard Suite enthalten.  Da die Installation dieser Anwendungen jedoch von der Standardinstallation der Office-Suite abhängt, hat Microsoft Managed Desktop standardmäßige InTune-Bereitstellungen und Sicherheitsgruppen erstellt, die der Kunde für die bereitstellungdieser Anwendungen verwendet. lizenzierte Endbenutzer.  
Store-Apps |    Microsoft Sway, Power BI Desktop werden nicht mit dem Gerät ausgeliefert. Diese Apps können im Microsoft Store heruntergeladen werden.
Win32-Anwendungen |    Power BI pro, Azure Information Protection-Client und Microsoft Planner werden nicht mit dem Gerät ausgeliefert und können für die Bereitstellung durch den Kunden verpackt werden. 
Webanwendungen |  Jammern, Office Online, untersuchen, Flow, StaffHub, PowerApps werden nicht mit dem Gerät ausgeliefert. Benutzer können mit einem Browser auf die Webversion dieser Anwendungen zugreifen.
Skype for Business Online Cloud-PBX | Diese Funktion ist über Office 365 verfügbar. Microsoft Managed Desktop konfiguriert keinen Aspekt dieses Diensts

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Schutz vor Anmeldeinformationen |  Microsoft bietet eine Orientierungs-und Cloud-Aspekte dieser Funktion.
Geräteschutz (Windows Defender-Anwendungssteuerung) | Microsoft Managed Desktop erstellt die Richtlinie. <br><br>Der Kunde verwaltet Signaturen.
AppLocker-Verwaltung |  Microsoft erstellt die Richtlinie. <br><br>Der Kunde verwaltet Signaturen.
Application Virtualization (App-V) |    Microsoft Managed Desktop unterstützt diese Art der Bereitstellung nicht, da Sie in InTune nicht unterstützt wird.
User Experience Virtualization (UE-V) | Dies wird nicht mit verwalteten verwalteten Desktop-Geräten von Microsoft verwendet.
Verwaltete Benutzeroberfläche  | Dies wird nicht mit verwalteten verwalteten Desktop-Geräten von Microsoft verwendet. MDM wird als Lösung für die Geräteverwaltung verwendet.
Windows Defender Advanced Threat Protection |   Diese wird von Microsoft Managed Desktop zum Verwalten von Gerätesicherheitsrichtlinien verwendet. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Alle Aspekte der Enterprise Mobility + Security E3 und AADP können zum Verwalten von MDM-Geräten verwendet werden.
Microsoft Cloud App Security |  Dies ist ein optionales Feature, das Kunden mit Microsoft Managed Desktop Service verwenden können.
Azure Information Protection P2  |Dies ist ein optionales Feature, das Kunden mit Microsoft Managed Desktop Service verwenden können.
