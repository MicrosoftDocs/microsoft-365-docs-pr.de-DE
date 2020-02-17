---
title: Erstellen eines benutzerdefinierten vertraulichen Informationstyps im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie benutzerdefinierten Typen für vertrauliche Informationen für DLP in der grafischen Benutzeroberfläche im Security & Compliance Center erstellen, ändern, entfernen und testen können.
ms.openlocfilehash: 726f21416a3e83a9c3024d810c4335ea263b3c20
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078041"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a>Erstellen eines benutzerdefinierten vertraulichen Informationstyps im Security & Compliance Center

## <a name="summary"></a>Zusammenfassung

Lesen Sie diesen Artikel, zum[Erstellen eines benutzerdefinierten vertraulichen Informationstyps](custom-sensitive-info-types.md) im Security & Compliance Center ([https://protection.office.com](https://protection.office.com)). Die benutzerdefinierte Typen vertraulicher Informationen, die Sie mit dieser Methode erstellen, werden zum Regelpaket namens `Microsoft.SCCManaged.CustomRulePack`hinzugefügt.

Sie können auch benutzerdefinierte vertrauliche Informationstypen mithilfe von PowerShell und genauer Datenübereinstimmung erstellen. Weitere Informationen zu diesen Methoden finden Sie unter:
- [Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps für DLP mit genauer Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a>Bevor Sie beginnen...

> [!NOTE]
> Sie sollten über globale Administrator-oder Compliance-Administratorberechtigungen verfügen, um über die Benutzeroberfläche einen benutzerdefinierten vertraulichen Informationstyp erstellen, testen und bereitstellen zu können. Informationen hierzu finden Sie unter[Zu Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.

- Ihre Organisation muss über ein Abonnement verfügen, z. B. Office 365 Enterprise, das Verhinderung von Datenverlust (DLP) beinhaltet. Siehe [Nachrichtenrichtlinie und Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc). 

- Benutzerdefinierte Typen für vertrauliche Informationen erfordern Kenntnisse über reguläre Ausdrücke (RegEx). Weitere Informationen über das Modul Boost.RegEx (vormals als RegEx++ bezeichnet), das für die Textverarbeitung verwendet wird, finden Sie unter [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).

  Der Kundendienst und Support von Microsoft kann beim Erstellen benutzerdefinierter Klassifizierungen oder Muster für reguläre Ausdrücke keine Unterstützung anbieten. Die Supportmitarbeiter können eingeschränkten Support für das Feature bereitstellen, beispielsweise Muster für reguläre Ausdrücke zu Testzwecken oder Hilfestellung bei der Problembehandlung eines bestehenden Musters für reguläre Ausdrücke, das nicht wie erwartet ausgelöst wird, es können jedoch keine Zusicherungen dahingehend gegeben werden, dass benutzerdefinierte Entwicklungen für die Inhaltsübereinstimmung Ihre Anforderungen oder Verpflichtungen erfüllen.

- DLP verwendet den Suchcrawler zum Erkennen und Klassifizieren vertraulicher Informationen in SharePoint Online- und OneDrive for Business-Websites. Um den neuen benutzerdefinierten vertraulichen Informationstyp in vorhandenen Inhalten zu identifizieren, müssen die Inhalte erneut durchforstet werden. Inhalte werden basierend auf einem Zeitplan durchforstet, aber Sie können Inhalte für eine Websitesammlung, Liste oder Bibliothek manuell erneut durchforsten. Weitere Informationen finden Sie unter [Manuelles Anfordern des Durchforstens und des erneuten Indizierens einer Website, Bibliothek oder Liste](https://docs.microsoft.com/sharepoint/crawl-site-content).

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a>Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center

Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und klicken Sie auf **Erstellen**.

Die Einstellungen sind selbsterklärend und werden auf der entsprechenden Seite des Assistenten erläutert:

- **Name**

- **Beschreibung**

- **Näherung**

- **Zuverlässigkeitsstufe**

- **Primäres Muster-Element** (Schlüsselwörter, reguläre Ausdrücke oder Wörterbuch)

- Optionale Elemente für **unterstützende Muster** (Schlüsselwörter, reguläre Ausdrücke oder Wörterbuch) und einen entsprechenden Wert für **Mindestkosten**.

Sehen Sie sich das folgende Szenario an: Sie möchten einen benutzerdefinierten Typ für vertrauliche Informationen, der neunstellige Mitarbeiternummern in Inhalten erkennt, zusammen mit den Schlüsselwörtern „Mitarbeiter“, „ID“ und „Ausweis“. Um diesen benutzerdefinierten Typ für vertrauliche Information zu erstellen, führen Sie die folgenden Schritte aus:

1. Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und klicken Sie auf **Erstellen**.

    ![Speicherort der Typen für vertrauliche Informationen und Schaltfläche „Erstellen“](../media/scc-cust-sens-info-type-new.png)

2. Geben Sie auf der Seite **Namen und Beschreibung auswählen**, die geöffnet wird, die folgenden Werte ein:

  - **Name**: Mitarbeiter-ID.

  - **Beschreibung**: Neunstellige Contoso-Mitarbeiter-ID-Nummern erkennen.

    ![Seite „Name und Beschreibung“](../media/scc-cust-sens-info-type-new-name-desc.png)

    Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

3. Klicken Sie auf der Seite **Anforderungen für Übereinstimmung** auf **Element hinzufügen**, um die folgenden Einstellungen zu konfigurieren:

    - **Inhalt erkennen, der Folgendes enthält**:
 
      a. Klicken Sie auf die Option, dass **eines der folgenden Elemente enthalten sein muss**, und wählen Sie **Regulärer Ausdruck** aus.

      b. Geben Sie in dem Feld für den regulären Ausdruck `(\s)(\d{9})(\s)` ein (neunstellige Zahlen umgeben von einem Leerzeichen).
  
    - **Unterstützende Elemente**: Klicken Sie auf **Unterstützende Elemente hinzufügen**, und wählen Sie **Enthält die folgende Schlüsselwortliste** aus.

    - Konfigurieren Sie in dem Bereich **Enthält die folgende Schlüsselwortliste**, der angezeigt wird, die folgenden Einstellungen:

      - **Schlüsselwortliste**: Geben Sie den folgenden Wert ein: Mitarbeiter,ID,Ausweis.

      - **Mindestanzahl**: Behalten Sie den Standardwert 1 bei.

    - Behalten Sie den Standardwert 60 für den **Zuverlässigkeitsgrad** bei. 

    - Behalten Sie den Standardwert 300 für den **Zeichenabstand** bei.

    ![Seite „Anforderungen für Übereinstimmung“](../media/scc-cust-sens-info-type-new-reqs.png)

    Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Überprüfen Sie auf der Seite **Überprüfen und Abschließen** die Einstellungen, und klicken Sie auf **Fertig stellen**.

    ![Seite „Überprüfen und Abschließen“](../media/scc-cust-sens-info-type-new-review.png)

5. Auf der nächsten Seite werden Sie aufgefordert, den neuen benutzerdefinierten Typ für vertrauliche Informationen zu testen. Klicken Sie dazu auf **Ja**. Weitere Informationen finden Sie unter [Testen von benutzerdefinierten Typen für vertrauliche Information im Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). Um die Regel später zu testen, klicken Sie auf **Nein**.

    ![Testempfehlungsseite](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Um sicherzustellen, dass Sie einen neuen Typ für vertrauliche Informationen erstellt haben, führen Sie einen der folgenden Schritte aus:

  - Wechseln Sie zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und bestätigen Sie, dass der neue benutzerdefinierte Typ für vertrauliche Informationen aufgeführt ist.

  - Testen Sie den neuen benutzerdefinierten Typ für vertrauliche Informationen. Weitere Informationen finden Sie unter [Testen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a>Ändern von benutzerdefinierten Typen für vertrauliche Information im Security & Compliance Center

**Hinweise**:
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- Sie können nur benutzerdefinierte Typen für vertrauliche Informationen ändern; integrierte Typen vertraulicher Informationen können nicht geändert werden. Sie können aber PowerShell verwenden, um integrierte Typen vertraulicher Informationen zu exportieren, diese anzupassen und sie als benutzerdefinierte Typen vertraulicher Informationen zu importieren. Weitere Informationen finden Sie unter [Anpassen eines integrierten benutzerdefinierten Typs für vertrauliche Informationen](customize-a-built-in-sensitive-information-type.md).

- Sie können nur benutzerdefinierte Typen für vertrauliche Informationen ändern, die Sie in der Benutzeroberfläche erstellt haben. Wenn Sie das [PowerShell-Verfahren](create-a-custom-sensitive-information-type-in-scc-powershell.md) zum Importieren eines Regelpakets für benutzerdefinierte Typen für vertrauliche Informationen verwendet haben, erhalten Sie eine Fehlermeldung.

Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und wählen Sie den benutzerdefinierten Typ vertraulicher Informationen aus, den Sie ändern möchten. Klicken Sie anschließend auf **Bearbeiten**.

  ![Speicherort der Typen für vertrauliche Informationen und Schaltfläche „Bearbeiten“](../media/scc-cust-sens-info-type-edit.png)

Hier stehen die gleichen Optionen wie beim Erstellen des benutzerdefinierten Typs für vertrauliche Informationen im Security & Compliance Center zur Verfügung. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Um sicherzustellen, dass Sie einen neuen Typ für vertrauliche Informationen erfolgreich geändert haben, führen Sie einen der folgenden Schritte aus:

  - Wechseln Sie zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, um die Eigenschaften des geänderten benutzerdefinierten Typs vertraulicher Informationen zu überprüfen. 

  - Testen Sie den geänderten benutzerdefinierten Typ für vertrauliche Informationen. Weitere Informationen finden Sie unter [Testen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a>Entfernen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center 

**Hinweise**:

- Sie können nur benutzerdefinierte Typen für vertrauliche Informationen entfernen; Sie können keine integrierten Typen vertraulicher Informationen entfernen.

- Bevor Sie einen benutzerdefinierten Typ für vertrauliche Informationen entfernen, überprüfen Sie, dass keine DLP-Richtlinien oder Exchange-Nachrichtenflussregeln (auch bezeichnet als Transportregeln) mehr auf den Typ vertraulicher Informationen verweisen.

1. Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und wählen Sie einen oder mehrere benutzerdefinierte Typen vertraulicher Informationen aus, die Sie entfernen möchten.

2. Klicken Sie in dem Fenster, das geöffnet wird, auf **Löschen** (oder auf **Typen vertraulicher Informationen löschen**, wenn Sie mehrere ausgewählt haben).

    ![Speicherort der Typen für vertrauliche Informationen und Schaltfläche „Löschen“](../media/scc-cust-sens-info-type-delete.png)

3. Klicken Sie in der angezeigten Warnmeldung auf **Ja**.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Um sicherzustellen, dass Sie einen benutzerdefinierten Typ vertraulicher Informationen erfolgreich entfernt haben, wechseln Sie zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und bestätigen Sie, dass der benutzerdefinierte Typ vertraulicher Informationen nicht mehr aufgeführt ist.

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a>Testen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**.

2. Wählen Sie einen oder mehrere benutzerdefinierte Typen vertraulicher Informationen aus, die Sie testen möchten. Klicken Sie in dem Fenster, das geöffnet wird, auf **Typ testen** (oder auf **Typen vertraulicher Informationen testen**, wenn Sie mehrere ausgewählt haben).

    ![Speicherort der Typen für vertrauliche Informationen und Schaltfläche „Typ testen“](../media/scc-cust-sens-info-type-test.png)

3. Laden Sie auf der Seite **Zu testende Datei hochladen**, die geöffnet wird, per Drag & Drop ein zu testendes Dokument hoch, oder klicken Sie auf **Durchsuchen**, und wählen Sie eine Datei aus.

    ![Seite „Zu testende Datei hochladen“](../media/scc-cust-sens-info-type-test-upload.png)

4. Klicken Sie auf die Schaltfläche **Testen**, um das Dokument auf Musterübereinstimmungen in der Datei zu testen.

5. Klicken Sie auf der Seite **Übereinstimmungsergebnisse** auf **Fertig stellen**.

    ![Übereinstimmungsergebnisse](../media/scc-cust-sens-info-type-test-results.png)
