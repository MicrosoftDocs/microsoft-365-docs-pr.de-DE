---
title: Identitäts- und Gerätezugriffskonfigurationen – Microsoft 365 für Unternehmen
description: Beschreibt Microsoft-Empfehlungen und Kernkonzepte für die Bereitstellung sicherer E-Mails, Dokumente und Apps-Richtlinien und -Konfigurationen.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: 464a99ca67da72633879840263fe64ad8311fd4c
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952572"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationen für den Identitäts- und Gerätezugriff

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)

Der moderne Sicherheitsperimeter Ihrer Organisation erstreckt sich nun über Ihr Netzwerk hinaus und umfasst Benutzer, die von einem beliebigen Standort aus auf cloudbasierte Apps mit einer Vielzahl von Geräten zugreifen. Ihre Sicherheitsinfrastruktur muss ermitteln, ob eine bestimmte Zugriffsanforderung gewährt werden soll und unter welchen Bedingungen.

Diese Bestimmung sollte auf dem Benutzerkonto der Anmeldung, dem verwendeten Gerät, der App, die der Benutzer für den Zugriff verwendet, dem Speicherort, von dem aus die Zugriffsanforderung erfolgt, und einer Bewertung des Risikos der Anforderung basieren. Diese Funktion trägt dazu bei, sicherzustellen, dass nur autorisierte Benutzer und Geräte auf Ihre kritischen Ressourcen zugreifen können.

In dieser Artikelreihe werden eine Reihe von Konfigurationen für voraussetzungenbasierte Identitäts- und Gerätezugriffsvoraussetzungen sowie eine Reihe von Azure Active Directory (Azure AD) Bedingter Zugriff, Microsoft Intune und andere Richtlinien zum Sichern des Zugriffs auf Microsoft 365 für Enterprise-Cloud-Apps und -Dienste, andere SaaS-Dienste und lokale Anwendungen beschrieben, die mit dem Azure AD-Anwendungsproxy veröffentlicht wurden.

Identitäts- und Gerätezugriffseinstellungen und -richtlinien werden in drei Ebenen empfohlen: Basisschutz, vertraulicher Schutz und Schutz für Umgebungen mit streng regulierten oder klassifizierten Daten. Diese Ebenen und die entsprechenden Konfigurationen bieten einheitliche Schutzniveaus für Ihre Daten, Identitäten und Geräte.

Diese Funktionen und ihre Empfehlungen:

- Werden in Microsoft 365 E3 und Microsoft 365 E5.
- Werden an [der Microsoft Secure Score](../defender/microsoft-secure-score.md) sowie der [Identitätspunktzahl in Azure AD](/azure/active-directory/fundamentals/identity-secure-score)ausgerichtet und erhöhen diese Bewertungen für Ihre Organisation.
- Wird Ihnen dabei helfen, diese [fünf Schritte zum Sichern Ihrer Identitätsinfrastruktur zu implementieren.](/azure/security/azure-ad-secure-steps)

Wenn Ihre Organisation eindeutige Umgebungsanforderungen oder Komplexitäten hat, verwenden Sie diese Empfehlungen als Ausgangspunkt. Die meisten Organisationen können diese Empfehlungen jedoch wie vorgeschrieben implementieren.

Sehen Sie sich dieses Video an, um einen schnellen Überblick über Identitäts- und Gerätezugriffskonfigurationen Microsoft 365 Unternehmen zu erhalten.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft verkauft auch Enterprise Mobility + Security (EMS)-Lizenzen für Office 365 Abonnements. EMS E3- und EMS E5-Funktionen entsprechen denen in Microsoft 365 E3 und Microsoft 365 E5. Weitere [Informationen finden Sie unter EMS-Pläne.](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing)

## <a name="intended-audience"></a>Zielgruppe

Diese Empfehlungen sind für Unternehmensarchitekten und IT-Experten gedacht, die mit Microsoft 365 cloud productivity and security services vertraut sind, einschließlich Azure AD (Identity), Microsoft Intune (Geräteverwaltung) und Microsoft Information Protection (Datenschutz).

### <a name="customer-environment"></a>Kundenumgebung

