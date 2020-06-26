---
title: IdentityLogonEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu Authentifizierungsereignissen, die von Active Directory in der IdentityLogonEvents-Tabelle des Advanced Hunting-Schemas aufgezeichnet wurden
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, Identitäten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 17e12e9095219b7ad7923f7b5664946fff6ce724
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899375"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Gilt für:**
- Microsoft Threat Protection

Die `IdentityLogonEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Authentifizierungs Aktivitäten, die von Azure Active Directory und anderen Microsoft Cloud-apps und-Diensten aufgezeichnet wurden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. |
| `LogonType` | string | Typ der Anmeldesitzung, insbesondere:<br><br> - **Interaktiv** – der Benutzer interagiert physisch mit dem Computer mit der lokalen Tastatur und dem Bildschirm.<br><br> - **Remote Interactive (RDP)-Anmeldungen** -Benutzer interagiert mit dem Computer remote mithilfe von Remote Desktop, Terminal Dienste, Remoteunterstützung oder anderen RDP-Clients<br><br> - **Netzwerk** Sitzung, die beim Zugriff auf den Computer mit PsExec initiiert wurde oder bei dem auf freigegebene Ressourcen auf dem Computer (beispielsweise Drucker und freigegebene Ordner) zugegriffen wird<br><br> - Von geplanten Vorgängen initiierte **Batch** Sitzung<br><br> - Von Diensten initiierte **Dienst** Sitzung beim Start |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `Protocol` | string | Während der Kommunikation verwendete Protokolle |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure AD |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen. |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `DeviceType` | string | Gerätetyp |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. |
| `IPAddress` | string | Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet |
| `Location` | string | Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist |
| `Isp` | string | Internet Dienstanbieter (Internet Service Provider, ISP), der der IP-Endpunktadresse zugeordnet ist |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
