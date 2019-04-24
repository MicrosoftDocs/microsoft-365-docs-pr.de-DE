---
title: Identitäts-und Gerätezugriffs Konfigurationen – Microsoft 365 Enterprise
description: Beschreibt Microsoft-Empfehlungen und Kernkonzepte für die Bereitstellung von Richtlinien und Konfigurationen für sichere e-Mails, Dokumente und apps.
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
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 9751d1e224d2fb4b879a5dbc37cb368af2152987
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291361"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationen für den Identitäts- und Gerätezugriff

In dieser Artikelreihe wird beschrieben, wie Sie den sicheren Zugriff auf Cloud-Dienste über Enterprise Mobility + Security-Produkte konfigurieren, indem Sie eine empfohlene Umgebung und Konfiguration implementieren, einschließlich einer vorgegebenen Reihe von Richtlinien für bedingten Zugriff und Verwandte Funktionen. Sie können diese Richtlinien verwenden, um den Zugriff auf alle in Azure Active Directory integrierten Dienste zu schützen, einschließlich Office 365-Diensten, anderen SaaS-Diensten und lokalen Anwendungen, die mit Azure AD Application Proxy veröffentlicht werden. 

Diese Empfehlungen richten sich sowohl an Microsoft Secure Score als auch [an die Identitäts Bewertung in Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score)und werden diese Punkte für Ihre Organisation erweitern. Diese Empfehlungen helfen Ihnen auch bei der Implementierung dieser [fünf Schritte zur Sicherung ihrer Identitätsinfrastruktur](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps). 

Microsoft ist sich bewusst, dass einige Organisationen über eindeutige Umgebungsanforderungen oder Komplexität verfügen. Wenn Sie eine dieser Organisationen sind, verwenden Sie diese Empfehlungen als Ausgangspunkt. Die meisten Organisationen können diese Empfehlungen jedoch wie vorgeschrieben implementieren. 

## <a name="intended-audience"></a>Zielgruppe

