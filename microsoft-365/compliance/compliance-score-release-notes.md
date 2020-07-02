---
title: Versionshinweise zu Microsoft Compliance Score
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Versionshinweise und bekannte Probleme für Microsoft Compliance Score (Preview), ein Feature im M365 Compliance Center, das das vereinfachen und Automatisieren von Risikobewertungen erleichtert.
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022192"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Versionshinweise zu Microsoft Compliance Score (Preview)

**In diesem Artikel:** Auf dieser Seite erfahren Sie, was in der Public Preview of [Microsoft Compliance Score](compliance-score.md) **neu ist** und Sie frühzeitig Zugriff auf neue Funktionen erhalten.

## <a name="assessment-creation-and-management-functionality"></a>Erstellungs-und Verwaltungsfunktionen für die Bewertung

Die Version Juni 2020 fügt Benutzern Funktionen zum Erstellen, löschen und Verwalten Ihrer Bewertungen direkt in Compliance Score hinzu. Zuvor war das gesamte Bewertungs Management im Compliance-Manager aufgewohnt. Wenn Sie eine Bewertung in Compliance Score erstellen oder ändern, werden die Aktualisierungen im Compliance-Manager angezeigt. Ebenso werden alle im Compliance-Manager durchgeführten Beurteilungs arbeiten in der Kompatibilitätsbewertung Oberfläche. Hier erfahren Sie, wie Sie [Assessments in Compliance Score verwalten](compliance-score-assessments.md). Beachten Sie, dass das Erstellen und Ändern von Vorlagen weiterhin im Compliance-Manager verwaltet wird.

## <a name="new-templates-for-assessments"></a>Neue Vorlagen für Bewertungen

Neue einsatzbereite Vorlagen für Bewertungen werden in der Kompatibilitätsbewertung veröffentlicht, sobald Sie verfügbar werden. Überprüfen Sie die [vollständige Liste der Vorlagen hier](compliance-score-templates.md). Zuletzt hinzugefügt:

- Dubai Information Security Resolution (DGISR)

## <a name="compliance-score-relationship-to-compliance-manager"></a>Kompatibilitäts Bewertungspunkt-Beziehung zum Compliance-Manager

Viele der Funktionen, die im Compliance-Manager verarbeitet werden, können jetzt in der Kompatibilitätsbewertung ausgeführt werden. Einige Funktionen sind jedoch weiterhin im Compliance-Manager zu beleben. Beachten Sie beim Arbeiten mit dem Kompatibilitäts Bewertungs-und Compliance-Manager während der öffentlichen Vorschau die folgenden Punkte:

 - **Erstellen von Vorlagen für Bewertungen**: 
   - Benutzer müssen zum Compliance-Manager wechseln, um [neue Vorlagen zu erstellen und vorhandene Vorlagen zu ändern](working-with-compliance-manager.md#templates).
   - Neue Vorlagen müssen Dimensionen für **Produkt** und **Zertifizierung**enthalten.
 - **Festlegen von Berechtigungen**: Benutzer, die noch nicht über Berechtigungen im Compliance-Manager verfügen, müssen Ihre Berechtigungen im Microsoft 365 Compliance Center festgelegt haben ([Weitere Informationen](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **Übertragung von Daten**: Organisationen mit Daten im Compliance-Manager sehen diese Daten in der Kompatibilitätsbewertung, und das gleiche gilt umgekehrt.
- **Anmelden beim Compliance-Manager aus Kompatibilitätsbewertung**: Wenn ein Benutzer bei der Kompatibilitätsbewertung angemeldet ist und einen Link auswählt, um zum Compliance-Manager zu wechseln, muss sich der Benutzer nicht erneut anmelden. Nachdem Sie auf den Link geklickt haben, wird in Ihrem Browser eine neue Registerkarte mit einem Dialogfeld geöffnet. Im oberen Abschnitt mit dem Header "bereits Microsoft Cloud Services-Kunde? Melden Sie sich bei Ihrem Konto an, "wählen Sie die Schaltfläche **Anmelden** aus, um sich automatisch beim Compliance-Manager anzumelden.

## <a name="known-issues-in-compliance-score-preview"></a>Bekannte Probleme in Compliance Score (Preview)

In den folgenden Abschnitten werden bekannte Probleme behandelt, die in bevorstehenden Versionen von Compliance Score behoben werden sollten.

### <a name="long-load-times-for-non-admin-users"></a>Lange Ladezeiten für Benutzer ohne Administratorrechte
Kompatibilitätsbewertung Benutzer, die andere Rollen als eine Administratorrolle innehaben, können lange Ladezeiten beim Versuch einer Anmeldung auftreten. Wenn Sie den Browser aktualisieren, wird dieses Problem behoben. Weitere Informationen finden Sie unter [Compliance Score Roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).

### <a name="supported-browsers"></a>Unterstützte Browser

- Die neuesten Versionen von Microsoft Edge, Chrome und Safari werden unterstützt.
- Aktualisierte Daten werden manchmal erst angezeigt, wenn Ihr Browser aktualisiert wurde.
- Internet Explorer wird nicht unterstützt.
