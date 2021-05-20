---
title: Untersuchen von Benutzern in Microsoft 365 Defender
description: Untersuchen Sie Benutzer auf einen Vorfall im Microsoft 365 Sicherheitscenter.
keywords: Sicherheit, Malware, Microsoft 365, M365, Sicherheitscenter, Monitor, Bericht, Identitäten, Daten, Geräte, Apps, Vorfall, Analysieren, Reagieren
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572801"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Untersuchen von Benutzern in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

Ein Teil Ihrer Vorfalluntersuchung kann Benutzerkonten umfassen. Beginnen Sie mit der Registerkarte **Benutzer** für einen Vorfall aus **Vorfällen & Warnungen >** *>* **Benutzer**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel für eine Benutzerseite für einen Vorfall":::

Um eine kurze Zusammenfassung eines Benutzerkontos für den Vorfall zu erhalten, wählen Sie das Häkchen neben dem Benutzernamen aus. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Beispiel für den Zusammenfassungsbereich des Benutzerkontos für einen Vorfall im Microsoft 365 Sicherheitscenter":::

> [!NOTE]
> Auf der Seite Benutzer werden Azure Active Directory (Azure AD)-Organisation sowie Gruppen angezeigt, die Ihnen helfen, die Gruppen und Berechtigungen zu verstehen, die einem Benutzer zugeordnet sind.

Auf dieser Fly-Out-Seite können Sie Informationen zu Benutzerbedrohungen überprüfen, einschließlich aktueller Vorfälle, aktiver Warnungen und Risikostufen sowie Benutzerexposition, Konten, Geräte und mehr.

Darüber hinaus können Sie direkt im Microsoft 365 Sicherheitscenter Maßnahmen ergreifen, um einen kompromittierten Benutzer zu adressieren, zu bestätigen, dass der Benutzer kompromittiert ist, oder dass er sich erneut anmelden muss.

Von hier aus können Sie die **Seite Zur Benutzerseite** wechseln auswählen, um die Details eines Benutzerkontos anzuzeigen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Beispiel für die Benutzerkontoseite für einen Vorfall im Microsoft 365 Sicherheitscenter":::

Sie können diese Seite auch anzeigen, indem Sie den Namen des Benutzerkontos aus der Liste auf der Seite **Benutzer** auswählen.

Die Benutzerseite Microsoft 365 Security Center kombiniert Informationen von Microsoft Defender for Endpoint, Microsoft Defender for Identity und Microsoft Cloud App Security (je nachdem, welche Lizenzen Sie haben). 

Auf dieser Seite werden Informationen angezeigt, die speziell auf das Sicherheitsrisiko eines Benutzerkontos zugeschnitten sind. Dazu gehört eine Bewertung, mit der Risiken und aktuelle Ereignisse und Warnungen bewertet werden, die zum Gesamtrisiko des Benutzers beigetragen haben.

Auf dieser Seite können Sie die folgenden zusätzlichen Aktionen ausführen: 

- Das Benutzerkonto als kompromittiert markieren
- Den Benutzer zur erneuten Anmeldung auffordern, sich anzumelden
- Sperren des Benutzerkontos
- Informationen zu den Azure Active Directory-Benutzerkontoeinstellungen (Azure AD)
- Anzeigen der Dateien, die im Besitz des Benutzerkontos sind
- Zeigen Sie Dateien an, die für diesen Benutzer freigegeben wurden. 

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Beispiel für aktionen in einem Benutzerkonto für einen Vorfall im Microsoft 365 Sicherheitscenter":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Nächste Schritte

Setzen Sie die [Untersuchung](investigate-incidents.md)bei Bedarf für Prozessvorfälle fort.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Priorisieren von Vorfällen](incident-queue.md)
- [Verwalten von Vorfällen](manage-incidents.md)