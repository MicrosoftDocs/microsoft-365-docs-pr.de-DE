---
title: Sicherheit und Datenschutz in Microsoft Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie Sicherheit und Datenschutz in Microsoft -Themen planen.
ms.openlocfilehash: be5be01bce117a80bd95ee268c193889eccea67f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107792"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Sicherheit und Datenschutz in Microsoft Topics

Themen verwenden vorhandene Inhaltssicherheitsfeatures in Microsoft 365 zusammen mit administrativen Steuerelementen, um zu steuern, welche von AI generierten Inhalte Benutzern in Ihrer Organisation angezeigt werden. Es ist die Kombination aus Microsoft 365-Sicherheitseinstellungen (Berechtigungen für Websites, Dateien und Ordner) und Themen-Administratoreinstellungen, die bestimmen, was ein Benutzer in Themen sehen kann.

Durch das Einrichten von Themen werden keine vorhandenen Zugriffssteuerungen für Inhalte in Ihrer Organisation geändert. Benutzer sehen nur, worauf sie bereits Zugriff haben.

In diesem Artikel wird beschrieben, wie Themen aus Sicherheitsperspektive funktionieren und welche Optionen Wissensadministratoren und Wissensmanager haben, um die Sichtbarkeit des Themas zu steuern. Lesen Sie diesen Artikel im Rahmen Ihrer [Planung für Themen.](plan-topic-experiences.md)

Bevor Sie diesen Artikel lesen, [](topic-center-overview.md)sollten Sie mit [](manage-topics.md) themen, dem Themencenter und der Arbeit mit Themen im Themencenter vertraut sein. [](topic-experiences-overview.md)

## <a name="what-users-can-see-in-topics"></a>Was Benutzer in Themen sehen können

Um Themen zu sehen, muss ein Benutzer:

- Lizenz für "Themen"
- Ein [Themenanzeiger,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [Mitwirkender oder Knowledge Manager sein](topic-experiences-user-permissions.md)

Diese beiden Dinge ermöglichen Benutzern den Zugriff auf das Themencenter und das Anzeigen von Highlights und Themenkarten.

Die Mitwirkenden von Themen verfügen außerdem über [Berechtigungen](topic-experiences-user-permissions.md) zum Erstellen und Bearbeiten von Themen, und Wissensmanager können Themen bestätigen oder entfernen.

Wenn ein Thema zum ersten Mal entdeckt wird, können Wissensmanager es im Themencenter sehen. Je nach Vollständigkeit und Relevanz des Themas wird den Themenbetrachtern das Thema möglicherweise in Themenkarten angezeigt.

Themen können informationen enthalten, die von AI generiert werden, sowie Informationen, die von Themen mitwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet wurden.

- Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf den Quellinhalt haben.
- Text, der von einem Mitwirkenden oder Wissensmanager manuell hinzugefügt oder bearbeitet wurde, ist für jeden sichtbar, der das Thema sehen kann.

Themenanzeiger und Mitwirkende können die Liste der bestätigten und veröffentlichten Themen im Themencenter anzeigen, aber die Themendetails, die eine bestimmte Person sehen kann, hängen von den Berechtigungen ab, die sie für das Quellmaterial haben, und davon, ob das Thema manuell bearbeitet wurde.

In der folgenden Tabelle wird beschrieben, was Benutzer – Themenanzeiger, Mitwirkende und Wissensmanager – basierend auf ihren Berechtigungen in einem bestimmten Thema sehen können.

|Themaelement|Was Benutzer sehen können|
|:---------|:------------------|
|Themaname|Benutzer können den Themennamen aller Themen im Themencenter sehen. Einige Themen sind möglicherweise nicht sichtbar, wenn sie eine geringe Relevanz für den Benutzer haben.|
|Themenbeschreibung|Von AI generierte Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen. Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.|
|Personen|Angeheftierte Personen sind für alle Benutzer sichtbar. Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Dateien|Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Seiten|Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Websites|Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|

## <a name="best-practices"></a>Bewährte Methoden

Themen stellen Benutzern Informationen basierend auf ihren vorhandenen Berechtigungen für Inhalte zur Verfügung. Microsoft 365 bietet eine Vielzahl von Möglichkeiten, um sicherzustellen, dass vertrauliche Inhalte auf geeignete Benutzer beschränkt sind. Neben standardmäßigen Team- oder Websiteberechtigungen [](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) können Sie Vertraulichkeitsbezeichnungen [](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) oder die Verhinderung von Datenverlust verwenden, um den Zugriff auf Inhalte und Zugriffsüberprüfungen einzuschränken, um den Benutzerzugriff auf vertrauliche Informationen regelmäßig zu überprüfen. [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)

Es wird empfohlen, diese Tools zu verwenden, um sicherzustellen, dass Ihre Inhaltsberechtigungen in Ihrer Organisation entsprechend festgelegt werden. Themenerfahrungen können ihren Benutzern dann nützliche und geeignete Informationen bereitstellen.

Wenn es Themen gibt, die Sie vollständig aus der Themenerfahrung ausschließen möchten, können Sie auch:

- [Ausschließen vertraulicher SharePoint-Websites von der Themenermittlung.](topic-experiences-discovery.md#select-sharepoint-topic-sources) Inhalte auf diesen Websites werden in den Themenerfahrungen nicht angezeigt.

- [Ausschließen von Themen nach Namen.](topic-experiences-discovery.md#exclude-topics-by-name) Explizit ausgeschlossene Themen werden in den Themenerfahrungen nicht angezeigt.

- Möchten Sie wissen, dass Manager Themen im Themencenter entfernen.

Darüber hinaus empfehlen wir die folgenden bewährten Methoden:

- Rekrutieren Sie Wissensmanager aus verschiedenen Bereichen Ihrer Organisation. Wissensmanager mit einer Vielzahl von Fachkenntnissen – und Zugriff auf die von AI verwendeten zugrunde liegenden Inhalte – können Ihnen dabei helfen, die nützlichsten Kenntnisse für Ihre Benutzer zu vermitteln und vertrauliche Informationen zu entfernen, wenn sie gefunden werden.

- Richten Sie einen Workflow zum Anfordern von Änderungen ein. Wissensmanager oder Team- oder Websitebesitzer sollten über einen Prozess verfügen, in dem sie den Ausschluss von Themen oder Websites anfordern können, wenn neue Projekte in Ihrer Organisation gestartet werden oder wenn sie Inhalte mit unangemessenen Berechtigungseinstellungen finden.

- Beachten Sie beim Erstellen von Themenbeschreibungen die Zielgruppe und die Vertraulichkeit von Informationen. Diese Beschreibungen sind möglicherweise für Benutzer sichtbar, die nicht über Berechtigungen für die Quellinhalte für das Thema verfügen.

Sie können zwar die Berechtigungen auf einzelnen Themenseiten ändern, um den Zugriff auf eine bestimmte Gruppe von Benutzern zu einengen, wir empfehlen diesen Ansatz jedoch aufgrund des hohen Verwaltungsaufwands nicht.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Teams mit drei Schutzebenen](../solutions/configure-teams-three-tiers-protection.md)

[Topic Experiences planen](plan-topic-experiences.md)

[Topic Experiences einrichten](set-up-topic-experiences.md)
