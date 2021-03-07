---
title: Konfigurieren von Teams mit drei Ebenen des Dateifreigabeschutzes
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- Ent_Architecture
- seo-marvel-jun2020
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: Erfahren Sie, wie Sie Teams für eine bessere Sicherheit bei der gemeinsamen Nutzung von Dateien konfigurieren können, indem Sie drei Schutzebenen verwenden, die ein Gleichgewicht zwischen Sicherheit und einfacher Zusammenarbeit herstellen.
ms.openlocfilehash: d41effb6db9f8995c3c878523babf200ab9af762
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509242"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>Konfigurieren von Teams mit drei Schutzebenen

Die Artikel in dieser Reihe bieten Empfehlungen, wie Teams in Microsoft Teams und deren zugehörigen SharePoint-Websites für den Dateischutz so konfiguriert werden können, dass sowohl die Sicherheit als auch eine einfache Zusammenarbeit sichergestellt sind.

In diesem Artikel werden vier verschiedene Konfigurationen, beginnend mit einem öffentlichen Team mit sehr offenen Freigaberichtlinien definiert. Jede zusätzliche Konfiguration stellt einen sinnvollen Schritt im Hinblick auf einen zusätzlichen Schutz dar, die Möglichkeit des Zugriffs auf und der Zusammenarbeit an Dateien in Teams wird jedoch auf die entsprechenden Teammitglieder reduziert. 

Die Konfigurationen in diesem Artikel sind auf die Microsoft-Empfehlungen für drei Schutzebenen für Daten, Identitäten und Geräte ausgerichtet:

- Grundlegender Schutz

- Schutz sensibler Daten

- Schutz vertraulicher Daten

