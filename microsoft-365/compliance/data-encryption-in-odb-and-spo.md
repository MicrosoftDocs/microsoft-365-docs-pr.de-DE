---
title: Datenverschlüsselung in OneDrive for Business und SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Verstehen Sie die grundlegenden Elemente der Verschlüsselung für die Datensicherheit in OneDrive for Business und SharePoint Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca93d04fa21487ad054cd9cb924dff1fc15abfbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922629"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Datenverschlüsselung in OneDrive for Business und SharePoint Online

Verstehen Sie die grundlegenden Elemente der Verschlüsselung für die Datensicherheit in OneDrive for Business und SharePoint Online.
  
## <a name="security-and-data-encryption-in-office-365"></a>Sicherheit und Datenverschlüsselung in Office 365

Microsoft 365 ist eine hochgradig sichere Umgebung, die umfassenden Schutz in mehreren Ebenen bietet: Sicherheit des physischen Rechenzentrums, Netzwerksicherheit, Zugriffssicherheit, Anwendungssicherheit und Datensicherheit. Dieser Artikel befasst sich speziell mit der Verschlüsselung der Datensicherheit während der Übertragung und im Ruhezustand für OneDrive for Business und SharePoint Online.
  
Sehen Sie sich im folgenden Video an, wie die Datenverschlüsselung funktioniert.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Verschlüsselung von Daten während der Übertragung

In OneDrive for Business und SharePoint Online gibt es zwei Szenarien, in denen Daten in Rechenzentren ein- und ausgehen.
  
- **Clientkommunikation mit dem Server** Bei der Kommunikation mit OneDrive for Business über das Internet werden SSL/TLS-Verbindungen verwendet. Alle SSL-Verbindungen werden mit 2048-Bit-Schlüsseln hergestellt.

- **Datenverschiebung zwischen Rechenzentren** Der wichtigste Grund zum Verschieben von Daten zwischen Rechenzentren ist die Georeplikation für die Notfallwiederherstellung. Beispielsweise werden SQL Server-Transaktionsprotokolle und BLOB-Speicher-Deltas entlang dieser Pipe übertragen. Während diese Daten bereits über ein privates Netzwerk übertragen werden, werden sie zusätzlich durch branchenbeste Verschlüsselung geschützt. 

## <a name="encryption-of-data-at-rest"></a>Verschlüsselung von Daten im Ruhezustand

Die Verschlüsselung im Ruhezustand enthält zwei Komponenten: BitLocker-Verschlüsselung auf Datenträgerebene und dateispezifische Verschlüsselung von Kundeninhalten.
  
BitLocker wird für OneDrive for Business und SharePoint Online im ganzen Dienst bereitgestellt. Die Dateiverschlüsselung befindet sich auch in OneDrive for Business und SharePoint Online in Microsoft 365 multi-tenant und neuen dedizierten Umgebungen, die auf mehrstufiger Technologie aufgebaut sind.
  
Während alle Daten auf einem Datenträger mit BitLocker verschlüsselt werden, geht die Dateiverschlüsselung sogar noch weiter, indem ein eindeutiger Schlüssel für jede Datei eingeschlossen wird. Darüber hinaus wird jede Aktualisierung jeder Datei mit einem eigenen Schlüssel verschlüsselt. Bevor sie gespeichert werden, werden die Schlüssel für die verschlüsselten Inhalte an einem vom Inhalt separaten Speicherort gespeichert. Jeder Schritt der Verschlüsselung verwendet AES (Advanced Encryption Standard, erweiterter Verschlüsselungsstandard) mit 256-Bit-Schlüsseln und ist zu FIPS 140-2 (Federal Information Processing Standard) kompatibel. Die verschlüsselten Inhalte werden auf einer Reihe von Containern im gesamten Rechenzentrum verteilt, und jeder Container besitzt eindeutige Anmeldeinformationen. Diese Anmeldeinformationen werden in einem vom Inhalt oder den Inhaltsschlüsseln separaten physischen Speicherort gespeichert.
  
Weitere Informationen zur FIPS 140-2-Compliance finden Sie unter [FIPS 140-2 Compliance](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).
  
Die Verschlüsselung im Ruhezustand auf Dateiebene nutzt BLOB-Speicher, um praktisch unbegrenzten Speicherplatz bereitzustellen und einen umfassenden Schutz zu ermöglichen. Alle Kundeninhalte in OneDrive for Business und SharePoint Online werden in BLOB-Speicher migriert. So werden die Daten geschützt:
  
1. Alle Inhalte werden, möglicherweise mit mehreren Schlüsseln, verschlüsselt und über Rechenzentren verteilt. Jede zu speichernde Datei wird je nach der Größe in einen oder mehrere Blöcke aufgeteilt. Dann wird jeder Block mit einem eigenen eindeutigen Schlüssel verschlüsselt. Aktualisierungen werden auf ähnliche Weise behandelt: Der Satz von Änderungen oder Deltas, die von einem Benutzer übermittelt werden, wird in Blöcke unterteilt, und jeder wird mit einem eigenen Schlüssel verschlüsselt.

2. Alle diese Blöcke - Dateien, Teile von Dateien und Aktualisierungsdeltas - werden als BLOBs in unserem BLOB-Speicher gespeichert. Sie werden zudem nach dem Zufallsprinzip auf mehrere BLOB-Container verteilt.

3. Die für das erneute Zusammensetzen der Datei aus ihren Komponenten verwendete „Karte" wird in der Inhaltsdatenbank gespeichert.

4. Jeder BLOB-Container besitzt eigene eindeutige Anmeldeinformationen pro Zugriffstyp (Lesen, Schreiben, Aufzählen und Löschen). Jeder Satz von Anmeldeinformationen wird im sicheren Schlüsselspeicher aufbewahrt und regelmäßig aktualisiert.

Anders gesagt, sind drei unterschiedliche Arten von Speicher an der Verschlüsselung im Ruhezustand beteiligt, jede mit einer anderen Funktion:
  
- Inhalt wird als verschlüsselte BLOBs im BLOB-Speicher gespeichert. Der Schlüssel für jeden Inhaltsblock wird verschlüsselt und separat in der Inhaltsdatenbank gespeichert. Der Inhalt selbst enthält keinen Hinweis darauf, wie er entschlüsselt werden kann.

- Die Inhaltsdatenbank ist eine SQL Server-Datenbank. Sie enthält die Karte zum Suchen und erneuten Zusammensetzen aller Inhalts-BLOBs im BLOB-Speicher sowie die Schlüssel zum Entschlüsseln dieser BLOBs.

Jede dieser drei Speicherkomponenten - BLOB-Speicher, Inhaltsdatenbank und Schlüsselspeicher - ist physisch getrennt. Die Informationen in einer der Komponenten sind allein unbrauchbar. Dies bietet eine einzigartige Sicherheitsstufe. Ohne Zugriff auf alle drei ist es unmöglich, die Schlüssel für die Datenblöcke abzurufen, die Schlüssel zu entschlüsseln, um sie verwendbar zu machen, die Schlüssel ihren entsprechenden Datenblöcken zuzuordnen, einen Block zu entschlüsseln oder ein Dokument aus den einzelnen Blöcken zusammenzusetzen.