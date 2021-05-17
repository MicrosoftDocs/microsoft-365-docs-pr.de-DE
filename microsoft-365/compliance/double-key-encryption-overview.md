---
title: Übersicht und Häufig gestellte Fragen zur Verschlüsselung von Doppelschlüsseln
description: Häufig gestellte Fragen zur Double Key Encryption for Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922049"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Häufig gestellte Fragen zur Doppelschlüsselverschlüsselung

Haben Sie eine Frage zur Funktionsweise der Double Key Encryption? Suchen Sie hier nach einer Antwort.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Was ist double key encryption for Microsoft 365 (DKE)?

Double Key Encryption for Microsoft 365 ermöglicht Es Kunden, ihre hochsensiblen Daten zu schützen, um spezielle Anforderungen zu erfüllen. Es hilft Kunden, die volle Kontrolle über ihre Verschlüsselungsschlüssel zu behalten. Es verwendet zwei Schlüssel zum Schützen von Daten. einen Schlüssel in Ihrem Steuerelement und einen zweiten Schlüssel, der sicher in einem Microsoft Azure. Das Anzeigen von Daten, die mit der Doppelschlüsselverschlüsselung geschützt sind, erfordert Zugriff auf beide Schlüssel. Da Microsoft nur auf einen dieser Schlüssel zugreifen kann, ist der Zugriff auf geschützte Daten für Microsoft weiterhin nicht möglich, um sicherzustellen, dass Sie die vollständige Kontrolle über Den Datenschutz und die Sicherheit Ihrer Daten haben.  

Sie können den Doppeltschlüsselverschlüsselungsdienst hosten, der zum Anfordern Ihres Schlüssels verwendet wird, an einem Speicherort Ihrer Wahl (lokalen Schlüsselverwaltungsserver oder in der Cloud). Sie verwalten den Dienst wie jede andere Anwendung. Mit der Doppelschlüsselverschlüsselung können Sie den Zugriff auf den Double Key Encryption-Dienst steuern. Sie können Ihre hochsensiblen Daten lokal speichern oder in die Cloud verschieben. Sie können sicher sein, den Zugriff durch Drittanbieter zu verhindern, da Sie die volle Kontrolle über Ihren Schlüssel behalten. Mit der Doppelschlüsselverschlüsselung können Sie Ihre Daten und Schlüssel am gleichen Speicherort speichern.

DKE hilft Ihnen bei der Erfüllung gesetzlicher Anforderungen in verschiedenen Vorschriften und Standards, wie z. B. der Datenschutz-Grundverordnung (DSGVO), dem Health Insurance Portability and Accountability Act (HIPAA), dem Gramm-Leach-Bliley Act (GLBA), dem russischen Datenlokalisierungsgesetz – Bundesgesetz Nr. 242-FZ, Australia es Federal Privacy Act 1988 und New Zealand es Privacy Act 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Kann ich die Double Key Encryption mit Microsoft Office integrierten Vertraulichkeitsbezeichnung verwenden?

Sie müssen den Azure Information Protection Unified Labeling-Client verwenden, um Dokumente mit Double Key Encryption zu schützen. Derzeit können Sie keine integrierte Microsoft Office Vertraulichkeitsbezeichnung verwenden.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>Welche Microsoft 365 Apps kann ich mit DKE verwenden?

Sie können DKE-Bezeichnungen verwenden, um Dokumente mithilfe der Desktopversionen von Word, Excel und PowerPoint auf Windows. Stellen Sie sicher, dass Sie *.12711 oder höher (Desktopversionen von Word, PowerPoint und Excel) auf Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>Inwiefern ist die Doppelschlüsselverschlüsselung von der vorhandenen Lösung für den eigenen Schlüssel (HYOK) unterschiedlich?

