---
title: Aufbewahren, Löschen und Zerstören von Daten in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Eine Übersicht über Microsoft-Richtlinien für Microsoft 365 bezüglich Datenaufbewahrung, Löschung und Vernichtung.
ms.openlocfilehash: 9708ed618528ce0ad5ef8656a85ffd4311395deb
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331896"
---
# <a name="data-retention-deletion-and-destruction-in-microsoft-365"></a>Aufbewahren, Löschen und Zerstören von Daten in Microsoft 365

Microsoft verfügt über eine Richtlinie zur Datenverarbeitung für Microsoft 365, die angibt, wie lange Kundendaten nach dem Löschen aufbewahrt werden. Es gibt in der Regel zwei Szenarien, in denen Kundendaten gelöscht werden:

- **Aktive Löschung**: der Mandant verfügt über ein aktives Abonnement, und ein Benutzer oder Administrator löscht Daten, oder Administratoren löschen einen Benutzer.
- **Passive Löschung**: das Mandanten Abonnement wird beendet.

## <a name="data-retention"></a>Datenaufbewahrung

In der folgenden Tabelle sind die maximalen Daten Aufbewahrungs Intervalle nach Datenkategorie und Klassifizierung für jedes dieser Lösch Szenarien dargestellt:

| Datenkategorie | Datenklassifikation | Beschreibung | Beispiele | Aufbewahrungszeitraum |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| Kundendaten | Kunden Inhalte| Inhalte, die von Administratoren und Benutzern direkt bereitgestellt/erstellt wurden <br><br> Enthält alle Text-, Sound-, Video-, Bilddateien und Software, die in Microsoft-Rechenzentren erstellt und gespeichert werden, wenn die Dienste in Microsoft 365 verwendet werden. | Beispiele für die am häufigsten verwendeten Microsoft 365-Anwendungen, mit denen Benutzerdaten erstellen können, sind Word, Excel, PowerPoint, Outlook und OneNote. <br><br> Kunden Inhalte enthalten auch kundeneigene/bereitgestellte Geheimnisse (Kennwörter, Zertifikate, Verschlüsselungsschlüssel, Speicherschlüssel) | **Aktives Lösch Szenario:** höchstens 30 Tage <br><br> **Szenario für passive Löschung:** höchstens 180 Tage |
| Kundendaten | Identifizierbare Informationen für Endbenutzer (EUII) | Daten, mit denen der Benutzer eines Microsoft-Diensts identifiziert oder verwendet werden kann. EUII enthält keine Kunden Inhalte. | Benutzername oder Anzeigename (Domäne \ Benutzername) <br><br> Benutzerprinzipalname (Name@Domain) <br><br>  Benutzerspezifische IP-Adressen | **Aktives Lösch Szenario:** höchstens 180 Tage (nur eine mandantenadministrator Aktion) <br><br> **Szenario für passive Löschung:** höchstens 180 Tage |
| Persönliche Daten <br> (Daten sind nicht in Kundendaten enthalten) | Pseudonyme Bezeichner für Endbenutzer (EUPI) | Ein von Microsoft erstellter Bezeichner, der mit dem Benutzer eines Microsoft-Diensts verbunden ist. In Kombination mit anderen Informationen, beispielsweise einer Zuordnungstabelle, identifiziert EUPI den Endbenutzer <br><br> EUPI enthält keine vom Kunden hochgeladenen oder erstellten Informationen. | Benutzer-GUIDs, PUIDs oder SIDs <br><br> Sitzungs-IDs | **Aktives Lösch Szenario:** höchstens 30 Tage <br><br> **Szenario für passive Löschung:** höchstens 180 Tage |

## <a name="subscription-retention"></a>Abonnement Aufbewahrung

Im Ausdruck eines aktiven Abonnements kann ein Abonnent auf Kundendaten zugreifen, diese extrahieren oder löschen, die in Microsoft 365 gespeichert sind. Wenn ein kostenpflichtiges Abonnement endet oder beendet wird, behält Microsoft die in Microsoft 365 gespeicherten Kundendaten in einem Konto mit begrenzter Funktion für 90 Tage bei, damit der Abonnent die Daten extrahieren kann. Nachdem der Aufbewahrungszeitraum von 90 Tagen abgelaufen ist, deaktiviert Microsoft das Konto und löscht die Kundendaten. Spätestens 180 Tage nach Ablauf oder Kündigung eines Microsoft 365-Abonnements deaktiviert Microsoft das-Konto und löscht alle Kundendaten daraus. Sobald der maximale Aufbewahrungszeitraum für Daten abgelaufen ist, werden die Daten kommerziell nicht mehr wiederhergestellt.

Für eine ﻿kostenlose Testversion wechselt Ihr Konto in den meisten Ländern und Regionen in den Kulanz Status für 30 Tage. Innerhalb dieser Nachfrist können Sie Microsoft 365 kaufen. Wenn Sie sich entscheiden, Microsoft 365 nicht zu kaufen, können Sie entweder Ihre Testversion kündigen oder die Nachfrist ablaufen und Ihre Testkontoinformationen und -daten löschen lassen.

## <a name="expedited-deletion"></a>Beschleunigtes löschen

Für jedes Abonnement kann ein Abonnent den Microsoft-Support kontaktieren und eine beschleunigte Deaktivierung anfordern. Bei diesem Vorgang werden alle Benutzerdaten drei Tage, nachdem der Administrator den von Microsoft bereitgestellten Sperrcode eingegeben hat, gelöscht. Dazu gehören Daten in SharePoint Online und Exchange Online, die gesperrt oder in inaktiven Postfächern gespeichert sind.

Weitere Informationen zur beschleunigten Deaktivierung finden Sie unter [kündigen Ihres Abonnements](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription).

## <a name="related-links"></a>Links zu verwandten Themen

- [Zerstörung von Daten](microsoft-365-data-destruction.md)
- [Unveränderbarkeit in Office 365](microsoft-365-data-immutability.md)
- [Löschen von Exchange Online-Daten](microsoft-365-exchange-online-data-deletion.md)
- [Löschen von SharePoint Online-Daten](microsoft-365-sharepoint-online-data-deletion.md)
- [Löschen von Skype for Business-Daten](microsoft-365-skype-data-deletion.md)
