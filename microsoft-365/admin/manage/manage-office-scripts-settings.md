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
description: Erfahren Sie, wie Sie Office Skripteinstellungen für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572309"
---
# <a name="manage-office-scripts-settings"></a>Einstellungen für Office-Skripts verwalten

[Office Skripts](/office/dev/scripts)können Benutzer Aufgaben automatisieren, indem Sie Skripts im Excel aufzeichnen, bearbeiten und ausführen. Office Skripts funktionieren mit Power Automate, und Benutzer führen Skripts in Arbeitsmappen mithilfe des Excel Online (Business)-Connectors aus. Microsoft 365 Administratoren können Office Skripteinstellungen über das Microsoft 365 verwalten.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Zum Verwalten Office Skripteinstellungen müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).

- Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen Microsoft 365- oder Office 365-kommerziellen oder EDU-Plan verfügen, der Zugriff auf Office-Desktop-Apps umfasst, z. B. einen der folgenden Pläne:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for Business
    - Microsoft 365 Apps for Enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Verwalten der Verfügbarkeit Office Skripts und freigabe von Skripts

1. Wechseln Sie Microsoft 365 Admin Center zur Registerkarte **Einstellungen** \> **Organisationseinstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Dienste.</a>

2. Wählen **Sie Office Skripts aus.**

3. Office Skripts sind standardmäßig aktiviert, und alle Benutzer in Ihrer Organisation können auf das Feature zugreifen und diese verwenden und Skripts freigeben. Deaktivieren Sie zum deaktivieren Office Skripts für Ihre Organisation das Kontrollkästchen Benutzer automatisieren ihre Aufgaben **in Excel im Web** aktivieren.

4. Wenn Sie zuvor Office Skripts für Ihre Organisation deaktiviert haben und sie wieder aktivieren möchten, wählen Sie Benutzer automatisieren **in Excel im Web** aus, und geben Sie dann an, wer auf das Feature zugreifen und diese verwenden kann:

    - Damit alle Benutzer in Ihrer Organisation auf skripts zugreifen und Office verwenden können, lassen Sie **Jeder** (Standard) ausgewählt.

    - Um nur Mitgliedern einer bestimmten Gruppe den Zugriff auf und die Verwendung von Office-Skripts zu ermöglichen, wählen Sie Bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste der zulässigen Elemente hinzuzufügen. Sie können der Liste "Zulassen" nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Compare groups](../create-groups/compare-groups.md).

5. Um Benutzern mit Zugriff auf Office-Skripts die Freigabe ihrer Skripts für andere Benutzer in Ihrer Organisation zu ermöglichen, wählen Sie Benutzer mit Zugriff auf Office Skripts freigeben für andere Benutzer in der **Organisation aus.** Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.
 
    > [!NOTE]
    > Wenn Sie später die Skriptfreigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.
 
6. Geben Sie an, welche Benutzer zugriff auf Office Skripts ihre Skripts freigeben können:
    
    - Damit alle Benutzer mit Zugriff auf skripts Office skripts freigeben können, lassen Sie **Jeder** (standard) ausgewählt.

    - Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office-Skripts die Freigabe ihrer Skripts zu ermöglichen, wählen Sie Bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste der zulässigen Skripts hinzuzufügen. Sie können der Liste "Zulassen" nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Compare groups](../create-groups/compare-groups.md).

7. Wenn Benutzer ihre Skripts Office in Power Automate ausführen können, wählen Sie Benutzer mit Zugriff auf **Office Skripts** ihre Skripts mit Power Automate . Auf diese Weise können Benutzer Flussschritte mit der Excel [(Business)-Connector ausführen](/connectors/excelonlinebusiness) **hinzufügen.**

    - Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts in Flüssen verwenden können, lassen Sie **Jeder** (Standard) ausgewählt.

    - Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office Scripts die Verwendung ihrer Skripts in Flüssen zu ermöglichen, wählen Sie Bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste der zulässigen Skripts hinzuzufügen. Sie können der Liste "Zulassen" nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe

        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Compare groups](../create-groups/compare-groups.md).

    - Weitere Informationen zur Verwendung von Office Skripts mit Power Automate finden Sie unter [Ausführen Office Skripts mit Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Klicken Sie auf **Speichern**.

    Es kann bis zu 48 Stunden dauern, bis Änderungen Office Skripteinstellungen wirksam werden.

## <a name="next-steps"></a>Nächste Schritte

Da Office Skripts mit Power Automate zusammenarbeiten, empfehlen wir, dass Sie Ihre vorhandenen Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer skripts Office verwenden. Weitere Informationen finden Sie unter [Data Loss Prevention (DLP)-Richtlinien](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Verwandte Inhalte

[Office Technische Dokumentation zu Skripts](/office/dev/scripts/) (Linkseite)\
[Einführung in Office Skripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel)\
[Freigeben Office Skripts in Excel für das Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel)\
[Aufzeichnen, Bearbeiten und Erstellen Office Skripts in Excel im Web](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)
