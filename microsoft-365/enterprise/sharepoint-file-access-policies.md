---
title: Empfohlene Richtlinien zum Schutz von Dokumenten – Microsoft 365 Enterprise | Microsoft-Dokumentation
description: Beschreibt die Richtlinien für Microsoft-Empfehlungen zum Schutz des Zugriffs auf SharePoint-Dateien.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72dd50649dba9e290d50c2831557c06db3cb7586
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867844"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Richtlinie Empfehlungen zum Sichern von SharePoint-Websites und Dateien
In diesem Artikel wird die Implementierung der empfohlenen Identität und Gerätezugriffs Richtlinien zum Schutz von SharePoint Online und OneDrive für Unternehmen beschrieben. Diese Anleitung basiert auf [Allgemeine Identität und Gerät Richtlinien zugreifen](identity-access-policies.md). 

Diese Empfehlungen sind auf drei verschiedene Ebenen der Sicherheit und Schutz für SharePoint-Dateien, die angewendet werden kann auf die Granularität von Ihren Anforderungen basieren: **Baseline**, **empfindlich**und **hochgradig regulierter**. Erfahren Sie mehr über diese Sicherheitskategorien und die empfohlenen Clientbetriebssysteme, die durch diesen Empfehlungen in der [Übersicht über die](microsoft-365-policies-configurations.md).

Zusätzlich zu diese Anleitung unbedingt Konfigurieren von SharePoint-Websites mit dem richtigen Schutz, einschließlich der entsprechende Berechtigungen für Inhalte vertrauliche und hochgradig regulierter festlegen. Weitere Informationen zum Erstellen von Websites für die Baseline, empfindlich und hochgradig regulierter Schutz finden Sie unter [Secure SharePoint Online-Websites und Dateien](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files). 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aktualisieren allgemeine Richtlinien zum Einschließen von SharePoint- und OneDrive für Unternehmen
Das folgende Diagramm veranschaulicht den Satz von empfohlenen Richtlinien für den Schutz von Dateien in SharePoint Online und OneDrive für Unternehmen. Es gibt an, welche Richtlinien aktualisiert oder zum Schutz für SharePoint Online und OneDrive for Business hinzufügen neu erstellt werden.

![Zusammenfassung der Richtlinien für SharePoint Online und OneDrive](../images/identity-access-ruleset-sharepoint.png)

Wenn Sie SharePoint Online eingeschlossen, wenn Sie die allgemeinen Richtlinien erstellt haben, müssen Sie nur die neuen Richtlinien erstellen. Beim Konfigurieren von Zugriffsregeln bedingte enthält SharePoint Online OneDrive für Unternehmen.

Die neuen Richtlinien implementieren Geräteschutz für vertrauliche und hochgradig regulierter Inhalte durch Anwenden von bestimmten Access-Anforderungen auf SharePoint-Websites, die Sie angeben. 

Die folgende Tabelle enthält die Richtlinien, die Sie entweder benötigen, um zu überprüfen und aktualisieren oder Erstellen einer neuen für SharePoint Online. Die allgemeinen Richtlinien link auf die entsprechende konfigurationsanweisungen im Artikel [Allgemeine Zugriffsrichtlinien Identität und Gerät](identity-access-policies.md) .


