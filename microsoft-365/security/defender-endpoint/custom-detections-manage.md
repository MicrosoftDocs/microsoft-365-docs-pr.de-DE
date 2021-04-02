---
title: Anzeigen und Verwalten von benutzerdefinierten Erkennungsregeln in Microsoft Defender ATP
ms.reviewer: ''
description: Informationen zum Anzeigen und Verwalten von benutzerdefinierten Erkennungsregeln
keywords: Benutzerdefinierte Erkennungen, Anzeigen, Verwalten, Warnungen, Bearbeiten, Ausführen bei Bedarf, Erkennungsregeln, erweiterte Suche, Suche, Abfrage, Reaktionsaktionen, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498758"
---
# <a name="view-and-manage-custom-detection-rules"></a>Anzeigen und Verwalten von benutzerdefinierten Erkennungsregeln

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Verwalten Sie Ihre [vorhandenen benutzerdefinierten Erkennungsregeln,](custom-detection-rules.md) um sicherzustellen, dass sie Bedrohungen effektiv finden und Aktionen ergreifen. Erfahren Sie, wie Sie die Liste der Regeln anzeigen, ihre vorherigen Läufe überprüfen und die ausgelösten Warnungen überprüfen. Sie können auch eine Regel bei Bedarf ausführen und ändern.

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Zum Erstellen oder Verwalten von benutzerdefinierten Erkennungen muss [Ihre Rolle](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) über die Berechtigung zum Verwalten **von Sicherheitseinstellungen** verfügen.

## <a name="view-existing-rules"></a>Anzeigen vorhandener Regeln

Navigieren Sie zum Anzeigen aller vorhandenen benutzerdefinierten Erkennungsregeln zu **Einstellungen**  >  **Benutzerdefinierte Erkennungen**. Auf der Seite sind alle Regeln mit den folgenden Ausführungsinformationen aufgeführt:

- **Letzte Ausführung**– bei der letzten Ausführung einer Regel zum Überprüfen von Abfrage übereinstimmungen und Generieren von Warnungen
- **Status der letzten Ausführung**– gibt an, ob eine Regel erfolgreich ausgeführt wurde
- **Nächste Ausführung**– die nächste geplante Ausführung
- **Status –** gibt an, ob eine Regel aktiviert oder deaktiviert wurde

## <a name="view-rule-details-modify-rule-and-run-rule"></a>Anzeigen von Regeldetails, Ändern der Regel und Ausführen der Regel

Wenn Sie umfassende Informationen zu einer benutzerdefinierten Erkennungsregel anzeigen möchten, wählen Sie in der Liste der Regeln unter **Einstellungen** Benutzerdefinierte Erkennungen den Namen  >  **der Regel aus.** Eine Seite über die ausgewählte Regel zeigt die folgenden Informationen an:

- Allgemeine Informationen zur Regel, einschließlich der Details der Warnung, des Ausführungsstatus und des Gültigkeitsbereichs
- Liste der ausgelösten Warnungen
- Liste der ausgelösten Aktionen

![Benutzerdefinierte Erkennungsregelseite](images/atp-custom-detection-rule-details.png)<br>
*Benutzerdefinierte Erkennungsregelseite*

Sie können auf dieser Seite auch die folgenden Aktionen für die Regel ausführen:

- **Ausführen**– Führen Sie die Regel sofort aus. Mit dieser Aktion wird auch das Intervall für die nächste Ausführung zurückgesetzt.
- **Bearbeiten**– Ändern der Regel, ohne die Abfrage zu ändern
- **Abfrage ändern**– Bearbeiten der Abfrage bei der erweiterten Suche
- **Aktivieren**  /  **Deaktivieren –** Aktivieren der Regel oder Beenden der Ausführung
- **Löschen**– Deaktivieren der Regel und Entfernen der Regel

>[!TIP]
>Verwenden Sie die Auswahlspalte [&#10003;] links neben der Tabelle, um Informationen schnell anzeigen und Aktionen für ein Element in einer Tabelle ergreifen zu können.

## <a name="related-topics"></a>Verwandte Themen
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
- [Erstellen von Erkennungsregeln](custom-detection-rules.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Anzeigen und Organisieren von Warnungen](alerts-queue.md)
