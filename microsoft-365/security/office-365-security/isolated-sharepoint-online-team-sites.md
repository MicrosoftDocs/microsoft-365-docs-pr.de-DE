---
title: Isolierte SharePoint Online-Teamwebsites
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Erfahren Sie mehr über isolierte SharePoint Online-Teamwebsites, einschließlich der Anwendungen, Anforderungen und Funktionen, mit denen sie verwendet werden können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286585"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Isolierte SharePoint Online-Teamwebsites

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 – Plan 1](office-365-atp.md)
- SharePoint Online 

 **Zusammenfassung:** Informationen zu Verwendungszwecken für isolierte SharePoint Online-Teamwebsites.

SharePoint Online-Teamwebsites sind eine einfache Möglichkeit, um schnell einen Ort für die Zusammenarbeit an Notizen, Dokumenten, Artikeln, einem Kalender und anderen Ressourcen in Microsoft Office 365 zu erstellen. SharePoint Online-Teamwebsites basieren auf einer Microsoft 365-Gruppe und verfügen über ein vereinfachtes Verwaltungsmodell, um die offene Zusammenarbeit mit einer als „Privat“ definierten Menge von Gruppenmitgliedern oder der gesamten Organisation zu ermöglichen. Über eine standardmäßige SharePoint Online-Teamwebsite können Mitglieder der Microsoft 365-Gruppe andere Benutzer einladen und Berechtigungseinstellungen steuern.

Manchmal ist es jedoch erforderlich, den Websitezugriff über Gruppenmitgliedschaften und SharePoint Online-Berechtigungsstufen, die von SharePoint-Administratoren verwaltet werden, zu steuern. Wir bezeichnen dies als eine isolierte Website, die auf die Gruppe der Benutzer beschränkt ist, die entweder auf der Website zusammenarbeiten, ihren Inhalt anzeigen oder diese verwalten. Eine isolierte Website kann z. B. in folgenden Fällen erforderlich sein:

- Für ein geheimes Projekt innerhalb Ihrer Organisation.

- Als Speicherort für das besonders vertrauliche oder wertvolle geistige Eigentum Ihrer Organisation.

- Für die Ressourcen im Zusammenhang mit einer Klage, die von Ihrer Organisation erhoben oder die gegen sie geführt wird.

- Zum Freigeben eines Microsoft 365-Abonnements für mehrere Organisationen, zwischen denen es zwar einige Überschneidungen gibt, die jedoch größtenteils als eigenständige Geschäftseinheiten existieren.

Dies sind die Anforderungen einer isolierten-Website:

- Nur SharePoint Online-Administratoren können Aufgaben der Websiteverwaltung ausführen; hierzu gehören die Gruppenmitgliedschaft für den Zugriff auf die Website und das Konfigurieren von benutzerdefinierten Berechtigungen.

- Mitglieder der Website können keine anderen Mitglieder zur Teamwebsite einladen.

- Benutzer, die kein Mitglied der isolierten Website sind, können keinen Zugriff auf die Website anfordern. Wenn sie versuchen, auf eine der Website zugeordnete URL zuzugreifen, wird eine Webseite mit der Meldung angezeigt, dass der Zugriff verweigert wurde.

Der Nachteil beim Anfordern einer zentralen Zugriffssteuerung und von benutzerdefinierten Berechtigungen von SharePoint Online-Administratoren besteht darin, dass die Website isoliert bleibt. Beispielsweise können aktuelle Mitglieder weder absichtlich noch versehentlich andere Benutzer innerhalb des Microsoft 365-Abonnements, die kein Mitglied der Website sein sollten, einladen oder benutzerdefinierte Berechtigungen für diese konfigurieren.

Eine isolierte Website kann mit anderen Features wie z. B. den folgenden verwendet werden:

- Information Rights Management, um sicherzustellen, dass die Ressourcen auf der Website verschlüsselt bleiben, auch wenn sie lokal heruntergeladen und auf eine andere Website hochgeladen werden, die der gesamten Organisation zur Verfügung steht.

- Verhinderung von Datenverlust, um Benutzer daran zu hindern, die Ressourcen der Website (z. B. Dateien) per E-Mail zu senden.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie eine isolierte SharePoint Online-Teamwebsite in einem Testabonnement ausprobieren möchten, finden Sie eine schrittweise Anleitung unter [Isolierte SharePoint Online-Teamwebsite in Ihrer Office 365-Entwicklungs-/Testumgebung](isolated-sharepoint-online-team-site-dev-test-environment.md).

Wenn Sie eine isolierte SharePoint Online-Teamwebsite in der Produktion bereitstellen möchten, lesen Sie die schrittweisen Überlegungen zum Entwurf unter [Entwerfen einer isolierten SharePoint Online-Teamwebsite](design-an-isolated-sharepoint-online-team-site.md).

## <a name="related-topics"></a>Verwandte Themen

[Entwerfen einer isolierten SharePoint Online-Teamwebsite](design-an-isolated-sharepoint-online-team-site.md)

[Verwalten einer isolierten SharePoint Online-Teamwebsite](manage-an-isolated-sharepoint-online-team-site.md)

[Bereitstellen einer isolierten SharePoint Online-Teamwebsite](deploy-an-isolated-sharepoint-online-team-site.md)