Die Doppelschlüsselverschlüsselung verschlüsselt Ihre Daten mit zwei Schlüsseln. Ihr Verschlüsselungsschlüssel befindet sich in Ihrem Steuerelement, und der zweite Schlüssel wird in Microsoft Azure gespeichert, sodass Sie Ihre verschlüsselten Daten in die Cloud verschieben können. HYOK schützt Ihre Inhalte mit nur einem Schlüssel, und der Schlüssel ist immer lokal.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>Können verschlüsselte Dokumente mit doppeltem Schlüssel extern freigegeben werden?

Sie können verschlüsselte Dokumente mit Doppelschlüsseln für Benutzer in einem separaten Mandanten freigeben, solange diese Benutzer:

- Verfügen Sie über die erforderliche Berechtigung für den Zugriff auf Ihren Schlüssel in Ihrem Double Key Encryption-Dienst.

- Verfügen Sie über die erforderliche Berechtigung für den Zugriff auf Ihren Schlüssel in Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>Was geschieht mit Dokumenten, die mit HYOK geschützt sind?

Die Bereitstellung der Doppelschlüsselverschlüsselung hat keine Auswirkungen auf Ihr vorhandenes HYOK-Setup. Es wird jedoch empfohlen, parallel zu HYOK mit der Verwendung der Doppelschlüsselverschlüsselung zu beginnen.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Kann ich die Double Key Encryption in meiner Nicht-Microsoft-Umgebung ausführen?

DKE unterstützt diese Umgebungen nicht, da der Dienst Zugriff auf Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Wo kann ich verschlüsselte Dokumente mit Doppelschlüssel speichern?

Sie können verschlüsselte Dokumente mit Doppelschlüssel lokal oder in der Cloud speichern. In der Cloud können Sie verschlüsselte Inhalte in SharePoint Online und OneDrive for Business. Da Microsoft keinen Zugriff auf Ihren privaten Schlüssel hat, bleiben die verschlüsselten Daten für Microsoft undurchsichtig. Dies bedeutet auch, dass Sie die verschlüsselten Dokumente nicht online in Office Web Apps anzeigen können.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>In welchen Regionen und Sprachen ist die Doppelschlüsselverschlüsselung verfügbar? Ist die Doppelschlüsselverschlüsselung weltweit verfügbar?

DKE-Bezeichnungen werden in die gleichen Sprachen lokalisiert wie andere Vertraulichkeitsbezeichnungen in Microsoft Information Protection. Double Key Encryption ist weltweit verfügbar.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>Kann ich eine Nicht-DKE-Bezeichnung in eine DKE-Bezeichnung konvertieren?

Nein. DkE kann nach dem Erstellen nicht mehr zu einer Bezeichnung hinzugefügt werden. Stattdessen müssen Sie beim Erstellen der Bezeichnung die Option Double **Key Encryption** verwenden und die URL Ihres Double Key Encryption-Diensts angeben.

## <a name="how-do-i-roll-my-dke-keys"></a>Wie rolle ich meine DKE-Schlüssel?

Anweisungen zum Rollieren (auch als Drehen oder Neuschlüsseln bezeichnet) des schlüssels, den Sie in Azure speichern, finden Sie unter Vorgänge für Ihren [Azure Information Protection-Mandantenschlüssel](/azure/information-protection/operations-customer-managed-tenant-key).

Informationen [zum Erstellen eines](double-key-encryption.md#tenant-and-key-settings) neuen Schlüssels für den DKE-Dienst finden Sie unter Mandanten- und Schlüsseleinstellungen.

Wenn Sie einen Schlüssel erstellen, richten Sie einen Namen und eine GUID ein. Wenn Sie dann einen Schlüssel drehen, behalten Sie den alten Datensatz mit dem Namen und der GUID bei, fügen jedoch einen neuen Datensatz mit demselben Namen, aber einer anderen GUID hinzu. Der neue Schlüssel wird als aktiv festgelegt, sodass die API für den öffentlichen Schlüssel mit der Rückgabe für neue Verschlüsselung beginnt. Beide Schlüssel stehen für die Entschlüsselung zur Verfügung, sodass neue und alte Inhalte entschlüsselt werden können.