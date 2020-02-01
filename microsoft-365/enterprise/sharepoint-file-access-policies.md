---
title: Empfohlene Richtlinien zum Schutz von Dokumenten – Microsoft 365 Enterprise | Microsoft-Dokumentation
description: Beschreibt die Richtlinien für Microsoft-Empfehlungen zum Schutz des Zugriffs auf SharePoint-Dateien.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: f0cd296157e1d4856c27d1dc547de045510e788b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600762"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Richtlinien Empfehlungen für das Sichern von SharePoint-Websites und-Dateien

In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien implementieren, um SharePoint Online und OneDrive für Unternehmen zu schützen. Dieser Leitfaden basiert auf den [allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md).

Diese Empfehlungen basieren auf drei verschiedenen Ebenen von Sicherheit und Schutz für SharePoint-Dateien, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: **Baseline**, **sensibel**und **streng reguliert**. Weitere Informationen zu diesen Sicherheitsebenen und zu den empfohlenen Clientbetriebssystemen, auf die diese Empfehlungen verweisen, finden Sie in [der Übersicht](microsoft-365-policies-configurations.md).

Zusätzlich zur Implementierung dieser Anleitung müssen Sie sicherstellen, dass Sie SharePoint-Websites mit der richtigen Schutz Menge konfigurieren, einschließlich der Festlegung geeigneter Berechtigungen für vertrauliche und stark regulierte Inhalte. Weitere Informationen zum Erstellen von Websites für den grundlegenden, vertraulichen und hoch regulierten Schutz finden Sie unter [Secure SharePoint Online Sites and Files](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aktualisieren allgemeiner Richtlinien, um SharePoint und OneDrive für Unternehmen einzubeziehen

Das folgende Diagramm veranschaulicht die empfohlenen Richtlinien für den Schutz von Dateien in SharePoint Online und OneDrive für Unternehmen. Es gibt an, welche Richtlinien aktualisiert oder neu erstellt werden sollen, um den Schutz für SharePoint Online und OneDrive für Unternehmen hinzuzufügen.

![Zusammenfassung der Richtlinien für SharePoint Online und OneDrive](../images/identity-access-ruleset-sharepoint.png)

Wenn Sie SharePoint Online beim Erstellen der allgemeinen Richtlinien einbezogen haben, müssen Sie nur die neuen Richtlinien erstellen. Beim Konfigurieren von Regeln für bedingten Zugriff enthält SharePoint Online OneDrive für Unternehmen.

Die neuen Richtlinien implementieren den Geräteschutz für vertrauliche und stark regulierte Inhalte, indem bestimmte Zugriffsanforderungen auf von Ihnen angegebene SharePoint-Websites angewendet werden.

In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder überprüfen und aktualisieren oder neu für SharePoint Online erstellen müssen. Die allgemeinen Richtlinien verweisen auf die zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md) .

