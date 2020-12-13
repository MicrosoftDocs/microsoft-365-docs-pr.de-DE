---
title: Übersicht über die Doppelschlüssel Verschlüsselung und häufig gestellte Fragen
description: Häufig gestellte Fragen zur Doppelschlüssel Verschlüsselung für Microsoft 365.
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
ms.openlocfilehash: 32686e76018d8b6a361ea99e6b00271b9547ed95
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663060"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Häufig gestellte Fragen zur doppelten Schlüssel Verschlüsselung

Haben Sie eine Frage zur Funktionsweise der Doppelschlüssel Verschlüsselung? Hier finden Sie eine Antwort.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Was ist die Doppelschlüssel Verschlüsselung für Microsoft 365 (DKE)?

Durch die Doppelschlüssel Verschlüsselung für Microsoft 365 können Kunden ihre hochsensiblen Daten schützen, um spezielle Anforderungen zu erfüllen. Es hilft Kunden, die vollständige Kontrolle über Ihre Verschlüsselungsschlüssel beizubehalten. Es verwendet zwei Schlüssel zum Schutz von Daten; ein Schlüssel in Ihrem Steuerelement und ein zweiter Schlüssel, der sicher in Microsoft Azure gespeichert ist. Für das Anzeigen von Daten, die mit Doppelschlüssel Verschlüsselung geschützt sind, ist der Zugriff auf beide Schlüssel erforderlich. Da Microsoft nur auf einen dieser Schlüssel zugreifen kann, bleiben geschützte Daten für Microsoft unzugänglich, um sicherzustellen, dass Sie den Datenschutz und die Sicherheit vollständig steuern können.  

Sie können den doppelten Schlüssel-Verschlüsselungsdienst hosten, der verwendet wird, um Ihren Schlüssel anzufordern, an einem Ort Ihrer Wahl (lokaler Schlüsselverwaltungsserver oder in der Cloud). Sie pflegen den Dienst wie jede andere Anwendung. Durch die Doppelschlüssel Verschlüsselung können Sie den Zugriff auf den doppelten Schlüssel Verschlüsselungsdienst steuern. Sie können Ihre vertraulichen Daten lokal speichern oder in die Cloud verlagern. Sie können sicher sein, den Zugriff durch Drittanbieter zu verhindern, da Sie die vollständige Kontrolle über Ihren Schlüssel erhalten. Die Verschlüsselung mit doppeltem Schlüssel ermöglicht Ihnen das Speichern Ihrer Daten und des Schlüssels am gleichen Speicherort.

DKE unterstützt Sie bei der Erfüllung behördlicher Anforderungen in verschiedenen Richtlinien und Standards wie der allgemeinen Datenschutzverordnung (dsgvo), der Krankenversicherungs-und Verantwortlichkeits-Act (HIPAA), dem Gramm-Leach-Bliley Act (GLBA), dem russischen Daten Lokalisierungs Gesetz – Bundesgesetz Nr. 242-FZ, Australiens Bundesdatenschutzgesetz (Privacy Act) 1988 und New Zealand es Privacy Act 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Kann ich die Doppelschlüssel Verschlüsselung mit Microsoft Office integrierten Empfindlichkeits Kennzeichnung verwenden?

Sie müssen den Azure Information Protection Unified Labeling-Client verwenden, um Dokumente mit doppelter Schlüssel Verschlüsselung zu schützen. Derzeit können Sie Microsoft Office integrierte Sensitivitäts Kennzeichnung nicht verwenden.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>Welche Microsoft 365-apps kann ich mit DKE verwenden?

Sie können DKE-Bezeichnungen verwenden, um Dokumente mithilfe der Desktop Versionen von Word, Excel und PowerPoint unter Windows zu schützen. Vergewissern Sie sich, dass Sie *. 12711 oder höher (Desktop Versionen von Word, PowerPoint und Excel) unter Windows verwenden.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>Inwiefern unterscheidet sich die doppelte Schlüssel Verschlüsselung von der vorhandenen halten Sie Ihre eigene Schlüssellösung (Hyok)?

