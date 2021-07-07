---
title: Konfigurieren von Warnungsbenachrichtigungen in Microsoft Defender für Endpunkt
description: Sie können Microsoft Defender für Endpunkt verwenden, um E-Mail-Benachrichtigungseinstellungen für Sicherheitswarnungen basierend auf dem Schweregrad und anderen Kriterien zu konfigurieren.
keywords: E-Mail-Benachrichtigungen, Warnungsbenachrichtigungen konfigurieren, Microsoft Defender für Endpunkt, Microsoft Defender für Endpunktbenachrichtigungen, Windows 10 Enterprise, Windows 10 Education
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
ms.openlocfilehash: d423c5051634334f9dbb19b236446cdb579aef69
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327035"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Konfigurieren von Warnungsbenachrichtigungen in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

Sie können Defender für Endpunkt so konfigurieren, dass E-Mail-Benachrichtigungen an angegebene Empfänger für neue Warnungen gesendet werden. Mit diesem Feature können Sie eine Gruppe von Personen identifizieren, die sofort informiert werden und basierend auf ihrem Schweregrad auf Warnungen reagieren können.

> [!NOTE]
> Nur Benutzer mit berechtigungen zum Verwalten von Sicherheitseinstellungen können E-Mail-Benachrichtigungen konfigurieren. Wenn Sie die grundlegende Berechtigungsverwaltung verwendet haben, können Benutzer mit Sicherheitsadministrator- oder globalen Administratorrollen E-Mail-Benachrichtigungen konfigurieren.

Sie können die Warnungsschweregrade festlegen, die Benachrichtigungen auslösen. Sie können auch Empfänger der E-Mail-Benachrichtigung hinzufügen oder entfernen. Neue Empfänger werden über Warnungen benachrichtigt, die ausgelöst werden, nachdem sie hinzugefügt wurden. Weitere Informationen zu Warnungen finden Sie unter [Anzeigen und Organisieren der Warnungswarteschlange.](alerts-queue.md)

Wenn Sie die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwenden, erhalten Empfänger nur Benachrichtigungen basierend auf den Gerätegruppen, die in der Benachrichtigungsregel konfiguriert wurden.
Benutzer mit der richtigen Berechtigung können nur Benachrichtigungen erstellen, bearbeiten oder löschen, die auf ihren Gerätegruppenverwaltungsbereich beschränkt sind.
Nur Benutzer, die der Rolle "Globaler Administrator" zugewiesen sind, können Benachrichtigungsregeln verwalten, die für alle Gerätegruppen konfiguriert sind.

Die E-Mail-Benachrichtigung enthält grundlegende Informationen zu der Warnung und einen Link zum Portal, in dem Sie weitere Untersuchungen durchführen können.

## <a name="create-rules-for-alert-notifications"></a>Erstellen von Regeln für Warnungsbenachrichtigungen
Sie können Regeln erstellen, die die Geräte und Warnungsschweregrade zum Senden von E-Mail-Benachrichtigungen für und die Benachrichtigungsempfänger bestimmen.


1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **E-Mail-Benachrichtigungen** aus.

2. Klicken Sie auf **"Element hinzufügen".**

3. Geben Sie die allgemeinen Informationen an:
    - **Regelname** : Geben Sie einen Namen für die Benachrichtigungsregel an.
    - **Organisationsname einschließen** – Geben Sie den Kundennamen an, der in der E-Mail-Benachrichtigung angezeigt wird.
    - **Mandantenspezifischer Portallink** einschließen – Fügt einen Link mit der Mandanten-ID hinzu, um den Zugriff auf einen bestimmten Mandanten zu ermöglichen.
    - **Geräteinformationen einschließen** – Enthält den Gerätenamen im E-Mail-Warnungstext.

        > [!NOTE]
        > Diese Informationen werden möglicherweise von Empfänger-E-Mail-Servern verarbeitet, die sich nicht an dem geografischen Standort befinden, den Sie für Ihre Defender für Endpunkt-Daten ausgewählt haben.

    - **Geräte** – Wählen Sie aus, ob Empfänger bei Warnungen auf allen Geräten benachrichtigt werden sollen (nur globale Administratorrolle) oder in ausgewählten Gerätegruppen. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen.](machine-groups.md)
    - **Warnungsschweregrad** – Wählen Sie den Warnungsschweregrad aus.

4. Klicken Sie auf **Weiter**.

5. Geben Sie die E-Mail-Adresse des Empfängers ein, und klicken Sie dann auf **"Empfänger hinzufügen".** Sie können mehrere E-Mail-Adressen hinzufügen.

6. Überprüfen Sie, ob E-Mail-Empfänger die E-Mail-Benachrichtigungen erhalten können, indem Sie **"Test-E-Mail senden"** auswählen.

7. Klicken Sie auf **"Benachrichtigungsregel speichern".**

## <a name="edit-a-notification-rule"></a>Bearbeiten einer Benachrichtigungsregel

1. Wählen Sie die Benachrichtigungsregel aus, die Sie bearbeiten möchten.

2. Aktualisieren Sie die Registerkarteninformationen "Allgemein" und "Empfänger".

3. Klicken Sie auf **"Benachrichtigungsregel speichern".**

## <a name="delete-notification-rule"></a>Benachrichtigungsregel löschen

1. Wählen Sie die Benachrichtigungsregel aus, die Sie löschen möchten.

2. Klicken Sie auf **Löschen**.

## <a name="troubleshoot-email-notifications-for-alerts"></a>Problembehandlung bei E-Mail-Benachrichtigungen für Warnungen

In diesem Abschnitt werden verschiedene Probleme aufgeführt, die bei der Verwendung von E-Mail-Benachrichtigungen für Warnungen auftreten können.

**Problem:** Beabsichtigte Empfänger melden, dass sie die Benachrichtigungen nicht erhalten.

**Lösung:** Stellen Sie sicher, dass die Benachrichtigungen nicht durch E-Mail-Filter blockiert werden:

1. Überprüfen Sie, ob die Defender für Endpunkt-E-Mail-Benachrichtigungen nicht an den Junk-E-Mail-Ordner gesendet werden. Markieren Sie sie als "Nicht junk".
2. Überprüfen Sie, ob Ihr E-Mail-Sicherheitsprodukt die E-Mail-Benachrichtigungen von Defender für Endpunkt nicht blockiert.
3. Überprüfen Sie ihre E-Mail-Anwendungsregeln, die Ihre Defender für Endpunkt-E-Mail-Benachrichtigungen möglicherweise abfangen und verschieben.

## <a name="related-topics"></a>Verwandte Themen

- [Aktualisieren der Einstellungen für die Datenaufbewahrung](data-retention-settings.md)
- [Konfigurieren erweiterter Funktionen](advanced-features.md)
- [Konfigurieren von E-Mail-Benachrichtigungen zu Sicherheitsrisiken in Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
