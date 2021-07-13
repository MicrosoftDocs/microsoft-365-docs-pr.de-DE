---
title: Aktivieren von Microsoft 365-Nutzungsanalysen
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Erfahren Sie, wie Sie mit dem Sammeln von Daten für Ihren Mandanten beginnen, indem Sie die Vorlagen-App Microsoft 365 Usage Analytics in Power BI verwenden.
ms.openlocfilehash: c0e39a307ee75c661e0f91fcbbcfeae3d95c7257
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394749"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Aktivieren von Microsoft 365-Nutzungsanalysen

Microsoft 365 Nutzungsanalyse ist für Microsoft 365 US Government Community noch nicht verfügbar.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 Admin Center, then initiate the template app in Power BI.

## <a name="get-power-bi"></a>So erhalten Sie Power BI

Wenn Sie noch nicht über Power BI verfügen, können Sie [sich für Power BI Pro registrieren.](https://go.microsoft.com/fwlink/p/?linkid=845347) Wählen Sie **"Kostenlos testen"** aus, um sich für eine Testversion zu registrieren, oder **"Jetzt kaufen",** um Power BI Pro zu erhalten.


Sie können auch **Produkte** erweitern, um eine Power BI-Version zu erwerben.

> [!NOTE]
> Sie benötigen eine Power BI Pro Lizenz zum Installieren, Anpassen und Verteilen einer Vorlagen-App. Weitere Informationen finden Sie unter ["Voraussetzungen".](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

Um Ihre Daten freizugeben, benötigen Sie und die Personen, mit denen Sie die Daten teilen, eine Power BI Pro Lizenz, oder der Inhalt muss sich in einem Arbeitsbereich in einem [Power BI Premiumdienst](/power-bi/service-premium-what-is)befinden.

## <a name="enable-the-template-app"></a>Aktivieren der Vorlagen-App

Um die Vorlagen-App zu aktivieren, müssen Sie ein **globaler Administrator** sein.

Weitere Informationen finden Sie [unter "Administratorrollen".](../add-users/about-admin-roles.md)

1. Wechseln Sie im Admin Center zur Registerkarte **Einstellungen** \> **Organisationseinstellungen** \> **für Dienste.**

2. Wählen Sie auf der Registerkarte **"Dienste"** die Option  **"Berichte"** aus.

3. Legen Sie im daraufhin geöffneten Berichtsbereich **"Berichtsdaten verfügbar machen" für Microsoft 365 Nutzungsanalyse für Power BI** **auf "Beim** \> **Speichern"** fest.

Der Datensammlungsprozess wird in zwei bis 48 Stunden abgeschlossen, abhängig von der Größe Ihres Mandanten. Die Schaltfläche **"Zu Power BI** wechseln" wird aktiviert (nicht mehr grau), wenn die Datensammlung abgeschlossen ist.

## <a name="start-the-template-app"></a>Starten der Vorlagen-App

Um die Vorlagen-App zu starten, müssen Sie entweder **ein globaler Administrator,** **ein Berichtsleser,** **Exchange Administrator,** **Skype for Business Administrator** oder **SharePoint Administrator** sein.

1. Kopieren Sie die Mandanten-ID, und wählen Sie **"Zu Power BI** wechseln" aus.

2. Wenn Power BI angezeigt wird, melden Sie sich an. Wählen **Sie** dann Apps -> **aus** dem Navigationsmenü aus.

3. Geben Sie auf der Registerkarte **"Apps"** Microsoft 365 in das Suchfeld ein, und wählen Sie dann **Microsoft 365 Nutzungsanalyse** abrufen \> **aus.**

    [![Wählen Sie "Jetzt abrufen" aus.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)

4. Sobald die App installiert ist. Wählen Sie die Kachel aus, um sie zu öffnen.

5. Wählen Sie **"App erkunden"** aus, um die App mit Beispieldaten anzuzeigen. Wählen Sie **Verbinden** aus, um die App mit den Daten Ihrer Organisation zu verbinden.

6. Wählen Sie im Verbinden **Verbinden** aus, um den Bildschirm für die **Nutzungsanalyse zu Microsoft 365,** geben Sie dann die Mandanten-ID (ohne Gedankenstriche) ein, die Sie in Schritt (1) kopiert haben, und wählen Sie **"Weiter"** aus.

7. Wählen Sie auf dem nächsten Bildschirm **OAuth2** als **Authentifizierungsmethode** \> **aus.** Wenn Sie eine andere Authentifizierungsmethode auswählen, schlägt die Verbindung mit der Vorlagen-App fehl.

    ![Auswählen eines Microsoft-Kontos als Authentifizierungsmethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. Nachdem die Vorlagen-App instanziiert wurde, ist das Dashboard für die Nutzungsanalyse Microsoft 365 in Power BI im Web verfügbar. Das erste Laden des Dashboards dauert zwischen 2 und 30 Minuten.

Aggregate auf Mandantenebene sind nach der Anmeldung in allen Berichten verfügbar. **Details auf Benutzerebene werden erst am 5. des nächsten Kalendermonats verfügbar sein, nachdem Sie sich angemeldet haben.** Dies wirkt sich auf alle Berichte unter "Benutzeraktivität&quot; aus (Tipps zum Anzeigen und Verwenden dieser Berichte finden Sie [unter &quot;Navigieren und Verwenden der Berichte in Microsoft 365 Nutzungsanalyse").](navigate-and-utilize-reports.md)

## <a name="make-the-collected-data-anonymous"></a>Anonymisieren der gesammelten Daten

Sie müssen ein globaler Administrator sein, um die für alle Berichte gesammelten Daten anonymisieren zu können. Dadurch werden identifizierbare Informationen wie Benutzer-, Gruppen- und Websitenamen in Berichten und in der Vorlagen-App ausgeblendet.

1. Wechseln Sie im Admin Center zum **Einstellungen** \> **Org Einstellungen,** und wählen Sie unter **"Dienste"** die Option **"Berichte"** aus.

2. Wählen Sie **"Berichte"** und dann **"Anonyme Bezeichner anzeigen" aus.** Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.

3. Wählen Sie **Änderungen speichern** aus.

## <a name="related-content"></a>Verwandte Inhalte

[Informationen zu Nutzungsanalysen](usage-analytics.md) (Artikel)\
[Abrufen der neuesten Version der Nutzungsanalyse](get-the-latest-version-of-usage-analytics.md) (Artikel)\
[Navigieren und Nutzen der Berichte in Microsoft 365 Nutzungsanalyse](navigate-and-utilize-reports.md) (Artikel)