---
title: Erstellen und Verwenden einer Vorlage, um Benutzer hinzuzufügen
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Sie können eine Vorlage erstellen und verwenden, um Zeit zu sparen und Einstellungen zu standardisieren, wenn Sie mehrere Benutzer hinzufügen.
ms.openlocfilehash: cbe61c87bec40196ffd7a8e9868ea4611e4c259e
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431809"
---
# <a name="create-and-use-a-template-to-add-users"></a>Erstellen und Verwenden einer Vorlage, um Benutzer hinzuzufügen

Sie können eine Vorlage erstellen und verwenden, um Zeit zu sparen und Einstellungen zu standardisieren, wenn Sie mehrere Benutzer hinzufügen. Vorlagen sind besonders nützlich, wenn Sie über Benutzer verfügen, die viele allgemeine Eigenschaften aufweisen, beispielsweise diejenigen, die dieselbe Rolle haben und am gleichen Speicherort arbeiten und die dieselbe Software benötigen. Möglicherweise verfügen Sie über ein Team von Supportingenieuren, die im gleichen Büro arbeiten.  

## <a name="create-a-template"></a>Erstellen einer Vorlage

Vorlagen sind einfach zu erstellen &mdash; Sie können Benutzervorlagen für **Benutzer**  >  **aktive**Benutzer auswählen  >  **User templates**und dann in der Dropdownliste **eine Vorlage hinzufügen** auswählen, oder Sie können einen neuen Benutzer hinzufügen, und wenn Sie fertig sind, haben Sie die Möglichkeit, den Eintrag als Vorlage zu speichern.

Wenn Sie nach dem Hinzufügen eines Benutzers eine Vorlage erstellen, werden die Werte, die Sie für die folgenden Einstellungen auswählen, in der Vorlage gespeichert:

- Domänenname
- Auswahl der Kennworteinstellungen: Sie können auswählen, ob Kennwörter erstellt oder automatisch generiert werden sollen.
- Auswahl eines einmaligen Kennworts: Sie können festlegen, dass der Benutzer nach dem ersten Anmelden ein neues Kennwort erstellt.
- Lizenz Speicherort
- Lizenzauswahl
- Anwendungsoptionen
- Rolle
- Die meisten Profilinformationen wie **Auftragsprofil**, **Abteilung**, **Office**, **Office Phone**und **Street Address** 

Die folgenden Informationen sind benutzerspezifisch und werden in der Vorlage nicht gespeichert:

- Vor- und Nachname
- Distinguished Name (DN)
- Benutzername
- Auswahl, um das Kennwort in einer e-Mail zu senden und an wen die Kennwort-e-Mail gesendet wird
- Mobiltelefonnummer

Wenn Sie keine Informationen für eine Einstellung in einem Abschnitt eingeben, ist dieser Wert leer, und diese Einstellung wird in der Vorlage nicht angezeigt. Wenn Sie beispielsweise die **Position des Auftrags** leer lassen, wird bei der Überprüfung ihrer Vorlage und bei der Verwendung Ihrer Vorlage keine **Auftragsbezeichnung** angezeigt. Wenn Sie alle **Profil** Abschnittseinstellungen leer lassen, wird im Abschnitt **Profil** keine in der endgültigen Vorlage **bereitgestellte** angezeigt.

Wenn Sie eine Vorlage erstellen, indem Sie die Option **Vorlage hinzufügen** auswählen, können Sie auswählen, welche Werte abgeschlossen werden sollen. Alle Elemente, die leer gelassen werden, werden in der Vorlage als **keine angegeben** angezeigt.

## <a name="use-a-template-to-add-a-user"></a>Verwenden einer Vorlage zum Hinzufügen eines Benutzers

So verwenden Sie eine vorhandene Vorlage zum Hinzufügen eines Benutzers:

1. Wählen Sie im Admin Center die Option **Users**  >  **Active Users**aus.

2. Wählen Sie **Benutzervorlagen**aus, und wählen Sie dann in der Dropdownliste eine Vorlage aus. (Die Liste enthält nur die Vorlagen, die Sie erstellt haben, nicht jene, die von anderen Administratoren erstellt wurden.)

 > [!NOTE]
 > Sie können auch eine Vorlage verwenden, um einen Benutzer hinzuzufügen, indem Sie **Benutzervorlagen**Vorlagen  >  **Verwalten**auswählen, eine Vorlage auswählen und dann **Vorlage verwenden**auswählen.

3. Führen Sie die Schritte aus, um einen Benutzer aus der ausgewählten Vorlage zu erstellen.

> [!NOTE]
> Wenn Sie nicht über ausreichende Lizenzen für einen Benutzer verfügen, den Sie hinzufügen, und Ihre Zahlungsinformationen verfügbar sind, werden wir versuchen, eine andere Lizenz mit Ihren vorhandenen Zahlungsinformationen zu erwerben. Wenn Ihre Zahlungsinformationen nicht verfügbar sind, wird der Benutzer als nicht lizenzierter Benutzer erstellt.

## <a name="manage-templates"></a>Vorlagen verwalten

Vorlagen, die Sie nicht mehr benötigen, können Sie ganz einfach löschen und neue hinzufügen. So löschen Sie eine Vorlage:

1. Wählen Sie im Admin Center die Option **Users**  >  **Active Users**aus.

2. Wählen Sie **Vorlagen**aus, und wählen Sie dann **Vorlagen verwalten** in der Dropdownliste aus.

3. Eine Liste mit Vorlagen wird angezeigt. Sie können eine Vorlage löschen, indem Sie eine der folgenden Aktionen ausführen:
    - Wählen Sie eine oder mehrere Vorlagen aus, und wählen Sie dann **Löschen**aus. 
    - Wählen Sie die drei Punkte rechts neben dem Vorlagennamen aus, und wählen Sie dann **Löschen**aus.
    - Wählen Sie den Vorlagennamen aus. Wenn die Vorlagen Details auf der rechten Seite des Bildschirms angezeigt werden, wählen Sie **Vorlage löschen**aus.

## <a name="related-articles"></a>Verwandte Artikel

[Hinzufügen von Benutzern einzeln oder in Massen zu Microsoft 365](add-users.md)

[Entfernen eines ehemaligen Mitarbeiters aus Microsoft 365](remove-former-employee.md)
  