Die empfohlenen Richtlinien gelten für Unternehmen, die vollständig in der Microsoft-Cloud arbeiten, und für Kunden mit hybrider Identitätsinfrastruktur, einer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur, die mit einem Azure AD-Mandanten synchronisiert wird.

Viele der bereitgestellten Empfehlungen beruhen auf Diensten, die nur mit Microsoft 365 E5, Microsoft 365 E3 E5 Security Add-On, EMS E5 oder Azure AD Premium P2-Lizenzen verfügbar sind.

Für Organisationen, die nicht über diese Lizenzen verfügen, empfiehlt Microsoft, mindestens Sicherheitseinstellungen zu [implementieren,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)die in allen Microsoft 365 sind.

### <a name="caveats"></a>Vorbehalte

Ihre Organisation unterliegt möglicherweise behördlichen oder anderen Complianceanforderungen, einschließlich spezifischer Empfehlungen, für die Sie Richtlinien anwenden müssen, die von diesen empfohlenen Konfigurationen abweichen. Diese Konfigurationen empfehlen Verwendungssteuerelemente, die bisher nicht verfügbar waren. Wir empfehlen diese Steuerelemente, da sie unserer Meinung nach ein Gleichgewicht zwischen Sicherheit und Produktivität darstellen.

Wir haben unser Bestes getan, um eine Vielzahl von Organisatorischen Schutzanforderungen zu berücksichtigen, aber wir sind nicht in der Lage, alle möglichen Anforderungen oder alle einzigartigen Aspekte Ihrer Organisation zu berücksichtigen.

## <a name="three-tiers-of-protection"></a>Drei Schutzebenen

Die meisten Organisationen haben spezifische Anforderungen bezüglich Datensicherheit und Datenschutz. Diese Anforderungen variieren je nach Branche und Tätigkeiten im Unternehmen. Beispielsweise benötigen Ihre Rechtsabteilung und Administratoren möglicherweise zusätzliche Sicherheits- und Informationsschutzkontrollen rund um ihre E-Mail-Korrespondenz, die für andere Unternehmenseinheiten nicht erforderlich sind.

Jede Branche verfügt auch über ihren eigenen Satz von spezialisierten Vorschriften. Anstatt eine Liste aller möglichen Sicherheitsoptionen oder eine Empfehlung pro Branchensegment oder Auftragsfunktion zur Verfügung zu stellen, wurden Empfehlungen für drei verschiedene Sicherheits- und Schutzebenen bereitgestellt, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können.

- **Basisplanschutz:** Es wird empfohlen, einen Mindeststandard für den Schutz von Daten sowie die Identitäten und Geräte zu erstellen, die auf Ihre Daten zugreifen. Sie können diese grundlegenden Empfehlungen befolgen, um einen starken Standardschutz zu bieten, der den Anforderungen vieler Organisationen entspricht.
- **Vertraulicher Schutz:** Einige Kunden verfügen über eine Teilmenge von Daten, die auf höheren Ebenen geschützt werden müssen, oder sie müssen möglicherweise alle Daten auf einer höheren Ebene schützen. Sie können einen erhöhten Schutz auf alle oder bestimmte Datensätze in Ihrer Microsoft 365 anwenden. Es wird empfohlen, Identitäten und Geräte mit Zugriff auf sensible Daten mit einem vergleichbaren Grad an Sicherheit auszustatten.
- **Streng reguliert:** Einige Organisationen verfügen möglicherweise über eine kleine Menge an Daten, die streng klassifiziert sind, Geschäftsgeheimnisse darstellen oder regulierte Daten sind. Microsoft stellt Funktionen bereit, die es Organisationen ermöglichen, diese Anforderungen zu erfüllen, wie etwa den zusätzlichen Schutz von Identitäten und Geräten.

