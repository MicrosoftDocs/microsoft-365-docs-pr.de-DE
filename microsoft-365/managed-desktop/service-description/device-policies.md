---
title: Gerätekonfiguration
description: Erfahren Sie mehr über die Standardrichtlinien, die auf Microsoft Managed Desktop-Geräte angewendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e4f07adb051dde24d374055d206955ad61df432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920492"
---
# <a name="device-configuration"></a>Gerätekonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wenn ein neues Microsoft Managed Desktop-Gerät eingerichtet wird, stellen wir sicher, dass es über die richtige Konfiguration verfügt, die für Microsoft Managed Desktop optimiert ist. Diese Konfiguration enthält eine Reihe von Standardrichtlinien, die im Rahmen des Onboardingprozesses festgelegt werden. Diese Richtlinien werden nach Möglichkeit mithilfe von Mobile Device Management (MDM) übermittelt. Weitere Informationen finden Sie unter [Mobile Device Management](/windows/client-management/mdm/). 

>[!NOTE]
>Ändern Sie diese Richtlinien nicht, um Konflikte zu vermeiden.

Geräte erhalten ein Signaturimage und treten dann bei der ersten Benutzerregistrierung der Azure Active Directory-Domäne bei. Das Gerät installiert die erforderlichen Richtlinien und Anwendungen automatisch, ohne dass Ihr IT-Personal eingreifen muss.

## <a name="default-policies"></a>Standardrichtlinien

In dieser Tabelle werden die Standardrichtlinien hervorgehoben, die während der Gerätebereitstellung auf alle Microsoft Managed Desktop-Geräte angewendet werden. Alle erkannten Änderungen, die nicht vom Microsoft Managed Desktop Operations Team an Objekten genehmigt wurden, die von Microsoft Managed Desktop verwaltet werden, werden wiederhergestellt.

Richtlinie | Beschreibung
--- | ---
Sicherheitsgrundlinie | [Die Microsoft-Sicherheitsgrundlinie](/windows/device-security/windows-security-baselines) für MDM ist für alle Microsoft Managed Desktop-Geräte konfiguriert. Diese Basislinie ist die Branchenstandardkonfiguration. Es ist öffentlich veröffentlicht, gut getestet und wurde von Microsoft-Sicherheitsexperten überprüft, um Microsoft Managed Desktop-Geräte und Apps am modernen Arbeitsplatz zu schützen. <br><br>Um Bedrohungen in der sich ständig weiterentwickelnden Sicherheitsrisikolandschaft zu mindern, wird die Microsoft-Sicherheitsgrundlinie mit jedem Windows 10-Featureupdate aktualisiert und auf Microsoft Managed Desktop-Geräten bereitgestellt.<br><br>Weitere Informationen finden Sie unter [Windows Security Baselines](/windows/security/threat-protection/windows-security-baselines).
Empfohlene Sicherheitsvorlage für Microsoft Managed Desktop | Eine Reihe empfohlener Änderungen an der Sicherheitsgrundlinie, die die Benutzerfreundlichkeit optimieren.  Diese Änderungen sind im Security [Addendum dokumentiert.](#security-addendum) Aktualisierungen des Richtlinien-Addendums erfolgen nach Bedarf.  
Aktualisieren der Bereitstellung | Verwenden Sie Windows Update for Business, um eine schrittweise Bereitstellung von Softwareupdates durchzuführen. IT-Administratoren können die Einstellungen für die Bereitstellungsgruppenrichtlinien nicht ändern. Weitere Informationen zur gruppenbasierten Bereitstellung finden Sie unter So werden Updates [in Microsoft Managed Desktop behandelt.](updates.md)
Gemessene Verbindungen | Standardmäßig sind Updates über gemessene Verbindungen (z. B. LTE-Netzwerke) deaktiviert, obwohl jeder Benutzer dieses Feature unabhängig unter Einstellungen > Updates > Erweiterte Optionen aktivieren **kann.** Wenn Sie allen Benutzern erlauben [möchten,](../working-with-managed-desktop/admin-support.md)Updates über gemessene Verbindungen zu aktivieren, senden Sie eine Änderungsanforderung, die diese Einstellung für alle Geräte aktiviert.
| Gerätekompatibilität | Diese Richtlinien sind für alle Microsoft Managed Desktop-Geräte konfiguriert. Ein Gerät wird als nicht kompatibel gemeldet, wenn es von unserer erforderlichen Sicherheitskonfiguration abdrift.

## <a name="windows-diagnostic-data"></a>Windows-Diagnosedaten

 Geräte werden so festgelegt, dass microsoft erweiterte Diagnosedaten unter einem bekannten kommerziellen Bezeichner zur Verfügung stellen. Als Teil von Microsoft Managed Desktop können IT-Administratoren diese Einstellungen nicht ändern. Für Kunden in Regionen der DSGVO (General Data Protection Regulation, DSGVO) können Benutzer die bereitgestellte Diagnosedatenstufe reduzieren, es wird jedoch zu einer Leistungsreduzierung kommen. Beispielsweise kann Microsoft Managed Desktop nicht die daten erfassen, die zum Iterieren von Einstellungen und Richtlinien erforderlich sind, um leistungs- und sicherheitsanforderungen optimal zu erfüllen. Weitere Informationen finden Sie unter [Configure Windows diagnostic data in your organization.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Sicherheits-Addendum

 In diesem Abschnitt werden die Richtlinien beschrieben, die zusätzlich zu den standardmäßigen Microsoft Managed Desktop-Richtlinien bereitgestellt werden, die unter [Standardrichtlinien aufgeführt sind.](#default-policies) Diese Konfiguration ist auf Finanzdienstleistungen und stark regulierte Branchen ausgelegt und optimiert für höchste Sicherheit bei gleichzeitiger Aufrechterhaltung der Benutzerproduktivität.

 ### <a name="additional-security-policies"></a>Zusätzliche Sicherheitsrichtlinien

 Diese Richtlinien werden hinzugefügt, um die Sicherheit für stark regulierte Branchen zu erhöhen. 
 - **Sicherheitsüberwachung:** Microsoft überwacht Geräte mithilfe [von Microsoft Defender for Endpoint](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Wenn eine Bedrohung erkannt wird, benachrichtigt Microsoft den Kunden, isoliert das Gerät und korrigiert das Problem remote. 
 - **PowerShell V2 deaktivieren:** Microsoft hat PowerShell V2 im August 2017 entfernt. Dieses Feature wurde auf allen Microsoft Managed Desktop-Geräten deaktiviert. Weitere Informationen zu dieser Änderung finden Sie [unter Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).