---
title: Konfigurieren von Benachrichtigungen in Microsoft Defender for Endpoint
description: Sie können Microsoft Defender for Endpoint verwenden, um E-Mail-Benachrichtigungseinstellungen für Sicherheitswarnungen basierend auf dem Schweregrad und anderen Kriterien zu konfigurieren.
keywords: E-Mail-Benachrichtigungen, Konfigurieren von Benachrichtigungen, Microsoft Defender für Endpunktbenachrichtigungen, Microsoft Defender für Endpunktbenachrichtigungen, Windows 10 Enterprise, Windows 10 Education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c60bed1fb2cc17c9f5dfbd1289ae5f5b5e13faec
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933949"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Konfigurieren von Benachrichtigungen in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

Sie können Defender for Endpoint so konfigurieren, dass E-Mail-Benachrichtigungen für neue Warnungen an angegebene Empfänger gesendet werden. Mit diesem Feature können Sie eine Gruppe von Personen identifizieren, die sofort informiert werden und basierend auf ihrem Schweregrad auf Warnungen reagieren können.

> [!NOTE]
> Nur Benutzer mit den Berechtigungen "Sicherheitseinstellungen verwalten" können E-Mail-Benachrichtigungen konfigurieren. Wenn Sie sich für die Verwendung der grundlegenden Berechtigungsverwaltung entschieden haben, können Benutzer mit Sicherheitsadministrator- oder globalen Administratorrollen E-Mail-Benachrichtigungen konfigurieren.

Sie können die Benachrichtigungsschweregrade festlegen, die Benachrichtigungen auslösen. Sie können auch Empfänger der E-Mail-Benachrichtigung hinzufügen oder entfernen. Neue Empfänger werden über Warnungen benachrichtigt, die ausgelöst werden, nachdem sie hinzugefügt wurden. Weitere Informationen zu Warnungen finden Sie unter [Anzeigen und Organisieren der Warnungswarteschlange](alerts-queue.md).

Wenn Sie die rollenbasierte Zugriffssteuerung verwenden, erhalten Empfänger nur Benachrichtigungen basierend auf den Gerätegruppen, die in der Benachrichtigungsregel konfiguriert wurden.
Benutzer mit der entsprechenden Berechtigung können nur Benachrichtigungen erstellen, bearbeiten oder löschen, die auf den Verwaltungsbereich der Gerätegruppe beschränkt sind.
Nur Benutzer, die der globalen Administratorrolle zugewiesen sind, können Benachrichtigungsregeln verwalten, die für alle Gerätegruppen konfiguriert sind.

Die E-Mail-Benachrichtigung enthält grundlegende Informationen zu der Warnung und einen Link zum Portal, in dem Sie weitere Untersuchungen machen können.


## <a name="create-rules-for-alert-notifications"></a>Erstellen von Regeln für Benachrichtigungen
Sie können Regeln erstellen, die die Geräte und Denkschweregrade zum Senden von E-Mail-Benachrichtigungen für und die Benachrichtigungsempfänger bestimmen.


1. Wählen Sie im Navigationsbereich die **Option Einstellungen**  >  **E-Mail-Benachrichtigungen aus.**

2. Klicken Sie **auf Element hinzufügen**.

3. Geben Sie die allgemeinen Informationen an:
    - **Regelname** : Geben Sie einen Namen für die Benachrichtigungsregel an.
    - **Name der Organisation angeben** – Geben Sie den Kundennamen an, der in der E-Mail-Benachrichtigung angezeigt wird.
    - **Mandantenspezifischer Portallink hinzufügen** – Fügt einen Link mit der Mandanten-ID hinzu, um zugriff auf einen bestimmten Mandanten zu ermöglichen.
    - **Geräteinformationen enthalten** – Enthält den Gerätenamen im E-Mail-Benachrichtigungstext.
    
        >[!NOTE]
        > Diese Informationen werden möglicherweise von E-Mail-Empfängerservern verarbeitet, die sich nicht am geografischen Standort befinden, den Sie für Ihre Defender for Endpoint-Daten ausgewählt haben.

    - **Geräte** : Wählen Sie aus, ob Empfänger für Warnungen auf allen Geräten (nur globale Administratorrolle) oder auf ausgewählten Gerätegruppen benachrichtigt werden sollen. Weitere Informationen finden Sie unter [Create and manage device groups](machine-groups.md).
    - **Warnungsschweregrad** : Wählen Sie den Schweregrad der Warnung aus.

4. Klicken Sie auf **Weiter**.
    
5. Geben Sie die E-Mail-Adresse des Empfängers ein, und klicken Sie dann **auf Empfänger hinzufügen.** Sie können mehrere E-Mail-Adressen hinzufügen.

6. Überprüfen Sie, ob E-Mail-Empfänger die E-Mail-Benachrichtigungen empfangen können, indem **Sie Test-E-Mail senden auswählen.**

7. Klicken **Sie auf Benachrichtigungsregel speichern.**

## <a name="edit-a-notification-rule"></a>Bearbeiten einer Benachrichtigungsregel
1. Wählen Sie die Benachrichtigungsregel aus, die Sie bearbeiten möchten.

2. Aktualisieren Sie die Registerkarteninformationen Allgemein und Empfänger.

3. Klicken **Sie auf Benachrichtigungsregel speichern.**


## <a name="delete-notification-rule"></a>Benachrichtigungsregel löschen

1. Wählen Sie die Benachrichtigungsregel aus, die Sie löschen möchten.

2. Klicken Sie auf **Löschen**.


## <a name="troubleshoot-email-notifications-for-alerts"></a>Problembehandlung bei E-Mail-Benachrichtigungen für Warnungen
In diesem Abschnitt werden verschiedene Probleme aufgeführt, die bei der Verwendung von E-Mail-Benachrichtigungen für Warnungen auftreten können.

**Problem:** Beabsichtigte Empfänger melden, dass sie die Benachrichtigungen nicht erhalten.

**Lösung:** Stellen Sie sicher, dass die Benachrichtigungen nicht von E-Mail-Filtern blockiert werden:

1. Überprüfen Sie, ob die Defender for Endpoint-E-Mail-Benachrichtigungen nicht an den Junk-E-Mail-Ordner gesendet werden. Markieren Sie sie als Nicht junk.
2. Überprüfen Sie, ob Ihr E-Mail-Sicherheitsprodukt die E-Mail-Benachrichtigungen von Defender for Endpoint nicht blockiert.
3. Überprüfen Sie Ihre E-Mail-Anwendungsregeln, die Ihre Defender for Endpoint-E-Mail-Benachrichtigungen möglicherweise abfangen und verschieben.

## <a name="related-topics"></a>Verwandte Themen
- [Aktualisieren von Einstellungen für die Datenaufbewahrung](data-retention-settings.md)
- [Konfigurieren erweiterter Funktionen](advanced-features.md)
