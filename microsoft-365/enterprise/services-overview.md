---
title: Microsoft 365 Enterprise Services (Übersicht) | Microsoft-Dokumente
description: Dieser Inhalt bietet eine Übersicht über Microsoft 365 Enterprise und Enterprise use-Empfehlungen.
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290160"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Microsoft 365 Enterprise-Dienste und-Konzepte

Microsoft 365 Enterprise ist für große Organisationen konzipiert, und darin sind Office 365 Enterprise, Windows 10 Enterprise und Enterprise Mobility + Security (EMS) integriert, um allen Beschäftigten zu ermöglichen, auf sichere Weise kreativ zu sein und zusammenzuarbeiten. Microsoft 365 Enterprise enthält eine Enterprise Edition von Windows 10 und Office-Anwendungen über Office 365 ProPlus.

Sowohl für Windows 10 als auch Office 365 ProPlus werden dem Unternehmen im März und September über den halbjährigen Kanal Releases neuer Features bereitgestellt. Für ein über den halbjährigen Kanal bereitgestelltes Featurerelease wird 18 Monate lang Support geboten. Microsoft Intune und System Center Configuration Manager bieten Funktionen zum Bereitstellen und Aktualisieren von Windows 10 und Office 365 ProPlus.

Dies sind die aktuellen Versionen von Windows 10, Office 365 ProPlus, Microsoft Intune und System Center Configuration Manager:

|     |**Halbjährlicher Kanal (gezielt)**|**Halbjährlicher Kanal**|
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

## <a name="important-concepts-to-understand"></a>Wichtige Konzepte zu verstehen
Die wichtigsten Konzepte und EMS-Funktionen, mit denen Sie vertraut sein sollten, werden in der folgenden Tabelle beschrieben.

