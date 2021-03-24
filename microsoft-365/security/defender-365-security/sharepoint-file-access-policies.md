---
title: Empfohlene Richtlinien für sichere Dokumente – Microsoft 365 for Enterprise | Microsoft Docs
description: Beschreibt die Richtlinien für Microsoft-Empfehlungen zum Schutz des Zugriffs auf SharePoint-Dateien.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064471"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Richtlinienempfehlungen zum Schützen von SharePoint-Websites und -Dateien

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- SharePoint Online 


In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts- und Gerätezugriffsrichtlinien zum Schutz von SharePoint und OneDrive for Business implementieren. Diese Anleitung baut auf den [allgemeinen Identitäts- und Gerätezugriffsrichtlinien auf.](identity-access-policies.md)

Diese Empfehlungen basieren auf drei verschiedenen Sicherheits- und Schutzebenen für SharePoint-Dateien, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: **Basisplan** **,** vertraulich und streng **reguliert.** Weitere Informationen zu diesen Sicherheitsebenen und zu den empfohlenen Clientbetriebssystemen, auf die in diesen Empfehlungen verwiesen wird, finden Sie in [der Übersicht](microsoft-365-policies-configurations.md).

Stellen Sie neben der Implementierung dieser Anleitung sicher, dass Sie SharePoint-Websites mit dem richtigen Schutz konfigurieren, einschließlich der Festlegung geeigneter Berechtigungen für vertrauliche und stark regulierte Inhalte.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aktualisieren gängiger Richtlinien für SharePoint und OneDrive for Business

Zum Schutz von Dateien in SharePoint und OneDrive zeigt das folgende Diagramm, welche Richtlinien aus den allgemeinen Identitäts- und Gerätezugriffsrichtlinien aktualisiert werden.

