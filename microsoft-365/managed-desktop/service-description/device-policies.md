---
title: Gerätekonfiguration
description: Erfahren Sie mehr über die Standardrichtlinien, die auf von Microsoft verwaltete Desktop Geräte angewendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 93c7cca75f513008706b4a52b4bbc1bc033341aa
ms.sourcegitcommit: 6cabf0226de1c95bff6ddb1852dac5ecdb2d6b96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "35830483"
---
# <a name="device-configuration"></a>Gerätekonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wenn ein neues Microsoft Managed Desktop-Gerät eingerichtet wird, stellen wir sicher, dass die richtige Konfiguration für Microsoft Managed Desktop optimiert wurde. Dies umfasst eine Reihe von Standardrichtlinien, die als Teil des Onboarding-Prozesses festgelegt werden. Um Konflikte zu vermeiden, sollten Sie diese Richtlinien nicht ändern. 

Geräte werden mit einem Signaturbild eingehen und dann der Azure Active Directory-Domäne beitreten, wenn sich der erste Benutzer anmeldet. Das Gerät installiert automatisch erforderliche Richtlinien und Anwendungen, ohne dass ein IT-Eingriff erforderlich ist.

## <a name="why-mdm-over-group-policy"></a>Warum MDM über Gruppenrichtlinien

Es gibt einige Gründe für die Verwendung der mobilen Geräteverwaltung (Mobile Device Management, MDM) anstelle von Gruppenrichtlinien:

- Sicherheits-MDM-Richtlinien sind sicherer. Gruppenrichtlinien sind für eine optimale Zusammenarbeit mit der lokalen Identität konzipiert, während MDM für die optimale Verwendung von Cloud Identity Management (Azure Active Directory) entwickelt wurde.
- Zuverlässigkeit-MDM-Richtlinien bieten eine zuverlässigere Richtlinienbereitstellung. Darüber hinaus überschreiben MDM-Einstellungen Gruppenrichtlinienobjekt-Richtlinien (GPO). Ab Windows 10, Version 1803, werden MDM-Einstellungen Vorrang vor den Gruppenrichtlinien Werten erhalten, wodurch Kunden in modernes Management wechseln. 
- Align with Microsoft Managed Desktop Weitblick-bietet umfassendere Überwachung der Richtlinienbereitstellung und unterstützt den gruppenbasierten Ansatz für eine schrittweise Einführung von Richtlinienänderungen mit der Möglichkeit, die Bereitstellung bei Bedarf anzuhalten/fortzusetzen.

Weitere Informationen finden Sie unter [Verwaltung mobiler Geräte](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Standardrichtlinien

In dieser Tabelle werden die Standardrichtlinien hervorgehoben, die während der Geräte Bereitstellung auf alle verwalteten Desktop Geräte von Microsoft angewendet werden. Alle erkannten Änderungen, die von Microsoft Managed Desktop Operations Team nicht für von Microsoft Managed Desktop verwaltete Objekte genehmigt wurden, werden zurückgesetzt.

Richtlinie | Beschreibung
--- | ---
Sicherheitsbasislinie | [Microsoft-Sicherheitsbasis](https://docs.microsoft.com/windows/device-security/windows-security-baselines) für MDM ist für alle von Microsoft verwalteten Desktop Geräte konfiguriert. Dieser Basisplan ist die Industriestandard Konfiguration. Es wird öffentlich veröffentlicht, gut getestet und von Microsoft-Sicherheitsexperten überprüft, um die Sicherheit von Microsoft-Desktop Geräten und-apps am modernen Arbeitsplatz zu gewährleisten. <br><br>Um Bedrohungen in der ständig wachsenden Sicherheits Bedrohungslandschaft zu verringern, wird die Microsoft-Sicherheitsbasislinie mit jeder Windows 10-Feature-Aktualisierung auf Microsoft Managed Desktop-Geräten aktualisiert und bereitgestellt.<br><br>Weitere Informationen finden Sie unter [Security Baseline for Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Empfohlene Sicherheitsvorlage für Microsoft Managed Desktop | Eine Reihe empfohlener Änderungen an der Sicherheitsbasislinie, die die Benutzerfreundlichkeit optimieren.  Diese Änderungen sind im [Sicherheits Nachtrag](#security-addendum)dokumentiert. Updates für den Richtlinien Nachtrag werden auf der Grundlage der erforderlichen Anforderungen ausgeführt.  
Update Bereitstellung | Verwenden Sie Windows Update für Unternehmen, um die schrittweise Bereitstellung von Softwareupdates durchzuführen. IT-Administratoren können Einstellungen für die Bereitstellungsgruppen Richtlinien nicht ändern. Weitere Informationen zur gruppenbasierten Bereitstellung finden Sie unter [How Updates are Handling](../working-with-managed-desktop/updates.md).
Diagnosedaten | Geräte werden so konfiguriert, dass Microsoft unter einer bekannten kommerziellen ID erweiterte Diagnosedaten bereitstellt. Als Teil von Microsoft Managed Desktop können IT-Administratoren diese Einstellungen nicht ändern. Für Kunden in dsgvo-Regionen (allgemeine Datenschutzverordnung) können Endbenutzer den Grad der bereitgestellten Diagnosedaten reduzieren, aber es wird eine Verringerung der Dienstleistung geben. Beispielsweise kann Microsoft Managed Desktop die erforderlichen Daten zum Durchlaufen von Einstellungen und Richtlinien nicht erfassen, um Leistungs-und Sicherheitsanforderungen optimal zu erfüllen. Weitere Informationen finden Sie unter [Konfigurieren von Windows-Diagnosedaten in Ihrer Organisation.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)
Gemessene Verbindungen | Standardmäßig sind Aktualisierungen über gemessene Verbindungen (wie LTE-Netzwerke) deaktiviert, obwohl jeder Benutzer dieses Feature in **Einstellungen #a0 Updates #a1 Erweiterte Optionen**unabhängig voneinander aktivieren kann. Wenn Sie zulassen möchten, dass alle Benutzer Aktualisierungen über gemessene Verbindungen aktivieren, [Senden Sie eine Änderungsanforderung](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/admin-support), die diese Einstellung für alle Geräte aktiviert.

 ## <a name="security-addendum"></a>Sicherheits Nachtrag

 In diesem Abschnitt werden die Richtlinien beschrieben, die zusätzlich zu den standardmäßigen Microsoft Managed Desktop-Richtlinien in [Standardrichtlinien](#default-policies)bereitgestellt werden. Diese Konfiguration ist für die Bereiche Finanzdienstleistungen und stark regulierte Branchen konzipiert, wobei die Optimierung für höchste Sicherheit bei gleichzeitiger Beibehaltung der Benutzerproduktivität erfolgt.

 ### <a name="additional-security-policies"></a>Zusätzliche Sicherheitsrichtlinien

 Diese Richtlinien werden hinzugefügt, um die Sicherheit für hochregulierte Branchen zu verbessern. 
 - **Sicherheitsüberwachung**: Microsoft überwacht die Geräte mit [Advanced Threat Protection von Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Wenn eine Bedrohung erkannt wird, wird Microsoft den Kunden Benachrichtigen, das Gerät isolieren und das Problem Remote beheben. 
 - **Deaktivieren von PowerShell v2**: Microsoft hat PowerShell v2 im August 2017 entfernt. Dieses Feature wurde auf allen Microsoft Managed Desktop-Geräten deaktiviert. Weitere Informationen zu dieser Änderung finden Sie unter [Windows PowerShell 2,0](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)-veraltete.
