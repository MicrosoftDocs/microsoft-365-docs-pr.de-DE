---
title: Microsoft Managed Desktop-Technologien
description: In diesem Thema werden die Technologien und apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9c0e6481d0dc80e7cf03de2b748935c2f59f132a
ms.sourcegitcommit: e54ec86310a18101f4688890cd5a9fc16bbe6f55
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2019
ms.locfileid: "35257818"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-Technologien

In diesem Thema werden die Technologien und apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-Lizenzierung ist für alle Benutzer von Microsoft Managed Desktop erforderlich. Weitere Informationen zu den Lizenzierungsanforderungen für den Dienst finden Sie unter Prerequisites [for Microsoft Managed Desktop](../get-ready/prerequisites.md).

Im folgenden sind alle Komponenten aufgeführt, die in den erforderlichen Enterprise-Lizenzen enthalten sind und wie der Dienst jede Komponente mit Microsoft Managed Desktop-Geräten verwendet. Bestimmte Rollen und Zuständigkeiten für jeden Bereich werden während des Microsoft Managed Desktop-Themas detailliert beschrieben. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64bit) * | Die standardmäßige Office-Suite mit Anwendungen wird mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Die Vollversionen von Microsoft Project und Microsoft Visio von 64bit-Klick zum Ausführen (C2R) sind nicht in der Office 365 Standard Suite enthalten.  Da die Installation dieser Anwendungen jedoch von der standardmäßigen Office Suite-Installation abhängt, hat Microsoft Managed Desktop standardmäßige InTune-Bereitstellungen und Sicherheitsgruppen erstellt, die der Kunde zum Bereitstellen dieser Anwendungen verwenden wird, um lizenzierte Endbenutzer.  
Store-Apps |    Microsoft Sway, Power BI Desktop werden nicht mit dem Gerät ausgeliefert. Diese apps stehen im Microsoft Store zum Download bereit.
Win32-Anwendungen |    Power BI pro, Azure Information Protection-Client und Microsoft Planner werden nicht mit dem Gerät ausgeliefert und können für die Bereitstellung durch den Kunden verpackt werden. 
Webanwendungen |  Jammern, Office Online, vertiefen, Durchfluss, StaffHub, PowerApps werden nicht mit dem Gerät ausgeliefert. Benutzer können über einen Browser auf die Webversion dieser Anwendungen zugreifen.
Skype for Business Online Cloud-PBX | Dieses Feature steht über Office 365 zur Verfügung. Von Microsoft Managed Desktop werden keine Aspekte dieses Diensts konfiguriert.

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Schutz von Anmeldeinformationen |  Microsoft stellt Anleitungen bereit und verwaltet Cloud-Aspekte dieser Funktion.
Application Virtualization (App-V) |    Diese Art der Bereitstellung wird von Microsoft Managed Desktop nicht unterstützt, da Sie in InTune nicht unterstützt wird.
User Experience Virtualization (UE-V) | Dies wird nicht für verwaltete Microsoft Managed Desktop-Geräte verwendet.
Verwaltete Benutzeroberfläche  | Dies wird nicht für verwaltete Microsoft Managed Desktop-Geräte verwendet. MDM wird als Lösung für die Geräteverwaltung verwendet.
Windows Defender Advanced Threat Protection |   Dieser wird von Microsoft Managed Desktop zum Verwalten von Gerätesicherheitsrichtlinien verwendet. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Sicherheit E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Zur Verwaltung von MDM-Geräten können alle Aspekte der Enterprise Mobility + Security E3 und AADP verwendet werden.
Microsoft Cloud App Security |  Dies ist ein optionales Feature, das Kunden mit dem Microsoft Managed Desktop-Dienst verwenden können.
Azure Information Protection P2  |Dies ist ein optionales Feature, das Kunden mit dem Microsoft Managed Desktop-Dienst verwenden können.
