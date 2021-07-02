---
title: Verwenden der Interoperabilität mit OneDrive Learning Tools
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Erstellen und Bewerten von Aufgaben, Erstellen und Kuratieren von Kursinhalten und Zusammenarbeit an Dateien in Echtzeit mit der neuen OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256984"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>Verwenden Microsoft OneDrive LTI mit Canvas

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="integrate-with-canvas"></a>Integration in Canvas

Die Person, die diese Integration durchführt, sollte ein Administrator von Canvas und ein Administrator des Microsoft 365 Mandanten sein.

1. Melden Sie sich mit dem Mandantenadministratorkonto beim Microsoft Azure-Portal an. Der Azure-Mandantenadministrator sollte auch über die Rolle "Gruppenadministrator" verfügen.

    ![Gruppenadministrator hervorgehoben](../media/lti-media/lti-group-admin.png)

2. Melden Sie sich beim Microsoft [OneDrive LTI-Portal](https://odltiappnl.azurewebsites.net/admin)an.

3. Akzeptieren Sie die Berechtigungen, um die Anmeldung abzuschließen.

    ![Berechtigungen akzeptieren](../media/lti-media/lti-permissions.png)

4. Wählen **Sie "LTI-Mandant hinzufügen"** aus.

     ![LTI-Mandant hinzufügen](../media/lti-media/lti-add-tenant.png)

5. Wählen Sie in der Dropdownliste **LTI Consumer Platform** als **Canvas** aus.

6. Wählen Sie **"Canvas-Basis-URL"** und dann **"Weiter"** aus.

    ![Canvas auswählen und Basis-URL hinzufügen](../media/lti-media/lti-canvas-base-url.png)

   Auf dem nächsten Bildschirm werden Felder angezeigt, die für Sie vertraulich sind.

7. Wählen Sie **"Weiter"** aus ?? den Link für resend the email auswählen. KÖNNEN PRÜFER HIER DIE LEERE AUSFÜLLEN?

8. Klicken Sie auf dem Bildschirm auf **"Weiter",** auf dem Informationen angezeigt werden, die Für Sie vertraulich sind.

   Der letzte Bildschirm des Azure-Portals zeigt die nächsten Schritte zum Hinzufügen Ihrer Canvas-Instanz.

9. Kopieren Sie die Entwicklerschlüssel von diesem Bildschirm. Sie werden beim Erstellen der Canvas-Instanz verwenden.

## <a name="add-the-canvas-instance"></a>Hinzufügen der Canvas-Instanz

1. Deaktivieren Sie in Ihrer Canvas-Instanz die Option **"Admin**  >  **Developer Keys".**

2. Wählen Sie **LTI-Schlüssel** in der Dropdownliste auf **"Entwicklerschlüssel" aus.**

   ![Abrufen der LTI-Entwicklerschlüssel](../media/lti-media/lti-developer-keys.png)

3. Fügen Sie die Entwicklerschlüssel hier ein.

     ![Einfügen der Entwicklerschlüssel](../media/lti-media/lti-developer-keys.png)

   Der Schlüssel wird im **AUS-Modus** erstellt.

   ![Die erstellten Entwicklerschlüssel im Aus-Modus](../media/lti-media/lti-copy-developer-keys.png)

4. Kopieren Sie den hervorgehobenen Text.
    Dies dient als Client-ID im Microsoft OneDrive LTI-Portal.

5. Fügen Sie den Text in das **Feld "Client-ID"** in Microsoft OneDrive LTI-Portal ein, und wählen Sie dann **"Weiter"** aus.

6. Klicken Sie auf **Speichern**.

7. Zeigen Sie die Einstellungen an, indem Sie **"LTI-Mandanten anzeigen"** auswählen.
