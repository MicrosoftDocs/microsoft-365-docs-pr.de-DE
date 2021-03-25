---
title: Erweitern der erweiterten Abdeckung der Suche mit den richtigen Einstellungen
description: Überprüfen der Überwachungseinstellungen auf Windows-Geräten und anderen Einstellungen, um sicherzustellen, dass Sie bei der erweiterten Suche die umfassendsten Daten erhalten
keywords: Erweiterte Suche, Vorfall, Pivot, Entität, Überwachungseinstellungen, Benutzerkontenverwaltung, Verwaltung von Sicherheitsgruppen, Bedrohungssuche, Cyberbedrohungensuche, Suche, Abfrage, Telemetrie, Mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: 60e8710415e328d06fac4c02e428094e5e4bcc92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067463"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Erweitern der erweiterten Abdeckung der Suche mit den richtigen Einstellungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[Die erweiterte Suche](advanced-hunting-overview.md) basiert auf Daten, die aus der gesamten Organisation kommen. Stellen Sie sicher, dass sie über die richtigen Einstellungen in den entsprechenden Datenquellen verfügen, um möglichst umfassende Daten zu erhalten.

## <a name="advanced-security-auditing-on-windows-devices"></a>Erweiterte Sicherheitsüberwachung auf Windows-Geräten

Aktivieren Sie diese erweiterten Überwachungseinstellungen, um sicherzustellen, dass Sie Daten zu Aktivitäten auf Ihren Geräten erhalten, z. B. lokale Kontoverwaltung, lokale Sicherheitsgruppenverwaltung und Diensterstellung.

Daten | Beschreibung | Schematabelle | Konfigurieren
-|-|-|-
Kontoverwaltung | Ereignisse, die als verschiedene Werte `ActionType` erfasst werden, die lokale Kontoerstellung, Löschung und andere kontobezogene Aktivitäten angeben | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Benutzerkontenverwaltung überwachen](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Verwaltung von Sicherheitsgruppen | Ereignisse, die als verschiedene Werte erfasst `ActionType` werden, die die Erstellung lokaler Sicherheitsgruppen und andere lokale Gruppenverwaltungsaktivitäten angeben | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Überwachung der Sicherheitsgruppenverwaltung](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Dienstinstallation | Ereignisse, die mit dem Wert `ActionType` erfasst `ServiceInstalled` werden und angeben, dass ein Dienst erstellt wurde | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
