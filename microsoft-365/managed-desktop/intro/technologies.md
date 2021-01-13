---
title: Microsoft Managed Desktop-Technologien
description: In diesem Artikel werden die Technologien und Apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840901"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-Technologien

In diesem Artikel werden die Technologien und Apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-Lizenzierung ist für alle Benutzer von Microsoft Managed Desktop erforderlich. Weitere Informationen zu den Lizenzierungsanforderungen für den Dienst finden Sie unter ["Voraussetzungen für Microsoft Managed Desktop".](../get-ready/prerequisites.md)

In diesem Artikel werden die Komponenten zusammengefasst, die in den erforderlichen Lizenzen für Unternehmen enthalten sind, sowie eine Beschreibung, wie der Dienst die einzelnen Komponenten mit Microsoft Managed Desktop-Geräten verwendet. Spezifische Rollen und Zuständigkeiten für jeden Bereich werden in der gesamten Microsoft Managed Desktop-Dokumentation ausführlich beschrieben. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 oder E5
 |
 --- | ---
Microsoft 365 Apps for Enterprise (64-Bit) | Diese Office-Anwendungen werden mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Die 64-Bit-Vollversionen von Microsoft Project und Microsoft Visio sind nicht enthalten. Da die Installation dieser Anwendungen jedoch von der Installation von Microsoft 365 Apps for Enterprise abhängt, hat Microsoft Managed Desktop standardmäßige Microsoft Intune-Bereitstellungen und Sicherheitsgruppen erstellt, die Sie dann verwenden können, um diese Anwendungen für lizenzierte Benutzer bereitzustellen. Weitere Informationen finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten.](../get-started/project-visio.md)
OneDrive |Azure Active #A0 ist für Benutzer aktiviert, wenn sie sich zum ersten Mal bei OneDrive anmelden.<br><br>Umleitung bekannter Ordner für die Ordner "Desktop", "Dokument" und "Bilder" ist enthalten; aktiviert und von Microsoft Managed Desktop konfiguriert.
Store-Apps |    Microsoft Sway und Power BI werden nicht im Lieferumfang des Geräts ausgeliefert. Diese Apps stehen im Microsoft Store zum Download zur Verfügung.
Win32-Anwendungen |    Teams ist nicht im Lieferumfang des Geräts enthalten, sondern wird von Microsoft für Microsoft Managed Desktop-Geräte gepackt und bereitgestellt. Azure Information Protection Client ist nicht im Lieferumfang des Geräts enthalten, Sie können ihn jedoch für die Bereitstellung packen.
Webanwendungen |  Yammer, Office in einem Browser, Delve, Flow, StaffHub, PowerApps und Planner werden nicht mit dem Gerät ausgeliefert. Benutzer können über einen Browser auf die Webversion dieser Anwendungen zugreifen.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 oder E3 mit Microsoft Defender for Endpoint

 |
 --- | ---
Application Virtualization (App-V) |    Kunden können App-V-Pakete mit dem Intune Win32-App-Verwaltungsclient bereitstellen.
Microsoft Defender für Endpunkt |    Microsoft Managed Desktop verwendet dieses Produkt, um die Gerätesicherheit zu überwachen. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Sie können alle Features von Enterprise Mobility + Security E3 und Azure Active Directory Premium P2 zum Verwalten von MDM-Geräten verwenden.
Microsoft Cloud App-Sicherheit |  Sie können dieses optionale Feature mit Microsoft Managed Desktop verwenden.
Azure Information Protection P2  | Sie können dieses optionale Feature mit Microsoft Managed Desktop verwenden.
