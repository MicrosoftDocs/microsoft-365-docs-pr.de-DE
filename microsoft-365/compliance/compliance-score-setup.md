---
title: Setup der Microsoft-Kompatibilitätsbewertung
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
description: In diesem Artikel erfahren Sie, wie Sie sich anmelden, Berechtigungen einrichten und das Dashboard für Microsoft Compliance Score verstehen, das die Vereinfachung und Automatisierung von Risikobewertungen erleichtert.
ms.openlocfilehash: 8233fb3174d822e4f71115cab2a1a174c1749810
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078612"
---
# <a name="microsoft-compliance-score-preview-setup"></a>Setup der Microsoft-Kompatibilitätsbewertung (Vorschau)

## <a name="before-you-begin"></a>Vorabinformationen

Der globale Administrator von Microsoft 365 für Ihre Organisation ist wahrscheinlich der erste Benutzer, der auf das Kompatibilitäts Ergebnis zugreift. Wenn Sie das Kompatibilitäts Ergebnis zum ersten Mal besuchen, empfehlen wir die globale Administratoranmeldung, und legen Sie die Benutzerberechtigungen fest, wie unten beschrieben.

## <a name="sign-in"></a>Anmelden

1. Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) , und **melden** Sie sich mit ihrem globalen Microsoft 365-Administratorkonto an.
2. Wählen Sie **Kompatibilitätsbewertung** im linken Navigationsbereich aus. Das [Dashboard für die Konformitätsbewertung sollte dann mit ihrer Bewertung](#understand-the-compliance-score-dashboard)angezeigt werden.

## <a name="set-user-permissions-and-assign-roles"></a>Festlegen von Benutzerberechtigungen und Zuweisen von Rollen

Bei der Kompatibilitätsbewertung wird ein RBAC-Berechtigungsmodell (Role-Based Access Control, rollenbasierte Zugriffssteuerung) verwendet. Nur Benutzer, denen eine Rolle zugewiesen ist, können auf die Konformitätsbewertung zugreifen, und die von den einzelnen Benutzern zugelassenen Aktionen sind nach Rollentyp eingeschränkt.

### <a name="where-to-set-permissions"></a>Festlegen von Berechtigungen

Der globale Administrator für Ihre Organisation kann Benutzerberechtigungen im Microsoft 365 Compliance Center oder in Azure Active Directory (Azure AD) festlegen. Sobald die Rollen an beiden Speicherorten festgelegt wurden, können Benutzer auf die Konformitätsbewertung (ebenso wie auf den Compliance-Manager) zugreifen.

Beachten Sie, dass vorhandene Compliance Manger-Rollen **nicht** auf die Konformitätsbewertung übertragen werden.  Wenn Sie zuvor eine Rolle im Compliance-Manager zugewiesen haben, gewährt diese Rolle Ihnen daher keinen Zugriff auf die Konformitätsbewertung. Ihr globaler Administrator muss im Microsoft 365 Compliance Center oder Azure AD Berechtigungen und eine Rolle für Sie festlegen, damit Sie auf das Kompatibilitäts Ergebnis zugreifen können.

### <a name="role-types"></a>Rollentypen

In der folgenden Tabelle wird gezeigt, wie die einzelnen Rollen des Compliance-Centers von Microsoft 365 den vorhandenen Compliance-Manager-Rollen zugeordnet werden und welche Funktionen für die jeweilige Rolle zulässig sind.


| Benutzer kann Folgendes: | Microsoft 365 Compliance Center-Rolle | Compliance-Manager-Rolle | 
| :------------- | :-------------: | :------------: |
| **Lesen, aber nicht bearbeiten von Daten**| Azure AD globaler Leser  | Azure AD globaler Leser | 
| **Lesen, aber nicht bearbeiten von Daten**| Benutzer mit Leseberechtigung für Sicherheitsfunktionen | Compliance-Manager-Leser  | 
| **Bearbeiten von Daten**| Compliance-Administrator | Compliance-Manager-Mitwirkender | 
| **Bearbeiten von Testergebnissen**| Compliance-Administrator | Auditor für Compliance-Manager | 
| **Verwalten von Bewertungen und Vorlagen-und Mandantendaten**| Compliance-Administrator<br>Compliancedatenadministrator<br>Sicherheitsadministrator | Compliance-Manager-Administrator | 
| **Zuweisen von Benutzern**| Globaler Administrator | Portal Administrator | 

> [!NOTE]
> Wenn Sie von der Kompatibilitätsbewertung zum Compliance-Manager wechseln, um eine Aufgabe abzuschließen (beispielsweise zum Verwalten von Bewertungen), öffnet Ihr Browser eine neue Registerkarte, und ein Dialogfeld wird angezeigt. Im oberen Abschnitt mit dem Header "bereits Microsoft Cloud Services-Kunde? Melden Sie sich bei Ihrem Konto an, "wählen Sie **Anmelden** bei Access Compliance Manager aus; Sie müssen Ihre Anmeldeinformationen nicht erneut eingeben.

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a>Vorgehensweise Festlegen von Berechtigungen und Rollen im Microsoft 365 Compliance Center

So legen Sie Berechtigungen im Microsoft 365 Compliance Center fest:

1. Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.
2. Wählen Sie im linken Navigationsbereich **Berechtigungen** aus. Von hier aus können Sie Rollen anzeigen und Berechtigungen zuweisen.

## <a name="configure-automatic-secure-score-updates"></a>Konfigurieren automatischer Updates für sichere Bewertungen

Standardmäßig haben alle neuen Mandanten die Option Automatische Updates für [sichere Bewertungen](../security/mtp/microsoft-secure-score.md) aktiviert. Dies bedeutet, dass alle Aktionen, die von Secure Score überwacht werden, den Status für dieselbe Aktion automatisch in der Kompatibilitätsbewertung aktualisieren.

Ihr globaler Administrator kann diese Einstellung verwalten, um automatische Updates für alle Aktionen zu deaktivieren oder Aktualisierungen für Aktionen einzeln festzulegen.

Während der öffentlichen Vorschau müssen Sie zum Microsoft Service Trust Portal (wo sich Compliance Manger befindet) wechseln, um sichere Bewertungs Aktualisierungen zu verwalten.

Führen Sie die folgenden Schritte aus, um automatische Bewertungen für sichere Gäste zu verwalten:

1. Melden Sie sich mit ihrem globalen Administratorkonto beim [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com) an.

2. Wählen Sie in der oberen Menüleiste des Dienst Vertrauensstellungs Portals unter **Weitere**die Option **Administrator** aus, und wählen Sie dann **Einstellungen**aus.

3. Wählen Sie auf der Registerkarte **sichere Punktzahl** die entsprechende Schaltfläche aus, um **für alle Aktionen**aktiviert, **für alle Aktionen**oder **pro Aktion festlegen** zu deaktivieren.

Wenn Sie die Option **pro Aktion festlegen auswählen,** führen Sie die folgenden zusätzlichen Schritte aus, um für einzelne Aktionen sichere Bewertungs Aktualisierungen zu aktivieren:

4. Wählen Sie im oberen Menü den Eintrag **Compliance-Manager** aus (Hinweis: Wählen Sie nicht "Compliance-Manager (klassisch)") aus.

5. Wählen Sie in der oberen rechten Ecke des Bildschirms **Mandantenverwaltung** aus.

6. Suchen Sie im Bereich **Kundenaktionen** die gewünschte Aktion mit einem Auslassungszeichen (**..**.) unter der Spalte **betroffene Aktionen** . Klicken Sie auf die Ellipsen, und wählen Sie **Bearbeiten aus.**

7. Wechseln Sie zur Option **Secure Score Continuous Update** Toggle to **on.**

8. Wählen Sie **Speichern aus.** Secure Score die kontinuierliche Überwachung ist nun für diese Aktion aktiviert.

**Hinweis:** Nur der globale Administrator kann automatische Updates für alle Aktionen aktivieren oder deaktivieren. Der Compliance-Manager-Administrator kann automatische Updates für einzelne Aktionen aktivieren, jedoch nicht für alle Aktionen Global.

Weitere Informationen finden Sie unter [Manage Secure Score Updates](compliance-manager-release-notes.md#secure-score).

## <a name="understand-the-compliance-score-dashboard"></a>Grundlegendes zum Kompatibilitäts Bewertungs Dashboard

Das Compliance Score-Dashboard bietet Ihnen einen Überblick über Ihre aktuelle Compliance-Position.

![Compliance Score-Dashboard](../media/compliance-score-dashboard.png "Konformitäts Bewertungs Dashboard")

### <a name="overall-compliance-score"></a>Gesamtergebnis der Konformität

Ihr Konformitäts Bewertungspunkt, der oben im Vordergrund steht, zeigt einen Prozentsatz basierend auf Punkten, die für die Durchführung von Verbesserungs Aktionen zur Behandlung wichtiger Datenschutzstandards und-Vorschriften erreichbar sind.

Wenn Sie zum ersten Mal auf die Konformitätsbewertung stoßen, basiert Ihr anfängliches Ergebnis auf der integrierten Microsoft 365-Datenschutz Basislinie – einer Reihe von Steuerelementen, die allgemeine Branchenvorschriften und-Standards umfassen. Da durch das Kompatibilitäts Ergebnis Ihr System vorhandener Microsoft 365-Lösungen überprüft wird, erhalten Sie eine erste Bewertung Ihrer Compliance-Haltung basierend auf den derzeit von Ihrer Organisation aktivierten Datenschutz-und Sicherheitseinstellungen.

Wenn Sie für Ihre Organisation relevante Bewertungen hinzufügen, wird Ihre Punktzahl noch aussagekräftiger. Erfahren Sie mehr darüber, [wie Ihre Punktzahl berechnet wird](compliance-score-methodology.md).

### <a name="key-improvement-actions"></a>Wichtige Verbesserungs Aktionen

In diesem Abschnitt werden die wichtigsten Verbesserungs Aktionen aufgelistet, die Sie im Moment durchführen können, um den größten positiven Einfluss auf Ihre gesamte Konformitätsbewertung zu nehmen. Es werden Aktionen aufgelistet, die nicht abgeschlossen sind oder mit der Bewertung mit hohen Risiken fehlgeschlagen sind.

### <a name="solutions-that-affect-your-score"></a>Lösungen, die Ihre Punktzahl beeinflussen

In diesem Abschnitt wird gezeigt, welche Lösungen Aktionen enthalten, mit denen die beste Möglichkeit besteht, Ihre Punktzahl positiv zu beeinflussen, und wie viele hervorragende Verbesserungs Aktionen in den einzelnen Lösungen vorhanden sind.

### <a name="compliance-score-breakdown"></a>Aufschlüsselung der Konformitätsbewertung

In diesem Abschnitt erhalten Sie zwei verschiedene Möglichkeiten, um eine detailliertere Darstellung ihrer Ergebnisse zu erzielen:

- **Kategorien**: zeigt den Prozentsatz der Gesamtpunktzahl in Datenschutzkategorien an, beispielsweise "Informationen schützen" oder "Geräte verwalten".
- **Assessments**: zeigt den Prozentsatz Ihrer Fortschritte bei der Verwaltung von Bewertungen für bestimmte Compliance-und Datenschutzstandards, Verordnungen oder Gesetze wie dsgvo oder NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtern der Dashboardansicht

Sie können die Dashboardansicht filtern, um nur die Elemente anzuzeigen, die sich auf bestimmte Vorschriften und Standards, Lösungen, Aktionstypen, [von Ihnen eingestellte Bewertungsgruppen](working-with-compliance-manager.md#groups)oder Datenschutzkategorien beziehen. Durch das Filtern der Ansicht auf diese Weise wird auch die Bewertung in Ihrem Dashboard gefiltert, und es wird angezeigt, wie viele Punkte Sie je nach den Filterkriterien aus insgesamt möglichen Punkten erzielt haben.

So wenden Sie Filter an:

1. Wählen Sie in der oberen rechten Ecke des Dashboards den **Filter** aus.
2. Wählen Sie **im Bereich flyoutfilter die Filterkriterien** aus, und klicken Sie dann auf über **nehmen**.

Nachdem ein Filter angewendet wurde, wird das Ergebnis in Echtzeit angepasst. Der Prozentsatz der Konformitätsbewertung und die Aufschlüsselung sowie die Verbesserungs Aktionen und-Lösungen beziehen sich jetzt nur auf Daten, die von Ihren Filterkriterien abgedeckt werden. Wenn Sie sich bei der Konformitätsbewertung abmelden, bleibt die gefilterte Ansicht erhalten, wenn Sie sich wieder anmelden.

So entfernen Sie Filter:

- Wählen Sie auf der Überschrift " **angewendete Filter** " oberhalb der Konformitätsbewertung das **X** neben dem einzelnen Filter aus, den Sie entfernen möchten. oder
- Wählen Sie in der oberen rechten Ecke des Dashboards **Filter** aus, und wählen Sie dann **Filter löschen**aus.

## <a name="next-step"></a>Nächster Schritt

Besuchen Sie [Arbeiten mit Compliance Score](working-with-compliance-score.md) , um den Workflow zu verstehen, wie Sie Aktionen zur Verbesserung Ihrer Partitur durchführen.
