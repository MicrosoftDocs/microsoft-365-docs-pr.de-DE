---
title: Erweitern der erweiterten Abdeckung der Suche mit den richtigen Einstellungen
description: Überprüfen der Überwachungseinstellungen auf Windows-Geräten und anderen Einstellungen, um sicherzustellen, dass Sie bei der erweiterten Suche die umfassendsten Daten erhalten
keywords: Erweiterte Suche, Vorfall, Pivot, Entität, Überwachungseinstellungen, Benutzerkontenverwaltung, Verwaltung von Sicherheitsgruppen, Bedrohungssuche, Suche nach Cyberbedrohungen, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1fc4635b71e68bb56fa7ec54c9c7b1263b83446b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498246"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Erweitern der erweiterten Abdeckung der Suche mit den richtigen Einstellungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[Die erweiterte](advanced-hunting-overview.md) Suche basiert auf Daten aus verschiedenen Quellen, einschließlich Ihrer Geräte, Ihrer Office 365-Arbeitsbereiche, Azure AD und Microsoft Defender for Identity. Stellen Sie sicher, dass sie über die richtigen Einstellungen in den entsprechenden Datenquellen verfügen, um möglichst umfassende Daten zu erhalten.

## <a name="advanced-security-auditing-on-windows-devices"></a>Erweiterte Sicherheitsüberwachung auf Windows-Geräten
Aktivieren Sie diese erweiterten Überwachungseinstellungen, um sicherzustellen, dass Sie Daten zu Aktivitäten auf Ihren Geräten erhalten, z. B. lokale Kontoverwaltung, lokale Sicherheitsgruppenverwaltung und Diensterstellung.

| Daten | Beschreibung | Schematabelle | Konfigurieren |
| --- | --- | --- | --- |
| Kontoverwaltung | Ereignisse, die als verschiedene Werte `ActionType` erfasst werden, die lokale Kontoerstellung, Löschung und andere kontobezogene Aktivitäten angeben | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Benutzerkontenverwaltung überwachen](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Verwaltung von Sicherheitsgruppen | Ereignisse, die als verschiedene Werte erfasst `ActionType` werden, die die Erstellung lokaler Sicherheitsgruppen und andere lokale Gruppenverwaltungsaktivitäten angeben | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Überwachung der Sicherheitsgruppenverwaltung](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Dienstinstallation | Ereignisse, die mit dem Wert `ActionType` erfasst `ServiceInstalled` werden und angeben, dass ein Dienst erstellt wurde | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Audit Security System Extension](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender for Identity-Sensor auf dem Domänencontroller
Wenn Sie Active Directory lokal ausführen, müssen Sie den Microsoft Defender for Identity-Sensor auf dem Domänencontroller installieren, um Daten für Microsoft Defender for Identity zu erhalten. Bei der Installation und ordnungsgemäßen Konfiguration werden diese Daten auch in die erweiterte Suche über Microsoft Defender for Identity einfährt und bieten ein ganzheitliches Bild von Identitätsinformationen und -ereignissen in Ihrem Netzwerk. Diese Daten verbessern außerdem die Fähigkeit von Microsoft Defender for Identity, relevante Warnungen zu generieren, die auch von der erweiterten Suche abgedeckt werden. 

| Daten | Beschreibung | Schematabelle | Konfigurieren |
| --- | --- | --- | --- |
| Domänencontroller | Daten aus lokalem Active Directory, die an Microsoft Defender for Identity gesendet werden, bereichern identitätsbezogene Informationen, z. B. Kontodetails, Anmeldeaktivitäten und Active Directory-Abfragen | Mehrere Tabellen, einschließlich [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)und [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installieren des Microsoft Defender for Identity-Sensors](/azure-advanced-threat-protection/install-atp-step4)<br>- [Aktivieren relevanter Windows-Ereignisse](/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)