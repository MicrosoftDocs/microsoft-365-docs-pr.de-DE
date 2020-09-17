---
title: Konfigurationen für den Identitäts-und Geräte Zugriff – Microsoft 365 für Unternehmen
description: Beschreibt Microsoft-Empfehlungen und Kernkonzepte für die Bereitstellung von Richtlinien und Konfigurationen für sichere e-Mails, Dokumente und apps.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/14/2020
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
ms.openlocfilehash: 686d31c64394094530099edb97bbd10912a58cb8
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949892"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationen für den Identitäts- und Gerätezugriff

Der moderne Sicherheitsumfang Ihrer Organisation reicht nun über das Netzwerk hinaus und umfasst Benutzer, die von einem beliebigen Standort mit einer Vielzahl von Geräten auf Cloud-basierte apps zugreifen. Ihre Sicherheitsinfrastruktur muss ermitteln, ob eine bestimmte Zugriffsanforderung erteilt werden soll und unter welchen Bedingungen. 

Diese Bestimmung sollte auf der Benutzerkontoanmeldung, dem verwendeten Gerät, den apps, auf die der Benutzer zuzugreifen versucht, dem Standort, von dem die Zugriffsanforderung erfolgt, und einer Bewertung des Risikos der Anforderung basieren. Diese Funktion stellt sicher, dass nur genehmigte Benutzer und Geräte auf Ihre kritischen Ressourcen zugreifen können.

In dieser Artikelreihe werden eine Reihe von erforderlichen Konfigurationen für den Identitäts-und Geräte Zugriff sowie eine Reihe von bedingten Zugriffen auf Azure Active Directory (Azure AD), Microsoft InTune und andere Richtlinien zum Sichern des Zugriffs auf Microsoft 365 für Enterprise-Cloud-apps und-Dienste, andere Saas-Dienste und lokale Anwendungen beschrieben, die mit Azure AD-Anwendungs Proxy veröffentlicht werden.

Einstellungen und Richtlinien für den Identitäts-und Geräte Zugriff werden auf drei Ebenen empfohlen: Basisschutz, vertraulicher Schutz und Schutz für Umgebungen mit stark regulierten oder klassifizierten Daten. Diese Ebenen und die entsprechenden Konfigurationen bieten konsistente Schutzebenen für Ihre Daten, Identitäten und Geräte.

Diese Funktionen und ihre Empfehlungen:

