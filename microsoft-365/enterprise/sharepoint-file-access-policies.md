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
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: dde6da008f9a7b6457c9ed4a01d88a8ab284511d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290733"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Richtlinien Empfehlungen zum Sichern von SharePoint-Websites und-Dateien
In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien implementieren, um SharePoint Online und OneDrive for Business zu schützen. Dieser Leitfadens basiert auf den allgemeinen [Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md). 

Diese Empfehlungen basieren auf drei verschiedenen Sicherheits-und Schutzebenen für SharePoint-Dateien, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: **Basisrichtlinie**, **vertraulich**und **stark reguliert**. Weitere Informationen zu diesen Sicherheitsebenen und den empfohlenen Clientbetriebssystemen, auf die durch diese Empfehlungen verwiesen wird, finden Sie in der [Übersicht](microsoft-365-policies-configurations.md).

Stellen Sie neben der Implementierung dieser Richtlinien sicher, dass Sie SharePoint-Websites mit der richtigen Menge an Schutz konfigurieren, einschließlich der Einstellung der entsprechenden Berechtigungen für vertrauliche und hochregulierte Inhalte. Weitere Informationen zum Erstellen von Websites für grundlegende, vertrauliche und hochgradig geregelte Schutzfunktionen finden Sie unter [Secure SharePoint Online Sites and Files](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files). 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aktualisieren gängiger Richtlinien für SharePoint und OneDrive for Business
Das folgende Diagramm veranschaulicht die empfohlenen Richtlinien für den Schutz von Dateien in SharePoint Online und OneDrive for Business. Er gibt an, welche Richtlinien aktualisiert oder neu erstellt werden sollen, um Schutz für SharePoint Online und OneDrive for Business hinzuzufügen.

![Zusammenfassung der Richtlinien für SharePoint Online und OneDrive](../images/identity-access-ruleset-sharepoint.png)

Wenn Sie SharePoint Online bei der Erstellung der allgemeinen Richtlinien hinzugefügt haben, müssen Sie nur die neuen Richtlinien erstellen. Beim Konfigurieren von Regeln für den bedingten Zugriff umfasst SharePoint Online OneDrive for Business.

Die neuen Richtlinien implementieren Geräteschutz für vertrauliche und hochgradig regulierte Inhalte, indem bestimmte Zugriffsanforderungen auf von Ihnen angegebene SharePoint-Websites angewendet werden. 

In der folgenden Tabelle werden die Richtlinien aufgeführt, die Sie für SharePoint Online entweder überarbeiten und aktualisieren oder neu erstellen müssen. Die allgemeinen Richtlinien verweisen auf die zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md) .


