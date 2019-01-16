---
title: Microsoft 365 Enterprise-Dienste – Übersicht | Microsoft-Dokumentation
description: Hier finden Sie eine Übersicht über Microsoft 365 Enterprise und Nutzungsempfehlungen für Enterprise.
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868120"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Dienste und Konzepte von Microsoft 365 Enterprise

Microsoft 365 Enterprise ist für große Organisationen konzipiert, und darin sind Office 365 Enterprise, Windows 10 Enterprise und Enterprise Mobility + Security (EMS) integriert, um allen Beschäftigten zu ermöglichen, auf sichere Weise kreativ zu sein und zusammenzuarbeiten. Microsoft 365 Enterprise enthält eine Enterprise Edition von Windows 10 und Office-Anwendungen über Office 365 ProPlus.

Sowohl für Windows 10 als auch Office 365 ProPlus werden dem Unternehmen im März und September über den halbjährigen Kanal Releases neuer Features bereitgestellt. Für ein über den halbjährigen Kanal bereitgestelltes Featurerelease wird 18 Monate lang Support geboten. Microsoft Intune und System Center Configuration Manager bieten Funktionen zum Bereitstellen und Aktualisieren von Windows 10 und Office 365 ProPlus.

Dies sind die aktuellen Versionen von Windows 10, Office 365 ProPlus, Microsoft Intune und System Center Configuration Manager:

|     |**Halbjähriger Kanal (gezielt)**|**Halbjähriger Kanal**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (demnächst verfügbar)|Version 1703|
|**Office 365 ProPlus**|Version 1803|Version 1708|
|**Intune**|N/V|Version 1708|
|**System Center Configuration Manager**|Technical Preview Version 1708|Version 1706<sup>*</sup>|

<sup>*</sup> Das Update 1706 für System Center Configuration Manager (Current Branch) ist als konsoleninternes Update für zuvor installierte Standorte verfügbar, die Version 1606, 1610 oder 1702 ausführen.

