---
title: Empfohlene Richtlinien für sichere Dokumente – Microsoft 365 für Unternehmen | Microsoft-Dokumente
description: Beschreibt die Richtlinien für Microsoft-Empfehlungen zum Schutz des Zugriffs auf SharePoint-Dateien.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 7e8104e234bd1b724bc62fb1a9b401ab83a2bcb4
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357527"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Richtlinien Empfehlungen für das Sichern von SharePoint-Websites und-Dateien

In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien zum Schutz von SharePoint und OneDrive für Unternehmen implementieren. Dieser Leitfaden basiert auf den [allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md).

Diese Empfehlungen basieren auf drei verschiedenen Ebenen von Sicherheit und Schutz für SharePoint-Dateien, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: **Baseline**, **sensibel** und **streng reguliert**. Weitere Informationen zu diesen Sicherheitsebenen und zu den empfohlenen Clientbetriebssystemen, auf die diese Empfehlungen verweisen, finden Sie in [der Übersicht](microsoft-365-policies-configurations.md).

Zusätzlich zur Implementierung dieser Anleitung müssen Sie sicherstellen, dass Sie SharePoint-Websites mit der richtigen Schutz Menge konfigurieren, einschließlich der Festlegung geeigneter Berechtigungen für vertrauliche und stark regulierte Inhalte.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aktualisieren allgemeiner Richtlinien, um SharePoint und OneDrive für Unternehmen einzubeziehen

Zum Schutz von Dateien in SharePoint und OneDrive zeigt das folgende Diagramm, welche Richtlinien aus den allgemeinen Richtlinien für Identitäts-und Geräte Zugriff zu aktualisieren sind.