- Werden in Microsoft 365 E3 und Microsoft 365 E5 unterstützt.
- Werden sowohl mit [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) als auch mit dem [Ergebnis der Identitäts Bewertung in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)ausgerichtet und werden diese Ergebnisse für Ihre Organisation verbessern.
- Hilft Ihnen bei der Implementierung dieser [fünf Schritte zur Sicherung ihrer Identitätsinfrastruktur](https://docs.microsoft.com/azure/security/azure-ad-secure-steps).

Wenn Ihre Organisation eindeutige Umgebungsanforderungen oder Komplexitäten aufweist, verwenden Sie diese Empfehlungen als Ausgangspunkt. Die meisten Organisationen können diese Empfehlungen jedoch wie vorgeschrieben implementieren.

>[!Note]
>Microsoft verkauft außerdem Enterprise Mobility + Security (EMS)-Lizenzen für Office 365 Abonnements. Die Funktionen EMS E3 und EMS E5 entsprechen denen in Microsoft 365 E3 und Microsoft 365 E5. Details finden Sie unter [EMS-Pläne](https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) .
>

## <a name="intended-audience"></a>Zielgruppe

Diese Empfehlungen sind für Enterprise-Architekten und IT-Experten gedacht, die mit Microsoft 365 Cloud Productivity and Security Services vertraut sind, einschließlich Azure AD (Identity), Microsoft InTune (Device Management) und Azure Information Protection (Datenschutz).

### <a name="customer-environment"></a>Kundenumgebung

Die empfohlenen Richtlinien gelten für Unternehmensorganisationen, die vollständig innerhalb der Microsoft-Cloud und für Kunden mit hybrider Identitätsinfrastruktur, die eine lokale Active Directory-Domänendienste (AD DS) Gesamtstruktur ist, die mit einem Azure AD Mandanten synchronisiert ist.

Viele der bereitgestellten Empfehlungen stützen sich auf Dienste, die nur mit Microsoft 365 E5, Microsoft 365 E3 mit dem Identity & Threat Protection-Add-on, EMS E5 oder Azure Premium P2-Lizenzen verfügbar sind.

Für Organisationen, die nicht über diese Lizenzen verfügen, empfiehlt Microsoft, dass Sie mindestens [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)implementieren, die in allen Microsoft 365-Plänen enthalten sind. 

### <a name="caveats"></a>Warnhinweise

Ihre Organisation unterliegt möglicherweise behördlichen oder anderen Compliance-Anforderungen, einschließlich spezifischer Empfehlungen, bei denen Sie möglicherweise Richtlinien anwenden müssen, die von diesen empfohlenen Konfigurationen abweichen. Bei diesen Konfigurationen werden Verwendungs Steuerelemente empfohlen, die nicht historisch verfügbar waren. Wir empfehlen diese Steuerelemente, da wir glauben, dass Sie ein Gleichgewichtzwischen Sicherheit und Produktivität darstellen.  

Wir haben unser Bestes getan, um eine Vielzahl von organisatorischen Schutzanforderungen zu erfüllen, aber wir können nicht alle möglichen Anforderungen oder alle einzigartigen Aspekte Ihrer Organisation berücksichtigen.

## <a name="three-tiers-of-protection"></a>Drei Schutzebenen

Die meisten Organisationen haben spezifische Anforderungen bezüglich Datensicherheit und Datenschutz. Diese Anforderungen variieren je nach Branche und Tätigkeiten im Unternehmen. Beispielsweise benötigen Ihre Rechtsabteilung und Administratoren möglicherweise zusätzliche Sicherheits-und Informationsschutz Kontrollen rund um Ihre e-Mail-Korrespondenz, die für andere Geschäftseinheiten nicht erforderlich sind. 

Jede Branche verfügt auch über ihren eigenen Satz von spezialisierten Vorschriften. Anstatt eine Liste aller möglichen Sicherheitsoptionen oder einer Empfehlung pro Branchensegment oder Auftragsfunktion bereitzustellen, wurden Empfehlungen für drei verschiedene Sicherheits-und Schutzstufen bereitgestellt, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können.

- **Grund**legender Schutz: Es wird empfohlen, einen Mindeststandard zum Schutz von Daten sowie die Identitäten und Geräte festzulegen, die auf Ihre Daten zugreifen. Sie können diese grundlegenden Empfehlungen befolgen, um einen starken Standardschutz bereitzustellen, der die Anforderungen vieler Organisationen erfüllt.
- **Vertraulicher Schutz**: einige Kunden verfügen über eine Teilmenge von Daten, die auf höheren Ebenen geschützt werden müssen, oder Sie erfordern möglicherweise, dass alle Daten auf einer höheren Ebene geschützt werden. Sie können einen erhöhten Schutz für alle oder bestimmte Datensätze in Ihrer Microsoft 365-Umgebung anwenden. Es wird empfohlen, Identitäten und Geräte mit Zugriff auf sensible Daten mit einem vergleichbaren Grad an Sicherheit auszustatten.  
- **Stark reguliert**: einige Organisationen haben möglicherweise eine kleine Menge an Daten, die streng klassifiziert sind, Geschäftsgeheimnisse darstellen oder regulierte Daten sind. Microsoft stellt Funktionen bereit, die es Organisationen ermöglichen, diese Anforderungen zu erfüllen, wie etwa den zusätzlichen Schutz von Identitäten und Geräten.

![Security Cone – alle Kunden > einige Kunden > bestimmte Kunden. Umfassende Anwendung für eine bestimmte Anwendung](../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

In diesem Leitfaden erfahren Sie, wie Sie den Schutz von Identitäten und Geräten für jede dieser Schutzebenen implementieren. Verwenden Sie diese Anleitung als Ausgangspunkt für Ihre Organisation, und passen Sie die Richtlinien an die spezifischen Anforderungen Ihrer Organisation an.

Es ist wichtig, konsistente Schutzebenen für Daten, Identitäten und Geräte zu verwenden. Wenn Sie beispielsweise diesen Leitfaden implementieren, müssen Sie Ihre Daten auf vergleichbaren Ebenen schützen. 

Der **Identitäts-und Geräteschutz für das Microsoft 365-** Architekturmodell zeigt Ihnen, welche Funktionen vergleichbar sind.

[![Daumen Bild für den Identitäts-und Geräteschutz für das Microsoft 365-Poster](../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br/>  [Als PDF anzeigen](../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Als PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| herunterladen [Als Visio herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Weitere Informationen finden Sie unter [Deploy Information Protection for Data Privacy Regulations](../solutions/information-protection-deploy.md) Solution zum Schutz der in Microsoft 365 gespeicherten Informationen.

## <a name="security-and-productivity-trade-offs"></a>Kompromisse in den Bereichen Sicherheit und Produktivität

Die Implementierung einer Sicherheitsstrategie erfordert Kompromisse zwischen Sicherheit und Produktivität. Es ist hilfreich, zu bewerten, wie sich jede Entscheidung auf das Gleichgewichtzwischen Sicherheit, Funktionalität und Benutzerfreundlichkeit auswirkt.

![Security Triad Balancing Sicherheit, Funktionalität und Benutzerfreundlichkeit.](../media/microsoft-365-policies-configurations/security-triad.png)

Die bereitgestellten Empfehlungen basieren auf folgenden Grundsätzen:

- Kennen Sie Ihre Benutzer, und lassen Sie sich an Ihre Sicherheits-und Funktionsanforderungen flexibel anpassen.
- Wenden Sie eine Sicherheitsrichtlinie rechtzeitig an, und stellen Sie sicher, dass Sie sinnvoll ist.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Dienste und Konzepte für den Identitäts-und Gerätezugriffs Schutz

Microsoft 365 für Unternehmen wurde für große Organisationen entwickelt, die es ermöglichen, kreativ zu sein und sicher zusammenzuarbeiten.

Dieser Abschnitt enthält eine Übersicht über die Microsoft 365-Dienste und-Funktionen, die für den Identitäts-und Geräte Zugriff wichtig sind.

### <a name="azure-ad"></a>Azure AD

Azure Ad bietet eine umfassende Sammlung von Funktionen zur Identitätsverwaltung. Es wird empfohlen, diese Funktionen zum Sichern des Zugriffs zu verwenden.

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| [Mehrstufige Authentifizierung (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) | Für MFA müssen Benutzer zwei Arten der Überprüfung bereitstellen, beispielsweise ein Benutzerkennwort sowie eine Benachrichtigung über die Microsoft Authenticator-APP oder einen Anruf. MFA reduziert das Risiko, dass gestohlene Anmeldeinformationen für den Zugriff auf Ihre Umgebung verwendet werden können, erheblich. Microsoft 365 verwendet den Azure-mehrstufigen Authentifizierungsdienst für MFA-basierte Anmeldungen. | Microsoft 365 E3 oder E5 |
| [Bedingter Zugriff](/azure/active-directory/conditional-access/overview) | Azure AD wertet die Bedingungen der Benutzeranmeldung aus und verwendet Richtlinien für den bedingten Zugriff, um den zulässigen Zugriff zu bestimmen. In diesem Leitfaden erfahren Sie beispielsweise, wie Sie eine Richtlinie für den bedingten Zugriff erstellen, um die Geräte Konformität für den Zugriff auf vertrauliche Daten zu erfordern. Dadurch wird das Risiko erheblich reduziert, dass ein Hacker mit seinem eigenen Gerät und die gestohlenen Anmeldeinformationen auf Ihre vertraulichen Daten zugreifen können. Außerdem werden vertrauliche Daten auf den Geräten geschützt, da die Geräte bestimmte Anforderungen an die Integrität und Sicherheit erfüllen müssen. | Microsoft 365 E3 oder E5 |
| [Azure Ad Gruppen](/azure/active-directory/fundamentals/active-directory-manage-groups) | Bedingte Zugriffsrichtlinien, Geräteverwaltung mit InTune und sogar Berechtigungen für Dateien und Websites in Ihrer Organisation beruhen auf der Zuweisung zu Benutzerkonten oder Azure Ad Gruppen. Es wird empfohlen, Azure Ad Gruppen zu erstellen, die den von Ihnen implementierten Schutzebenen entsprechen. Beispielsweise sind Ihre Führungskräfte wahrscheinlich höhere Wert Ziele für Hacker. Daher ist es sinnvoll, die Benutzerkonten dieser Mitarbeiter einer Azure Ad Gruppe hinzuzufügen und diese Gruppe den Richtlinien für bedingten Zugriff und anderen Richtlinien zuzuweisen, die eine höhere Schutzebene für den Zugriff erzwingen. | Microsoft 365 E3 oder E5 |
| [Geräteregistrierung](/azure/active-directory/devices/overview) | Sie registrieren ein Gerät in Azure AD, um eine Identität für das Gerät zu erstellen. Diese Identität wird verwendet, um das Gerät zu authentifizieren, wenn ein Benutzer sich anmeldet und Richtlinien für bedingten Zugriff anwendet, die Domänenbeitritt oder kompatible PCs erfordern. Für diesen Leitfaden verwenden wir die Geräteregistrierung, um Domänenbeitritt von Windows-Computern automatisch zu registrieren. Die Geräteregistrierung ist eine Voraussetzung für die Verwaltung von Geräten mit InTune. | Microsoft 365 E3 oder E5 |
| [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview) | Ermöglicht Ihnen das Erkennen potenzieller Sicherheitsanfälligkeiten, die sich auf die Identitäten Ihrer Organisation auswirken, und die Konfiguration der automatischen Behebungs Richtlinie auf niedrigem, mittlerem und hohem Anmelde-und Benutzer Risiko. Dieser Leitfaden basiert auf dieser Risikobewertung, um Richtlinien für bedingten Zugriff für mehrstufige Authentifizierung anzuwenden. Dieser Leitfaden enthält auch eine Richtlinie für den bedingten Zugriff, bei der Benutzer Ihr Kennwort ändern müssen, wenn für Ihr Kontoaktivitäten mit hohem Risiko erkannt werden. | Microsoft 365 E5, Microsoft 365 E3 mit dem Identity & Threat Protection-Add-on, EMS E5 oder Azure Premium P2-Lizenzen |
| [Zurücksetzen von Kennwörtern durch den Benutzer (Self-Service Password Reset, SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks) | Ermöglichen Sie Ihren Benutzern, ihre Kennwörter sicher und ohne Helpdesk-Eingriff zurückzusetzen, indem Sie die Überprüfung von mehreren Authentifizierungsmethoden bereitstellen, die der Administrator steuern kann. | Microsoft 365 E3 oder E5 |
| [Azure AD Kennwortschutz](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Erkennen und blockieren Sie bekannte schwache Kennwörter und deren Varianten sowie zusätzliche schwache Ausdrücke, die für Ihre Organisation spezifisch sind. Standardmäßige globale gesperrte Kenn Wortlisten werden automatisch auf alle Benutzer in einem Azure AD Mandanten angewendet. Sie können zusätzliche Einträge in einer benutzerdefinierten Liste gesperrter Kennwörter definieren. Wenn Benutzer ihre Kennwörter ändern oder zurücksetzen, werden diese gesperrten Kenn Wortlisten überprüft, um die Verwendung sicherer Kennwörter zu erzwingen. |  Microsoft 365 E3 oder E5 |
||||

![Komponenten des Identitäts-und Gerätezugriffs.](../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[InTune](https://docs.microsoft.com/intune/introduction-intune) ist der Cloud-basierte Verwaltungsdienst von Microsoft für mobile Geräte. In diesem Leitfaden wird die Geräteverwaltung von Windows-PCs mit InTune empfohlen und die Konfiguration von Richtlinienkonfigurationen für Geräte Konformität empfohlen. InTune ermittelt, ob Geräte kompatibel sind, und sendet diese Daten an Azure AD, die beim Anwenden von Richtlinien für den bedingten Zugriff verwendet werden sollen.

#### <a name="intune-app-protection"></a>InTune-App-Schutz

[InTune-App-Schutz](https://docs.microsoft.com/intune/app-protection-policy) Richtlinien können verwendet werden, um die Daten Ihrer Organisation in Mobile Apps zu schützen, mit oder ohne Registrierung von Geräten in der Verwaltung. InTune hilft, Informationen zu schützen, um sicherzustellen, dass Ihre Mitarbeiter produktiv bleiben und Datenverluste verhindern. Durch die Implementierung von Richtlinien auf App-Ebene können Sie den Zugriff auf Unternehmensressourcen einschränken und Daten im Rahmen der Steuerung Ihrer IT-Abteilung verwalten.

In diesem Leitfaden erfahren Sie, wie Sie empfohlene Richtlinien erstellen, um die Verwendung genehmigter apps zu erzwingen und zu ermitteln, wie diese apps mit ihren Geschäftsdaten verwendet werden können.

### <a name="microsoft-365"></a>Microsoft 365

Dieser Leitfaden zeigt Ihnen, wie Sie eine Reihe von Richtlinien implementieren, um den Zugriff auf Microsoft 365-Cloud-Dienste zu schützen, einschließlich Microsoft Teams, Exchange Online, SharePoint Online und OneDrive für Unternehmen. Zusätzlich zur Implementierung dieser Richtlinien sollten Sie auch den Schutzgrad für Ihren Mandanten mit diesen Ressourcen erhöhen:

- [Konfigurieren Ihres Mandanten für höhere Sicherheit](../security/office-365-security/tenant-wide-setup-for-increased-security.md)

  Empfehlungen, die für die grundlegende Sicherheit für Ihren Mandanten gelten.

- [Sicherheits Wegweiser: wichtige Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](../security/office-365-security/security-roadmap.md)

  Empfehlungen einschließlich Protokollierung, Datensteuerung, Administratorzugriff und Bedrohungsschutz.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 und Microsoft 365 Apps for Enterprise

Windows 10 mit Microsoft 365 apps for Enterprise ist die empfohlene Clientumgebung für PCs. Windows 10 wird empfohlen, da Azure so konzipiert ist, dass es sowohl lokal als auch Azure AD eine möglichst reibungslose Umgebung bietet. Windows 10 umfasst außerdem erweiterte Sicherheitsfunktionen, die über InTune verwaltet werden können. Microsoft 365 apps for Enterprise enthält die neuesten Versionen von Office-Anwendungen. Diese verwenden moderne Authentifizierung, die sicherer und eine Anforderung für bedingten Zugriff ist. Zu diesen apps gehören auch erweiterte Sicherheits-und Compliance-Tools.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Anwenden dieser Funktionen auf die drei Schutzebenen

In der folgenden Tabelle sind unsere Empfehlungen für die Verwendung dieser Funktionen in den drei Schutzebenen zusammengefasst.

|Schutzmechanismus|Baseline|Vertraulich|Streng geregelt|
|:-------------------|:-------|:--------|:---------------|
|**MFA erzwingen**|Bei mittlerem oder höherem Anmelderisiko|Bei niedrigem oder höherem Anmelderisiko|Auf alle neuen Sitzungen|
|**Erzwingen der Kennwortänderung**|Für Benutzer mit hohem Risiko|Für Benutzer mit hohem Risiko|Für Benutzer mit hohem Risiko|
|**Erzwingen des InTune-Anwendungsschutzes**|Ja|Ja|Ja|
|**Erzwingen der InTune-Registrierung für das organisationseigene Gerät**|Erfordern eines kompatiblen oder von einer Domäne verbundenen PCs, aber zulassen von BYOD-Telefonen und Tablets für eigene Geräte|Erfordern eines kompatiblen oder mit der Domäne verbundenen Geräts|Erfordern eines kompatiblen oder mit der Domäne verbundenen Geräts|

## <a name="device-ownership"></a>Gerätebesitz

Die obige Tabelle zeigt den Trend vieler Organisationen zur Unterstützung einer Kombination aus unternehmenseigenen Geräten sowie persönlichen oder BYODs, um die mobile Produktivität für die gesamte Belegschaft zu ermöglichen. Mit InTune-App-Schutzrichtlinien wird sichergestellt, dass e-Mails vor exfiltrating aus dem Outlook-Mobile App und anderen Office-Mobile Apps geschützt werden, sowohl auf organisationseigenen Geräten als auch auf BYODs.  

Es wird empfohlen, dass unternehmenseigene Geräte von InTune oder von der Domäne verbunden verwaltet werden, um zusätzliche Schutzmaßnahmen und Steuerelemente anzuwenden. Je nach Daten Empfindlichkeit kann Ihre Organisation festlegen, dass BYODs für bestimmte Benutzer Populationen oder bestimmte apps nicht zulässig ist.

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Schritte beim Konfigurieren des Identitäts-und Gerätezugriffs

![Schritte zum Konfigurieren des Identitäts-und Gerätezugriffs.](../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Konfigurieren Sie die erforderlichen Identitätsfeatures und deren Einstellungen.
2. Konfigurieren der allgemeinen Identitäts-und Zugriffsrichtlinien für den bedingten Zugriff.
3. Konfigurieren Sie Richtlinien für bedingten Zugriff für Gast-und externe Benutzer.
4. Konfigurieren Sie Richtlinien für bedingten Zugriff für Microsoft 365 Cloud-apps wie Microsoft Teams, Exchange Online und SharePoint.

## <a name="next-step"></a>Nächster Schritt

[Erforderliche Arbeit für die Implementierung von Identitäts-und Gerätezugriffs Richtlinien](identity-access-prerequisites.md)
