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
ms.openlocfilehash: f0c78a9ca6e6bad1e4aea707f8be5dec818b7a27
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817924"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Datenverschlüsselung in OneDrive for Business und SharePoint Online

Verstehen Sie die grundlegenden Elemente der Verschlüsselung für die Datensicherheit in OneDrive for Business und SharePoint Online.
  
## <a name="security-and-data-encryption-in-office-365"></a>Sicherheit und Datenverschlüsselung in Office 365

Microsoft 365 ist eine hochsichere Umgebung mit umfangreichem Schutz in mehreren Schichten: Sicherheit von physischen Rechenzentren, Netzwerksicherheit, Zugriffssicherheit, Anwendungssicherheit und Datensicherheit. Dieser Artikel befasst sich speziell mit der Verschlüsselung der Datensicherheit während der Übertragung und im Ruhezustand für OneDrive for Business und SharePoint Online.
  
Sehen Sie sich im folgenden Video an, wie die Datenverschlüsselung funktioniert.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Verschlüsselung von Daten während der Übertragung

In OneDrive for Business und SharePoint Online gibt es zwei Szenarien, in denen Daten in Rechenzentren ein- und ausgehen.
  
- **Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.

- **Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption. 

## <a name="encryption-of-data-at-rest"></a>Verschlüsselung von Daten im Ruhezustand

Die Verschlüsselung im Ruhezustand enthält zwei Komponenten: BitLocker-Verschlüsselung auf Datenträgerebene und dateispezifische Verschlüsselung von Kundeninhalten.
  
BitLocker wird für OneDrive for Business und SharePoint Online im ganzen Dienst bereitgestellt. Die Verschlüsselung per Datei befindet sich auch in OneDrive für Unternehmen und SharePoint Online in Microsoft 365 Multi-Mandanten und neue dedizierte Umgebungen, die auf mehr mandantenfähiger Technologie basieren.
  
While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.
  
Weitere Informationen zur FIPS 140-2-Konformität finden Sie unter [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).
  
File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:
  
1. All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.

2. All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.

3. Die für das erneute Zusammensetzen der Datei aus ihren Komponenten verwendete „Karte" wird in der Inhaltsdatenbank gespeichert.

4. Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.

Anders gesagt, sind drei unterschiedliche Arten von Speicher an der Verschlüsselung im Ruhezustand beteiligt, jede mit einer anderen Funktion:
  
- Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.

- The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.

Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.