Durch die Doppelschlüssel Verschlüsselung werden Ihre Daten mit zwei Schlüsseln verschlüsselt. Der Verschlüsselungsschlüssel befindet sich in Ihrem Steuerelement, und der zweite Schlüssel wird in Microsoft Azure gespeichert, sodass Sie Ihre verschlüsselten Daten in die Cloud verlagern können. Hyok schützt Ihre Inhalte nur mit einem Schlüssel, und der Schlüssel ist immer lokal.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>Können doppelt Schlüssel verschlüsselte Dokumente extern freigegeben werden?

Sie können Doppelschlüssel-verschlüsselte Dokumente für Benutzer in einem separaten Mandanten freigeben, solange diese Benutzer:

- Verfügen über die erforderliche Berechtigung für den Zugriff auf Ihren Schlüssel in ihrem doppelten Schlüssel Verschlüsselungsdienst.

- Verfügen über die erforderliche Berechtigung für den Zugriff auf Ihren Schlüssel in Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>Was geschieht mit Dokumenten, die mit Hyok geschützt sind?

Die Bereitstellung der doppelten Schlüssel Verschlüsselung wirkt sich nicht auf das vorhandene Hyok-Setup aus. Es wird jedoch empfohlen, die doppelte Schlüssel Verschlüsselung parallel mit Hyok zu verwenden.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Kann ich in meiner nicht-Microsoft-gapped-Umgebung eine Doppelschlüssel Verschlüsselung ausführen?

DKE unterstützt diese Umgebungen nicht, da der Dienst Zugriff auf Microsoft Azure benötigt.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Wo kann ich doppelt Schlüssel verschlüsselte Dokumente speichern?

Sie können Doppelschlüssel-verschlüsselte Dokumente lokal oder in der Cloud speichern. In der Cloud können Sie verschlüsselte Inhalte in SharePoint Online und OneDrive für Unternehmen verlagern. Da Microsoft keinen Zugriff auf Ihren privaten Schlüssel hat, bleiben die verschlüsselten Daten für Microsoft undurchsichtig. Dies bedeutet auch, dass Sie die verschlüsselten Dokumente nicht online in Office-Webanwendungen anzeigen können.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>In welchen Regionen und Sprachen ist die Doppelschlüssel Verschlüsselung verfügbar? Ist die doppelte Schlüssel Verschlüsselung weltweit verfügbar?

DKE-Bezeichnungen werden in die gleichen Sprachen wie andere Vertraulichkeits Bezeichnungen in Microsoft Information Protection lokalisiert. Die Doppelschlüssel Verschlüsselung ist weltweit verfügbar.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>Kann ich eine nicht-DKE Bezeichnung in eine DKE-Bezeichnung umwandeln?

Nein. Sie können DKE nicht zu einer Bezeichnung hinzufügen, nachdem Sie Sie erstellt haben. Sie müssen stattdessen die **Doppelschlüssel Verschlüsselung verwenden** und die URL des doppelten Schlüssels für die Verschlüsselung angeben, wenn Sie die Bezeichnung erstellen.

## <a name="how-do-i-roll-my-dke-keys"></a>Wie kann ich meine DKE-Schlüsselrollen?

Anweisungen zum Rollen (auch als rotierende oder neukeying bezeichnet) des Schlüssels, den Sie in Azure speichern, finden Sie unter [Vorgänge für Ihren Azure Information Protection-Mandanten Schlüssel](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key).

Informationen zum Erstellen eines neuen Schlüssels für den DKE-Dienst finden Sie unter [Mandanten-und Schlüsseleinstellungen](double-key-encryption.md#tenant-and-key-settings) .

Wenn Sie einen Schlüssel erstellen, richten Sie einen Namen und eine GUID ein. Wenn Sie dann einen Schlüssel drehen, behalten Sie den alten Datensatz mit dem Namen und der GUID bei, fügen jedoch einen neuen Datensatz mit demselben Namen, aber unterschiedlichen GUIDs hinzu. Der neue Schlüssel wird als aktiv festgelegt, damit die öffentliche Schlüssel-API für die neue Verschlüsselung zurückgegeben wird. Beide Schlüssel stehen zur Entschlüsselung zur Verfügung, damit neue Inhalte und alte Inhalte entschlüsselt werden können.