[![Zusammenfassung der Richtlinienupdates zum Schutz des Zugriffs auf Teams und seine abhängigen Dienste](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Wenn Sie SharePoint bei der Erstellung der allgemeinen Richtlinien einbezogen haben, müssen Sie nur die neuen Richtlinien erstellen. Für Richtlinien für bedingten Zugriff enthält SharePoint OneDrive.

Die neuen Richtlinien implementieren den Geräteschutz für vertrauliche und stark regulierte Inhalte, indem bestimmte Zugriffsanforderungen auf von Ihnen festgelegte SharePoint-Websites angewendet werden.

In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder überprüfen und aktualisieren oder neue richtlinien für SharePoint erstellen müssen. Die allgemeinen Richtlinien verknüpfen mit den zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Identitäts- und Gerätezugriffsrichtlinien.](identity-access-policies.md)

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Fügen Sie SharePoint in die Zuweisung von Cloud-Apps ein.|
||[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Fügen Sie SharePoint in die Zuweisung von Cloud-Apps ein.|
||[Anwenden von APP-Datenschutzrichtlinien](identity-access-policies.md#apply-app-data-protection-policies)|Stellen Sie sicher, dass alle empfohlenen Apps in der Liste der Apps enthalten sind. Achten Sie darauf, die Richtlinie für jede Plattform (iOS, Android, Windows) zu aktualisieren.|
||[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Fügen Sie SharePoint in die Liste der Cloud-Apps ein.|
||[Verwenden erzwungener Einschränkungen für Apps in SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Fügen Sie diese neue Richtlinie hinzu. Dies weist Azure Active Directory (Azure AD) an, die in SharePoint angegebenen Einstellungen zu verwenden. Diese Richtlinie gilt für alle Benutzer, wirkt sich jedoch nur auf den Zugriff auf Websites aus, die in SharePoint-Zugriffsrichtlinien enthalten sind.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelderisiko *niedrig,* *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Fügen Sie SharePoint in die Zuweisungen von Cloud-Apps ein.|
||[Erfordern kompatibler PCs *und* mobiler Geräte](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Fügen Sie SharePoint in die Liste der Cloud-Apps ein.|
||[SharePoint-Zugriffssteuerungsrichtlinie:](#sharepoint-access-control-policies)Nur Browserzugriff auf bestimmte SharePoint-Websites von nicht verwalteten Geräten zulassen.|Dadurch wird das Bearbeiten und Herunterladen von Dateien verhindert. Verwenden Sie PowerShell, um Websites anzugeben.|
|**Streng geregelt**|[*MFA* immer erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Fügen Sie SharePoint in die Zuweisung von Cloud-Apps ein.|
||[SharePoint-Zugriffssteuerungsrichtlinie:](#use-app-enforced-restrictions-in-sharepoint)Blockieren des Zugriffs auf bestimmte SharePoint-Websites von nicht verwalteten Geräten.|Verwenden Sie PowerShell, um Websites anzugeben.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Verwenden von Einschränkungen, die von Apps erzwungen werden, in SharePoint

Wenn Sie Zugriffssteuerelemente in SharePoint implementieren, müssen Sie diese Richtlinie für bedingten Zugriff in Azure AD erstellen, damit Azure AD die richtlinien erzwingen kann, die Sie in SharePoint konfigurieren. Diese Richtlinie gilt für alle Benutzer, wirkt sich jedoch nur auf den Zugriff auf die Websites aus, die Sie mithilfe von PowerShell angeben, wenn Sie die Zugriffssteuerelemente in SharePoint erstellen.

Informationen zum Konfigurieren dieser Richtlinie finden Sie unter "Blockieren oder Einschränken des Zugriffs auf bestimmte SharePoint-Websitesammlungen oder #A0" unter Steuern des Zugriffs von [nicht verwalteten Geräten.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>Richtlinien für die SharePoint-Zugriffssteuerung

Microsoft empfiehlt, Inhalte auf SharePoint-Websites mit vertraulichen und streng regulierten Inhalten mit Gerätezugriffssteuerelementen zu schützen. Dazu erstellen Sie eine Richtlinie, die das Schutzniveau und die Websites angibt, auf die der Schutz angewendet werden soll.

- Vertrauliche Websites: Nur Browserzugriff zulassen. Dadurch wird verhindert, dass Benutzer Dateien bearbeiten und herunterladen.
- Streng regulierte Websites: Blockieren des Zugriffs von nicht verwalteten Geräten.

Weitere Informationen finden Sie unter "Blockieren oder Einschränken des Zugriffs auf bestimmte SharePoint-Websitesammlungen oder #A0" unter Steuern des Zugriffs von [nicht verwalteten Geräten](/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Funktionsweise dieser Richtlinien

Es ist wichtig zu wissen, dass SharePoint-Websiteberechtigungen in der Regel auf den geschäftlichen Notwendigkeiten für den Zugriff auf Websites basieren. Diese Berechtigungen werden von Websitebesitzern verwaltet und können sehr dynamisch sein. Die Verwendung von SharePoint-Gerätezugriffsrichtlinien stellt den Schutz dieser Websites sicher, unabhängig davon, ob Benutzer einer Azure AD-Gruppe zugewiesen sind, die dem Basisschutz, vertraulichen oder streng regulierten Schutz zugeordnet ist.

Die folgende Abbildung enthält ein Beispiel dafür, wie SharePoint-Gerätezugriffsrichtlinien den Zugriff auf Websites für einen Benutzer schützen.

[![Beispiel für den Schutz von Websites durch SharePoint-Gerätezugriffsrichtlinien](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Eine größere Version dieses Bilds sehen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James wurden grundlegende Richtlinien für bedingten Zugriff zugewiesen, aber er kann Zugriff auf SharePoint-Websites mit vertraulichem oder streng regulierten Schutz erhalten.

- Wenn James auf eine sensible oder stark regulierte Website zutritt, ist er Mitglied der Verwendung seines PCs, wird sein Zugriff gewährt, solange sein PC kompatibel ist.
- Wenn James auf eine vertrauliche Website zutritt, ist er Mitglied der Verwendung seines nicht verwalteten Telefons, was für Basisbenutzer zulässig ist, erhält er aufgrund der für diese Website konfigurierten Gerätezugriffsrichtlinie nur Browserzugriff auf die vertrauliche Website.
- Wenn James auf eine stark regulierte Website zutritt, ist er Mitglied der Verwendung seines nicht verwalteten Telefons, wird er aufgrund der für diese Website konfigurierten Zugriffsrichtlinie blockiert. Er kann nur über seinen verwalteten und kompatiblen PC auf diese Website zugreifen.

## <a name="next-step"></a>Nächster Schritt

![Schritt 4: Richtlinien für Microsoft 365-Cloud-Apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren von Richtlinien für bedingten Zugriff für:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)