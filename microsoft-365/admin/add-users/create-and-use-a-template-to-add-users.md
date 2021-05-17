---
title: Erstellen und Verwenden einer Vorlage, um Benutzer hinzuzufügen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
ms.openlocfilehash: 3ce70f6d37036a2f71bdc2d41bfb5677a54b8db9
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579386"
---
# <a name="create-and-use-a-template-to-add-users"></a>Erstellen und Verwenden einer Vorlage, um Benutzer hinzuzufügen

Sie können eine Vorlage erstellen und verwenden, um Zeit zu sparen und Einstellungen zu standardisieren, wenn Sie mehrere Benutzer hinzufügen. Vorlagen sind besonders nützlich, wenn Sie Benutzer haben, die viele allgemeine Eigenschaften gemeinsam verwenden, z. B. Benutzer, die dieselbe Rolle haben und am gleichen Standort arbeiten, und wenn sie dieselbe Software benötigen. Sie haben beispielsweise ein Team von Supporttechnikern, die im gleichen Büro arbeiten.  

## <a name="create-a-template"></a>Erstellen einer Vorlage

Vorlagen sind einfach zu erstellen Sie können Benutzer Aktive Benutzer Benutzervorlagen auswählen und dann in der Dropdownliste Eine Vorlage hinzufügen auswählen, oder Sie können einen neuen Benutzer hinzufügen, und wenn Sie fertig sind, haben Sie die Möglichkeit, den Eintrag als Vorlage zu &mdash;   >    >  speichern. 

Wenn Sie nach dem Hinzufügen eines Benutzers eine Vorlage erstellen, werden die Werte, die Sie für die folgenden Einstellungen auswählen, in der Vorlage gespeichert:

- Domänenname
- Auswahl der Kennworteinstellungen: Sie können Kennwörter erstellen oder automatisch generieren lassen
- Einmalkennwortauswahl: Sie können festlegen, dass der Benutzer nach der ersten Anmeldung ein neues Kennwort erstellt.
- Lizenzspeicherort
- Lizenzauswahl
- Anwendungsauswahl
- Rolle
- Die meisten Profilinformationen, **z. B. Auftragsprofil,** **Abteilung,** **Office**, **Office Und** **Adresse** 

Die folgenden Informationen sind benutzerspezifisch und werden nicht in der Vorlage gespeichert:

- Vor- und Nachname
- Anzeigename
- Benutzername
- Auswahl zum Senden des Kennworts in E-Mail und an wen die Kennwort-E-Mail gesendet wird
- Mobiltelefonnummer

Wenn Sie keine Informationen für eine Einstellung in einem Abschnitt eingeben möchten, ist dieser Wert leer, und diese Einstellung wird nicht in der Vorlage angezeigt. Wenn Sie beispielsweise den Auftragstitel leer **lassen,** wenn Sie Ihre Vorlage überprüfen und wenn Sie Ihre Vorlage verwenden, wird der **Auftragstitel** überhaupt nicht angezeigt. Wenn Sie alle **Profilabschnittseinstellungen** leer lassen, zeigt der **Abschnitt Profil** keine in **der** endgültigen Vorlage bereitgestellten None an.

Wenn Sie eine Vorlage erstellen, indem Sie **die** Option Vorlage hinzufügen auswählen, können Sie auswählen, welche Werte abgeschlossen werden sollen. Alles, was leer bleibt, wird in der Vorlage **als Keine** angezeigt.

## <a name="use-a-template-to-add-a-user"></a>Verwenden einer Vorlage zum Hinzufügen eines Benutzers

So verwenden Sie eine vorhandene Vorlage zum Hinzufügen eines Benutzers:

1. Wählen Sie im Admin Center Die Option **Benutzer**  >  **Aktive Benutzer aus.**

2. Wählen **Sie Benutzervorlagen** aus, und wählen Sie dann eine Vorlage aus der Dropdownliste aus. (Die Liste enthält nur die vorlagen, die Sie erstellt haben, nicht die vorlagen, die von anderen Administratoren erstellt wurden.)

   > [!NOTE]
   > Sie können auch eine Vorlage verwenden, um einen Benutzer hinzuzufügen, indem Sie Benutzervorlagen Vorlagen verwalten, eine Vorlage auswählen und  >  dann Vorlage **verwenden auswählen.**

3. Führen Sie die Schritte aus, um einen Benutzer aus der ausgewählten Vorlage zu erstellen.

   > [!NOTE]
   > Wenn für einen benutzer, den Sie hinzufügen, nicht genügend Lizenzen verfügbar sind und Ihre Zahlungsinformationen verfügbar sind, versuchen wir, eine weitere Lizenz mit Ihren vorhandenen Zahlungsinformationen zu erwerben. Wenn Ihre Zahlungsinformationen nicht verfügbar sind, wird der Benutzer als nicht lizenzierter Benutzer erstellt.

## <a name="manage-templates"></a>Verwalten von Vorlagen

Sie können nur nicht mehr benötigte Vorlagen löschen und neue hinzufügen. So löschen Sie eine Vorlage:

1. Wählen Sie im Admin Center Die Option **Benutzer**  >  **Aktive Benutzer aus.**

2. Wählen **Sie Vorlagen** aus, und wählen Sie dann Vorlagen **verwalten** in der Dropdownliste aus.

3. Eine Liste der Vorlagen wird angezeigt. Sie können eine Vorlage löschen, indem Sie eine der folgenden Schritte tun:
    - Wählen Sie eine oder mehrere Vorlagen aus, und wählen Sie dann **Löschen aus.** 
    - Wählen Sie die drei Punkte rechts neben dem Vorlagennamen aus, und wählen Sie dann **Löschen aus.**
    - Wählen Sie den Vorlagennamen aus. Wenn die Vorlagendetails auf der rechten Seite des Bildschirms angezeigt werden, wählen Sie **Vorlage löschen aus.**

## <a name="related-articles"></a>Verwandte Artikel

[Gleichzeitiges Hinzufügen von Benutzern und Zuweisen von Lizenzen](add-users.md)

[Entfernen eines ehemaligen Mitarbeiters aus Microsoft 365](remove-former-employee.md)
  