|Schutzebene|Richtlinien|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA erfordern, wenn das Anmelde Risiko *Mittel* oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint Online in die Zuweisung von Cloud-apps|
|        |[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Einbeziehen von SharePoint Online in die Zuweisung von Cloud-apps|
|        |[Definieren von App-Schutzrichtlinien](identity-access-policies.md#define-app-protection-policies)|Stellen Sie sicher, dass alle empfohlenen apps in der Liste der Apps enthalten sind. Achten Sie darauf, die Richtlinie für jede Plattform zu aktualisieren (iOS, Android, Windows)|
|        |[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Einbeziehen von SharePoint Online in die Liste der Cloud-apps|
|        |[Verwenden von erzwungenen App-Einschränkungen in SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Fügen Sie diese neue Richtlinie hinzu. Dies weist Azure AD an, die in SharePoint Online angegebenen Einstellungen zu verwenden. Diese Regel gilt für alle Benutzer, aber betrifft nur den Zugriff auf Websites, die in SharePoint Online-Zugriffsrichtlinien enthalten sind.|
|**Vertraulich**|[MFA erfordern, wenn das Anmelde Risiko *niedrig*, *Mittel* oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint Online in die Zuweisungen von Cloud-apps|
|         |[Erfordern kompatibler PCs *und* mobiler Geräte](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Einbeziehen von SharePoint Online in die Liste der Cloud-apps|
||[Richtlinie für die SharePoint Online-Zugriffssteuerung](#sharepoint-online-access-control-policies): zulassen des Zugriffs auf bestimmte SharePoint-Websites auf nicht verwaltete Geräte durch den Browser|Dies verhindert das Bearbeiten und Herunterladen von Dateien. Verwenden von PowerShell zum Angeben von Websites|
|**Streng geregelt**|[*Immer* MFA erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von SharePoint Online in die Zuweisung von Cloud-apps|
||[Richtlinie für die SharePoint Online-Zugriffssteuerung](#use-app-enforced-restrictions-in-sharepoint-online): Blockieren des Zugriffs auf bestimmte SharePoint-Websites von nicht verwalteten Geräten|Verwenden von PowerShell zum Angeben von Websites|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Verwenden von App-erzwungenen Einschränkungen in SharePoint Online
Wenn Sie Zugriffssteuerungen in SharePoint Online implementieren, müssen Sie diese Richtlinie für den bedingten Zugriff in Azure AD erstellen, um Azure AD zu sagen, dass Sie die in SharePoint Online konfigurierten Richtlinien erzwingen. Diese Regel gilt für alle Benutzer, hat aber nur Auswirkungen auf den Zugriff auf die Websites, die Sie mithilfe von PowerShell angeben, wenn Sie die Zugriffssteuerung in SharePoint Online erstellen.

Informationen zum Konfigurieren dieser Richtlinie finden Sie unter "Sperren oder Einschränken des Zugriffs auf bestimmte SharePoint-Websitesammlungen oder OneDrive-Konten" in diesem Artikel: [Steuern des Zugriffs auf nicht verwaltete Geräte](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).


## <a name="sharepoint-online-access-control-policies"></a>Richtlinien für die SharePoint Online-Zugriffssteuerung
Microsoft empfiehlt, dass Sie Inhalte in SharePoint-Websites mit vertraulichen und hoch regulierten Inhalten mit Gerätezugriffs Steuerungen schützen. Hierzu erstellen Sie eine Richtlinie, die den Schutzgrad und die Websites angibt, auf die der Schutz angewendet werden soll. 
- Vertrauliche Websites: Browser Zugriff zulassen. Dadurch wird verhindert, dass Benutzer Dateien bearbeiten und herunterladen.
- Stark regulierte Websites: Blockieren des Zugriffs von nicht verwalteten Geräten aus.

Weitere Informationen finden Sie unter "blockieren oder Einschränken des Zugriffs auf bestimmte SharePoint-Websitesammlungen oder OneDrive-Konten" in diesem Artikel: [Steuern des Zugriffs auf nicht verwaltete Geräte](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622) . 

## <a name="how-these-policies-work-together"></a>Zusammenarbeit dieser Richtlinien
Es ist wichtig zu wissen, dass SharePoint-Websiteberechtigungen in der Regel auf geschäftliche Anforderungen für den Zugriff auf Websites basieren. Diese Berechtigungen werden von Websitebesitzern verwaltet und können sehr dynamisch sein. Die Verwendung von SharePoint-Gerätezugriffs Richtlinien stellt den Schutz dieser Websites sicher, unabhängig davon, ob Benutzer einer Azure AD-Gruppe zugewiesen sind, die mit dem Basisplan, dem vertraulichen oder dem hoch regulierten Schutz verknüpft ist. 

Die folgende Abbildung zeigt ein Beispiel dafür, wie der Zugriff auf Websites durch SharePoint-Gerätezugriffs Richtlinien geschützt wird.

![Schutz von Websites durch SharePoint-Gerätezugriffs Richtlinien](../images/SharePoint-rules-scenario.png)

In der Abbildung sehen Sie Folgendes:
- James wird bedingten Zugriffsrichtlinien zugeordnet, die mit dem Basisschutz verbunden sind, aber er kann Zugriff auf SharePoint-Websites erhalten, die mit vertraulichen oder hoch regulierten Schutzfunktionen verbunden sind. 
- Wenn James auf eine vertrauliche oder hochregulierte Website zugreift, in der er Mitglied der Verwendung seines PCs ist, wird sein Zugriff gewährt, solange sein PC kompatibel ist.
- Wenn James auf eine vertrauliche Website zugreift, in der er sein nicht verwaltetes Telefon verwendet, das für Basisbenutzer zulässig ist, erhält er aufgrund der für diese Website konfigurierten Gerätezugriffs Richtlinie nur Browser Zugriff auf die vertrauliche Website. 
- Wenn James auf eine stark regulierte Website zugreift, in der er Mitglied der Verwendung seines nicht verwalteten Telefons ist, wird er aufgrund der für diese Website konfigurierten Zugriffsrichtlinie blockiert. Er kann nur mit seinem verwalteten und kompatiblen PC auf diese Website zugreifen.




## <a name="next-steps"></a>Nächste Schritte
[Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