![Sicherheitskegel – Alle Kunden > Einige Kunden > Kunden. Breite Anwendung auf eine bestimmte Anwendung](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

In diesem Leitfaden wird gezeigt, wie Sie den Schutz für Identitäten und Geräte für jede dieser Schutzebenen implementieren. Verwenden Sie diese Anleitung als Ausgangspunkt für Ihre Organisation, und passen Sie die Richtlinien an die spezifischen Anforderungen Ihrer Organisation an.

Es ist wichtig, konsistente Schutzebenen für Daten, Identitäten und Geräte zu verwenden. Wenn Sie beispielsweise diese Anleitung implementieren, müssen Sie Ihre Daten auf vergleichbaren Ebenen schützen.

Der **Identitäts- und Geräteschutz für Microsoft 365** architekturmodell zeigt, welche Funktionen vergleichbar sind.

[![Thumb image for Identity and device protection for Microsoft 365 poster](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [Anzeigen als PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Als PDF herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Herunterladen als Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Weitere Informationen finden Sie unter [Deploy information protection for data privacy regulations solution](../../solutions/information-protection-deploy.md) to protect information stored in Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Kompromisse in den Bereichen Sicherheit und Produktivität

Die Implementierung jeder Sicherheitsstrategie erfordert Trade-offs zwischen Sicherheit und Produktivität. Es ist hilfreich zu bewerten, wie sich jede Entscheidung auf das Gleichgewicht von Sicherheit, Funktionalität und Benutzerfreundlichkeit auswirkt.

![Sicherheitstriaden für Sicherheit, Funktionalität und Benutzerfreundlichkeit.](../../media/microsoft-365-policies-configurations/security-triad.png)

Die bereitgestellten Empfehlungen basieren auf den folgenden Grundsätzen:

- Kennen Sie Ihre Benutzer und können Sie flexibel auf ihre Sicherheits- und Funktionsanforderungen sein.
- Wenden Sie eine Sicherheitsrichtlinie just in time an, und stellen Sie sicher, dass sie sinnvoll ist.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Dienste und Konzepte für den Identitäts- und Gerätezugriffsschutz

Microsoft 365 für Unternehmen ist für große Organisationen konzipiert, um alle zu befähigen, kreativ zu sein und sicher zusammen zu arbeiten.

Dieser Abschnitt enthält eine Übersicht über Microsoft 365 Dienste und Funktionen, die für den Identitäts- und Gerätezugriff wichtig sind.

### <a name="azure-ad"></a>Azure AD

Azure AD bietet eine vollständige Suite von Identitätsverwaltungsfunktionen. Es wird empfohlen, diese Funktionen zum Sichern des Zugriffs zu verwenden.

|Funktion oder Feature|Beschreibung|Lizenzierung|
|---|---|---|
|[Mehrstufige Authentifizierung (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA erfordert, dass Benutzer zwei Arten der Überprüfung bereitstellen, z. B. ein Benutzerkennwort plus eine Benachrichtigung von der Microsoft Authenticator-App oder einem Telefonanruf. MFA reduziert das Risiko, dass gestohlene Anmeldeinformationen für den Zugriff auf Ihre Umgebung verwendet werden können, erheblich. Microsoft 365 verwendet den Azure AD-Mehrstufigen Authentifizierungsdienst für MFA-basierte Anmeldungen.|Microsoft 365 E3 oder E5|
|[Bedingter Zugriff](/azure/active-directory/conditional-access/overview)|Azure AD wertet die Bedingungen der Benutzer-Anmeldung aus und verwendet Richtlinien für bedingten Zugriff, um den zulässigen Zugriff zu bestimmen. In diesem Leitfaden wird beispielsweise gezeigt, wie Sie eine Richtlinie für bedingten Zugriff erstellen, um gerätekonformität für den Zugriff auf vertrauliche Daten zu verlangen. Dadurch wird das Risiko erheblich reduziert, dass ein Hacker mit seinem eigenen Gerät und gestohlenen Anmeldeinformationen auf Ihre vertraulichen Daten zugreifen kann. Außerdem werden vertrauliche Daten auf den Geräten geschützt, da die Geräte bestimmte Anforderungen an Integrität und Sicherheit erfüllen müssen.|Microsoft 365 E3 oder E5|
|[Azure AD-Gruppen](/azure/active-directory/fundamentals/active-directory-manage-groups)|Richtlinien für bedingten Zugriff, Geräteverwaltung mit Intune und sogar Berechtigungen für Dateien und Websites in Ihrer Organisation beruhen auf der Zuweisung zu Benutzerkonten oder Azure AD-Gruppen. Es wird empfohlen, Azure AD-Gruppen zu erstellen, die den von Ihnen implementierenen Schutzebenen entsprechen. Beispielsweise sind Ihre Führungskräfte wahrscheinlich höhere Wertziele für Hacker. Daher ist es sinnvoll, die Benutzerkonten dieser Mitarbeiter einer Azure AD-Gruppe hinzuzufügen und diese Gruppe Richtlinien für bedingten Zugriff und anderen Richtlinien zuzuordnen, die einen höheren Schutz für den Zugriff erzwingen.|Microsoft 365 E3 oder E5|
|[Geräteregistrierung](/azure/active-directory/devices/overview)|Sie registrieren ein Gerät bei Azure AD, um eine Identität für das Gerät zu erstellen. Diese Identität wird verwendet, um das Gerät zu authentifizieren, wenn sich ein Benutzer anmeldet, und um Richtlinien für bedingten Zugriff anzuwenden, für die in die Domäne getretene oder kompatible PCs erforderlich sind. Für diese Anleitung verwenden wir die Geräteregistrierung, um automatisch domänenbeigetretene Computer Windows registrieren. Die Geräteregistrierung ist eine Voraussetzung für die Verwaltung von Geräten mit Intune.|Microsoft 365 E3 oder E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Ermöglicht ihnen das Erkennen potenzieller Sicherheitsrisiken, die sich auf die Identität Ihrer Organisation ausdingen, und die Konfiguration einer automatisierten Korrekturrichtlinie auf ein niedriges, mittleres und hohes Anmelde- und Benutzerrisiko. Diese Anleitung basiert auf dieser Risikobewertung, um Richtlinien für bedingten Zugriff für die mehrstufige Authentifizierung anzuwenden. Diese Anleitung enthält auch eine Richtlinie für bedingten Zugriff, nach der Benutzer ihr Kennwort ändern müssen, wenn für ihr Konto Aktivitäten mit hohem Risiko erkannt werden.|Microsoft 365 E5, Microsoft 365 E3 E5 Security Add-On, EMS E5 oder Azure AD Premium P2-Lizenzen|
|[Self-Service Password Reset (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Ermöglichen Sie Benutzern, ihre Kennwörter sicher und ohne Helpdeskeingriff zurückzusetzen, indem Sie die Überprüfung mehrerer Authentifizierungsmethoden bereitstellen, die der Administrator steuern kann.|Microsoft 365 E3 oder E5|
|[Azure AD-Kennwortschutz](/azure/active-directory/authentication/concept-password-ban-bad)|Erkennen und blockieren Sie bekannte schwache Kennwörter und deren Varianten sowie zusätzliche schwache Begriffe, die spezifisch für Ihre Organisation sind. Listen standardmäßig global gesperrter Kennwörter werden automatisch auf alle Benutzer in einem Azure AD-Mandanten angewendet. Sie können zusätzliche Einträge in einer benutzerdefinierten Liste gesperrter Kennwörter angeben. Wenn Benutzer ihre Kennwörter ändern oder zurücksetzen, werden diese Listen gesperrter Kennwörter überprüft, um die Verwendung von sicheren Kennwörtern zu erzwingen.|Microsoft 365 E3 oder E5|
|

Hier sind die Komponenten des Identitäts- und Gerätezugriffs, einschließlich Intune- und Azure AD-Objekten, Einstellungen und Unterdiensten.

![Komponenten des Identitäts- und Gerätezugriffs](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune) ist der cloudbasierte Verwaltungsdienst für mobile Geräte von Microsoft. In diesem Leitfaden wird die Geräteverwaltung von Windows PCs mit Intune und Richtlinienkonfigurationen für Gerätekonformität empfohlen. Intune bestimmt, ob Geräte kompatibel sind, und sendet diese Daten an Azure AD zur Verwendung beim Anwenden von Richtlinien für bedingten Zugriff.

#### <a name="intune-app-protection"></a>Intune-App-Schutz

[Intune-App-Schutzrichtlinien](/intune/app-protection-policy) können verwendet werden, um die Daten Ihrer Organisation in mobilen Apps zu schützen, mit oder ohne Geräte für die Verwaltung zu registrieren. Intune trägt zum Schutz von Informationen bei, stellt sicher, dass Ihre Mitarbeiter weiterhin produktiv sein können, und verhindert Datenverluste. Durch die Implementierung von Richtlinien auf App-Ebene können Sie den Zugriff auf Unternehmensressourcen einschränken und Daten in der Kontrolle Ihrer IT-Abteilung behalten.

In diesem Leitfaden erfahren Sie, wie Sie empfohlene Richtlinien erstellen, um die Verwendung genehmigter Apps zu erzwingen und zu bestimmen, wie diese Apps mit Ihren Geschäftsdaten verwendet werden können.

### <a name="microsoft-365"></a>Microsoft 365

In diesem Leitfaden wird gezeigt, wie Sie eine Reihe von Richtlinien implementieren, um den Zugriff auf Microsoft 365-Clouddienste zu schützen, einschließlich Microsoft Teams, Exchange Online, SharePoint Online und OneDrive for Business. Neben der Implementierung dieser Richtlinien wird empfohlen, dass Sie auch das Schutzniveau für Ihren Mandanten erhöhen, indem Sie die folgenden Ressourcen verwenden:

- [Konfigurieren Ihres Mandanten für höhere Sicherheit](tenant-wide-setup-for-increased-security.md)

  Empfehlungen, die für die Basissicherheit für Ihren Mandanten gelten.

- [Sicherheits-Roadmap: Die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md)

  Empfehlungen, die Protokollierung, Datenverwaltung, Administratorzugriff und Bedrohungsschutz umfassen.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 und Microsoft 365 Apps for Enterprise

Windows 10 mit Microsoft 365 Apps for Enterprise ist die empfohlene Clientumgebung für PCs. Wir empfehlen Windows 10, da Azure so konzipiert ist, dass sowohl für lokale als auch für Azure AD eine möglichst reibungslose Oberfläche bereitgestellt wird. Windows 10 umfasst auch erweiterte Sicherheitsfunktionen, die über Intune verwaltet werden können. Microsoft 365 Apps for Enterprise enthält die neuesten Versionen Office Anwendungen. Diese verwenden eine moderne Authentifizierung, die sicherer ist und bedingten Zugriff erfordert. Diese Apps enthalten auch erweiterte Sicherheits- und Compliancetools.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Anwenden dieser Funktionen auf die drei Schutzebenen

In der folgenden Tabelle sind unsere Empfehlungen für die Verwendung dieser Funktionen in den drei Schutzebenen zusammengefasst.

|Schutzmechanismus|Baseline|Vertraulich|Streng geregelt|
|---|---|---|---|
|**MFA erzwingen**|Bei mittlerem oder höherem Anmelderisiko|Bei niedrigem oder höherem Anmelderisiko|Auf alle neuen Sitzungen|
|**Erzwingen der Kennwortänderung**|Für Benutzer mit hohem Risiko|Für Benutzer mit hohem Risiko|Für Benutzer mit hohem Risiko|
|**Erzwingen des Intune-Anwendungsschutzes**|Ja|Ja|Ja|
|**Erzwingen der Intune-Registrierung für Geräte im Besitz der Organisation**|Benötigen Sie einen kompatiblen PC oder einen in die Domäne mit der Domäne verbundenen PC, lassen Sie jedoch byod-Telefone und Tablets (Bring-your-own Devices) zu.|Erfordern eines kompatiblen oder in die Domäne mit der Domäne verbundenen Geräts|Erfordern eines kompatiblen oder in die Domäne mit der Domäne verbundenen Geräts|
|

## <a name="device-ownership"></a>Gerätebesitz

Die obige Tabelle spiegelt den Trend vieler Organisationen wider, eine Mischung aus unternehmenseigenen Geräten sowie persönlichen oder BYODs zu unterstützen, um die mobile Produktivität in der gesamten Belegschaft zu ermöglichen. Intune-App-Schutzrichtlinien stellen sicher, dass E-Mails nicht aus der mobilen Outlook-App und anderen Office mobilen Apps auf Geräten im Besitz der Organisation und BYODs entfernt werden.

Es wird empfohlen, geräte im Besitz der Organisation von Intune oder der Domäne verwaltet zu werden, um zusätzlichen Schutz und Kontrolle anzuwenden. Je nach Datensensitivität kann Ihre Organisation BYODs für bestimmte Benutzerpopulationen oder bestimmte Apps nicht zulassen.

## <a name="deployment-and-your-apps"></a>Bereitstellung und Ihre Apps

Vor dem Konfigurieren und Bereitstellen der Identitäts- und Gerätezugriffskonfiguration für Ihre Azure AD-integrierten Apps müssen Sie:

- Entscheiden Sie, welche Apps in Ihrer Organisation verwendet werden, die Sie schützen möchten.
- Analysieren Sie diese Liste von Apps, um die Richtliniensätze zu ermitteln, die geeignete Schutzebenen bieten.

  Sie sollten keine separaten Richtliniensätze für jede App erstellen, da deren Verwaltung umständlich werden kann. Microsoft empfiehlt, Ihre Apps zu gruppieren, die die gleichen Schutzanforderungen für dieselben Benutzer haben.

  Sie könnten beispielsweise einen Satz von Richtlinien haben, die alle Microsoft 365-Apps für alle Benutzer für den Basisschutz und einen zweiten Satz von Richtlinien für alle vertraulichen Apps umfassen, z. B. die, die von Personalabteilungen oder Finanzabteilungen verwendet werden, und sie auf diese Gruppen anwenden.

Nachdem Sie den Satz von Richtlinien für die Apps bestimmt haben, die Sie sichern möchten, führen Sie die Richtlinien inkrementell auf Ihre Benutzer aus, und beheben Sie dabei Probleme.

Konfigurieren Sie beispielsweise die Richtlinien, die für alle Ihre Microsoft 365-Apps verwendet werden, nur für Exchange Online mit den zusätzlichen Änderungen für Exchange. Führen Sie diese Richtlinien für Ihre Benutzer aus, und arbeiten Sie an allen Problemen. Fügen Sie dann Teams zusätzlichen Änderungen hinzu, und stellen Sie dies für Ihre Benutzer vor. Fügen Sie dann SharePoint zusätzlichen Änderungen hinzu. Fahren Sie mit dem Hinzufügen der restlichen Apps fort, bis Sie diese Basisrichtlinien so konfigurieren können, dass alle Microsoft 365 werden.

Erstellen Sie auf ähnliche Weise für Ihre vertraulichen Apps den Satz von Richtlinien, fügen Sie eine App gleichzeitig hinzu, und arbeiten Sie alle Probleme durch, bis sie alle in den Richtliniensatz für vertrauliche Apps einbezogen sind.

Microsoft empfiehlt, keine Richtliniensätze zu erstellen, die für alle Apps gelten, da dies zu unbeabsichtigten Konfigurationen führen kann. Beispielsweise könnten Richtlinien, die alle Apps blockieren, Ihre Administratoren aus dem Azure-Portal sperren, und Ausschlüsse können nicht für wichtige Endpunkte wie Microsoft Graph.

## <a name="steps-to-configure-identity-and-device-access"></a>Schritte zum Konfigurieren des Identitäts- und Gerätezugriffs

![Schritte zum Konfigurieren des Identitäts- und Gerätezugriffs.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Konfigurieren sie erforderliche Identitätsfeatures und deren Einstellungen.
2. Konfigurieren Sie die allgemeinen Identitäts- und Zugriffsrichtlinien für bedingten Zugriff.
3. Konfigurieren sie Richtlinien für bedingten Zugriff für Gastbenutzer und externe Benutzer.
4. Konfigurieren sie Richtlinien für bedingten Zugriff für Microsoft 365 Cloud-Apps, z. B. Microsoft Teams, Exchange Online und SharePoint-, Microsoft Cloud App Security-Richtlinien.

Nachdem Sie den Identitäts- und Gerätezugriff konfiguriert haben, finden Sie im Azure AD-Featurebereitstellungshandbuch eine schrittweise Prüfliste mit zusätzlichen zu berücksichtigenden Features und [Azure AD Identity Governance](/azure/active-directory/governance/) zum Schützen, Überwachen und Überwachen des Zugriffs. [](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2)

## <a name="next-step"></a>Nächster Schritt

[Erforderliche Arbeit für die Implementierung von Identitäts- und Gerätezugriffsrichtlinien](identity-access-prerequisites.md)