> [!NOTE]
> Microsoft Azure-Dienste werden auch in regelmäßigen Abständen aktualisiert, aber nicht mit Versionsnummern versehen. Die [Cloud platform roadmap](https://www.microsoft.com/cloud-platform/roadmap) (Roadmap für die Cloudplattform) informiert Sie über die neuesten Updates und sonstige zukünftige Neuheiten für Azure-Dienste.

Weitere Informationen zu den in diesen Versionen verfügbaren Features finden Sie in den folgenden Artikeln:
- [Neuigkeiten in Windows 10](https://docs.microsoft.com/windows/whats-new/)
- [Windows 10-Versionsinformationen](https://technet.microsoft.com/windows/release-info)
- [Windows 10-Updateverlauf](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Office 365-Clientupdate-Kanalversionen](https://technet.microsoft.com/office/mt465751)
- [Neuerungen in Microsoft Intune](https://docs.microsoft.com/intune/whats-new)
- [Neuerungen in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [Funktionen in der Technical Preview 1708 für System Center Configuration Manager](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="services-overview"></a>Übersicht über Dienste

In diesem Abschnitt finden Sie eine Übersicht über die EMS- und Office 365-Dienste, die in Microsoft 365 Enterprise enthalten sind. Darüber hinaus finden Sie eine Einführung in die grundlegenden Konzepte, die nötig sind, um es den Anforderungen Ihrer Organisation entsprechend optimal zu verwenden. Diese Dienste bieten Funktionen, die es den Administratoren von Microsoft-Clouddiensten in Ihrem Unternehmen nicht nur ermöglicht, die Identitäten und Geräte der Angestellten Ihrer Organisation zu schützen, sondern auch den Zugriff auf Ihre Unternehmensdaten zu steuern, was sowohl während der Übertragung als auch während der Speicherung möglich ist.

|Dienst|Beschreibung|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD bietet umfassende Identitätsverwaltungsfunktionen, einschließlich mehrstufiger Authentifizierung, Geräteregistrierung, Self-Service-Kennwortverwaltung, Self-Service-Gruppenverwaltung, rollenbasierter Zugriffssteuerung, Nutzungsüberwachung für Anwendungen, umfassender Überwachung und Sicherheitsüberwachung und -warnungen.|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|Dieser Dienst ermöglicht es Ihnen, potenzielle Sicherheitslücken zu erkennen, die die Identitäten Ihrer Organisation betreffen und automatische Antworten bei geringem, mittlerem und hohem Anmelde- und Benutzerrisiko über die bedingten Zugriffsrichtlinien zu konfigurieren.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|Dieser Dienst ermöglicht es Organisationen, die Anzahl der Personen zu minimieren, die ständigen Zugriff auf privilegierte Vorgänge haben. Mit Azure AD Privileged Identity Management wird das Konzept des „berechtigten Administrators“ eingeführt. Berechtigte Administratoren sollten die Benutzer sein, die gelegentlich, aber nicht täglich, Zugriff auf privilegierte Vorgänge benötigen. Diese Rolle ist inaktiv, bis der Benutzer den Zugriff benötigt und dann den Aktivierungsprozess abschließt, der ihn für einen vorab festgelegten Zeitraum zum aktiven Administrator macht.|
|[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure Information Protection ist eine cloudbasierte Lösung, die im Lieferumfang des EMS E5-Angebots enthalten ist und eine Organisationen beim Klassifizieren, Bezeichnen und Schützen von Dokumenten und E-Mails unterstützt. Dies kann automatisch durch Administratoren, die Regeln und Bedingungen definieren, manuell durch Benutzer oder durch eine Kombination beider Verfahren erfolgen, indem Benutzern Vorschläge angezeigt werden. Sie verwenden Azure Information Protection-Bezeichnungen, um die Klassifizierung auf Dokumente und E-Mails anzuwenden. Damit ist die Klassifizierung jederzeit identifizierbar – unabhängig davon, wo die Daten gespeichert sind oder für wen sie freigegeben wurden.<br><br>Die Azure Information Protection-Richtlinieneinstellungen werden von [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms) geschützt. Wie bei Bezeichnern, die angewendet werden, bleibt der mithilfe von Rights Management angewendete Schutz unabhängig vom Ort an die Dokumente und E-Mails gebunden – sowohl innerhalb oder als auch außerhalb Ihrer Organisation bzw. der Netzwerke, Dateiserver und Anwendungen.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune ist ein cloudbasierter Enterprise Mobility-Verwaltungsdienst (Enterprise Mobility Management; EMM), der die Produktivität Ihrer Mitarbeiter unterstützt und gleichzeitig Ihre Unternehmensdaten schützt. Intune wird zur Identitäts- und Zugriffssteuerung eng in Azure AD integriert und zur Geräte- und Anwendungsverwaltung verwendet. Die Funktionen zur [Geräteverwaltung in Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) werden verwendet, um die Geräte (einschließlich Windows-PCs) Ihrer Benutzer zu konfigurieren und zu schützen.<br><br>Die Geräteverwaltungsfunktionen in Intune unterstützen sowohl die [Bring Your Own Device (BYOD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod)-Registrierung, durch die Benutzer Ihre persönlichen Smartphones, Tablets oder PCs anmelden können, als auch die Registrierung von [firmeneigenen Geräten (COD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices), durch die Verwaltungsszenarios wie die automatische Registrierung, gemeinsam genutzte Geräte oder Anforderungskonfigurationen für die vorab autorisierte Registrierung ermöglicht werden. Zur Erhöhung der Sicherheit können Sie sogar eine MFA zur Registrierung eines Geräts anfordern. Sobald ein Gerät für die Verwaltung registriert ist, kann Intune Gerätefunktionen und -einstellungen konfigurieren, um einen sicheren Zugriff auf Unternehmensressourcen zu aktivieren.|

## <a name="important-concepts-to-understand"></a>Erläuterung wichtiger Konzepte
Grundlegende Konzepte und EMS-Funktionen, mit denen Sie vertraut sein sollten, werden in der folgenden Tabelle beschrieben.

|Grundlegende Konzepte|Beschreibung|
|------------|-----------|
|[Azure Multi-Factor Authentication (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Azure MFA ist Microsofts zweistufige Überprüfungslösung, die einen sicheren Zugriff auf Daten und Anwendungen ermöglicht und gleichzeitig den Anspruch der Benutzer an einen einfachen Anmeldevorgang erfüllt. Sie bietet eine strenge Authentifizierung über eine Reihe von Überprüfungsmethoden, einschließlich Telefonanrufen, Textnachrichten oder Überprüfungen über mobile Apps.|
|[Azure AD Conditional Access (Bedingter Zugriff auf Azure AD)](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Diese Funktion von Azure AD ermöglicht es Ihnen, den Zugriff auf Cloud-Apps in Ihrer Umgebung basierend auf spezifischen Bedingungen zu erzwingen. Mit Steuerelementen können Sie entweder zusätzliche Anforderungen für den Zugriff festlegen oder ihn blockieren. Die Implementierung des bedingten Zugriffs basiert auf Richtlinien.|
|[Exchange Online Data Loss Prevention (DLP) (Verhindern von Datenverlust (DLP) für Exchange Online)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|Die Richtlinien zum Verhindern von Datenverlust (DLP) für Exchange Online sind als Premium-Funktion in Exchange Online Plan 2- und Office 365-Abonnements enthalten. Durch diese wird es Organisationen ermöglicht, vertrauliche Informationen in Office 365 zu identifizieren, zu überwachen und automatisch zu schützen.<br><br>Mit den DLP-Richtlinien von Exchange Online können Sie vertrauliche Informationen an vielen Standorten identifizieren, zum Beispiel Exchange Online, SharePoint Online und OneDrive for Business. Beispielsweise können Sie mit diesen Richtlinien Dokumente erkennen, die vertrauliche Informationen enthalten oder die versehentliche Freigabe von vertraulichen Informationen für Personen außerhalb Ihrer Organisation verhindern.|
|[Exchange Mail Flow/Transport Rules (E-Mail-Flussregeln/Transportregeln in Exchange)](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Die E-Mail-Flussregeln in Exchange, auch als Transportregeln bezeichnet, untersuchen Nachrichten, die an Ihre Organisation weitergeleitet werden, auf bestimmte Bedingungen und reagieren auf diese. Die E-Mail-Flussregeln sind wie die Posteingangsregeln, die in vielen E-Mail-Clients verfügbar sind. Der Hauptunterschied zwischen den E-Mail-Flussregeln und den Regeln, die Sie für eine Clientanwendung wie Outlook festlegen würden, ist der, dass die E-Mail-Flussregeln auf Nachrichten während statt nach der Übertragung reagieren. Die E-Mail-Flussregeln enthalten auch einen umfassenden Satz an Bedingungen, Ausnahmen und Aktionen, der Ihnen die Flexibilität bietet, zahlreiche Typen von Nachrichtenrichtlinien zu implementieren.|
|[Intune Mobile Device Management (Verwaltung mobiler Geräte mit Intune)](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune bietet eine mobile Geräteverwaltung (MDM), indem es die Protokolle oder APIs verwendet, die in den mobilen Betriebssystemen verfügbar sind. Sie umfasst Aufgaben wie die Registrierung von Geräten für die Verwaltung, sodass eine Bestandsaufnahme der Geräte zur Verfügung steht, die auf Unternehmensdienste zugreifen, die Konfiguration von Geräten, um sicherzustellen, dass sie den Sicherheits- und Integritätsstandards des Unternehmens entsprechen, die Bereitstellung von Zertifikaten und WLAN-/VPN-Profilen für den Zugriff auf Unternehmensdienste, das Messen der Gerätekompatibilität nach Standards des Unternehmens, inklusive Berichterstellung und die Entfernung von Unternehmensdaten von verwalteten Geräten.|
|[Intune app protection policies (Intune-App-Schutzrichtlinien)](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|Die Intune-App-Schutzrichtlinien können verwendet werden, um Ihre Unternehmensdaten in mobilen Apps mit oder ohne Registrierung der Geräte für die Verwaltung zu schützen. Die mobilen Geräte Ihrer Benutzer können sogar über eine nicht von Microsoft stammende MDM-Lösung verwaltet werden, während [Intune helps protect Office 365 information (Intune hilft, die Office 365-Informationen zu schützen)](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices). Während Ihre Angestellten also weiterhin produktiv sein können, verhindern Sie gleichzeitig beabsichtigten und unbeabsichtigten Datenverlust. Durch die Implementierung von Richtlinien auf App-Ebene können Sie den Zugriff auf Unternehmensressourcen einschränken und die Steuerung der Daten innerhalb Ihrer IT-Abteilung halten.|
|[Azure AD Token Lifetime (Tokengültigkeitsdauer in Azure AD)](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|Sie können die Gültigkeitsdauer eines von Azure Active Directory (Azure AD) ausgestellten Tokens festlegen. Sie können die Tokengültigkeitsdauer für alle Apps in Ihrer Organisation festlegen, für eine mehrinstanzfähige (multiorganisatorische) Anwendung oder für einen bestimmten Dienstprinzipal in Ihrer Organisation.|
|Microsoft Identitäts-Broker|Microsoft stellt Anwendungen für jede mobile Plattform bereit, die das Bridging von Anmeldeinformationen anwendungsübergeifend von verschiedenen Herstellern zulassen und ermöglicht bestimmte verbesserte Features, die einen einzelnen sicheren Ort benötigen, von dem aus Anmeldeinformationen überprüft werden. Wir bezeichnen diese als Broker. Unter iOS und Android werden diese Broker durch den Microsoft Authenticator und die Intune-Unternehmensportal-Apps bereitgestellt. Diese Funktionalität wird in Windows 10 durch eine in das Betriebssystem integrierte Kontoauswahl bereitgestellt, die in der Fachsprache als Webauthentifizierungsbroker bezeichnet wird.|

## <a name="security-best-practices-and-recommendations"></a>Bewährte Sicherheitsmethoden und -empfehlungen
Es gibt zwar keine allgemeingültige Empfehlung für alle Kundenumgebungen, jedoch finden Sie unter [empfohlene Sicherheitsrichtlinien und -konfigurationen](microsoft-365-policies-configurations.md) Konzepte zu wichtigen bewährten Sicherheitsmethoden. Dieser Artikel beschreibt auch allgemeine Empfehlungen von Microsoft zur Anwendung von Microsoft 365-Richtlinien und -Konfigurationseinstellungen innerhalb der Microsoft-Cloud. So wird sichergestellt, dass Ihre Mitarbeiter sowohl sicher als auch produktiv arbeiten können.

### <a name="baseline-recommended-security-policies-and-configurations"></a>Empfohlene Sicherheitsrichtlinien und -konfigurationen
Unter [General identity and device access policy recommendations (Allgemeine Empfehlungen zu Richtlinien für den Identitäts- und Gerätezugriff)](identity-access-policies.md) sind die allgemeinen empfohlenen Richtlinien beschrieben, die Ihnen bei der Sicherung von Microsoft 365 Enterprise helfen. Es werden ebenfalls die von uns empfohlenen Standardkonfigurationen für Ihren Plattform-Client beschrieben, um die bestmögliche Benutzererfahrung bei der einmaligen Anmeldung zu erzielen und die technischen Voraussetzungen für einen bedingten Zugriff bereitzustellen.

### <a name="exchange-online-access-policies"></a>Exchange Online-Zugriffsrichtlinien
Der Artikel [Policy recommendations to help secure email (Richtlinienempfehlungen zum Sichern von E-Mails)](secure-email-recommended-policies.md) stellt Empfehlungen von Microsoft bereit, die Ihnen bei der Sicherung der E-Mails Ihrer Organisation und von E-Mail-Clients helfen, die eine moderne Authentifizierung und einen bedingten Zugriff unterstützen. Diese Empfehlungen stehen zusätzlich zu den [allgemeinen Empfehlungen für die Identitäts- und Zugriffsrichtlinie](identity-access-policies.md) für Sie bereit.

### <a name="sharepoint-online-access-policies"></a>SharePoint Online-Zugriffsrichtlinien
Empfehlungen werden zum [Schützen des SharePoint Online-Dateizugriffs](sharepoint-file-access-policies.md) zusätzlich zu den [allgemeinen Empfehlungen für die Identitäts- und Zugriffsrichtlinien](identity-access-policies.md) sowie [Richtlinienempfehlungen zum Sichern von E-Mails](secure-email-recommended-policies.md) bereitgestellt. In diesem Artikel werden die neuen Richtlinien beschrieben, die erstellt werden müssen, und wie vorhandene Richtlinien geändert werden müssen, um jeweils die Exchange Online-E-Mail und den SharePoint Online-Dateizugriff zu schützen.

## <a name="deploy-windows-10-and-office-365-proplus"></a>Bereitstellen von Windows 10 und Office 365 ProPlus
Erfahren Sie, wie Sie Windows 10 und Office 365 ProPlus bereitstellen und in Microsoft Azure Active Directory (Azure AD) oder lokale Active Directory Domain Services (AD DS) integrieren. Stellen Sie Windows 10, Office 365 ProPlus und Ihre anderen branchenspezifischen Apps auf neuen Geräten bereit, oder aktualisieren Sie vorhandene Geräte unter Verwendung von Intune, System Center Configuration Manager und Gruppenrichtlinie zum Verwalten von Geräten auf Windows 10.

Weitere Informationen finden Sie in den folgenden Artikeln:
- [Windows 10 deployment considerations](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations) (Überlegungen zur Bereitstellung von Windows 10)
- [Bereitstellungshandbuch für Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)
- [Bewährte Methoden für die Bereitstellung von Office 365 ProPlus im Unternehmen](https://docs.microsoft.com/DeployOffice/best-practices/best-practices)
- [So weisen Sie Office 365 ProPlus 2016-Apps Windows 10-Geräten mit Microsoft Intune hinzu](https://docs.microsoft.com/intune/apps-add-office365)

Unterstützung zur Bereitstellung mit Microsoft 365 finden Sie unter [FastTrack for Office 365](https://fasttrack.microsoft.com/microsoft365) (FastTrack für Office 365).

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Verwalten von Updates für Windows 10 und Office 365 ProPlus
Die folgenden Links zeigen Ihnen, wie Sie maximale Kontrolle über die Qualitäts- und Featureupdates für Windows 10 und Office 365 ProPlus erhalten. Erfahren Sie, wie Sie die Bandbreitenauslastung effektiv steuern und Windows und Office mit den neuesten Features, Funktionen und Sicherheitsupdates auf dem neuesten Stand halten.

Weitere Informationen finden Sie in den folgenden Artikeln:
- [Übersicht über Windows as a Service](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Übersicht über die Updatekanäle für Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)
- [Verwalten von Softwareupdates](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [Bereitstellen von Windows 10-Updates mit System Center Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Verwalten von Office 365 ProPlus mit Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup> Microsoft empfiehlt Organisationen, die zurzeit die Updateverwaltung des Configuration Manager für Windows verwenden, bei Windows 10-Clientcomputern ebenso zu verfahren.

## <a name="next-steps"></a>Nächste Schritte
[Microsoft 365 Enterprise product page (Microsoft 365 Enterprise-Produktseite)](https://www.microsoft.com/microsoft-365/enterprise)<br/>
[Cloud platform roadmap](https://www.microsoft.com/cloud-platform/roadmap) (Roadmap für die Cloudplattform)