Diese Empfehlungen sind für Enterprise-Architekten und IT-Experten gedacht, die mit [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) und [Microsoft Enterprise Mobility + Security](http://microsoft.com/ems)vertraut sind und unter anderem Azure Active Directory (Identity), Microsoft InTune (Geräteverwaltung) und Azure Information Protection (Datenschutz).

### <a name="customer-environment"></a>Kundenumgebung

Die empfohlenen Richtlinien gelten für Unternehmensorganisationen, die sowohl vollständig innerhalb der Microsoft-Cloud als auch für Kunden mit einer hybriden Infrastrukturarbeiten (sowohl lokal als auch in der Microsoft-Cloud bereitgestellt).

Viele der bereitgestellten Empfehlungen basieren auf Diensten, die nur für Enterprise Mobility + Security (EMS) E5-Lizenzen verfügbar sind. Empfohlene Empfehlungen übernehmen die vollständigen EMS E5-Lizenz Funktionen.

Für Organisationen, die über keine Enterprise Mobility + Security E5-Lizenzen verfügen, empfiehlt Microsoft, dass Sie mindestens Azure AD Baseline Protection-Funktionen implementieren, die in allen Plänen enthalten sind. Weitere Informationen finden Sie im Artikel [Was ist Grund](/azure/active-directory/active-directory-conditional-access-baseline-protection)legender Schutz in der Azure AD-Bibliothek.

### <a name="caveats"></a>Warnhinweise

Ihre Organisation unterliegt möglicherweise behördlichen oder anderen Compliance-Anforderungen, einschließlich spezifischer Empfehlungen, die Sie möglicherweise zum Anwenden von Richtlinien benötigen, die von diesen empfohlenen Konfigurationen abweichen. Diese Konfigurationen empfehlen Verwendungs Steuerelemente, die nicht historisch verfügbar waren. Wir empfehlen diese Steuerelemente, da wir glauben, dass Sie eine Balance zwischen Sicherheit und Produktivität darstellen.  

Wir haben unser Bestes getan, um eine Vielzahl von Anforderungen des organisatorischen Schutzes zu berücksichtigen, aber wir können nicht alle möglichen Anforderungen oder alle eindeutigen Aspekte Ihrer Organisation berücksichtigen.

## <a name="three-tiers-of-protection"></a>Drei Schutzebenen

Die meisten Organisationen haben spezifische Anforderungen bezüglich Datensicherheit und Datenschutz. Diese Anforderungen variieren je nach Branche und Tätigkeiten im Unternehmen. Angenommen, Ihre Rechtsabteilung und Office 365-Administratoren erfordern möglicherweise zusätzliche Sicherheit- und Informationsschutzüberprüfungen für die E-Mail-Korrespondenz, die nicht für andere Benutzer des Geschäftsbereich erforderlich sind. 

Jede Branche verfügt auch über ihren eigenen Satz von spezialisierten Vorschriften. Anstatt eine Liste aller möglichen Sicherheitsoptionen oder eine Empfehlung pro Branchensegment oder Job-Funktion bereitzustellen, wurden Empfehlungen für drei verschiedene Sicherheits-und Schutzebenen bereitgestellt, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können. .

- **Basisschutz**: Es wird empfohlen, einen Mindeststandard für den Schutz von Daten sowie die Identitäten und Geräte einzurichten, die auf Ihre Daten zugreifen. Sie können diese Basis Empfehlungen befolgen, um einen starken Standardschutz zu bieten, der den Anforderungen vieler Organisationen entspricht.
- **Vertraulicher Schutz**: einige Kunden verfügen über eine Teilmenge von Daten, die auf höheren Ebenen geschützt werden müssen, oder Sie erfordern möglicherweise, dass alle Daten auf einer höheren Ebene geschützt werden. Sie können den verstärkten Schutz auf alle oder bestimmte Datensätze in Ihrer Office 365-Umgebung anwenden. Es wird empfohlen, Identitäten und Geräte mit Zugriff auf sensible Daten mit einem vergleichbaren Grad an Sicherheit auszustatten.  
- **Stark reguliert**: einige Organisationen verfügen möglicherweise über eine geringe Menge an Daten, die hochgradig klassifiziert sind, consititutes Geschäftsgeheimnisse aufweisen oder Daten reguliert werden. Microsoft stellt Funktionen bereit, die es Organisationen ermöglichen, diese Anforderungen zu erfüllen, wie etwa den zusätzlichen Schutz von Identitäten und Geräten.

![Security Cone-alle Kunden > einige Kunden > bestimmte Kunden. Breite Anwendung für eine bestimmte Anwendung](../images/M365-idquality-threetiers.png)

In diesem Handbuch wird gezeigt, wie Sie Schutz für Identitäten und Geräte für jede dieser Schutzebenen implementieren. Verwenden Sie diese Richtlinien als Ausgangspunkt für Ihre Organisation, und passen Sie die Richtlinien an, um die spezifischen Anforderungen Ihrer Organisation zu erfüllen.

Es ist wichtig, konsistente Schutzebenen für Ihre Daten, Identitäten und Geräte zu verwenden. Wenn Sie beispielsweise dieses Handbuch implementieren, achten Sie darauf, Ihre Daten auf vergleichbaren Ebenen zu schützen. Diese Architekturmodelle zeigen, welche Funktionen vergleichbar sind.

**Identität- und Geräteschutz für Office 365**<br/>
![Miniaturansicht für das Poster "Identitäts-und Geräteschutz für Office 365"](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55032)

**Lösungen zum Schutz von Dateien in Office 365**<br/>
![Miniaturansicht für Poster "Dateischutz Lösungen in Office 365"](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Kompromisse in den Bereichen Sicherheit und Produktivität

Die Implementierung einer Sicherheitsstrategie erfordert Kompromisse zwischen Sicherheit und Produktivität. Es ist hilfreich zu bewerten, wie sich jede Entscheidung auf die Balance zwischen Sicherheit, Funktionalität und Benutzerfreundlichkeit auswirkt.

![Sicherheits-Triade, die Sicherheit, Funktionalität und Benutzerfreundlichkeit ausgleicht.](media/policies-configurations/security-triad.png)

Die bereitgestellten Empfehlungen basieren auf den folgenden Prinzipien:

- Kennen Sie Ihre Zielgruppe und seien Sie flexibel für Ihre Sicherheits-und funktionalen Anforderungen.
- Wenden Sie eine Sicherheitsrichtlinie rechtzeitig an, und stellen Sie sicher, dass Sie sinnvoll ist.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Dienste und Konzepte für den Identitäts-und Gerätezugriffs Schutz

Microsoft 365 Enterprise ist für große Organisationen konzipiert und integriert Office 365 Enterprise, Windows 10 Enterprise und Enterprise Mobility + Security (EMS), um alle Benutzer kreativ zu machen und sicher zu arbeiten.

Dieser Abschnitt bietet eine Übersicht über die Microsoft 365-Dienste und-Funktionen, die für den Identitäts-und Geräte Zugriff wichtig sind.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD bietet eine umfassende Palette an Identitäts Verwaltungsfunktionen. Zur Sicherung des Zugriffs empfehlen wir die folgenden Funktionen:

- **[Self-Service Password Reset (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: ermöglichen Sie Ihren Benutzern, ihre Kennwörter sicher und ohne Helpdesk-Intervention zurückzusetzen, indem Sie mehrere Authentifizierungsmethoden überprüfen, die der Administrator kontrollieren kann.

- **[Multi-Factor Authentication (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)**: MFA erfordert, dass Benutzer zwei Arten der Überprüfung bereitstellen, beispielsweise ein Benutzerkennwort sowie eine Benachrichtigung von der Microsoft Authenticator-APP oder einem Telefonanruf. MFA reduziert das Risiko, dass eine gestohlene Identität für den Zugriff auf Ihre Office 365-Umgebung verwendet werden kann, erheblich.

- **[Bedingter Zugriff](/azure/active-directory/conditional-access/overview)**: Azure AD wertet die Bedingungen der Benutzeranmeldung aus und verwendet die von Ihnen erstellten bedingten Zugriffsrichtlinien, um den Zugriff zuzulassen. In diesem Handbuch wird beispielsweise gezeigt, wie Sie eine Richtlinie für den bedingten Zugriff erstellen, die die Geräte Konformität für den Zugriff auf vertrauliche Daten erfordert. Dadurch wird das Risiko erheblich reduziert, dass ein Hacker mit einer gestohlenen Identität auf Ihre vertraulichen Daten zugreifen kann. Außerdem werden vertrauliche Daten auf den Geräten geschützt, da die Geräte bestimmte Anforderungen an Gesundheit und Sicherheit erfüllen.

- **[Azure Ad-Gruppen](/azure/active-directory/fundamentals/active-directory-manage-groups)**: Regeln für bedingten Zugriff, Geräteverwaltung mit InTune und sogar Berechtigungen für Dateien und Websites in Ihrer Organisation basieren auf der Zuweisung zu Benutzer-und/oder Azure Ad-Gruppen. Es wird empfohlen, Azure AD-Gruppen zu erstellen, die den Schutzebenen entsprechen, die Sie implementieren. Beispielsweise sind Ihre Führungskräfte wahrscheinlich höhere Wert Ziele für Hacker. Daher ist es sinnvoll, diese Mitarbeiter einer Azure AD-Gruppe zuzuweisen und diese Gruppe den Richtlinien für den bedingten Zugriff und anderen Richtlinien zuzuweisen, die einen höheren Schutz für den Zugriff erzwingen.

- **[Geräteregistrierung](/azure/active-directory/devices/overview)**: Sie registrieren ein Gerät in Azure AD, um dem Gerät eine Identität bereitzustellen. Diese Identität wird verwendet, um das Gerät zu authentifizieren, wenn sich ein Benutzer anmeldet und Regeln für den bedingten Zugriff anzuwenden, die Domänen-oder kompatible PCs erfordern. Für diese Richtlinie verwenden wir die Geräteregistrierung, um automatisch Domänen verbundene Windows-Computer zu registrieren. Die Geräteregistrierung ist eine Voraussetzung für die Verwaltung von Geräten mit InTune. 

- **[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)**: Azure AD Identity Protection ermöglicht es Ihnen, potenzielle Sicherheitsrisiken zu ermitteln, die sich auf die Identitäten Ihrer Organisation auswirken, und die automatische Korrektur Richtlinie auf niedriges, mittleres und hohes Anmelde-und Benutzer Risiko zu konfigurieren. Diese Richtlinie basiert auf dieser Risikobewertung, um Richtlinien für bedingten Zugriff für die mehrstufige Authentifizierung anzuwenden. Dieser Leitlinie enthält auch eine Richtlinie für den bedingten Zugriff, bei der Benutzer Ihr Kennwort ändern müssen, wenn die Aktivität mit hohem Risiko für Ihr Konto erkannt wird.

### <a name="microsoft-intune"></a>Microsoft Intune

[InTune](https://docs.microsoft.com/intune/introduction-intune) ist der Cloud-basierte Verwaltungsdienst für mobile Geräte von Microsoft. In diesem Handbuch wird die Geräteverwaltung von Windows-PCs mit InTune empfohlen und die Konfiguration der Geräte Kompatibilitätsrichtlinien empfohlen. InTune bestimmt, ob Geräte kompatibel sind, und sendet diese Daten an Azure AD, um Sie beim Anwenden von Richtlinien für bedingten Zugriff zu verwenden.

#### <a name="intune-app-protection"></a>InTune-App-Schutz

[InTune-App-Schutz](https://docs.microsoft.com/intune/app-protection-policy) Richtlinien können verwendet werden, um die Daten Ihrer Organisation in mobilen apps zu schützen, mit oder ohne Registrierung von Geräten in der Verwaltung. InTune schützt Office 365-Informationen und stellt sicher, dass Ihre Mitarbeiter weiterhin produktiv arbeiten und Datenverluste verhindern können. Durch das Implementieren von Richtlinien auf App-Ebene können Sie den Zugriff auf Unternehmensressourcen einschränken und Daten in der Steuerung Ihrer IT-Abteilung speichern.

In diesem Handbuch wird erläutert, wie Sie empfohlene Richtlinien erstellen, um die Verwendung genehmigter apps zu erzwingen und um zu bestimmen, wie diese apps mit ihren Geschäftsdaten verwendet werden können.

### <a name="office-365"></a>Office 365

In diesem Handbuch wird gezeigt, wie Sie eine Reihe von Richtlinien zum Schutz des Zugriffs auf Office 365 implementieren, einschließlich Exchange Online, SharePoint Online und OneDrive for Business. Zusätzlich zur Implementierung dieser Richtlinien sollten Sie auch den Schutzgrad für Ihren Office 365-Mandanten mit den folgenden Ressourcen erhöhen:

- [Konfigurieren Sie Ihren office 365-Mandanten für mehr Sicherheit](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355): Diese Empfehlungen gelten für die grundlegende Sicherheit für ihren Office 365-Mandanten.
- [Office 365 Security Roadmap: die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352): Diese Empfehlungen betreffen Protokollierung, Datensteuerung, Administratorzugriff und Bedrohungsschutz.
- [Sichere SharePoint Online-Websites und-Dateien](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files): in diesem Artikel wird beschrieben, wie Sie Dateien und Websites auf geeigneten Ebenen für grundlegende, vertrauliche und hochgradig vertraulichen Schutz schützen.

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 und Office 365 ProPlus

Windows 10 und Office 365 proPlus ist die empfohlene Clientumgebung für PCs. Wir empfehlen Windows 10, da Azure so konzipiert wurde, dass sowohl lokale als auch Azure AD eine optimale Lösung bieten. Windows 10 enthält außerdem erweiterte Sicherheitsfunktionen, die über InTune verwaltet werden können. Office 365 proPlus enthält die neuesten Versionen von Office-Anwendungen. Diese verwenden eine moderne Authentifizierung, die sicherer und eine Voraussetzung für bedingten Zugriff ist. Zu diesen apps gehört auch erweiterte Sicherheits-und Konformitäts Tools.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Anwenden dieser Funktionen auf die drei Schutzebenen

In der folgenden Tabelle werden unsere Empfehlungen für die Verwendung dieser Funktionen für die drei Schutzebenen zusammengefasst.

|Schutzmechanismus|Baseline|Vertraulich|Hoch reguliert|
|:-------------------|:-------|:--------|:---------------|
|**MFA erzwingen**|Bei mittlerem oder höherem Anmelderisiko|Bei niedrigem oder höherem Anmelderisiko|Auf alle neuen Sitzungen|
|**Kennwortänderung erzwingen**|Für Benutzer mit hohem Risiko|Für Benutzer mit hohem Risiko|Für Benutzer mit hohem Risiko|
|**Erzwingung des InTune-Anwendungsschutzes**|Ja|Ja|Ja|
|**Erzwingung der InTune-Registrierung (COD)**|Sie benötigen einen kompatiblen oder einem Domänen beigetretenen PC, lassen aber BYOD-Telefone/Tablets zu|Erforderliches kompatibles oder Domänen verbundenes Gerät|Erforderliches kompatibles oder Domänen verbundenes Gerät|

## <a name="device-ownership"></a>Gerätebesitz

Die obige Tabelle spiegelt den Trend für viele Organisationen wider, eine Kombination aus unternehmenseigenen Geräten sowie persönliche oder eigene Geräte (BYODs) zu unterstützen, um die mobile Produktivität über die gesamte Belegschaft hinweg zu ermöglichen. InTune-App-Schutzrichtlinien stellen sicher, dass e-Mails von exfiltrating aus der mobilen Outlook-APP und anderen Office Mobile-Apps auf beiden unternehmenseigenen Geräten und BYODs geschützt werden.  

Wir empfehlen, dass unternehmenseigene Geräte von InTune oder Domänen verbunden verwaltet werden, um zusätzliche Schutzfunktionen und Kontrolle zu übernehmen. Je nach Datenvertraulichkeit kann Ihre Organisation BYODs für bestimmte Benutzer Populationen oder bestimmte apps nicht zulassen.

## <a name="next-steps"></a>Nächste Schritte

[VoraussetZungen für die Implementierung von Identitäts-und Gerätezugriffs Richtlinien](identity-access-prerequisites.md)
