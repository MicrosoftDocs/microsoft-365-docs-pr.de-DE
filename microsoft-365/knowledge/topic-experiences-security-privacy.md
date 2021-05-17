---
title: Sicherheit und Datenschutz in Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informationen zum Planen von Sicherheit und Datenschutz für Microsoft Viva Topics
ms.openlocfilehash: 587b6a2921e7d1a3cc8d4ab663ff199fdd36871d
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114062"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Sicherheit und Datenschutz in Microsoft Viva Topics

Themen verwenden vorhandene Inhaltssicherheitsfeatures in Microsoft 365 zusammen mit administrativen Steuerelementen, um zu steuern, welche VON AI generierten Inhalte benutzern in Ihrer Organisation angezeigt werden. Es ist die Kombination aus Microsoft 365-Sicherheitseinstellungen (Berechtigungen für Websites, Dateien und Ordner) und Themen-Administratoreinstellungen, die bestimmen, was einem bestimmten Benutzer in Themen angezeigt werden kann.

Durch das Einrichten von Themen werden keine vorhandenen Zugriffssteuerelemente für Inhalte in Ihrer Organisation geändert. Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben.

In diesem Artikel wird beschrieben, wie Themen aus Sicherheitssicht funktionieren und welche Optionen Wissensadministratoren und Wissensmanager haben, um die Sichtbarkeit von Themen zu steuern. Lesen Sie diesen Artikel im Rahmen Ihrer [Planung für Themen](plan-topic-experiences.md).

Bevor Sie diesen Artikel lesen, [](topic-center-overview.md)sollten Sie mit [Themen,](topic-experiences-overview.md)dem Themencenter und der Arbeit mit Themen [im Themencenter](manage-topics.md) vertraut sein.

## <a name="what-users-can-see-in-topics"></a>Informationen, die Benutzer in Themen sehen können

Um Themen zu sehen, muss ein Benutzer:

- Über eine Lizenz für "Viva Topics" verfügen
- Ein [Themenbetrachter,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [Mitwirkender oder Wissensmanager sein](topic-experiences-user-permissions.md)

Diese beiden Dinge ermöglichen Benutzern den Zugriff auf das Themencenter und ermöglichen es ihnen, Highlights und Themenkarten zu sehen.

Die Mitwirkenden von Themen verfügen zusätzlich über [Berechtigungen](topic-experiences-user-permissions.md) zum Erstellen und Bearbeiten von Themen, und Wissensmanager können Themen bestätigen oder entfernen.

Wenn ein Thema zum ersten Mal entdeckt wird, können Wissensmanager es im Themencenter sehen. Je nach Vollständigkeit und Relevanz des Themas wird den Themenbetrachtern das Thema möglicherweise in Themenkarten angezeigt.

Themen können informationen enthalten, die durch KI generiert werden, und Informationen, die von Themenwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet werden.

- Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf die Quellinhalte haben.
- Text, der von einem Mitwirkenden oder Wissensmanager manuell hinzugefügt oder bearbeitet wurde, ist für jeden sichtbar, der das Thema sehen kann.

Themenbetrachter und Mitwirkende können die Liste der bestätigten und veröffentlichten Themen im Themencenter anzeigen, aber die Themendetails, die eine bestimmte Person sehen kann, hängen von den Berechtigungen ab, die sie für das Quellmaterial haben, und davon, ob das Thema manuell bearbeitet wurde.

In der folgenden Tabelle wird beschrieben, was Benutzer – Themenbetrachter, Mitwirkende und Wissensmanager – basierend auf ihren Berechtigungen in einem bestimmten Thema sehen können.

|Themenelement|Anzeige für Benutzer|
|:---------|:------------------|
|Themenname|Benutzer können den Themanamen von Themen im Themencenter sehen. Einige Themen sind möglicherweise nicht sichtbar, wenn Benutzer nicht über Berechtigungen für den Quellinhalt verfügen oder eine geringe Relevanz für den Benutzer haben.|
|Beschreibung des Themas|Von der KI generierten Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen. Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.|
|Personen|Angeheftete Personen sind für alle Benutzer sichtbar. Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Dateien|Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Seiten|Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Websites|Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|

## <a name="best-practices"></a>Bewährte Methoden

In Den Themen werden Benutzern Informationen basierend auf ihren vorhandenen Berechtigungen für Inhalte angezeigt. Microsoft 365 bietet eine Vielzahl von Möglichkeiten, um sicherzustellen, dass vertrauliche Inhalte auf geeignete Benutzer beschränkt sind. Über standardmäßige Team- oder [](../compliance/sensitivity-labels.md) Websiteberechtigungen hinaus können Sie Vertraulichkeitsbezeichnungen oder Verhinderung von Datenverlust verwenden, um den Zugriff auf Inhalte und Zugriffsüberprüfungen einzuschränken, um den Benutzerzugriff auf vertrauliche Informationen regelmäßig zu überprüfen. [](../compliance/dlp-learn-about-dlp.md) [](/azure/active-directory/governance/access-reviews-overview)

Es wird empfohlen, diese Tools zu verwenden, um sicherzustellen, dass Ihre Inhaltsberechtigungen in Ihrer Organisation entsprechend festgelegt werden. Anschließend können Themenerfahrungen nützliche und passende Informationen für Ihre Benutzer bereitstellen.

Wenn Es Themen gibt, die Sie vollständig aus den Themenerfahrungen ausschließen möchten, können Sie auch:

- [Ausschließen vertraulicher SharePoint-Websites von der Themenerkennung](topic-experiences-discovery.md#select-sharepoint-topic-sources). Inhalte auf diesen Websites werden in der Themenerfahrung nicht angezeigt.

- [Ausschließen von Themen nach Name](topic-experiences-discovery.md#exclude-topics-by-name). Themen, die explizit ausgeschlossen werden, werden in der Themenerfahrung nicht angezeigt.

- Wissensmanager müssen Themen im Themencenter entfernen.

Darüber hinaus empfehlen wir die folgenden bewährten Methoden:

- Rekrutieren von Wissensmanagern aus verschiedenen Bereichen Ihrer Organisation. Wissensmanager mit einer Vielzahl von Fachwissen – und Zugriff auf die von AI verwendeten zugrunde liegenden Inhalte – können Ihnen dabei helfen, das nützlichste Wissen für Ihre Benutzer zu kuratieren und vertrauliche Informationen zu entfernen, falls gefunden.

- Richten Sie einen Workflow zum Anfordern von Änderungen ein. Wissensmanager oder Team- oder Websitebesitzer sollten über einen Prozess verfügen, mit dem sie den Ausschluss von Themen oder Websites anfordern können, wenn neue Projekte in Ihrer Organisation gestartet werden oder wenn sie Inhalte mit unangemessenen Berechtigungseinstellungen finden.

- Beachten Sie beim Erstellen von Themenbeschreibungen die Benutzergruppe und die Vertraulichkeit von Informationen. Diese Beschreibungen sind möglicherweise für Benutzer sichtbar, die nicht über Berechtigungen für den Quellinhalt des Themas verfügen.

Sie können zwar die Berechtigungen auf einzelnen Themenseiten ändern, um den Zugriff auf eine bestimmte Benutzergruppe einzuschränken, aber wegen des hohen Verwaltungsaufwands wird diese Vorgehensweise nicht empfohlen.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Teams mit drei Schutzebenen](../solutions/configure-teams-three-tiers-protection.md)

[Topic Experiences planen](plan-topic-experiences.md)

[Topic Experiences einrichten](set-up-topic-experiences.md)
