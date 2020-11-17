---
title: Microsoft Managed Desktop-Technologien
description: In diesem Thema werden die Technologien und apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9ec6f73996b2626ef62d33435ed88fb08dfc1a16
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126579"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-Technologien

In diesem Thema werden die Technologien und apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-Lizenzierung ist für alle Benutzer von Microsoft Managed Desktop erforderlich. Weitere Informationen zu den Lizenzierungsanforderungen für den Dienst finden Sie unter [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).

In diesem Thema werden die Komponenten der erforderlichen Enterprise-Lizenzen zusammengefasst, und es wird beschrieben, wie der Dienst jede Komponente mit Microsoft Managed Desktop-Geräten verwendet. Bestimmte Rollen und Verantwortlichkeiten für jeden Bereich werden in der Microsoft Managed Desktop-Dokumentation detailliert beschrieben. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 oder E5
 |
 --- | ---
Microsoft 365-Apps für Unternehmen (64-Bit) | Diese Office-Anwendungen werden mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Die 64-Bit-Vollversionen von Microsoft Project und Microsoft Visio sind nicht enthalten. Da die Installation dieser Anwendungen jedoch von der Installation von Microsoft 365 apps for Enterprise abhängt, hat Microsoft Managed Desktop standardmäßig Microsoft InTune-Bereitstellungen und Sicherheitsgruppen erstellt, die Sie dann verwenden können, um diese Anwendungen für lizenzierte Benutzer bereitzustellen. Weitere Informationen finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten](../get-started/project-visio.md).
OneDrive |Azure Active Directory einmaliges Anmelden ist für Benutzer bei der ersten Anmeldung bei OneDrive aktiviert.<br><br>Die bekannte Ordnerumleitung für "Desktop"-, "Document"-und "Pictures"-Ordner ist enthalten; aktiviert und konfiguriert von Microsoft Managed Desktop.
Store-Apps |    Microsoft Sway und Power BI werden nicht mit dem Gerät ausgeliefert. Diese apps stehen im Microsoft Store zum Download bereit.
Win32-Anwendungen |    Teams werden nicht mit dem Gerät ausgeliefert, sondern werden von Microsoft für von Microsoft verwaltete Desktop Geräte gepackt und bereitgestellt. Azure Information Protection-Client wird nicht mit dem Gerät ausgeliefert, aber Sie können dieses Paket für die Bereitstellung bereitstellen.
Webanwendungen |  Jammern, Office in einem Browser, vertiefen, Durchfluss, StaffHub, PowerApps und Planer werden nicht mit dem Gerät ausgeliefert. Benutzer können über einen Browser auf die Webversion dieser Anwendungen zugreifen.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 oder E3 mit Microsoft Defender für Endpoint

 |
 --- | ---
Application Virtualization (App-V) |    Kunden können App-V-Pakete mithilfe des App-Verwaltungsclients für InTune Win32 bereitstellen.
Microsoft Defender für Endpunkt |    Microsoft Managed Desktop verwendet diese, um die Gerätesicherheit zu überwachen. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Sicherheit E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Sie können alle Funktionen von Enterprise Mobility + Security E3 und Azure Active Directory Premium P2 zum Verwalten von MDM-Geräten verwenden.
Microsoft Cloud App Security |  Sie können diese optionale Funktion mit Microsoft Managed Desktop verwenden.
Azure Information Protection P2  | Sie können diese optionale Funktion mit Microsoft Managed Desktop verwenden.
