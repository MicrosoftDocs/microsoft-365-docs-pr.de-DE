---
title: Identität und Gerät zugreifen Konfigurationen – Microsoft 365 Enterprise
description: Beschreibt Microsoft Empfehlungen und zentrale Konzepte für die Bereitstellung von sicheren e-Mail, Dokumente, und apps Richtlinien und Konfigurationen.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ea03143c7c42952ab6963d38ae44e79822d0b90a
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867580"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationen für den Identitäts- und Gerätezugriff

Diese Artikelreihe wird beschrieben, wie sicheren Zugriff auf die Cloud-Diensten über Enterprise Mobilität + Security-Produkte zu konfigurieren, durch die Implementierung einer empfohlenen-Umgebung und-Konfiguration, einschließlich einer Reihe vorgeschriebenen bedingte Zugriffsrichtlinien und Verwandte Funktionen. Dieser Anleitung können Sie um Zugriff auf alle Dienste zu schützen, die mit Azure Active Directory, einschließlich Office 365-Dienste, andere SaaS-Dienste und lokalen Applications veröffentlicht mit Azure AD-Anwendungsproxy integriert sind. 

Diesen Empfehlungen mit Microsoft Secure Score sowie [Identität in Azure AD Punktzahl](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score)ausgerichtet werden, und nimmt diese Faktoren für Ihre Organisation. Diesen Empfehlungen hilft Ihnen diese [fünf Schritte zum Sichern der Identitätsinfrastruktur](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps)zu implementieren. 

Microsoft weiß, dass einige Organisationen eindeutige Umgebung Anforderungen oder Komplexität haben. Wenn Sie eine der folgenden Organisationen sind, verwenden Sie diesen Empfehlungen als Ausgangspunkt. Die meisten Organisationen können jedoch diesen Empfehlungen implementieren, wie vorgeschrieben. 

## <a name="intended-audience"></a>Zielgruppe