|Schutzebene|Richtlinien|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint Online in die Zuweisung von Cloud-apps|
|        |[Sperrt Clients, die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Einbeziehen von SharePoint Online in die Zuweisung von Cloud-apps|
|        |[Definieren von App-Schutzrichtlinien](identity-access-policies.md#define-app-protection-policies)|Stellen Sie sicher, dass alle empfohlenen apps in der Liste der Apps enthalten sind. Achten Sie darauf, die Richtlinie für jede Plattform (Ios, Android, Windows) zu aktualisieren.|
|        |[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Einschließen von SharePoint Online in die Liste der Cloud-apps|
|        |[Verwenden von App-erzwungenen Einschränkungen in SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Fügen Sie diese neue Richtlinie hinzu. Dies weist Azure AD an, die in SharePoint Online angegebenen Einstellungen zu verwenden. Diese Regel gilt für alle Benutzer, wirkt sich jedoch nur auf den Zugriff auf Websites aus, die in SharePoint Online-Zugriffsrichtlinien enthalten sind.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelde Risiko *niedrig*, *Mittel* oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint Online in die Zuweisungen von Cloud-apps|
|         |[Erfordern von kompatiblen PCs *und* mobilen Geräten](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Einschließen von SharePoint Online in die Liste der Cloud-apps|
||[SharePoint Online Richtlinie für die Zugriffssteuerung](#sharepoint-online-access-control-policies): zulassen des reinen Browser Zugriffs auf bestimmte SharePoint-Websites von nicht verwalteten Geräten|Dadurch wird verhindert, dass Dateien bearbeitet und heruntergeladen werden. Verwenden von PowerShell zum Angeben von Websites|
|**Hochgradig reguliert**|[*Immer* MFA erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint Online in die Zuweisung von Cloud-apps|
||[SharePoint Online Richtlinie für die Zugriffssteuerung](#use-app-enforced-restrictions-in-sharepoint-online): Blockieren des Zugriffs auf bestimmte SharePoint-Websites von nicht verwalteten Geräten|Verwenden von PowerShell zum Angeben von Websites|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Verwenden von App-erzwungenen Einschränkungen in SharePoint Online

Wenn Sie Zugriffssteuerungen in SharePoint Online implementieren, müssen Sie diese Richtlinie für den bedingten Zugriff in Azure AD erstellen, um Azure AD zur Erzwingung der in SharePoint Online konfigurierten Richtlinien zu informieren. Diese Regel gilt für alle Benutzer, wirkt sich jedoch nur auf den Zugriff auf die Websites aus, die Sie mithilfe von PowerShell angeben, wenn Sie die Zugriffssteuerungen in SharePoint Online erstellen.

Informationen zum Konfigurieren dieser Richtlinie finden Sie unter "blockieren oder begrenzen des Zugriffs auf bestimmte SharePoint-Websitesammlungen oder OneDrive-Konten" in diesem Artikel: [Steuern des Zugriffs von nicht verwalteten Geräten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online von Zugriffssteuerungsrichtlinien

Microsoft empfiehlt, Inhalte auf SharePoint-Websites mit vertraulichen und streng reglementierten Inhalten mit Gerätezugriffs Steuerelementen zu schützen. Hierzu erstellen Sie eine Richtlinie, die den Schutzgrad und die Websites angibt, auf die der Schutz angewendet werden soll.

- Vertrauliche Websites: nur Browser Zugriff zulassen. Dadurch wird verhindert, dass Benutzer Dateien bearbeiten und herunterladen können.
- Stark regulierte Websites: Blockieren des Zugriffs von nicht verwalteten Geräten.

Weitere Informationen finden Sie unter "blockieren oder begrenzen des Zugriffs auf bestimmte SharePoint-Websitesammlungen oder OneDrive-Konten" in diesem Artikel: [Steuern des Zugriffs von nicht verwalteten Geräten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="how-these-policies-work-together"></a>Zusammenarbeit dieser Richtlinien

Es ist wichtig zu wissen, dass die Berechtigungen für SharePoint-Websites in der Regel auf geschäftlichen Anforderungen für den Zugriff auf Websites basieren. Diese Berechtigungen werden von Websitebesitzern verwaltet und können sehr dynamisch sein. Durch die Verwendung von SharePoint-Gerätezugriffs Richtlinien wird der Schutz für diese Websites sichergestellt, unabhängig davon, ob Benutzer einer Azure Ad Gruppe zugeordnet sind, die dem Basisplan, dem vertraulichen oder dem hoch regulierten Schutz unterliegt.

Die folgende Abbildung enthält ein Beispiel dafür, wie SharePoint-Gerätezugriffs Richtlinien den Zugriff auf Websites schützen.

![Schützen von Websites durch SharePoint-Gerätezugriffs Richtlinien](../images/SharePoint-rules-scenario.png)

In der Darstellung sehen Sie Folgendes:

- James ist den bedingten Zugriffsrichtlinien im Zusammenhang mit dem grundlegenden Schutz zugeordnet, kann jedoch Zugriff auf SharePoint-Websites erhalten, die mit einem sensiblen oder stark regulierten Schutz verbunden sind.
- Wenn James auf eine vertrauliche oder stark regulierte Website zugreift, die er bei der Verwendung seines PCs verwendet, wird sein Zugriff gewährt, solange sein PC konform ist.
- Wenn James auf eine vertrauliche Website zugreift, die er bei der Verwendung seines nicht verwalteten Telefons verwendet, das für Basisbenutzer zulässig ist, erhält er aufgrund der für diese Website konfigurierten Gerätezugriffs Richtlinie nur Browser Zugriff auf die vertrauliche Website.
- Wenn James auf eine stark regulierte Website zugreift, die er bei der Verwendung seines nicht verwalteten Telefons verwendet, wird er aufgrund der für diese Website konfigurierten Zugriffsrichtlinie blockiert. Er kann nur über seinen verwalteten und kompatiblen PC auf diese Website zugreifen.

## <a name="next-steps"></a>Nächste Schritte

[Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
