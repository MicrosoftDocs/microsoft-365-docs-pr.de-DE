---
title: Thema Experiences Security and Privacy
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Planen von Sicherheits-und Datenschutzthemen in Microsoft 365
ms.openlocfilehash: b3c33a49b8273c5f7830f08de17af9757a858413
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698497"
---
# <a name="topic-experiences-security-and-privacy"></a>Thema Experiences Security and Privacy

In den Themen Erfahrungen werden vorhandene Inhalts Sicherheitsfeatures in Microsoft 365 sowie Wissensnetzwerk-Steuerelemente verwendet, um zu steuern, welche AI-generierten Inhalte Benutzern in Ihrer Organisation angezeigt werden. Dies ist die Kombination aus Microsoft 365-Sicherheitseinstellungen (Berechtigungen für Websites, Dateien und Ordner) und Verwaltungseinstellungen für Themen, die bestimmen, was ein bestimmter Benutzer in Themen sehen kann.

Durch das Einrichten des Wissensnetzwerks werden keine vorhandenen Zugriffssteuerungen für Inhalte in Ihrer Organisation geändert. Benutzer können nur sehen, worauf Sie bereits Zugriff haben.

In diesem Artikel wird beschrieben, wie das Thema Erfahrungen aus Sicherheitsgründen und den Optionen, die Wissens Administratoren und Knowledge Manager haben, die Themen Sichtbarkeit steuern müssen, verwendet werden. Lesen Sie diesen Artikel im Rahmen ihrer [Planung für Themen Erfahrungen](plan-topic-experiences.md).

Sie sollten mit Themen [Erfahrungen](topic-experiences-overview.md), dem [Themen Center](topic-center-overview.md)und der [Arbeit mit Themen im Thema Center](manage-topics.md) vertraut sein, bevor Sie diesen Artikel lesen.

## <a name="what-users-can-see-in-topics"></a>Was Benutzer in Themen sehen können

Um Themen anzuzeigen, muss ein Benutzer:

- Haben Sie ein Thema Erfahrungen Lizenz
- Ein [Themen Betrachter](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [Mitwirkender oder Wissensmanager](topic-experiences-user-permissions.md) sein

Diese beiden Dinge ermöglichen Benutzern den Zugriff auf das Themen Center, sodass Sie Highlights und Themenkarten anzeigen können.

Thema Mitwirkende haben zusätzlich [Erstellen und bearbeiten](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) von Berechtigungen für Themen, und Knowledge Manager können Themen bestätigen oder entfernen.

Wenn ein Thema erstmals erkannt wird, können es Knowledge Manager im Themen Center anzeigen. Je nach Vollständigkeit und Relevanz des Themas wird das Thema in den Themenkarten möglicherweise vom Thema Betrachter angezeigt.

Themen können Informationen enthalten, die von AI generiert werden, sowie Informationen, die von Mitwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet wurden.

- Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf den Quellinhalt haben.
- Text, der manuell von einem Thema Mitwirkenden oder Wissensmanager hinzugefügt oder bearbeitet wurde, ist für jeden sichtbar, der das Thema sehen kann.

Thema Betrachter und Mitwirkende können die Liste der bestätigten und veröffentlichten Themen im Thema Center anzeigen, aber die Details des Themas, die eine bestimmte Person sehen kann, hängen von den Berechtigungen ab, die Sie für das Quellmaterial haben, und darüber, ob das Thema manuell bearbeitet wurde.

In der folgenden Tabelle wird beschrieben, was Benutzer – Thema Betrachter, Mitwirkende und Wissensmanager – in einem bestimmten Thema basierend auf Ihren Berechtigungen sehen können.

|Thema-Element|Was Benutzer sehen können|
|:---------|:------------------|
|Name des Themas|Benutzer können den Thema Namen aller Themen im Thema Center anzeigen. Einige Themen sind möglicherweise nicht sichtbar, wenn Sie eine geringe Relevanz für den Benutzer haben.|
|Beschreibung des Themas|Von AI generierte Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen. Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.|
|Personen|Angeheftete Personen sind für alle Benutzer sichtbar. Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Dateien|Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Seiten|Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Websites|Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|

## <a name="best-practices"></a>Bewährte Methoden

In den Themen Erfahrungen werden Benutzern Informationen basierend auf den vorhandenen Berechtigungen für Inhalte präsentiert. Microsoft 365 bietet eine Vielzahl von Möglichkeiten, um sicherzustellen, dass vertrauliche Inhalte auf geeignete Benutzer beschränkt sind. Über standardmäßige Team-oder Websiteberechtigungen hinaus können Sie [Vertraulichkeits Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) oder [Verhinderung von Datenverlusten](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) verwenden, um den Zugriff auf Inhalte und [Zugriffs](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) Überprüfungen einzuschränken, um den Benutzer Zugriff auf vertrauliche Informationen regelmäßig

Es wird empfohlen, dass Sie diese Tools verwenden, um sicherzustellen, dass Ihre Inhaltsberechtigungen in Ihrer Organisation ordnungsgemäß festgelegt sind. Thema-Erlebnisse können dann nützliche und geeignete Informationen für Ihre Benutzer bereitstellen.

Wenn Themen vorhanden sind, die Sie vollständig aus Themenbereichen ausschließen möchten, können Sie auch folgende Aufgaben ausführen:

- [Ausschließen vertraulicher SharePoint-Websites von der Themen Ermittlung](topic-experiences-discovery.md#select-sharepoint-topic-sources). Inhalte auf diesen Websites werden in den Themen Erfahrungen nicht angezeigt.

- [Themen nach Namen ausschließen](topic-experiences-discovery.md#exclude-topics-by-name). Themen, die explizit ausgeschlossen werden, werden in den Themen Erfahrungen nicht angezeigt.

- Lassen Sie die Knowledge Manager Themen im Themen Center entfernen.

Außerdem werden diese bewährten Methoden empfohlen:

- Rekrutieren von Wissensmanagern aus unterschiedlichen Bereichen Ihrer Organisation. Mit Wissensmanagern mit einer Vielzahl von Fachwissen und dem Zugriff auf den zugrunde liegenden Inhalt, der von AI verwendet wird, können Sie das nützlichste wissen für Ihre Benutzer erfinden und vertrauliche Informationen entfernen, wenn diese gefunden werden.

- Richten Sie einen Workflow zum Anfordern von Änderungen ein. Wissensmanager oder Team-oder Websitebesitzer sollten über einen Prozess verfügen, bei dem Sie den Ausschluss von Themen oder Websites anfordern können, wenn neue Projekte in Ihrer Organisation gestartet werden oder wenn Inhalte mit unangemessenen Berechtigungseinstellungen gefunden werden.

- Achten Sie beim Erstellen von Themenbeschreibungen auf die Benutzergruppe und die Vertraulichkeit von Informationen. Diese Beschreibungen sind möglicherweise für Benutzer sichtbar, die nicht über Berechtigungen für den Quellinhalt für das Thema verfügen.

Während Sie die Berechtigungen für einzelne Themenseiten ändern können, um den Zugriff auf eine bestimmte Benutzergruppe einzuschränken, wird dieser Ansatz aufgrund des hohen Verwaltungsaufwands nicht empfohlen.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Teams mit drei Schutzebenen](../solutions/configure-teams-three-tiers-protection.md)

[Planen von Themen Erfahrungen](plan-topic-experiences.md)

[Einrichten von Themen Erfahrungen](set-up-topic-experiences.md)
