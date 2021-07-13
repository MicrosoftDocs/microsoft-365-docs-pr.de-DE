---
title: Übersicht über die Verwendung von Basisplänen zum Bereitstellen von Standardmandantenkonfigurationen
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Informationen zur Verwendung von Basisplänen zum Bereitstellen von Standardmandantenkonfigurationen für verwaltete Dienstanbieter (Managed Service Providers, MSPs) mit Microsoft 365 Lighthouse.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409179"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>Übersicht über die Verwendung von Basisplänen zum Bereitstellen von Standardmandantenkonfigurationen 

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die [Anforderungen](m365-lighthouse-requirements.md)erfüllen. Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse Basispläne bieten eine wiederholbare und skalierbare Möglichkeit, Microsoft 365 Sicherheitseinstellungen über mehrere Mandanten hinweg zu bewerten und zu verwalten. Basispläne helfen auch bei der Überwachung der wichtigsten Sicherheitsrichtlinien und Mandantencompliancestandards mit Konfigurationen, die Benutzer, Geräte und Daten schützen.

Microsoft 365 Lighthouse soll Partnern dabei helfen, die Einführung von Sicherheit durch Kunden in ihrem eigenen Tempo zu ermöglichen. Microsoft 365 Lighthouse bietet einen Standardsatz von Basisparametern und vordefinierte Konfigurationen für Microsoft 365-Dienste. Diese Sicherheitskonfigurationen helfen bei der Messung der Microsoft 365 Sicherheits- und Compliance-Fortschritt Ihrer Mandanten.

Sie können die Standardbasislinie und die zugehörigen Bereitstellungsschritte in Microsoft 365 Lighthouse anzeigen. Wenn Sie Basispläne auf einen Mandanten anwenden möchten, wählen Sie im linken Navigationsbereich **Mandanten** aus, und wählen Sie dann einen Mandanten aus. Wechseln Sie als Nächstes zur Registerkarte **"Bereitstellungspläne",** und implementieren Sie den gewünschten Basisplan.

## <a name="standard-baseline-security-templates"></a>Standard-Basisplansicherheitsvorlagen

Microsoft 365 Lighthouse Standardbasiskonfigurationen für Sicherheitsworkloads sollen allen verwalteten Mandanten dabei helfen, einen akzeptablen Status der Sicherheitsabdeckung und Compliance zu erreichen.

Die Basislinienkonfigurationen in der folgenden Tabelle weisen standardmäßig die Microsoft 365 Lighthouse Standardbasislinie auf.<br><br>

| Basiskonfiguration | Beschreibung |
|--|--|
| MFA für Administratoren anfordern | Eine nur berichtsbasierte Richtlinie für bedingten Zugriff, die eine mehrstufige Authentifizierung für Administratoren erfordert. Sie ist für alle Cloudanwendungen erforderlich. |
| MFA für Endbenutzer anfordern | Eine berichtbasierte Richtlinie für bedingten Zugriff, die eine mehrstufige Authentifizierung für Benutzer erfordert. Sie ist für alle Cloudanwendungen erforderlich. |
| Blockieren von Legacy-Authentifizierung | Eine berichtbasierte Richtlinie für bedingten Zugriff zum Blockieren der älteren Clientauthentifizierung. |
| Registrieren von Geräten in Microsoft Endpoint Manager – Azure AD-Beitritt | Geräteregistrierung, damit sich Ihre Mandantengeräte bei Microsoft Endpoint Manager registrieren können. Dazu wird die automatische Registrierung zwischen Azure Active Directory und Microsoft Endpoint Manager eingerichtet. |
| Av-Richtlinienkonfiguration (Antivirus) | Ein Gerätekonfigurationsprofil für Windows Geräte mit vorkonfigurierten Microsoft Defender Antivirus Einstellungen. |
| Windows 10 Compliance-Richtlinie eingerichtet | Eine Windows Geräterichtlinie mit vorkonfigurierten Einstellungen, um grundlegende Complianceanforderungen zu erfüllen. |

## <a name="related-content"></a>Verwandte Inhalte

[Bereitstellen Microsoft 365 Lighthouse Baselines](m365-lighthouse-deploy-baselines.md) (Artikel)\
[faq zu Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (Artikel)
