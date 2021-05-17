---
title: Untersuchen von Benutzern im Microsoft 365 Security Center
description: Untersuchen von Benutzern im Microsoft 365 Security Center
keywords: Security, Malware, Microsoft 365, M365, Security Center, monitor, report, identities, data, devices, apps, incident, analyze, response
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
ms.openlocfilehash: c03e4d5bd94eb6105ffab91c6dad2b74d7159dde
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300061"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a>Untersuchen von Benutzern im Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

Ein Teil Ihrer Vorfalluntersuchung kann Benutzerkonten enthalten. Beginnen Sie mit der **Registerkarte Benutzer** für einen Vorfall von & Warnungen **>** *Vorfall* **> Benutzer**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel einer Benutzerseite für einen Vorfall":::

Um eine kurze Zusammenfassung eines Benutzerkontos für den Vorfall zu erhalten, aktivieren Sie das Kontrollkästchen neben dem Benutzernamen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Beispiel für den Zusammenfassungsbereich des Benutzerkontos für einen Vorfall im Microsoft 365 Security Center":::

> [!NOTE]
> Auf der Seite Benutzer werden die Azure Active Directory (AD)-Organisation sowie Gruppen angezeigt, die Ihnen dabei helfen, die Gruppen und Berechtigungen zu verstehen, die einem Benutzer zugeordnet sind.

Auf dieser Fly-Out-Seite können Sie Informationen zu Benutzerbedrohungen überprüfen, einschließlich aktueller Vorfälle, aktiver Warnungen und Risikostufe sowie benutzerexposition, Konten, Geräte und mehr.

Darüber hinaus können Sie direkt im Microsoft 365 Security Center Maßnahmen ergreifen, um einen gefährdeten Benutzer zu adressieren, um zu bestätigen, dass der Benutzer gefährdet ist oder dass er sich erneut anmelden muss.

Hier können Sie zur Benutzerseite wechseln **auswählen,** um die Details eines Benutzerkontos anzuzeigen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Beispiel für die Benutzerkontoseite für einen Vorfall im Microsoft 365 Security Center":::

Sie können diese Seite auch anzeigen, indem Sie den Namen des Benutzerkontos aus der Liste auf der Seite **Benutzer** auswählen.

Die Microsoft 365 Security Center-Benutzerseite kombiniert Informationen von Microsoft Defender for Endpoint, Microsoft Defender for Identity und Microsoft Cloud App Security (je nachdem, welche Lizenzen Sie besitzen). 

Diese Seite enthält Informationen, die speziell für das Sicherheitsrisiko eines Benutzerkontos spezifisch sind. Dies umfasst eine Bewertung, die bei der Bewertung von Risiken und aktuellen Ereignissen und Warnungen hilft, die zum Gesamtrisiko des Benutzers beigetragen haben.

Auf dieser Seite können Sie die folgenden zusätzlichen Aktionen ausführen: 

- Kennzeichnen des Benutzerkontos als gefährdet
- Benutzer erneut anmelden
- Anhalten des Benutzerkontos
- Weitere Informationen finden Sie unter Azure Active Directory (Azure AD)-Benutzerkonteneinstellungen.
- Anzeigen der Dateien im Besitz des Benutzerkontos
- Anzeigen von Dateien, die für diesen Benutzer freigegeben sind. 

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Beispiel für die Aktionen für ein Benutzerkonto für einen Vorfall im Microsoft 365 Security Center":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Nächste Schritte

Setzen Sie ihre Untersuchung nach Bedarf für Prozessvorfälle [fort.](investigate-incidents.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Priorisieren von Vorfällen](incident-queue.md)
- [Verwalten von Vorfällen](manage-incidents.md)