|Schutzebene|Policies|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Baseline**|[Erfordern Sie mehrstufiger Authentifizierung das, bei der Anmeldung Risiko *Mittel* oder *Hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einschließen von SharePoint Online bei der Zuweisung von Cloud-apps|
|        |[Blockierung von Clients, die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Einschließen von SharePoint Online bei der Zuweisung von Cloud-apps|
|        |[Definieren von Richtlinien für die app-Schutz](identity-access-policies.md#define-app-protection-policies)|Achten Sie alle empfohlenen apps in der Liste apps enthalten sind. Achten Sie zum Aktualisieren der Richtlinie für jede Plattform (iOS, Android, Windows)|
|        |[Kompatible PCs erfordern](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Einschließen von SharePoint Online in der Liste der Cloud-apps|
|        |[Verwenden Sie die app erzwungen Einschränkungen in SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Fügen Sie diese neue Richtlinie hinzu. Dies weist Azure AD, verwenden Sie die Einstellungen in SharePoint Online angegeben. Diese Regel gilt für alle Benutzer, aber wirkt sich nur auf den Zugriff auf Websites in SharePoint Online-Richtlinien enthalten|
|**Vertraulich**|[Erfordern Sie mehrstufiger Authentifizierung das, bei der Anmeldung Risiko *Niedrig*, *Mittel* oder *Hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einschließen von SharePoint Online in die Zuordnungen von Cloud-apps|
|         |[Erfordern Sie kompatible PCs *und* mobile Geräten](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Einschließen von SharePoint Online in der Liste der Cloud-apps|
||[SharePoint Online-Steuerelement Zugriffsrichtlinie](#sharepoint-online-access-control-policies): Browser nur Zugriff auf bestimmte SharePoint-Websites von nicht verwalteten Geräten zulassen|Dies verhindert, dass bearbeiten und Herunterladen von Dateien. Geben Sie Websites mithilfe von PowerShell|
|**Streng geregelt**|[*Immer* erfordern mehrstufiger Authentifizierung das](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einschließen von SharePoint Online bei der Zuweisung von Cloud-apps|
||[SharePoint Online-Steuerelement Zugriffsrichtlinie](#use-app-enforced-restrictions-in-sharepoint-online): blockieren Sie den Zugriff auf bestimmte SharePoint-Websites aus einer nicht verwalteten Geräten|Geben Sie Websites mithilfe von PowerShell|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Verwenden Sie die app erzwungene Einschränkungen in SharePoint Online
Wenn Sie zugreifen auf Steuerelemente in SharePoint Online zu implementieren, müssen Sie diese Richtlinie bedingten Zugriff in Azure AD anzuweisen, Azure AD, die Richtlinien zu erzwingen, die Sie in SharePoint Online konfigurieren erstellen. Diese Regel gilt für alle Benutzer, aber wirkt sich nur auf Zugriff auf die Websites, die von die Ihnen von PowerShell angegebenen, wenn Sie die Access-Steuerelemente in SharePoint Online erstellen.

So konfigurieren Sie diese Richtlinie finden Sie unter "Sperren oder beschränken Zugriff auf bestimmte SharePoint-Websitesammlungen oder OneDrive Konten" in diesem Artikel: [Steuern des Zugriffs von nicht verwalteten Geräten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).


## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online Zugriffsrichtlinien
Microsoft empfiehlt, dass Sie Inhalte in SharePoint-Websites mit vertraulichen und hochgradig regulierter Inhalte mit Gerät zugreifen auf Steuerelemente zu schützen. Zu diesem Zweck erstellen eine Richtlinie, die Ebene der Schutz und die Websites, um den Schutz für anwenden angibt. 
- Vertrauliche Websites: nur ein Browser-Zugriff erlauben. Dies verhindert, dass Benutzer bearbeiten und Herunterladen von Dateien.
- Stark regulierter Websites: blockieren Sie den Zugriff von nicht verwalteten Geräten.

Finden Sie unter "Sperren oder beschränken Zugriff auf bestimmte SharePoint-Websitesammlungen oder OneDrive Konten" in diesem Artikel: [Steuern des Zugriffs von nicht verwalteten Geräten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622) . 

## <a name="how-these-policies-work-together"></a>Zusammenarbeit von dieser Richtlinien
Es ist wichtig zu verstehen, dass SharePoint-Websiteberechtigungen geschäftlicher Bedarf für den Zugriff auf Websites in der Regel basieren. Diese Berechtigungen werden vom Websitebesitzer verwaltet und dynamisch angepasst werden können. Verwendung von SharePoint-Gerät Zugriffsrichtlinien Schutz auf diese Standorte, unabhängig davon, ob Benutzer eine Azure Active Directory-Gruppe zugewiesen sind sicher mit Basisplan von Groß-und Kleinschreibung oder stark regulierter Schutz. 

Die folgende Abbildung enthält ein Beispiel, wie SharePoint Gerät Zugriffsrichtlinien Zugriff auf Websites schützen.

![Wie SharePoint Gerät Zugriffsrichtlinien Websites schützen](../images/SharePoint-rules-scenario.png)

In der Abbildung sehen Sie Folgendes:
- James bedingte Zugriffsrichtlinien Baseline-Schutz zugeordnet zugewiesen ist, aber er Zugriff gewährt werden kann auf SharePoint-Websites, die sensible oder stark regulierter Schutz zugeordnet. 
- Wenn James greift auf eine sensible oder stark regulierter-Website, die er mit seinem PC gehört, wird seine Zugriff gewährt, solange seinem PC kompatibel ist.
- Wenn James eine vertrauliche Website zugreift, die er Mitglied von seinem nicht verwalteten Telefon, was für geplante Benutzer zulässig ist ist, erhält er nur ein Browser-Zugriff auf die vertraulichen Website aufgrund der Gerät Zugriffsrichtlinie für diesen Standort konfiguriert. 
- James greift auf einer stark regulierten Website er mit seinem nicht verwalteten Telefon gehört, wird er aufgrund der Richtlinie für diesen Standort konfiguriert blockiert werden. Er kann nur auf dieser Website mithilfe von seinem verwalteten und kompatible PC zugreifen.


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a>Nächste Schritte
[Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
