---
title: Verwenden der Interoperabilität mit Microsoft OneDrive Learning Tools
ms.author: heidip
author: MicrosoftHeidi
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
description: Erstellen und Bewerten von Aufgaben, Erstellen und Kuratieren von Kursinhalten und Zusammenarbeit an Dateien in Echtzeit mit der neuen Interoperabilitäts-App für Microsoft OneDrive Learning Tools.
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257018"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Integrieren Microsoft OneDrive LTI in Canvas

Die Integration Microsoft OneDrive LTI in Canvas ist ein zweistufiger Prozess. Der erste Schritt aktiviert Microsoft OneDrive in Canvas, und im zweiten Schritt wird die Microsoft OneDrive LTI in Canvas-Kursen verfügbar.

## <a name="recommended-browser-settings"></a>Empfohlene Browsereinstellungen

- Cookies sollten für Microsoft OneDrive aktiviert sein.
- Popups sollten nicht für Microsoft OneDrive blockiert werden.

> [!NOTE]
> - Cookies sind im Inkognito-Modus des Chrome-Browsers nicht standardmäßig aktiviert und müssen aktiviert werden.
> - Microsoft OneDrive LTI funktioniert im privaten Modus in Microsoft Edge Browser. Stellen Sie sicher, dass Sie keine Cookies blockiert haben (die standardmäßig aktiviert sind).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Aktivieren Microsoft OneDrive LTI in Canvas

> [!IMPORTANT]
> Die Person, die diese Integration durchführt, sollte ein Administrator von Canvas und ein Administrator des Microsoft 365 Mandanten sein.

1. Melden Sie sich beim <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI-Registrierungsportal an.</a>
1. Wählen Sie die Schaltfläche **"Administratorzustimmung"** aus, und akzeptieren Sie die Berechtigungen.
1. Wählen Sie die Schaltfläche **"Neuen LTI-Mandanten erstellen"** aus. **Wählen** Sie auf der LTI-Registrierungsseite canvas in der Dropdownliste aus, und geben Sie die Basis-URL Ihrer Canvas-Instanz ein.

> [!NOTE]
> Wenn Ihre Canvas-Instanz z. B. https://contoso.test.instructure.com ]( https://contoso.test.instructure.com) ist, sollte die vollständige URL eingegeben werden.

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Die LTI-Mandantenverwaltungsseite mit einem Dropdownfeld zum Auswählen der LTI-Verbraucherplattform und einem URL-Textfeld.":::

4. Kopieren Sie den JSON-Code, indem Sie die Schaltfläche **"Kopieren"** auswählen (ein Symbol auf der rechten Seite, das zwei Seiten übereinander zeigt). Dies wird verwendet, um den Schlüssel in Canvas zu generieren.

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Ein Bild mit der Schaltfläche zum Kopieren, die den angezeigten JSON-Text kopiert und für die Schlüsselgenerierung in Canvas verfügbar macht.":::

5. Melden Sie sich als Administrator bei Ihrer Canvas-Instanz an, und wählen Sie im Menü auf der linken Seite der Seite die Option **"Entwicklerschlüssel"** aus. Erstellen Sie in der Dropdownliste einen Entwicklerschlüssel, indem Sie **LTI Key** aus der Dropdownliste oben rechts auf der Seite auswählen.

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Screenshot der linken Navigationsleiste mit ausgewählten Entwicklerschlüsseln und ausgewählter LTI-Tasteneingabe in einer Dropdownliste auf der rechten Seite.":::

6. Wählen Sie auf der Seite "Konfigurieren" im Dropdown **"Methode"** die Option "JSON als Methode **einfügen"** aus, und fügen Sie den JSON-Text, den Sie in Schritt 5 kopiert haben, in das angezeigte Textfeld ein.
7. Speichern Sie den Schlüssel, und er wird in Canvas im **Status "Aus"** verfügbar. Aktivieren Sie den **Schlüssel,** und kopieren Sie den in der Spalte **"Details"** angegebenen Schlüssel, der im nächsten Schritt verwendet werden soll.

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Die Canvas-Seite, auf der der Schlüssel in einem ausgeschalteten Zustand festgelegt ist. Sie muss aktiviert sein, und der Schlüssel muss aus der Detailspalte auf dieser Seite kopiert werden.":::

8. Kehren Sie zum Microsoft OneDrive LTI-Registrierungsportal zurück, und fügen Sie den Schlüssel in das **Canvas-Client-ID-Feld** ein. Wählen Sie **"Weiter"** aus, wenn Sie bereit sind.

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Die LTI-Mandantenregistrierungsseite, die den JSON-Text und das Textfeld anzeigt, in das der Schlüssel kopiert werden soll.":::

9. Überprüfen und speichern Sie Ihre Änderungen. Bei erfolgreicher Registrierung wird eine Meldung angezeigt.
10. Ihre Registrierungsdetails können auch überprüft werden, indem Sie auf der Startseite die Schaltfläche **"LTI-Mandanten anzeigen"** auswählen.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Aktivieren Microsoft OneDrive LTI in Canvas-Kursen

Ein Canvas-Administrator kann Microsoft OneDrive LTI für alle Kurse aktivieren. Wenn Microsoft OneDrive LTI in einem bestimmten Kurs (und nicht in allen Kursen) benötigt wird, muss die Kursleiterin die gleichen Schritte in den Kurseinstellungen ausführen.

1. Melden Sie sich als Administrator an, und wechseln Sie zum **Abschnitt Einstellungen.**
2. Wechseln Sie zum Abschnitt **"Apps",** und wählen Sie die Schaltfläche **"App-Konfigurationen anzeigen" aus.**
3. Wählen Sie die Schaltfläche **"App hinzufügen"** aus.
4. Wählen Sie im Dropdownmenü **"Konfigurationstyp"** die Option **"Nach Client-ID"** aus.
5. Fügen Sie den Wert des zuvor generierten Entwicklerschlüssels in das **Feld "Client-ID"** ein, und wählen Sie die Schaltfläche **"Absenden"** aus.

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Die Seite &quot;App hinzufügen&quot;, auf der die Option &quot;Nach Client-ID&quot; im Dropdownmenü &quot;Konfigurationstyp&quot; angezeigt wird.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Zusammenarbeits-Einstellungen für Microsoft OneDrive LTI in Canvas-Kursen

> [!NOTE]
> Damit die Zusammenarbeit für Lehrkräfte und Schüler/Studenten funktioniert, sollten Sie die Einstellung für die Zusammenarbeit nicht aktivieren. Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die Einstellung nicht aktiviert ist.

1. Melden Sie sich als Administrator an, und wechseln Sie zum **Abschnitt Einstellungen.**
1. Wechseln Sie zum Abschnitt **"Featureoptionen",** und wechseln Sie dann zum Abschnitt **"Kurs".**
1. Legen Sie fest, dass das Feature **"Tool für externe Zusammenarbeiten"** nicht aktiviert ist.

> [!NOTE]
> Die Zusammenarbeit kann einzelnen Kursteilnehmern und Gruppen von Kursteilnehmern zugewiesen werden. Das Zuweisen zu einzelnen Kursteilnehmern funktioniert standardmäßig. Führen Sie die folgenden Schritte aus, um einer Gruppe von Schülern/Studenten zusammenarbeiten zu können:

1. Melden Sie sich als Administrator an, und wechseln Sie zum Abschnitt **"Entwicklerschlüssel".**
1. Suchen Sie den Schlüssel mit dem Wert 170000000000710, und legen Sie ihn auf **"Ein"** fest.
