---
title: Einstellungen für Office-Skripts verwalten
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
search.appverid: MET150
description: Erfahren Sie, wie Sie Office Skripteinstellungen für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: fea50838cf1089b73a6af5bbf86d490293831085
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392671"
---
# <a name="manage-office-scripts-settings"></a>Einstellungen für Office-Skripts verwalten

[Office Skripts](/office/dev/scripts)ermöglicht Benutzern das Automatisieren von Aufgaben durch Aufzeichnen, Bearbeiten und Ausführen von Skripts in Excel im Web. Office Skripts funktionieren mit Power Automate, und Benutzer führen Skripts für Arbeitsmappen mithilfe des Excel Online-Connectors (Business) aus. Microsoft 365 Administratoren können Office Skripteinstellungen über die Microsoft 365 Admin Center verwalten.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Um Office Skripteinstellungen zu verwalten, müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter ["Informationen zu Administratorrollen".](../add-users/about-admin-roles.md)

- Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen Microsoft 365- oder Office 365 kommerziellen oder EDU-Plan verfügen, der zugriff auf Office Desktop-Apps umfasst, z. B. einen der folgenden Pläne:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for Business
    - Microsoft 365 Apps for Enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Verwalten der Verfügbarkeit von Office Skripts und der Freigabe von Skripts

1. Wechseln Sie im Microsoft 365 Admin Center zur Registerkarte **Einstellungen** \> **Organisationseinstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">für Dienste.</a>

2. Wählen Sie **Office Skripts aus.**

3. Office Skripts sind standardmäßig aktiviert, und jeder Benutzer in Ihrer Organisation kann auf das Feature zugreifen und es verwenden und Skripts freigeben. Deaktivieren Sie zum Deaktivieren Office Skripts für Ihre Organisation das Kontrollkästchen **"Benutzer ihre Aufgaben automatisieren lassen" in Excel im Web** Kontrollkästchen.

4. Wenn Sie zuvor Office Skripts für Ihre Organisation deaktiviert haben und sie wieder aktivieren möchten, wählen Sie **"Benutzer können ihre Aufgaben in Excel im Web automatisieren"** aus, und geben Sie dann an, wer auf das Feature zugreifen und es verwenden kann:

    - Damit alle Benutzer in Ihrer Organisation auf Office Skripts zugreifen und diese verwenden können, lassen **Sie "Jeder"** (Standard) ausgewählt.

    - Damit nur Mitglieder einer bestimmten Gruppe auf Office Skripts zugreifen und diese verwenden können, wählen Sie **"Bestimmte Gruppe"** aus, und geben Sie dann den Namen oder den E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen. Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter ["Gruppen vergleichen".](../create-groups/compare-groups.md)

5. Um Benutzern mit Zugriff auf Office Skripts zu ermöglichen, ihre Skripts für andere Benutzer in Ihrer Organisation freizugeben, wählen Sie **"Benutzer mit Zugriff auf Office Skripts ihre Skripts für andere Personen in der Organisation freigeben"** aus. Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.
 
    > [!NOTE]
    > Wenn Sie später die Skriptfreigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.
 
6. Geben Sie an, welche Benutzer zugriff auf Office Skripts ihre Skripts freigeben können:
    
    - Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts freigeben können, lassen **Sie "Jeder"** (Standard) ausgewählt.

    - Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office Skripts die Freigabe ihrer Skripts zu ermöglichen, wählen Sie **bestimmte Gruppe** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen. Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter ["Gruppen vergleichen".](../create-groups/compare-groups.md)

7. Um Benutzern das Ausführen ihrer Office Skripts in Power Automate Flüssen zu ermöglichen, wählen Sie **"Benutzer mit Zugriff auf Office Skripts ausführen ihre Skripts mit Power Automate .** Auf diese Weise können Benutzer Flussschritte mit der **Skriptoption "Ausführen"** des [Excel Online (Business)-Connectors](/connectors/excelonlinebusiness) hinzufügen.

    - Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts in Flüssen verwenden können, lassen **Sie "Jeder"** (Standard) ausgewählt.

    - Damit nur Mitglieder einer bestimmten Gruppe mit Zugriff auf Office Skripts ihre Skripts in Flüssen verwenden können, wählen Sie **"Bestimmte Gruppe"** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen. Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe

        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter ["Gruppen vergleichen".](../create-groups/compare-groups.md)

    - Weitere Informationen zur Verwendung von Office Skripts mit Power Automate finden Sie unter [Ausführen Office Skripts mit Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Klicken Sie auf **Speichern**.

    Es kann bis zu 48 Stunden dauern, bis Änderungen in den Einstellungen von Office-Skripts wirksam werden.

## <a name="next-steps"></a>Nächste Schritte

Da Office Skripts mit Power Automate zusammenarbeiten, empfehlen wir, ihre vorhandenen DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) zu überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer Office Skripts verwenden. Weitere Informationen finden Sie unter [Richtlinien zur Verhinderung von Datenverlust (DLP)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Verwandte Inhalte

[technische Dokumentation zu Office Skripts](/office/dev/scripts/) (Linkseite)\
[Einführung in Office Skripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel)\
[Freigeben Office Skripts in Excel für das Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel)\
[Aufzeichnen, Bearbeiten und Erstellen Office Skripts in Excel im Web](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)
