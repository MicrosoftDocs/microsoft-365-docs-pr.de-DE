---
title: Microsoft Managed Desktop-Technologien
description: In diesem Thema werden die Technologien und apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9f3094b1a1272b0c200271b8d5703fe7173683a6
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171735"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-Technologien

In diesem Thema werden die Technologien und apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-Lizenzierung ist für alle Benutzer von Microsoft Managed Desktop erforderlich. Weitere Informationen zu den Lizenzierungsanforderungen für den Dienst finden Sie unter Prerequisites [for Microsoft Managed Desktop](../get-ready/prerequisites.md).

In diesem Thema werden die Komponenten der erforderlichen Enterprise-Lizenzen zusammengefasst, und es wird beschrieben, wie der Dienst jede Komponente mit Microsoft Managed Desktop-Geräten verwendet. Bestimmte Rollen und Verantwortlichkeiten für jeden Bereich werden in der Microsoft Managed Desktop-Dokumentation detailliert beschrieben. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64 Bit) | Die standardmäßige Office-Suite mit Anwendungen wird mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Die Vollversionen von Microsoft Project und Microsoft Visio von 64-Bit-Click-to-Run (C2R) sind nicht in Office 365 enthalten. Da die Installation dieser Anwendungen jedoch von der standardmäßigen Office Suite-Installation abhängt, hat Microsoft Managed Desktop standardmäßig Microsoft InTune-Bereitstellungen und Sicherheitsgruppen erstellt, die Sie dann zum Bereitstellen dieser Anwendungen verwenden können, um lizenzierte Endbenutzer. Weitere Informationen finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten](../get-started/project-visio.md)  
Store-Apps |    Microsoft Sway und Power BI werden nicht mit dem Gerät ausgeliefert. Diese apps stehen im Microsoft Store zum Download bereit.
Win32-Anwendungen |    Teams werden nicht mit dem Gerät ausgeliefert, sondern werden von Microsoft für von Microsoft verwaltete Desktop Geräte gepackt und bereitgestellt. Azure Information Protection-Client wird nicht mit dem Gerät ausgeliefert, aber Sie können dieses Paket für die Bereitstellung bereitstellen. 
Webanwendungen |  Jammern, Office in einem Browser, vertiefen, Durchfluss, StaffHub, PowerApps und Planer werden nicht mit dem Gerät ausgeliefert. Benutzer können über einen Browser auf die Webversion dieser Anwendungen zugreifen.


## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Application Virtualization (App-V) |    Diese Art der Bereitstellung wird von Microsoft Managed Desktop nicht unterstützt, da Sie von Microsoft InTune nicht unterstützt wird.
Erweiterter Bedrohungsschutz von Microsoft Defender |  Microsoft Managed Desktop verwendet diese, um die Gerätesicherheit zu überwachen. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Sicherheit E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Sie können alle Funktionen von Enterprise Mobility + Security E3 und Azure Active Directory Premium P2 zum Verwalten von MDM-Geräten verwenden.
Microsoft Cloud App Security |  Sie können diese optionale Funktion mit Microsoft Managed Desktop verwenden.
Azure Information Protection P2  | Sie können diese optionale Funktion mit Microsoft Managed Desktop verwenden.