[![Zusammenfassung der Richtlinienaktualisierungen für den Schutz des Zugriffs auf Teams und deren abhängigen Dienste](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Wenn Sie SharePoint beim Erstellen der allgemeinen Richtlinien einbezogen haben, müssen Sie nur die neuen Richtlinien erstellen. Für Richtlinien für bedingten Zugriff umfasst SharePoint OneDrive.

Die neuen Richtlinien implementieren den Geräteschutz für vertrauliche und stark regulierte Inhalte, indem bestimmte Zugriffsanforderungen auf von Ihnen angegebene SharePoint-Websites angewendet werden.

In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder überprüfen und aktualisieren oder neu für SharePoint erstellen müssen. Die allgemeinen Richtlinien verweisen auf die zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md) .

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint in die Zuordnung von Cloud-apps.|
||[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Einbeziehen von SharePoint in die Zuordnung von Cloud-apps.|
||[Anwenden von App-Datenschutzrichtlinien](identity-access-policies.md#apply-app-data-protection-policies)|Stellen Sie sicher, dass alle empfohlenen apps in der Liste der Apps enthalten sind. Achten Sie darauf, die Richtlinie für jede Plattform (Ios, Android, Windows) zu aktualisieren.|
||[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Einbeziehen von SharePoint in die Liste der Cloud-apps.|
||[Verwenden von App-erzwungenen Einschränkungen in SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Fügen Sie diese neue Richtlinie hinzu. Dadurch wird Azure Active Directory (Azure AD) mitgeteilt, die in SharePoint angegebenen Einstellungen zu verwenden. Diese Richtlinie gilt für alle Benutzer, wirkt sich jedoch nur auf den Zugriff auf Websites aus, die in SharePoint-Zugriffsrichtlinien enthalten sind.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelde Risiko *niedrig*, *Mittel* oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint in die Zuweisungen von Cloud-apps.|
||[Erfordern von kompatiblen PCs *und* mobilen Geräten](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Schließen Sie SharePoint in die Liste der Cloud-apps ein.|
||[SharePoint-Zugriffssteuerungsrichtlinie](#sharepoint-access-control-policies): zulassen des reinen Browser Zugriffs auf bestimmte SharePoint-Websites von nicht verwalteten Geräten.|Dadurch wird verhindert, dass Dateien bearbeitet und heruntergeladen werden. Verwenden von PowerShell zum Angeben von Websites|
|**Streng geregelt**|[*Immer* MFA erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint in die Zuordnung von Cloud-apps.|
||[SharePoint-Zugriffssteuerungsrichtlinie](#use-app-enforced-restrictions-in-sharepoint): Blockieren des Zugriffs auf bestimmte SharePoint-Websites von nicht verwalteten Geräten.|Verwenden von PowerShell zum Angeben von Websites|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Verwenden von App-erzwungenen Einschränkungen in SharePoint

Wenn Sie Zugriffssteuerungen in SharePoint implementieren, müssen Sie diese Richtlinie für den bedingten Zugriff in Azure AD erstellen, um Azure AD zum Erzwingen der in SharePoint konfigurierten Richtlinien zu informieren. Diese Richtlinie gilt für alle Benutzer, wirkt sich jedoch nur auf den Zugriff auf die Websites aus, die Sie mithilfe von PowerShell angeben, wenn Sie die Zugriffssteuerungen in SharePoint erstellen.

Informationen zum Konfigurieren dieser Richtlinie finden Sie unter "blockieren oder begrenzen des Zugriffs auf bestimmte SharePoint-Websitesammlungen oder OneDrive-Konten" unter [Steuern des Zugriffs von nicht verwalteten Geräten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-access-control-policies"></a>SharePoint-Zugriffssteuerungsrichtlinien

Microsoft empfiehlt, Inhalte auf SharePoint-Websites mit vertraulichen und streng reglementierten Inhalten mit Gerätezugriffs Steuerelementen zu schützen. Hierzu erstellen Sie eine Richtlinie, die den Schutzgrad und die Websites angibt, auf die der Schutz angewendet werden soll.

- Vertrauliche Websites: nur Browser Zugriff zulassen. Dadurch wird verhindert, dass Benutzer Dateien bearbeiten und herunterladen können.
- Stark regulierte Websites: Blockieren des Zugriffs von nicht verwalteten Geräten.

Weitere Informationen finden Sie unter "blockieren oder begrenzen des Zugriffs auf bestimmte SharePoint-Websitesammlungen oder OneDrive-Konten" im [Steuerelement Zugriff von nicht verwalteten Geräten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Zusammenarbeit dieser Richtlinien

Es ist wichtig zu wissen, dass die Berechtigungen für SharePoint-Websites in der Regel auf geschäftlichen Anforderungen für den Zugriff auf Websites basieren. Diese Berechtigungen werden von Websitebesitzern verwaltet und können sehr dynamisch sein. Durch die Verwendung von SharePoint-Gerätezugriffs Richtlinien wird der Schutz für diese Websites sichergestellt, unabhängig davon, ob Benutzer einer Azure Ad Gruppe zugeordnet sind, die dem Basisplan, dem vertraulichen oder dem hoch regulierten Schutz unterliegt.

Die folgende Abbildung enthält ein Beispiel dafür, wie SharePoint-Gerätezugriffs Richtlinien den Zugriff auf Websites für einen Benutzer schützen.

[![Beispiel für den Schutz von Websites durch SharePoint-Gerätezugriffs Richtlinien](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James verfügt über grundlegende Richtlinien für bedingten Zugriff, aber ihm kann der Zugriff auf SharePoint-Websites mit vertraulichem oder stark reguliertem Schutz gewährt werden.

- Wenn James auf eine vertrauliche oder stark regulierte Website zugreift, die er bei der Verwendung seines PCs verwendet, wird sein Zugriff gewährt, solange sein PC konform ist.
- Wenn James auf eine vertrauliche Website zugreift, die er bei der Verwendung seines nicht verwalteten Telefons verwendet, das für Basisbenutzer zulässig ist, erhält er aufgrund der für diese Website konfigurierten Gerätezugriffs Richtlinie nur Browser Zugriff auf die vertrauliche Website.
- Wenn James auf eine stark regulierte Website zugreift, die er bei der Verwendung seines nicht verwalteten Telefons verwendet, wird er aufgrund der für diese Website konfigurierten Zugriffsrichtlinie blockiert. Er kann nur über seinen verwalteten und kompatiblen PC auf diese Website zugreifen.

## <a name="next-step"></a>Nächster Schritt

![Schritt 4: Richtlinien für Microsoft 365 Cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren von Richtlinien für bedingten Zugriff für:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