|Kernkonzept|Beschreibung|
|------------|-----------|
|[Azure Multi-Factor Authentication (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Als die zweistufige Verifizierungs Lösung von Microsoft hilft Azure MFA beim Schutz des Zugriffs auf Daten und Anwendungen, während die Benutzernachfrage nach einem einfachen Anmeldevorgang erfüllt wird. Es bietet eine starke Authentifizierung über eine Reihe von Überprüfungsmethoden, einschließlich Telefonanruf, Textnachricht oder Überprüfung mobiler apps.|
|[Bedingter Zugriff durch Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Diese Funktion von Azure AD ermöglicht Ihnen das Erzwingen von Steuerelementen für den Zugriff auf Cloud-apps in Ihrer Umgebung basierend auf bestimmten Bedingungen. Mit Steuerelementen können Sie entweder zusätzliche Anforderungen an den Zugriff binden oder Sie blockieren. Die Implementierung des bedingten Zugriffs basiert auf Richtlinien.|
|[Exchange Online Data Loss Prevention (DLP)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|Exchange Online Data Loss Prevention (DLP)-Richtlinien, die als Premium-Feature von Exchange Online-Plan 2-und Office 365-Abonnements verfügbar sind, ermöglichen Organisationen, vertrauliche Informationen in Office 365 zu identifizieren, zu überwachen und automatisch zu schützen.<br><br>Mit Exchange Online DLP-Richtlinien können Sie vertrauliche Informationen über viele Standorte hinweg identifizieren, beispielsweise Exchange Online, SharePoint Online und OneDrive for Business. Diese Richtlinien helfen Ihnen beispielsweise bei der Identifizierung von Dokumenten mit vertraulichen Informationen oder bei der versehentlichen Freigabe vertraulicher Informationen mit Personen außerhalb Ihrer Organisation.|
|[Exchange-Nachrichtenfluss-/-Transport Regeln](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Exchange-Nachrichtenfluss Regeln, die auch als Transportregeln bezeichnet werden, suchen nach Nachrichten, die Ihre Organisation durchlaufen und darauf reagieren. Nachrichtenfluss Regeln sind wie die postEingangsregeln, die in vielen e-Mail-Clients verfügbar sind. Der Hauptunterschied zwischen den Nachrichtenfluss Regeln und-Regeln, die Sie in einer Clientanwendung wie Outlook einrichten, besteht darin, dass Nachrichtenfluss Regeln auf Nachrichten angewendet werden, während Sie übertragen werden, statt nach der Übermittlung der Nachricht. Nachrichtenfluss Regeln enthalten auch eine umfassendere Reihe von Bedingungen, Ausnahmen und Aktionen, die Ihnen die Flexibilität bieten, viele Arten von Messagingrichtlinien zu implementieren.|
|[InTune-Verwaltung mobiler Geräte](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|InTune stellt die Mobile Geräteverwaltung (MDM) mithilfe der in den mobilen Betriebssystemen verfügbaren Protokolle oder APIs bereit. Sie umfasst Aufgaben wie die Registrierung von Geräten in der Verwaltung, sodass Sie über eine Bestandsaufnahme der Geräte verfügt, die auf Unternehmensdienste zugreifen, indem Sie Geräte konfigurieren, um sicherzustellen, dass Sie die Sicherheits-und Integritätsstandards des Unternehmens erfüllen und Zertifikate und WLAN/VPN-Profile für Zugriff auf Unternehmensdienste, Berichterstellung und Messung der Geräte Konformität an Unternehmensstandards und Entfernen von Unternehmensdaten von verwalteten Geräten.|
|[InTune-App-Schutzrichtlinien](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|InTune-App-Schutzrichtlinien können verwendet werden, um die Daten Ihres Unternehmens in mobilen apps mit oder ohne Registrierung der Geräte in die Verwaltung zu schützen. Tatsächlich können die mobilen Geräte ihrer Benutzer sogar von einer anderen nicht-Microsoft MDM-Lösung verwaltet werden, während [InTune zum Schutz von Office 365-Informationen beiträgt](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices). Während Sie sicherstellen, dass Ihre Mitarbeiter weiterhin produktiv sein können, können Sie auch Datenverluste verhindern – absichtlich und unbeabsichtigt. Durch das Implementieren von Richtlinien auf App-Ebene können Sie den Zugriff auf Unternehmensressourcen einschränken und Daten in der Steuerung Ihrer IT-Abteilung speichern.|
|[Gültigkeitsdauer des Azure AD-Tokens](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|Sie können die Lebensdauer eines Tokens angeben, das von Azure Active Directory (Azure AD) ausgegeben wird. Sie können Token-Gültigkeitsdauer für alle apps in Ihrer Organisation, für eine mehrinstanzenfähige Anwendung (mehr Organisationsumgebung) oder für einen bestimmten Dienstprinzipal in Ihrer Organisation festlegen.|
|Microsoft Identity Broker|Microsoft stellt Anwendungen für jede Mobile Plattform bereit, die das überbrücken von Anmeldeinformationen zwischen Anwendungen von unterschiedlichen Anbietern ermöglichen, und ermöglicht spezielle erweiterte Features, die einen einzigen sicheren Ort für die Überprüfung von Anmeldeinformationen erfordern. Wir nennen diese Broker. Unter iOS und Android werden diese Broker über die Microsoft Authenticator-und InTune-Unternehmens Portal-apps bereitgestellt. In Windows 10 wird diese Funktionalität von einer im Betriebssystem integrierten Kontoauswahl bereitgestellt, die technisch als webAuthentifizierungs Broker bezeichnet wird.|

## <a name="security-best-practices-and-recommendations"></a>Bewährte Sicherheitsmethoden und -empfehlungen
Es gibt zwar keine allgemeingültige Empfehlung für alle Kundenumgebungen, jedoch finden Sie unter [empfohlene Sicherheitsrichtlinien und -konfigurationen](microsoft-365-policies-configurations.md) Konzepte zu wichtigen bewährten Sicherheitsmethoden. Dieser Artikel beschreibt auch allgemeine Empfehlungen von Microsoft zur Anwendung von Microsoft 365-Richtlinien und -Konfigurationseinstellungen innerhalb der Microsoft-Cloud. So wird sichergestellt, dass Ihre Mitarbeiter sowohl sicher als auch produktiv arbeiten können.

### <a name="baseline-recommended-security-policies-and-configurations"></a>Geplante Empfohlene Sicherheitsrichtlinien und-Konfigurationen
[Allgemeine Empfehlungen zu Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md) beschreibt die allgemeinen empfohlenen Richtlinien für die Sicherung von Microsoft 365 Enterprise. Es werden ebenfalls die von uns empfohlenen Standardkonfigurationen für Ihren Plattform-Client beschrieben, um die bestmögliche Benutzererfahrung bei der einmaligen Anmeldung zu erzielen und die technischen Voraussetzungen für einen bedingten Zugriff bereitzustellen.

### <a name="exchange-online-access-policies"></a>Exchange Online-Zugriffsrichtlinien
[Richtlinien Empfehlungen zur Unterstützung von sicheren e-Mails](secure-email-recommended-policies.md) bieten Microsoft-Empfehlungen zur Sicherung von Organisations-e-Mails sowie e-Mail-Clients, die moderne Authentifizierung und bedingten Zugriff ermöglichen. Diese Empfehlungen stehen zusätzlich zu den [allgemeinen Empfehlungen für die Identitäts- und Zugriffsrichtlinie](identity-access-policies.md) für Sie bereit.

### <a name="sharepoint-online-access-policies"></a>SharePoint-Zugriffsrichtlinien
Es werden Empfehlungen bereitgestellt, um den [Zugriff auf SharePoint Online-Dateien](sharepoint-file-access-policies.md) zusätzlich zu den [allgemeinen Empfehlungen zu Identitäts-und Zugriffsrichtlinien](identity-access-policies.md) und [Richtlinien Empfehlungen für sichere e-Mails](secure-email-recommended-policies.md)zu schützen. In diesem Artikel werden die neuen Richtlinien beschrieben, die erstellt werden müssen, und die Art und Weise, wie vorhandene Richtlinien geändert werden sollen, um sowohl Exchange Online-als auch SharePoint Online-Dateizugriff zu schützen.

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
