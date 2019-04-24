---
title: Gerätekonfiguration
description: Informationen zu den Standardrichtlinien, die auf von Microsoft verwaltete Desktop Geräte angewendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a080c044939dfde223c231dfebdd248861d5f9f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278624"
---
# <a name="device-configuration"></a>Gerätekonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wenn ein neues Microsoft Managed Desktop-Gerät bereitgestellt wird, stellen wir sicher, dass die richtige Konfiguration, optimiert für Microsoft Managed Desktop, vorhanden ist. Dies umfasst eine Reihe von Standardrichtlinien, die als Teil des Onboarding-Prozesses festgelegt werden. Um Konflikte zu vermeiden, sollten diese Richtlinien nicht geändert werden. 

Geräte werden mit einem Signaturbild eingehen und dann der Azure Active Directory-Domäne beitreten, wenn sich der erste Benutzer anmeldet. Das Gerät installiert automatisch erforderliche Richtlinien und Anwendungen, ohne dass ein IT-Eingriff erforderlich ist.

## <a name="why-mdm-over-group-policy"></a>Warum MDM über Gruppenrichtlinien

Es gibt einige Gründe für die Verwendung der mobilen Geräteverwaltung (MDM) anstelle von Gruppenrichtlinien:

- Security-MDM-Richtlinien sind in der modernen Welt sicherer. Gruppenrichtlinien sind so konzipiert, dass Sie am besten mit der lokalen Identität arbeiten, während MDM für die Cloud Identity Management (Azure Active Directory) am besten geeignet ist.
- Zuverlässigkeit – MDM-Richtlinien bieten eine zuverlässigere Richtlinienbereitstellung. Darüber hinaus überschreiben MDM-Einstellungen Gruppenrichtlinienobjekt-Richtlinien. Beginnend mit Windows 10, Version 1803, werden die MDM-Einstellungen über die Gruppenrichtlinien Werte priorisiert, die Kunden, die auf modernes Management umstellen, unterstützen. 
- Align with Microsoft Managed Desktop-Weitblick – bietet eine umfassendere Überwachung der Richtlinienbereitstellung und unterstützt den gruppenbasierten Ansatz zur schrittweisen Einführung von Richtlinienänderungen mit der Möglichkeit, die Bereitstellung bei Bedarf anzuhalten/fortzusetzen.

Weitere Informationen finden Sie unter [Mobile Device Management](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Standardrichtlinien

In dieser Tabelle werden die Standardrichtlinien hervorgehoben, die während der Geräte Bereitstellung auf alle verwalteten Desktop Geräte von Microsoft angewendet werden. Alle erkannten Änderungen, die von Microsoft Managed Desktop Operations Team nicht an von Microsoft Managed Desktop verwaltete Objekte genehmigt wurden, werden zurückgesetzt.

Richtlinie | Beschreibung
--- | ---
Sicherheitsbasis | [Microsoft-Sicherheits Basisplan](https://docs.microsoft.com/windows/device-security/windows-security-baselines) für MDM ist für alle Microsoft Managed Desktop-Geräte konfiguriert. Diese Baseline ist die Standardkonfiguration. Es ist öffentlich veröffentlicht, gut getestet und wurde von Microsoft-Sicherheitsexperten überprüft, um die Sicherheit von Microsoft-Desktop Geräten und-apps am modernen Arbeitsplatz sicherzustellen. <br><br>Um Bedrohungen in der sich ständig weiter entwickelnden Sicherheits Bedrohungslandschaft zu verringern, wird die Microsoft-Sicherheitsbasislinie mit jedem Windows 10-Funktions Update auf Microsoft Managed Desktop-Geräten aktualisiert und bereitgestellt.<br><br>Weitere Informationen finden Sie unter [Sicherheits Basisplan für Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Empfohlene Sicherheitsvorlage für Microsoft Managed Desktop | Eine Reihe von empfohlenen Änderungen an der Sicherheitsbasislinie, die die Benutzerfreundlichkeit optimieren.  Diese Änderungen werden im [Sicherheits Nachtrag](#security-addendum)dokumentiert. Aktualisierungen des Richtlinien Nachweises erfolgen auf Bedarfsbasis.  
Geräte Konformität | Diese Richtlinien werden standardmäßig für alle verwalteten Microsoft-Desktop Geräte konfiguriert. Ein Gerät wird als nicht kompatibel gemeldet, wenn eine der folgenden Sicherheitsbedingungen nicht erfüllt ist:<br>-BitLocker-Geräteverschlüsselung aktiviert, um Daten auf Geräten zu schützen. Weitere Informationen finden Sie unter [Übersicht über die BitLocker-Geräteverschlüsselung in Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Secure Boot aktiviert und erzwungen, um die Firmware-Images auf Geräten zu überprüfen, bevor Sie ausgeführt werden können. Weitere Informationen finden Sie unter [Secure Boot and Device Encryption Overview.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Microsoft Managed Desktop Device erfordert ein Kennwort für die Anmeldung.
Update-Bereitstellung | Verwenden Sie Windows Update for Business (WUfB), um die schrittweise Bereitstellung von Softwareupdates durchzuführen. IT-Administratoren können keine Einstellungen für die Bereitstellungsgruppen Richtlinien ändern. Weitere Informationen zur gruppenbasierten Bereitstellung finden Sie unter [wie Updates behandelt werden](../working-with-managed-desktop/updates.md).
Diagnosedaten | Geräte werden so festgelegt, dass Microsoft unter einer bekannten kommerziellen ID erweiterte Diagnosedaten bereitgestellt werden. Als Teil von Microsoft Managed Desktop können IT-Administratoren diese Einstellungen nicht ändern. Für Kunden in allgemeinen Datenschutzbestimmungen (DSGVO) können Endbenutzer den Grad der bereitgestellten Diagnosedaten reduzieren, es wird jedoch eine Reduzierung des Diensts geben. Microsoft Managed Desktop kann beispielsweise nicht die erforderlichen Daten sammeln, um Einstellungen und Richtlinien zu durchlaufen, um die Leistungs-und Sicherheitsanforderungen am besten zu erfüllen. Weitere Informationen finden Sie unter [Konfigurieren von Windows-Diagnosedaten in Ihrer Organisation.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>Sicherheits Nachtrag

 In diesem Abschnitt werden die Richtlinien erläutert, die zusätzlich zu den Standardrichtlinien für Microsoft Managed Desktops bereitgestellt werden. Standardrichtlinien sind in [Standardrichtlinien](#default-policies)aufgeführt. Diese Konfiguration ist für Finanzdienstleister und hochregulierte Branchen konzipiert: Optimierung für die sicherste Position bei gleichzeitiger Beibehaltung der Benutzerproduktivität.

 ### <a name="additional-security-policies"></a>Zusätzliche Sicherheitsrichtlinien

 Diese Richtlinien werden hinzugefügt, um die Sicherheit für hochregulierte Branchen zu verbessern. 
 - **App-Zulassungsliste**: apps müssen von der Organisation als vertrauenswürdig eingestuft werden, wenn Sie auf verwalteten Desktop Geräten von Microsoft ausgeführt werden. Dadurch wird eine gesperrte Umgebung bereitgestellt. Alle apps, die onboarded werden müssen, müssen dem Microsoft Managed Desktop Operations-Team mitgeteilt werden. Weitere Informationen finden Sie unter [Windows Defender Device Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Sicherheitsüberwachung**: Microsoft überwacht Geräte mithilfe von [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Wenn eine Bedrohung erkannt wird, wird der Kunde von Microsoft benachrichtigt, das Gerät isolieren und das Problem Remote beheben. 

