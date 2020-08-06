---
title: Verwenden Sie Exchange Online und das Security & Compliance Center, um die SEC-Richtlinie 17a-4 einzuhalten
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Konfigurieren Sie Exchange Online & Compliance Center, um den behördlichen Bestimmungen von CFTC Regel 1.31(c)-(d), FINRA Regel 4511 und SEC Regel 17a-4 gerecht zu werden.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: bba51bed4409bfb933b577419f48ab6963d4f7d6
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577115"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>Verwenden Sie Exchange Online und das Security & Compliance Center, um die SEC-Richtlinie 17a-4 einzuhalten

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Wenn Ihre Organisation gesetzliche Standards für die Aufbewahrung von Daten einhalten muss, bietet das Security & Compliance Center Features zur Verwaltung des Lebenszyklus Ihrer Daten in Exchange Online. Dazu gehört auch die Möglichkeit zum Aufbewahren, Überwachen, Durchsuchen und Exportieren der Daten. Diese Funktionen reichen aus, um die Anforderungen der meisten Organisationen zu erfüllen.

Einige Organisationen in stark regulierten Branchen unterliegen jedoch stringenteren aufsichtsrechtlichen Anforderungen. Finanzinstitute wie Banken oder Broker-Händler unterliegen beispielsweise der Richtlinie 17a-4 der Securities and Exchange Commission (SEC). Die Richtlinie 17a-4 enthält spezielle Anforderungen an die elektronische Datenspeicherung, darunter einige Aspekte der Aufzeichnungsverwaltung wie z. B. Dauer, Format, Qualität, Verfügbarkeit und Haftung für die Datenaufbewahrung.

Damit diese Organisationen besser verstehen, wie das Security & Compliance Center genutzt werden kann, um ihre gesetzlichen Auflagen für Exchange Online einzuhalten, insbesondere in Bezug auf die Anforderungen der Richtlinie 17a-4, haben wir in Zusammenarbeit mit Cohasset Associates eine Bewertung veröffentlicht.

Cohasset Associates bestätigt, dass Exchange Online und das Security & Compliance Center bei der empfohlenen Konfiguration die relevanten Speicheranforderungen der CFTC-Richtlinie 1.31(c)-(d), der FINRA-Richtlinie 4511 und der SEC-Richtlinie 17a-4 erfüllen. Diese Richtlinien wurden ausgewählt, da sie die ausführlichsten globalen Anleitungen für die Datenaufbewahrung für Finanzinstitute darstellen.

## <a name="download-the-cohasset-assessment"></a>Die Bewertung von Cohasset herunterladen

Sie können [hier die Bewertung von Cohasset herunterladen](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).

![Titelseite für die Bewertung von Cohasset Associates zum Herunterladen](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>Diese Bewertung ist beschränkt auf Exchange Online

Beachten Sie, dass diese Bewertung auf Exchange Online beschränkt ist. Die Bewertung umfasst keine anderen Microsoft 365-Dienste wie SharePoint Online oder OneDrive for Business, obwohl in Zukunft der Support für diese Dienste unter Einhaltung der SEC 17a-4 geplant ist.

Es ist wichtig zu verstehen, dass Skype for Business und Teams auch Daten in Exchange Online speichern. Daher deckt die Bewertung Nachrichten von Skype for Business sowie Kanal- und Chatnachrichten von Teams ab.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>Die Verwendung der Erhaltungssperre ist für die empfohlene Konfiguration essentiell

In hochgradig regulierten Branchen müssen oft elektronische Kommunikationsdaten gespeichert werden, um die sogenannte WORM-Anforderung (write onde, read many) zu erfüllen. Die WORM-Anforderung schreibt eine Speicherlösung vor, in der folgende Voraussetzungen in Bezug auf Datensätze erfüllt werden müssen:

- Sie müssen über einen erforderlichen Aufbewahrungszeitraum gespeichert werden, der nicht verkürzt sondern nur verlängert werden kann.
- Sie müssen unveränderlich sein, d. h. Datensätze können während des erforderlichen Aufbewahrungszeitraums nicht überschrieben, gelöscht oder geändert werden.

Wenn in Exchange Online eine [Aufbewahrungsrichtlinie](retention.md) auf das Postfach eines Benutzers angewendet wird, werden alle Inhalte des Benutzers basierend auf den Kriterien der Richtlinie aufbewahrt. Dis bedeutet, dass, sobald ein Benutzer versucht, eine E-Mail zu löschen oder zu ändern, eine Kopie der E-Mail im unveränderten Zustand an einem sicheren, versteckten Speicherort im Postfach des Benutzers abgelegt wird. Durch Aufbewahrungsrichtlinien kann sichergestellt werden, dass eine Organisation elektronische Kommunikationsdaten aufbewahrt, allerdings können derartige Richtlinien geändert werden.

Durch das Anwenden einer Erhaltungssperre auf eine Aufbewahrungsrichtlinie kann eine Organisation sicherstellen, dass die Richtlinie nicht geändert werden kann. Nach dem Anwenden einer Erhaltungssperre auf eine Aufbewahrungsrichtlinie sind folgende Aktionen eingeschränkt:

- Die in der Richtlinie enthaltene Aufbewahrungsdauer kann nur verlängert, nicht gekürzt werden.
- Benutzer können der Richtlinie hinzugefügt werden, jedoch können keine Benutzer entfernt werden.
- Die Aufbewahrungsrichtlinie kann nicht von einem Administrator gelöscht werden.

Eine Erhaltungssperre kann Sie bei der Einhaltung der gesetzlichen Bestimmungen der SEC 17a-4 unterstützen.

## <a name="how-to-set-up-preservation-lock"></a>So richten Sie eine Erhaltungssperre ein

Sie können eine Aufbewahrungsrichtlinie nur mithilfe von PowerShell sperren. Weitere Informationen hierzu finden Sie unter [Verwenden der Erhaltungssperre zur Einhaltung gesetzlicher Vorschriften](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).