Für weitere Informationen zu diesen Ebenen und Funktionen, die für jede Ebene empfohlen werden, lesen Sie [Illustrationen zu Microsoft Cloud für Enterprise-Architekten](https://docs.microsoft.com/microsoft-365/solutions/cloud-architecture-models)


## <a name="three-tiers-at-a-glance"></a>Drei Ebenen auf einen Blick

Die folgende Tabelle enthält die Konfigurationen für jede Ebene. Verwenden Sie diese Konfigurationen als Ausgangsempfehlungen, und passen Sie die Websitekonfigurationen entsprechend den Bedürfnissen Ihrer Organisation an. Sie benötigen möglicherweise nicht jede Ebene.

|-|Basisplan (öffentlich)|Basisplan (privat)|Vertraulich|Streng vertraulich|
|:-----|:-----|:-----|:-----|:-----|
|Privates oder öffentliches Team|Öffentlich|Private|Private|Private|
|Wer hat Zugriff?|Alle Benutzer in der Organisation, einschließlich der B2B-Benutzer.|Nur Mitglieder des Teams. Andere Benutzer können den Zugriff auf die zugeordnete Website anfordern.|Nur Mitglieder des Teams.|Nur Mitglieder des Teams.|
|Private Kanäle|Teambesitzer und -mitglieder können private Kanäle erstellen.|Teambesitzer und -mitglieder können private Kanäle erstellen.|Nur Teambesitzer können private Kanäle erstellen.|Nur Teambesitzer können private Kanäle erstellen.|
|Gastzugriff auf Websiteebene|**Neue und vorhandene Gäste** (standardmäßig).|**Neue und vorhandene Gäste** (standardmäßig).|**Neue und vorhandene Gäste** oder **Nur Personen in Ihrer Organisation**, je nach den Teamanforderungen.|**Neue und vorhandene Gäste** oder **Nur Personen in Ihrer Organisation**, je nach den Teamanforderungen.|
|Freigabeeinstellungen für Websites|**Websitebesitzer und -mitglieder sowie Personen mit Bearbeitungsberechtigungen können Dateien und Ordner freigeben, aber nur Websitebesitzer können die Website freigeben**.|**Websitebesitzer und -mitglieder sowie Personen mit Bearbeitungsberechtigungen können Dateien und Ordner freigeben, aber nur Websitebesitzer können die Website freigeben**.|**Websitebesitzer und -mitglieder sowie Personen mit Bearbeitungsberechtigungen können Dateien und Ordner freigeben, aber nur Websitebesitzer können die Website freigeben**.|**Nur Websitebesitzer können Dateien, Ordner und die Website teilen**.<br>Zugriffsanforderungen **Aus**.|
|Zugriff von nicht verwalteten Geräten auf Websiteebene|**Vollzugriff über Desktop-Apps, mobile Apps und das Internet** (standardmäßig).|**Vollzugriff über Desktop-Apps, mobile Apps und das Internet** (standardmäßig).|**Eingeschränkten, reinen Webzugriff zulassen**.|**Zugriff blockieren**.|
|Standardmäßiger Freigabe-Linktyp|**Nur Personen in Ihrer Organisation**|**Nur Personen in Ihrer Organisation**|**Bestimmte Personen**|**Personen mit vorhandenem Zugriff**|
|Vertraulichkeitsbezeichnungen|Keine|Keine|Vertraulichkeitsbezeichnung zur Klassifizierung des Teams und zur Steuerung der Gastfreigabe und des nicht verwalteten Gerätezugriffs.|Vertraulichkeitsbezeichnung zur Klassifizierung des Teams und zur Steuerung der Gastfreigabe und des nicht verwalteten Gerätezugriffs. Die Bezeichnung kann auch für Dateien verwendet werden, um Dateien zu verschlüsseln.|

Eine Variation der Option „Streng vertraulich“, [Teams mit Sicherheitsisolierung](secure-teams-security-isolation.md) verwendet eine eindeutige Vertraulichkeitsbezeichnung für ein Team, das zusätzliche Sicherheit bietet. Sie können diese Bezeichnung verwenden, um Dateien zu verschlüsseln, und nur Mitglieder dieses Teams können diese lesen.

Der grundlegende Schutz enthält jeweils öffentliche und private Teams. Öffentliche Teams können von allen Benutzern in der Organisation ermittelt werden und alle haben Zugriff auf diese. Private Teams können nur von Mitgliedern des Standorts ermittelt werden und nur diese haben Zugriff auf diese. Beide Konfigurationen schränken die Freigabe der zugehörigen SharePoint-Website nur auf Teambesitzer ein, um die Berechtigungsverwaltung zu unterstützen.

Teams für vertraulichen und streng vertraulichen Schutz sind private Teams, in denen die Freigabe und das Anfordern von Zugriff für die zugeordnete Website eingeschränkt ist und Vertraulichkeitsbezeichnungen zum Festlegen von Richtlinien für die gemeinsame Nutzung, den Gerätezugriff und die Inhaltsverschlüsselung verwendet werden.

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Die Ebenen „Vertraulich“ und „Streng vertraulich“ verwenden Vertraulichkeitsbezeichnungen, um das Team und die zugehörigen Dateien zu schützen. Um diese Ebenen einzuführen, müssen Sie [Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Office 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) aktivieren.

Während auf der Basisebene keine Vertraulichkeitsbezeichnungen erforderlich sind, sollten Sie erwägen, eine "allgemeine" Bezeichnung zu erstellen und dann zu verlangen, dass alle Teams eine Bezeichnung erhalten. Auf diese Weise können Sie sicherstellen, dass die Benutzer die Vertraulichkeit beim Erstellen eines Teams bewusst auswählen. Wenn Sie die Ebenen „Vertraulich“ und „Streng vertraulich“ bereitstellen möchten, empfiehlt es sich, eine "allgemeine" Bezeichnung zu erstellen, die Sie für Basisplan-Teams und für Dateien verwenden können, die nicht vertraulich sind.

Wenn Sie mit der Verwendung von Vertraulichkeitsbezeichnungen noch nicht vertraut sind, empfehlen wir Ihnen, [Erste Schritte mit Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels) zu lesen. 

Wenn Sie in Ihrer Organisation bereits Vertraulichkeitsbezeichnungen eingeführt haben, sollten Sie bedenken, wie die in den Ebenen „Vertraulich“ und „Streng vertraulich“ verwendeten Bezeichnungen Ihrer Gesamtstrategie für Bezeichnungen entsprechen. 

## <a name="sharing-the-sharepoint-site"></a>Die SharePoint-Website freigeben

Jedes Team verfügt über eine zugeordnete SharePoint-Website, auf der Dokumente gespeichert werden. (Dies ist die Registerkarte "**Dateien**" in einem Teams-Kanal.) Die SharePoint-Website behält ihre eigene Berechtigungsverwaltung, ist aber mit Teamberechtigungen verknüpft. Teambesitzer werden als Websitebesitzer und Teammitglieder als Websitemitglieder in der zugehörigen Website einbezogen.

Die resultierenden Berechtigungen ermöglichen Folgendes:

- Teambesitzer können die Website verwalten und haben Vollzugriff auf die Websiteinhalte.
- Teammitglieder können Dateien auf der Website erstellen und bearbeiten. 

Standardmäßig können Teambesitzer und -mitglieder die Website selbst für Personen außerhalb des Teams freigeben, ohne Sie dem Team hinzuzufügen. Wir empfehlen, dies zu vermeiden, da es die Benutzerverwaltung erschwert und dazu führen kann, dass Personen, die keine Teammitglieder sind, Zugriff auf Teamdateien haben, ohne dass Teambesitzer dies bemerken. Um dies zu verhindern, empfiehlt es sich den direkten Zugriff auf die Website von der grundlegenden Schutzebene auf zu ermöglichen.

Obwohl Teams keine schreibgeschützte Berechtigungsoption haben, hat die SharePoint-Website eine. Wenn Sie Beteiligte von Partnergruppen haben, die in der Lage sein sollen, Teamdateien anzuzeigen ohne sie zu bearbeiten, sollten Sie diese direkt der SharePoint-Website mit Leseberechtigungen hinzufügen.

## <a name="sharing-files-and-folders"></a>Freigeben von Dateien und Ordnern

Besitzer und Mitglieder des Teams können standardmäßig Dateien und Ordner für Personen außerhalb des Teams freigeben. Dazu gehören möglicherweise Personen außerhalb Ihrer Organisation, wenn Sie die Gastfreigabe zugelassen haben. In allen drei Ebenen wird der standardmäßige Freigabe-Linktyp aktualisiert, um versehentliche Freigabe zu vermeiden. In der Ebene „Streng vertraulich“ wird eine solche Freigabe nur auf Teambesitzer beschränkt.

## <a name="guest-sharing"></a>Gastfreigabe

Wenn Sie mit Personen außerhalb Ihrer Organisation zusammenarbeiten müssen, empfiehlt es sich, [SharePoint- und OneDrive-Integration mit Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) für optimale Freigabe- und Verwaltungsfunktionen zu konfigurieren.

Die Gastfreigabe von Teams ist standardmäßig deaktiviert, obwohl die Freigabe für Office 365-Gruppen (in denen die Teammitgliedschaft gespeichert ist) und SharePoint aktiviert ist. Die Freigabe von Teams wird auf der Basisplan-Ebene aktiviert und Sie können sie bei Bedarf in den Ebenen „Vertraulich“ und „Streng vertraulich“ mithilfe einer Vertraulichkeitsbezeichnung deaktivieren.

Die Vertraulichkeitsbezeichnung betrifft nur die Gastfreigabe für das Team. Die Gastfreigabeeinstellungen für die zugeordnete SharePoint-Website werden separat gesteuert und Sie können die beiden Einstellungen sowohl für Ebene „Vertraulich“ als auch für die Ebene „Streng vertraulich“ ausrichten.

Auf der Ebene „Streng vertraulich“ wird die Vertraulichkeitsbezeichnung so konfiguriert, dass Dateien, auf die Sie angewendet wurde, verschlüsselt sind. Wenn Sie möchten, dass Gäste auf diese Dateien zugreifen können, müssen Sie ihnen bei der Erstellung der Bezeichnung die entsprechenden Berechtigungen erteilen.

Es wird dringend empfohlen, dass Sie die Gastfreigabe für die Grundebene aktiviert lassen und für die Ebenen „Vertraulich“ und „Streng vertraulich“ aktivieren, wenn Sie mit Personen außerhalb Ihrer Organisation zusammenarbeiten müssen. Die Gastfreigabefunktionen in Microsoft 365 bieten eine viel sicherere und steuerbare Freigabefunktionalität als das Senden von Dateien als Anlagen in E-Mail-Nachrichten. Außerdem verringert sich das Risiko der Schatten-IT, wenn Benutzer nicht geregelte Verbraucherprodukte verwenden, um mit legitimen externen Mitarbeiter Daten und Dateien auszutauschen.

Lesen Sie die folgenden Verweise, um eine sichere und produktive Gastumgebung für Ihre Organisation zu erstellen:

- [Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](best-practices-anonymous-sharing.md)
- [Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation](share-limit-accidental-exposure.md)
- [Erstellen einer sicheren Gastfreigabeumgebung](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>Zugriff von nicht verwalteten Geräten aus

Bei den Ebenen „Vertraulich“ und „Streng vertraulich“ wird der Zugriff auf SharePoint-Inhalte mit Vertraulichkeitsbezeichnungen eingeschränkt. Der bedingte Zugriff über Azure AD bietet zahlreiche Optionen, um zu bestimmen, wie Personen auf Microsoft 365 zugreifen, einschließlich Einschränkungen basierend auf Standort, Risiko, Gerätekonformität und anderen Faktoren. Wir empfehlen Ihnen, den Artikel [Was ist bedingter Zugriff?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) zu lesen, und sich zu überlegen, welche zusätzlichen Richtlinien für Ihre Organisation geeignet sein könnten.

Beachten Sie, dass Gäste oft keine Geräte haben, die von Ihrer Organisation verwaltet werden. Wenn Sie Gäste in eine der Ebenen erlauben, überlegen Sie, welche Arten von Geräten diese für den Zugriff auf Teams und Websites verwenden, und legen Sie Ihre Richtlinien für nicht verwaltete Geräte entsprechend fest.

## <a name="next-step"></a>Nächster Schritt

Beginnen Sie mit dem [Konfigurieren der grundlegenden Schutzebene](configure-teams-baseline-protection.md). Bei Bedarf können Sie einen [Schutz sensibler Daten](configure-teams-sensitive-protection.md) oder einen [Schutz vertraulicher Daten](configure-teams-highly-sensitive-protection.md) zusätzlich zum Basisplan hinzufügen.

## <a name="see-also"></a>Siehe auch

[Sicherheit und Compliance in Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Warnungsrichtlinien im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)
