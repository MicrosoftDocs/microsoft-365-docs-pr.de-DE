---
title: Voraussetzungen für Microsoft Managed Desktop
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.openlocfilehash: a7e82c0f4301b00e3d9e923dca10d1630744b8c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868071"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Voraussetzungen für Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Erfolg mit Microsoft verwalteter Desktop beginnt mit bekannten dokumentierte und vereinbarten Anforderungen für die Infrastruktur des Kunden. In diesem Abschnitt werden die erforderlichen Komponenten beschrieben. 

Microsoft FastTrack ist, damit Kunden diese Anforderungen erfüllen und helfen Ihnen bei der Vorbereitung zur Teilnahme an modernen Jahrestag als Dienst verfügbar. Weitere Informationen finden Sie unter [Microsoft schnelle](https://fasttrack.microsoft.com/about). 

Bereich | Erforderliche Informationen
--- | ---
Lizenzierung | Eine Microsoft 365 E5 Lizenz oder gleichwertige Lizenzen sind erforderlich.<br><br>Diese Lizenz beinhaltet Office 365 E5, Windows 10 Enterprise E5 & Enterprise Mobilität + E5 Sicherheit (zur Abstimmung). Weitere Informationen finden Sie unter [Microsoft-365-Lizenzierung](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Konnektivität |  Alle Microsoft verwalteter Desktop-Geräte müssen Connectivity zahlreiche Microsoft Dienstendpunkten aus dem internen Netzwerk Organisationseinheit, einschließlich:<br>-Windows Update<br>-Microsoft Speicher für Unternehmen<br>-Azure Active Directory<br>-Windows Fehlerberichterstattung<br>-Online-Absturzanalyse<br>-Benutzeroberfläche und Telemetrie verbunden<br>-OneDrive app für Windows 10<br><br>Die vollständige Liste der erforderlichen IP Adressen und URLs finden Sie unter [Proxy-Konfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (AD Azure) muss entweder der Autoritätsquelle für alle Benutzerkonten oder Benutzerkonten synchronisiert werden müssen, aus dem lokalen Active Directory mit Azure Active Directory verbinden, Version 1.1.654.0 oder höher. Weitere Informationen finden Sie unter [Azure Active Directory verbinden](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
Authentifizierung |    Wenn Azure AD nicht der Autoritätsquelle für ein Benutzerkonto ist, müssen Sie eine der folgenden in Azure AD-Connect konfigurieren:<br>-Kennwort Hash-Synchronisierung (empfohlen)<br>-Pass-Through Authentifizierung<br>-Verbund mit ADFS<br><br>Beim Festlegen von Authentifizierungsoptionen mit Azure Active Directory verbinden Kennwort Rückschreiben auch erforderlich ist. Weitere Informationen finden Sie unter [Kennwort Rückschreiben](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).<br><br>Weitere Informationen über Authentifizierungsoptionen mit Azure AD finden Sie unter [Azure AD-Connect - Anmeldung Benutzeroptionen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    Es wird dringend empfohlen, dass die folgenden Dienste in die Cloud migriert werden:<br>-E-Mail - Migration zu cloudbasierten Postfächer Exchange online oder mit Exchange Online Hybrid mit Exchange 2013 oder höher, lokalen konfiguriert werden.<br>-Dateien und Ordnern – Migrieren von SharePoint Online/Office 365.<br>-Skype for Business – Migrieren zu Skype für Unternehmen Online.<br>-Gerätemanagement - Microsoft Intune A Cloud-only MDM-Lösung (nicht-hybridbereitstellungen) ist erforderlich, wodurch die IT-Administratoren zum Verwalten von Microsoft verwalteter Desktop-Geräten, die über eine Webkonsole, die aus zugegriffen werden kann an einer beliebigen Stelle in der ganzen Welt. Microsoft Intune ist die erforderlichen MDM-Lösung.<br><br>Weitere Informationen finden Sie unter [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Daten sichern und Wiederherstellen | Microsoft verwalteter Desktop müssen Dateien zu OneDrive for Business synchronisiert werden, für den Schutz. Alle Dateien, die nicht zu OneDrive for Business synchronisiert werden von Microsoft verwaltet Desktop nicht garantiert und verloren während Gerät Austausch oder Supportanrufe erfordern Gerät zurückgesetzt. Microsoft verwalteter Desktop unterstützt zugeordneten Netzlaufwerke nicht.  

[Erfahren Sie, wie die erforderlichen Komponenten für die Registrierung von Microsoft verwalteten Desktops zu erfüllen.](../get-ready/index.md)

Wenn Sie die erste Schritte mit Microsoft verwalteter Desktop bereit sind, wenden Sie sich an Ihren Microsoft-Konto-Manager. 