---
title: 'Schritt 13: Überwachen der Mandanten- und Anmeldeaktivität'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren von Azure AD-Zugriffs- und Verwendungsberichten.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867545"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a>Schritt 13: Überwachen der Mandanten- und Anmeldeaktivität

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt überprüfen Sie Überwachungsprotokolle und Anmeldeaktivitäten mithilfe von Azure AD-Berichten. Es stehen zwei Arten von Berichten zur Verfügung.

Der **Aktivitätsbericht „Überwachungsprotokolle“** verzeichnet den Verlauf jeder in Ihrem Azure AD-Mandanten ausgeführten Aufgabe. In diesem Bericht finden Sie Antworten auf Fragen wie:

- Wer hat eine Person zu einer Administratorengruppe hinzugefügt?
- Welche Benutzer melden sich bei einer bestimmten App an?
- Wie viele Kennwortzurücksetzungen werden ausgeführt?

Der **Aktivitätsbericht „Anmeldungen“** verzeichnet, wer die im Überwachungsprotokollbericht gemeldeten Aufgaben ausgeführt hat. In diesem Bericht finden Sie Antworten auf Fragen wie:

- Welches Anmeldemuster gilt für einen bestimmten untersuchten Benutzer?
- Wie groß ist das Volumen von Anmeldungen über einen Tag, eine Woche oder einen Monat?
- Wie viele dieser Anmeldeversuche waren nicht erfolgreich und für welche Konten?

Weitere Informationen zu den Berichten und den Zugriffsmöglichkeiten auf diese finden Sie unter [Azure Active Directory-Berichterstellung](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).

In diesem Schritt lernen Sie die Berichte kennen und erfahren, wie Sie sie verwenden können, um zu Planungs- und Sicherheitszwecken Informationen über Azure AD-Ereignisse und -Aktivitäten zu erhalten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer](identity-self-service-group-management.md) |