Diese Empfehlungen sind für die direkte Verwendung Enterprise konstruiert und IT-Experten, die mit [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) und [Microsoft Enterprise Mobilität + Sicherheit](http://microsoft.com/ems), die unter anderem, Azure Active Directory (Identität), Microsoft enthält vertraut sind Intune (Gerätemanagement) und Azure Information Protection (Datenschutz).

### <a name="customer-environment"></a>Kunden-Umgebung

Die empfohlenen Richtlinien gelten auch für Enterprise-Organisationen Betrieb vollständig in der Microsoft-Cloud sowohl für Kunden mit Hybrid-Infrastruktur (lokalen und Cloud von Microsoft bereitgestellt).

Viele der bereitgestellten Empfehlungen verlassen auf Dienste nur mit Enterprise-Mobilität + Sicherheit (zur Abstimmung) E5 Lizenzen zur Verfügung stehen. Empfehlungen davon vollständige zur Abstimmung E5 Lizenzfunktionen aus.

Für Organisationen, die Enterprise-Mobilität + Sicherheit E5 Lizenzen nicht verfügen, empfiehlt es sich, dass Sie mindestens Azure AD-Baseline Schutzfunktionen implementieren, die mit allen Plänen enthalten sind. Weitere Informationen finden im Artikel, [Was Baseline Schutz ist](/azure/active-directory/active-directory-conditional-access-baseline-protection), in der Azure AD-Bibliothek.

### <a name="caveats"></a>Warnhinweise

Ihrer Organisation möglicherweise aus rechtlichen oder sonstigen Compliance-Bestimmungen, einschließlich bestimmte Empfehlungen, die Sie Richtlinien anwenden, die aus folgenden empfohlenen Konfigurationen abweichen möglicherweise unterliegen. Diese Konfigurationen empfehlen Usage-Steuerelemente, die nicht in der Vergangenheit verfügbar waren. Diese Steuerelemente wird empfohlen, weil wir glauben, dass sie ein Gleichgewicht zwischen Sicherheit und Produktivität darstellen.  

Wir haben unsere besten durchgeführt, um eine Vielzahl von organisatorischen Protection Anforderungen berücksichtigt werden, aber nicht können wir Konto für alle möglichen Anforderungen oder für die eindeutige Aspekte Ihrer Organisation.

## <a name="three-tiers-of-protection"></a>Drei Ebenen des Schutzes

Die meisten Organisationen haben spezifische Anforderungen bezüglich Datensicherheit und Datenschutz. Diese Anforderungen variieren je nach Branche und Tätigkeiten im Unternehmen. Angenommen, Ihre Rechtsabteilung und Office 365-Administratoren erfordern möglicherweise zusätzliche Sicherheit- und Informationsschutzüberprüfungen für die E-Mail-Korrespondenz, die nicht für andere Benutzer des Geschäftsbereich erforderlich sind. 

In jeder Branche verfügt auch über einen eigenen Satz von speziellen Vorschriften. Anstatt pro Segment oder Auftrag Funktion Branche Recommendations angegeben wurden für drei verschiedene Ebenen der Sicherheit und Schutz, die angewendet werden können basierend auf der Granularität von Ihren Anforderungen bietet eine Übersicht über alle möglichen Sicherheitsoptionen oder Empfehlung .

- **Geplante Schutz**: Es wird empfohlen, Sie einen minimalen Standard für den Schutz von Daten, sowie die Identitäten und Geräte, die Zugriff auf Ihre Daten herstellen. Führen Sie diesen Empfehlungen Baseline starken standardmäßigen Schutz bereitstellen, die den Bedürfnissen von viele Organisationen entspricht.
- **Vertrauliche Schutz**: Einige Kunden haben eine Teilmenge der Daten, die geschützt werden müssen, höherer, oder alle Daten auf einer höheren Ebene geschützt werden müssen. Sie können verbesserten Schutz auf alle oder bestimmte Daten in der Office 365-Umgebung festgelegt. Es wird empfohlen, Schützen von Identitäten und Geräten, die mit vergleichbaren Sicherheitsstufen vertrauliche Daten zugreifen.  
- **Stark regulierter**: Einige Organisationen möglicherweise eine kleine Datenmenge stark klassifiziert ist, Consititutes Handel Secrets oder regulierten Daten ist. Microsoft stellt Funktionen bereit, mit deren Hilfe Organisationen, die diese Anforderungen, einschließlich zusätzlichen Schutz für Identitäten und Geräte erfüllen.

![Sicherheit Kegel - alle Kunden > einige Kunden > bestimmte Kunden. Umfassende Anwendung zu bestimmten Anwendung](../images/M365-idquality-threetiers.png)

Diese Anleitung zeigt, wie Schutz für Identitäten und Geräte für jede der folgenden Ebenen des Schutzes implementieren. Verwenden Sie diese Richtlinien als Ausgangspunkt für Ihre Organisation, und passen Sie die Richtlinien, um bestimmte Anforderungen Ihrer Organisation zu erfüllen.

Es ist wichtig, konsistente Schutzebenen für Ihre Daten, Identitäten und Geräte zu verwenden. Wenn Sie diese Richtlinien implementieren, müssen Sie beispielsweise Sie zum Schutz Ihrer Daten auf vergleichbare Ebenen. Diese Architektur Modelle zeigen, welche Funktionen vergleichbar sind.

**Identität- und Geräteschutz für Office 365**<br/>
![Miniaturansicht für Poster "Identity" und "Gerät Schutz für Office 365"](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55032)

**Lösungen zum Schutz von Dateien in Office 365**<br/>
![Miniaturansicht für Poster "Datei Protection-Lösungen in Office 365"](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Kompromisse in den Bereichen Sicherheit und Produktivität

Jede Sicherheitsstrategie Implementierung müssen Kompromisse zwischen Sicherheit und Produktivität. Es ist hilfreich, bewerten, wie jede Entscheidung das Verhältnis von Sicherheit, Funktionen und Bedienung auswirkt.

![Sicherheit Triaden Netzwerklastenausgleich Sicherheit, Funktionen und Bedienung.](media/policies-configurations/security-triad.png)

Die Empfehlungen basieren auf die folgenden Grundsätze:

- Ihr Publikum und flexibel auf die Sicherheit und funktionellen Anforderungen.
- Anwenden einer Sicherheitsrichtlinie Just-in-Time, und stellen Sie sicher, dass es sinnvoll ist.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Dienste und Konzepte für die Identität und Gerät Zugriffsschutz

Microsoft 365 Enterprise ist darauf ausgelegt für große Organisationen und Office 365 Enterprise, Windows 10 Enterprise und Enterprise-Mobilität + Sicherheit (zur Abstimmung), jeder werden Webinhalte Creative und zusammenarbeiten sicher integriert.

Dieser Abschnitt enthält eine Übersicht über die Microsoft-365-Dienste und Funktionen, die für den Zugriff von Identität und Gerät eine wichtige Rolle spielen.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD bietet ein umfassendes Identity Management-Funktionen. Es wird empfohlen, für den sicheren Zugriff mithilfe der folgenden Funktionen:

- **[Self-service-Kennwort zurücksetzen (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: Benutzer ihre Kennwörter zurücksetzen sicher und ohne Benutzereingriff Helpdesk, durch die Bereitstellung der Überprüfung der mehrere Authentifizierungsmethoden, die der Administrator steuern können.

- **[Mehrstufige Authentifizierung (mehrstufiger Authentifizierung das)](/azure/active-directory/authentication/concept-mfa-howitworks)**: mehrstufiger Authentifizierung das erfordert, dass Benutzer zwei Formen der Überprüfung, wie ein Benutzerkennwort plus eine Benachrichtigung von Microsoft Authenticator app oder einem Telefonanruf bereitstellen. Mehrstufiger Authentifizierung das erheblich verringert des Risikos, die ein gestohlenen Identitätsdaten werden können, auf der Office 365-Umgebung zugegriffen hat.

- **[Bedingte Zugriff](/azure/active-directory/conditional-access/overview)**: Azure AD wertet die Bedingungen der Benutzername und bedingte Zugriffsrichtlinien, die Sie erstellen, um die Gewährung des Zugriffs verwendet. Beispielsweise wird in dieser Anleitung wir Sie veranschaulicht erstellen Sie eine bedingte Zugriffsrichtlinie, um das Gerät-Kompatibilität für den Zugriff auf vertrauliche Daten erforderlich ist. Dies reduziert erheblich das Risiko, dass ein Hacker mit einer Identität gestohlenen Ihre sensiblen Daten zugreifen kann. Er schützt auch vertrauliche Daten auf den Geräten, da die Geräte spezifische Anforderungen für die Integrität und Sicherheit erfüllen.

- **[Azure Active Directory-Gruppen](/azure/active-directory/fundamentals/active-directory-manage-groups)**: Zuweisung zu Benutzer und/oder Azure AD-Gruppen, bedingte Zugriffsregeln, Gerätemanagement mit Intune und sogar Berechtigungen auf Dateien und Websites in Ihrer Organisation nutzen. Es wird empfohlen, dass Sie Azure AD-Gruppen erstellen, die die Schutzebenen entsprechen, die Sie implementieren. Beispielsweise sind Ihre Mitarbeiter executive wahrscheinlich höheren Wert Zielwerte für Hacker. Aus diesem Grund ist es sinnvoll, weisen Sie diese Mitarbeiter eine Azure Active Directory-Gruppe, und weisen Sie diese Gruppe bedingte Zugriffsrichtlinien und andere Richtlinien, die einen besseren Schutz für den Zugriff zu erzwingen.

- **[Gerät Registrierung](/azure/active-directory/devices/overview)**: Registrieren Sie ein Gerät in Azure AD eine Identität an das Gerät bereitstellen. Diese Identität wird verwendet, um das Gerät zu authentifizieren, wenn ein Benutzer anmeldet und bedingte Zugriffsregeln anwenden, die in die Domäne eingebundener oder kompatible PCs erfordern. In diesem Handbuch verwenden wir Gerät Registrierung, um automatisch in die Domäne eingebundener Windows-Computern zu registrieren. Gerät-Registrierung ist eine Voraussetzung für die Verwaltung von Geräten mit Intune. 

- **[Azure AD-Schutz](/azure/active-directory/identity-protection/overview)**: Azure AD-Schutz ermöglicht Ihnen das potenzielle Sicherheitsrisiken Identitäten Ihrer Organisation beeinflussen zu erkennen und zu niedrig, Mittel und hoch-Anmeldung Risiken und Benutzer Risiko automatischen Behebung Richtlinie konfigurieren. Diese Anleitung nutzt dieses Risiko Evaluation Anwenden bedingter Zugriffsrichtlinien für die mehrstufige Authentifizierung. Diese Anleitung enthält auch eine bedingte Zugriffsrichtlinie, die erfordert, dass Benutzer ihre Kennwörter ändern, wenn mit hohem Risiko Aktivität für ihr Konto erkannt wird.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) ist Microsofts Cloud-basierten Mobilgerät-Verwaltungsdienst. Diese Anleitung empfiehlt Gerätemanagement Windows PCs mit Intune und empfiehlt Gerät Compliance Richtlinienkonfigurationen. Intune bestimmt, ob Geräte konform sind und sendet diese Daten Azure AD beim Anwenden von Richtlinien für den bedingten verwendet werden.

#### <a name="intune-app-protection"></a>Intune app Schutz

Richtlinien [Intune app](https://docs.microsoft.com/intune/app-protection-policy) können zum Schützen von Daten in mobilen apps mit oder ohne zum Registrieren von Geräten in der Verwaltung Ihrer Organisation verwendet werden. Intune trägt zum Schutz von Office 365-Informationen, und stellen Sie sicher, dass Ihre Mitarbeiter noch Datenverlust produktiv und verhindert werden können. Implementieren von app-Ebene Richtlinien, können Sie einschränken des Zugriffs auf Unternehmensressourcen und Beibehalten von Daten in die Kontrolle über Ihre IT-Abteilung.

Diese Anleitung zeigt, wie erstellen die empfohlenen Richtlinien zum Erzwingen der Verwendung von genehmigten apps und um zu bestimmen, wie diese apps mit Geschäftsdaten verwendet werden können.

### <a name="office-365"></a>Office 365

Diese Anleitung zeigt, wie eine Reihe von Richtlinien zum Schutz des Zugriffs auf Office 365, einschließlich Exchange Online, SharePoint Online und OneDrive für Unternehmen implementieren. Zusätzlich zu diesen Richtlinien implementieren, wird empfohlen, dass Sie auch die Ebene der Schutz für Ihre Office 365-Mandanten mithilfe dieser Ressourcen auslösen:

- [Konfigurieren Sie Ihre Office 365-Mandanten für erhöhte Sicherheit](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355): diesen Empfehlungen gelten für grundlegende Sicherheit für Office 365-Mandanten.
- [Wegweiser für Office 365-Sicherheit: Top-Prioritäten für den ersten 30 Tagen 90 Tage und darüber hinaus](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352): Diese wird Folgendes Protokollierung, Daten Governance, Administratorzugriff und Virenschutz.
- [Secure SharePoint Online-Websites und Dateien](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files): mit dieser Gruppe von Artikeln wird beschrieben, wie Dateien und Websites auf entsprechende Ebenen für geplante, empfindlich und streng vertraulich Protection geschützt.

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 und Office 365 ProPlus

Windows-10 und Office 365 ProPlus ist der empfohlene-Umgebung für PCs. Wir empfehlen Windows 10, wie Azure Erfahrung mit die reibungslose für lokale und Azure Active Directory bereitgestellt werden sollen. Windows-10 umfasst auch erweiterte Sicherheit, die über Intune verwaltet werden können. Office 365 ProPlus enthält die aktuellen Versionen von Office-Anwendungen. Diese verwenden moderne Authentifizierung, die sicherer ist und eine Voraussetzung für bedingten Zugriff. Diese apps enthalten außerdem verbesserte Sicherheit und Compliance-Tools.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Diese Funktionen anwenden über die drei Ebenen von Schutz

In der folgenden Tabelle sind unsere Empfehlungen für die Verwendung dieser Funktionen auf allen drei Ebenen des Schutzes zusammengefasst.

|Schutzmechanismus|Baseline|Vertraulich|Hoch reguliert|
|:-------------------|:-------|:--------|:---------------|
|**MFA erzwingen**|Bei mittlerem oder höherem Anmelderisiko|Bei niedrigem oder höherem Anmelderisiko|Auf alle neuen Sitzungen|
|**Erzwingen der kennwortänderung**|Für Benutzer mit hohem Risiko|Für Benutzer mit hohem Risiko|Für Benutzer mit hohem Risiko|
|**Anwendungsschutz Intune erzwingen**|Ja|Ja|Ja|
|**Erzwingen von Intune Registrierung (COD)**|Erfordern Sie einen kompatiblen oder Domäne PC, aber zulassen Sie BYOD Telefone/tablets|Benötigen Sie ein Gerät kompatibel oder Domäne|Benötigen Sie ein Gerät kompatibel oder Domäne|

## <a name="device-ownership"></a>Gerätebesitz

Die oben stehenden Tabelle entspricht den Trend für viele Organisationen eine Kombination von firmeneigenen Geräten sowie persönliche oder bringen eigener Geräten (BYODs) So aktivieren Sie die mobile Produktivität über der Belegschaft unterstützt. Richtlinien für die Intune app Schutz sicherstellen, dass e-Mail aus Outlook mobile app und anderen Office mobile apps auf firmeneigenen Geräten und BYODs Exfiltrating geschützt ist.  

Wir empfehlen firmeneigenen Geräten von Intune verwaltet oder Domäne, um zusätzliche Schutzebenen und Steuerelement angewendet werden. Je nach Daten Empfindlichkeit können Ihre Organisation BYODs für bestimmte Benutzeranzahl oder bestimmte apps nicht zulassen.

## <a name="next-steps"></a>Nächste Schritte

[Erforderliche Arbeit für die Implementierung von Identität und Gerät Zugriffsrichtlinien](identity-access-prerequisites.md)
