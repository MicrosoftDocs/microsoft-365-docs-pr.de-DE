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
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Erfahren Sie, wie Sie Einstellungen für Office-Skripts für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058423"
---
# <a name="manage-office-scripts-settings"></a>Einstellungen für Office-Skripts verwalten

Mit Office Scripts können Benutzer Aufgaben automatisieren, indem Skripts in Excel im Web aufgezeichnet, bearbeitet und ausgeführt werden. Office Scripts funktioniert mit Power Automate, und Benutzer führen Skripts in Arbeitsmappen mithilfe des Excel Online (Business)-Connectors aus. Microsoft 365-Administratoren können Einstellungen für Office-Skripts über das Microsoft 365 Admin Center verwalten.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Zum Verwalten von Einstellungen für Office-Skripts müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter ["Informationen zu Administratorrollen".](../add-users/about-admin-roles.md)

- Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen kommerziellen Microsoft 365- oder Office 365-Bildungsplan verfügen, der Zugriff auf Office-Desktop-Apps umfasst, z. B. einen der folgenden Pläne:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for Business
    - Microsoft 365 Apps for Enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Verwalten der Verfügbarkeit von Office-Skripts und der Freigabe von Skripts

1. Wechseln Sie im Microsoft 365 Admin Center zur Registerkarte **"Einstellungen** \> **für** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Organisationseinstellungen".</a>

2. Wählen Sie **Office-Skripts aus.**

3. Office-Skripts sind standardmäßig aktiviert, und jeder in Ihrer Organisation kann auf das Feature zugreifen und es verwenden und Skripts freigeben. Deaktivieren Sie das Kontrollkästchen "Benutzern das Automatisieren ihrer Aufgaben **in Excel im Web** ermöglichen", um die Office-Skripts für Ihre Organisation zu deaktivieren.

4. Wenn Sie zuvor die Office-Skripts für Ihre Organisation deaktiviert haben und wieder aktivieren möchten, wählen Sie "Benutzern das Automatisieren ihrer Aufgaben **in Excel im Web** ermöglichen" aus, und geben Sie dann an, wer auf das Feature zugreifen und es verwenden kann:

    - Um allen Benutzern in Ihrer Organisation den Zugriff auf und die Verwendung von Office-Skripts zu ermöglichen, lassen Sie **"Jeder"** (Standard) ausgewählt.

    - Um nur Mitgliedern einer bestimmten Gruppe den Zugriff auf und die Verwendung von Office-Skripts zu ermöglichen, wählen Sie eine bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste "Zulassen" hinzuzufügen. Sie können nur eine Gruppe zur Liste der zulässigen Gruppen hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365-Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Vergleichen von Gruppen.](../create-groups/compare-groups.md)

5. Damit Benutzer mit Zugriff auf Office-Skripts ihre Skripts für andere Personen in Ihrer Organisation freigeben können, wählen Sie "Benutzern mit Zugriff auf Office-Skripts erlauben" aus, ihre Skripts für andere Personen in der **Organisation zu freigeben.** Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.
 
    > [!NOTE]
    > Wenn Sie später die Skriptfreigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.
 
6. Geben Sie an, welche Benutzer mit Zugriff auf Office-Skripts ihre Skripts freigeben können:
    
    - Damit alle Benutzer mit Zugriff auf Office-Skripts ihre Skripts freigeben können, lassen Sie **"Jeder"** (Standard) ausgewählt.

    - Damit nur Mitglieder einer bestimmten Gruppe mit Zugriff auf Office-Skripts ihre Skripts freigeben können, wählen Sie eine bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste "Zulassen" hinzuzufügen. Sie können nur eine Gruppe zur Liste der zulässigen Gruppen hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365-Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Vergleichen von Gruppen.](../create-groups/compare-groups.md)

7. Damit Benutzer ihre Office-Skripts in Power Automate-Flüssen ausführen können, wählen Sie "Benutzern mit Zugriff auf Office-Skripts die Ausführung ihrer Skripts mit **Power Automate erlauben" aus.** Auf diese Weise können Benutzer Flussschritte mit der Skriptoption "Ausführen" des [Excel Online (Business)-Connectors](/connectors/excelonlinebusiness) **hinzufügen.**

    - Damit alle Benutzer mit Zugriff auf Office-Skripts ihre Skripts in Flüssen verwenden können, lassen Sie **"Jeder"** (Standard) ausgewählt.

    - Damit nur Mitglieder einer bestimmten Gruppe mit Zugriff auf Office-Skripts ihre Skripts in Flüssen verwenden können, wählen Sie eine bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste "Zulassen" hinzuzufügen. Sie können der Liste "Zulassen" nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365-Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe

        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Vergleichen von Gruppen.](../create-groups/compare-groups.md)

    - Weitere Informationen zur Verwendung von Office-Skripts mit Power Automate, einschließlich der Auswirkungen auf Ihre Richtlinien zur Verhinderung von Datenverlust, finden Sie unter Ausführen von [Office-Skripts mit Power Automate.](/office/dev/scripts/develop/power-automate-integration)

8. Wählen Sie **Speichern** aus.

    Es kann bis zu 48 Stunden dauern, bis Änderungen an den Einstellungen für Office-Skripts wirksam werden.

## <a name="next-steps"></a>Nächste Schritte

Da Office Scripts mit Power Automate verwendet werden können, sollten Sie Ihre vorhandenen Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer Office Scripts verwenden. Weitere Informationen finden Sie unter Richtlinien zur [Verhinderung von Datenverlust (Data Loss Prevention, DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Verwandte Inhalte

[Technische Dokumentation zu Office Scripts](/office/dev/scripts/) (Linkseite)\
[Einführung in Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel)\
[Freigeben von Office-Skripts in Excel für das Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel)\
[Aufzeichnen, Bearbeiten und Erstellen von Office-Skripts in Excel im Web](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)
