---
title: Vorlagen für Benachrichtigungen zum Insider-Risikomanagement
description: Erfahren Sie mehr über Benachrichtigungsvorlagen für insider risk management in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416479"
---
# <a name="insider-risk-management-notice-templates"></a>Vorlagen für Benachrichtigungen zum Insider-Risikomanagement

Benachrichtigungsvorlagen für insider risk management ermöglichen das Senden von E-Mail-Nachrichten an Benutzer, wenn ihre Aktivitäten eine Richtlinien übereinstimmung und Warnung generieren. In den meisten Fällen sind Benutzeraktionen, die Warnungen generieren, das Ergebnis von Fehlern oder unbeabsichtigten Aktivitäten ohne absichtslose Absicht. Hinweise dienen benutzern als einfache Erinnerung, um vorsichtiger zu sein, Links zu Informationen für Aktualisierungsschulungen oder zu Unternehmensrichtlinienressourcen zur Verfügung zu stellen. Hinweise können ein wichtiger Bestandteil Ihres internen Complianceschulungsprogramms sein und dazu beitragen, einen dokumentierten Überwachungspfad für Benutzer mit wiederkehrenden Risikoaktivitäten zu erstellen.

Erstellen Sie Benachrichtigungsvorlagen, wenn Sie Benutzern eine E-Mail-Erinnerungsbenachrichtigung für Richtlinien übereinstimmungen als Teil des Problemlösungsprozesses senden möchten. Benachrichtigungen können nur an die E-Mail-Adresse des Benutzers gesendet werden, die der zu überprüfenden bestimmten Warnung zugeordnet ist. Wenn Sie eine Benachrichtigungsvorlage auswählen, die auf eine Richtlinien übereinstimmung angewendet werden soll, können Sie die in der Vorlage definierten Feldwerte akzeptieren oder die Felder bei Bedarf überschreiben.

## <a name="notice-templates-dashboard"></a>Dashboard für Benachrichtigungsvorlagen

Im **Benachrichtigungsvorlagen-Dashboard** wird eine Liste der konfigurierten Benachrichtigungsvorlagen angezeigt, und Sie können neue Benachrichtigungsvorlagen erstellen. Die Benachrichtigungsvorlagen werden in umgekehrter Datumsreihenfolge aufgelistet, wobei die aktuellste Benachrichtigungsvorlage zuerst aufgelistet wird.

