---
title: Verwalten von Office-Skripteinstellungen
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
description: Hier erfahren Sie, wie Sie Office-Skripteinstellungen für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300833"
---
# <a name="manage-office-scripts-settings"></a>Verwalten von Office-Skripteinstellungen

Office-Skripts ermöglichen Benutzern das Automatisieren von Aufgaben durch aufzeichnen, bearbeiten und Ausführen von Skripts in Excel im Internet. Office-Skripts arbeiten mit Power Automation, und Benutzer führen Skripts für Arbeitsmappen mithilfe des Excel Online (Business)-Connectors aus. Microsoft 365-Administratoren können Office-Skripteinstellungen im Microsoft 365 Admin Center verwalten.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Zum Verwalten von Office-Skripteinstellungen müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).

- Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen Microsoft 365-oder Office 365-Geschäfts-oder-edu-Plan verfügen, der Zugriff auf Office-Desktop-Apps umfasst, beispielsweiseeines der folgenden Pläne:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for Business
    - Microsoft 365 Apps for Enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Verwalten der Verfügbarkeit von Office-Skripts und der Freigabe von Skripts

1. Wechseln Sie im Microsoft 365 Admin Center zur Registerkarte **Settings** \> **org Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .

2. Wählen Sie **Office-Skripts**aus.

3. Office-Skripts sind standardmäßig aktiviert, und jeder in Ihrer Organisation kann auf das Feature und die Freigabe von Skripts zugreifen und diese verwenden. Wenn Sie Office-Skripts für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen zulassen, dass **Benutzer ihre Aufgaben in Excel im Internet automatisieren** .

4. Wenn Sie zuvor Office-Skripts für Ihre Organisation deaktiviert haben und Sie wieder aktivieren möchten, wählen Sie **Benutzer können Ihre Aufgaben in Excel im Internet automatisieren**aus, und geben Sie dann an, wer auf das Feature zugreifen und dieses verwenden kann:

    - Wenn Sie allen Benutzern in Ihrer Organisation den Zugriff auf und die Verwendung von Office-Skripts gestatten möchten, lassen Sie **alle** (Standard) ausgewählt. 

    - Wenn Sie nur Mitgliedern einer bestimmten Gruppe den Zugriff auf und die Verwendung von Office-Skripts gestatten möchten, wählen Sie **bestimmte Gruppe**aus, und geben Sie dann den Namen oder e-Mail-Alias der Gruppe ein, um ihn der Zulassungsliste hinzuzufügen. Sie können nur eine Gruppe zur Zulassungsliste hinzufügen, und es muss sich um einen der folgenden Typen handeln:
        - Microsoft 365-Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Typen von Gruppen finden Sie unter [Compare Groups](../create-groups/compare-groups.md).

5. Um Benutzern mit Zugriff auf Office-Skripts das Freigeben Ihrer Skripts für andere Personen in Ihrer Organisation zu ermöglichen, wählen Sie **Benutzer mit Zugriff auf Office-Skripts zulassen, dass Ihre Skripts für andere Personen in der Organisation freigegeben**werden. Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.
 
    > [!NOTE]
    > Wenn Sie später die Skript Freigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.
 
6. Geben Sie an, welche Benutzer mit Zugriff auf Office-Skripts Ihre Skripts freigeben können:
    
    - Damit alle Benutzer, die Zugriff auf Office-Skripts haben, Ihre Skripts freigeben können, lassen Sie **alle** (Standard) ausgewählt.

    - Wenn Sie nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office-Skripts das Freigeben Ihrer Skripts gestatten möchten, wählen Sie **bestimmte Gruppe**aus, und geben Sie dann den Namen oder e-Mail-Alias der Gruppe ein, um Sie der Zulassungsliste hinzuzufügen. Sie können nur eine Gruppe zur Zulassungsliste hinzufügen, und es muss sich um einen der folgenden Typen handeln:
        - Microsoft 365-Gruppe
        - Verteilergruppe
        - Sicherheitsgruppe
        - E-Mail-aktivierte Sicherheitsgruppe
    
        Weitere Informationen zu den verschiedenen Typen von Gruppen finden Sie unter [Compare Groups](../create-groups/compare-groups.md).

7. Klicken Sie auf **Speichern**.

    Es kann bis zu 48 Stunden dauern, bis Änderungen an Office-Skripteinstellungen wirksam werden.

## <a name="next-steps"></a>Nächste Schritte

Da Office-Skripts mit Power Automation verwendet werden, sollten Sie die vorhandenen DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer Office-Skripts verwenden. Weitere Informationen finden Sie unter [Richtlinien zur Verhinderung von Datenverlust (DLP)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Verwandte Inhalte

[Technische Dokumentation zu Office-Skripts](/office/dev/scripts/) (Linkseite) \
[Einführung in Office-Skripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel) \
[Freigeben von Office-Skripts in Excel für das Internet](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel) \
[Aufzeichnen, bearbeiten und Erstellen von Office-Skripts in Excel im Internet](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)