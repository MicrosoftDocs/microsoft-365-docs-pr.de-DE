---
title: Erweitern der erweiterten Suche mit den richtigen Einstellungen
description: Überprüfen Sie Überwachungseinstellungen auf Windows-Geräten und anderen Einstellungen, um sicherzustellen, dass Sie bei der erweiterten Suche die umfassendsten Daten erhalten.
keywords: Erweiterte Suche, Vorfall, Pivot, Entität, Überwachungseinstellungen, Benutzerkontenverwaltung, Sicherheitsgruppenverwaltung, Bedrohungssuche, Cyberbedrohungssuche, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929586"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Erweitern der erweiterten Suche mit den richtigen Einstellungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[Die erweiterte](advanced-hunting-overview.md) Suche basiert auf Daten aus verschiedenen Quellen, einschließlich Ihrer Geräte, Ihrer Office 365-Arbeitsbereiche, Azure AD und Microsoft Defender for Identity. Um möglichst umfassende Daten zu erhalten, stellen Sie sicher, dass sie über die richtigen Einstellungen in den entsprechenden Datenquellen verfügen.

## <a name="advanced-security-auditing-on-windows-devices"></a>Erweiterte Sicherheitsüberwachung auf Windows-Geräten
Aktivieren Sie diese erweiterten Überwachungseinstellungen, um sicherzustellen, dass Sie Daten zu Aktivitäten auf Ihren Geräten erhalten, z. B. lokale Kontoverwaltung, lokale Sicherheitsgruppenverwaltung und Diensterstellung.

| Daten | Beschreibung | Schematabelle | Konfigurieren |
| --- | --- | --- | --- |
| Kontoverwaltung | Ereignisse, die als verschiedene Werte `ActionType` erfasst werden, die lokale Kontoerstellung, Löschung und andere kontobezogene Aktivitäten angeben | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Benutzerkontenverwaltung überwachen](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Informationen zu erweiterten Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Sicherheitsgruppenverwaltung | Ereignisse, die als verschiedene Werte erfasst werden, `ActionType` die die Erstellung lokaler Sicherheitsgruppen und andere lokale Gruppenverwaltungsaktivitäten angeben | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Sicherheitsgruppenverwaltung überwachen](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Informationen zu erweiterten Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Dienstinstallation | Mit dem Wert erfasste `ActionType` `ServiceInstalled` Ereignisse, die angeben, dass ein Dienst erstellt wurde | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Sicherheitssystemerweiterung überwachen](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Informationen zu erweiterten Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender for Identity Sensor auf dem Domänencontroller
Wenn Sie Active Directory lokal ausführen, müssen Sie den Microsoft Defender for Identity-Sensor auf dem Domänencontroller installieren, um Daten für Microsoft Defender for Identity zu erhalten. Wenn diese Daten installiert und ordnungsgemäß konfiguriert sind, werden sie auch in die erweiterte Suche über Microsoft Defender for Identity eingesenist und bieten ein ganzheitliches Bild der Identitätsinformationen und -ereignisse in Ihrem Netzwerk. Diese Daten verbessern auch die Fähigkeit von Microsoft Defender for Identity, relevante Warnungen zu generieren, die auch von der erweiterten Suche abgedeckt werden. 

| Daten | Beschreibung | Schematabelle | Konfigurieren |
| --- | --- | --- | --- |
| Domänencontroller | Daten aus dem lokalen Active Directory, die an Microsoft Defender for Identity gesendet werden, erweitern identitätsbezogene Informationen wie Kontodetails, Anmeldeaktivitäten und Active Directory-Abfragen. | Mehrere Tabellen, einschließlich [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)und [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installieren des Microsoft Defender for Identity-Sensors](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Aktivieren relevanter Windows-Ereignisse](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