![Dashboard für Insider-Risikomanagement-Benachrichtigungen](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>HTML für Hinweise

Wenn Sie mehr als eine einfache textbasierte E-Mail-Nachricht für Benachrichtigungen erstellen möchten, können Sie eine ausführlichere Nachricht mithilfe von HTML im Nachrichtentextfeld einer Benachrichtigungsvorlage erstellen. Das folgende Beispiel enthält das Nachrichtentextformat für eine einfache HTML-basierte E-Mail-Benachrichtigungsvorlage:

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> Die Implementierung des HTML href-Attributs in den Vorlagen für Insider-Risikomanagement unterstützt derzeit nur einzelne Anführungszeichen anstelle doppelter Anführungszeichen für URL-Verweise.

## <a name="create-a-new-notice-template"></a>Erstellen einer neuen Benachrichtigungsvorlage

Zum Erstellen einer neuen Vorlage für Insider-Risikomanagement-Benachrichtigungen verwenden Sie den Benachrichtigungs-Assistenten in **insider risk management** solution im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine neue Vorlage für insider risk management zu erstellen:

1. Wechseln Sie [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Benachrichtigungsvorlagen** aus.
2. Wählen **Sie Benachrichtigungsvorlage erstellen aus,** um den Benachrichtigungs-Assistenten zu öffnen.
3. Füllen Sie **auf der Seite Neue Benachrichtigungsvorlage erstellen** die folgenden Felder aus:
    - **Vorlagenname**: Geben Sie einen Anzeigenamen für den Hinweis ein. Dieser Name wird in der Liste der Benachrichtigungen im Benachrichtigungsdashboard und in der Auswahlliste für Benachrichtigungen angezeigt, wenn Benachrichtigungen aus einem Fall versandt werden.
    - **Senden von**: Geben Sie die Absender-E-Mail-Adresse für den Hinweis ein. Diese Adresse wird im Feld **Von:** in allen an Benutzer gesendeten Benachrichtigungen angezeigt, sofern sie beim Senden einer Benachrichtigung aus einem Fall nicht geändert wird.
    - **Cc- und Bcc-Felder:** Optionale Benutzer oder Gruppen, die über die Richtlinienab übereinstimmung benachrichtigt werden sollen, ausgewählt aus Active Directory für Ihr Abonnement.
    - **Betreff**: Informationen, die in der Betreffzeile der Nachricht angezeigt werden, unterstützen Textzeichen.
    - **Nachrichtentext**: Informationen, die im Nachrichtentext angezeigt werden und Text- oder HTML-Werte unterstützen.
4. Wählen **Sie Erstellen** aus, um die Benachrichtigungsvorlage zu erstellen und zu speichern, oder wählen Sie **Abbrechen** aus, um zu schließen, ohne die Benachrichtigungsvorlage zu speichern.

## <a name="update-a-notice-template"></a>Aktualisieren einer Benachrichtigungsvorlage

Führen Sie die folgenden Schritte aus, um eine vorhandene Vorlage für Insider-Risikomanagement zu aktualisieren:

1. Wechseln Sie [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Benachrichtigungsvorlagen** aus.
2. Wählen Sie im Benachrichtigungsdashboard die Benachrichtigungsvorlage aus, die Sie verwalten möchten.
3. Wählen Sie auf der Seite Benachrichtigungsdetails die Option **Bearbeiten aus.**
4. Auf der **Seite** Bearbeiten können Sie die folgenden Felder bearbeiten:
    - **Vorlagenname**: Geben Sie einen neuen Anzeigenamen für den Hinweis ein. Dieser Name wird in der Liste der Benachrichtigungen im Benachrichtigungsdashboard und in der Auswahlliste für Benachrichtigungen angezeigt, wenn Benachrichtigungen aus einem Fall versandt werden.
    - **Senden von**: Aktualisieren Sie die Absender-E-Mail-Adresse für den Hinweis. Diese Adresse wird im Feld **Von:** in allen an Benutzer gesendeten Benachrichtigungen angezeigt, sofern sie beim Senden einer Benachrichtigung aus einem Fall nicht geändert wird.
    - **Cc- und Bcc-Felder:** Aktualisieren Sie optionale Benutzer oder Gruppen, um über die Richtlinienab übereinstimmung benachrichtigt zu werden, die aus Active Directory für Ihr Abonnement ausgewählt wurde.
    - **Betreff**: Informationen aktualisieren, die in der Betreffzeile der Nachricht angezeigt werden, unterstützt Textzeichen.
    - **Nachrichtentext:** Aktualisieren Sie Informationen, die im Nachrichtentext angezeigt werden, unterstützt Text- oder HTML-Werte.
5. Wählen **Sie Speichern** aus, um den Hinweis zu aktualisieren und zu speichern, oder wählen Sie **Abbrechen** aus, um zu schließen, ohne die Benachrichtigungsvorlage zu speichern.

## <a name="delete-a-notice-template"></a>Löschen einer Benachrichtigungsvorlage

Führen Sie die folgenden Schritte aus, um eine vorhandene Vorlage für Insider-Risikomanagement zu löschen:

1. Wechseln Sie [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Benachrichtigungsvorlagen** aus.
2. Wählen Sie im Benachrichtigungsdashboard die Benachrichtigungsvorlage aus, die Sie löschen möchten.
3. Wählen Sie **auf der** Symbolleiste das Symbol Löschen aus.
4. Wenn Sie die Benachrichtigungsvorlage löschen möchten, wählen **Sie im** Dialogfeld Löschen die Option Ja aus. Wenn Sie den Löschvorgang abbrechen möchten, wählen Sie **Abbrechen aus.**
