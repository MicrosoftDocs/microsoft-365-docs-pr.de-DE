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

[Office-Skripts](/office/dev/scripts)ermöglicht es Benutzern, Aufgaben zu automatisieren, indem sie Skripts in Excel im Web aufzeichnen, bearbeiten und ausführen. Office Skripts arbeiten mit Power Automate, und Benutzer führen Skripts in Arbeitsmappen mithilfe des Excel Online-Connector (Business) aus. Microsoft 365 Administratoren können Office Scripts-Einstellungen über das Microsoft 365 Admin Center verwalten.

## <a name="before-you-begin"></a>Bevor Sie loslegen

- Um Office Scripts-Einstellungen zu verwalten, müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).

- Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen Microsoft 365 oder Office 365 kommerziellen oder EDU-Plan verfügen, der den Zugriff auf Office Desktop-Apps umfasst, z. B. einen der folgenden Pläne:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for Business
    - Microsoft 365 Apps for Enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Verwalten der Verfügbarkeit Office Skripts und Freigeben von Skripts

1. Wechseln Sie im Microsoft 365 Admin Center zur Registerkarte **Einstellungen** \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Organisationsdienste.</a>

2. Wählen Sie **Office Scripts** aus.

3. Office Skripts sind standardmäßig aktiviert, und jeder in Ihrer Organisation kann auf die Feature- und Freigabeskripts zugreifen und diese verwenden. Um Office Skripts für Ihre Organisation zu deaktivieren, deaktivieren Sie das Kontrollkästchen **Benutzer automatisieren lassen, Excel im Web.**

4. Wenn Sie zuvor Office Skripts für Ihre Organisation deaktiviert haben und sie wieder aktivieren möchten, wählen Sie **Benutzer in Excel im Web automatisieren** aus, und geben Sie dann an, wer auf die Funktion zugreifen und diese verwenden kann:

    - Damit alle Benutzer in Ihrer Organisation auf Office Skripts zugreifen und diese verwenden können, lassen Sie **Alle** (Standard) ausgewählt.

    - Um nur Mitgliedern einer bestimmten Gruppe den Zugriff auf und die Verwendung Office Skripts zu ermöglichen, wählen Sie **Spezifische Gruppe** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen. Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und es muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter Vergleichen von [Gruppen](../create-groups/compare-groups.md).

5. Damit Benutzer mit Zugriff auf Office Skripts ihre Skripts für andere Benutzer in Ihrer Organisation freigeben können, wählen Sie **Benutzer mit Zugriff auf Office Skripts für andere in der Organisation freigeben.** Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.
 
    > [!NOTE]
    > Wenn Sie später die Skriptfreigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.
 
6. Geben Sie an, welche Benutzer mit Zugriff auf Office Skripts ihre Skripts freigeben können:
    
    - Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts freigeben können, lassen Sie **Alle** (standardwert) ausgewählt.

    - Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office Skripts die Freigabe ihrer Skripts zu ermöglichen, wählen Sie **Spezifische Gruppe** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen. Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und es muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter Vergleichen von [Gruppen](../create-groups/compare-groups.md).

7. Damit Benutzer ihre Office Skripts in Power Automate-Flows ausführen können, wählen Sie **Zulassen, dass Benutzer mit Zugriff auf Office Skripts ihre Skripts mit Power Automate ausführen.** Auf diese Weise können Benutzer Flow-Schritte mit der **Skriptoption** [Excel Online (Business) Connector hinzufügen.](/connectors/excelonlinebusiness)

    - Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts in Flows verwenden können, lassen Sie **Alle** (standard) ausgewählt.

    - Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office Skripts die Verwendung ihrer Skripts in Flows zu ermöglichen, wählen Sie **Spezifische Gruppe** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen. Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und es muss einer der folgenden Typen sein:
        - Microsoft 365 Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe

        Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter Vergleichen von [Gruppen](../create-groups/compare-groups.md).

    - Weitere Informationen zur Verwendung von Office Skripts mit Power Automate finden Sie unter [Ausführen Office Skripts mit Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Wählen Sie **Speichern** aus.

    Es kann bis zu 48 Stunden dauern, bis Änderungen an Office Scripts-Einstellungen wirksam werden.

## <a name="next-steps"></a>Nächste Schritte

Da Office Skripts mit Power Automate funktioniert, wird empfohlen, dass Sie Ihre vorhandenen DLP-Richtlinien (Data Loss Prevention) überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer Office Skripts verwenden. Weitere Informationen finden Sie unter [DLP-Richtlinien (Data Loss Prevention)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Verwandte Inhalte

[Office technische Dokumentation von Scripts](/office/dev/scripts/) (Linkseite)
[Einführung in Office Skripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel)
[Freigeben Office Skripts in Excel für das Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel)
[Aufzeichnen, Bearbeiten und Erstellen Office Skripts in Excel im Web](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)
