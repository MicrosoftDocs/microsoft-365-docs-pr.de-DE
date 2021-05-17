---
title: BitLocker für Verschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Erfahren Sie, Office 365 die BitLocker verwendet, um das Risiko von Datendiebstahl aufgrund von verlorenen oder gestohlenen Computern und Datenträgern zu verringern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033623"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker und Distributed Key Manager (DKM) für die Verschlüsselung

Microsoft server use BitLocker to encrypt the disk drives containing customer data at rest at the volume-level. BitLocker-Verschlüsselung ist eine Datenverschlüsselungsfunktion, die in Windows integriert ist. BitLocker ist eine der Technologien, die zum Schutz vor Bedrohungen verwendet werden, falls andere Prozesse oder Steuerelemente hinfällig werden (z. B. Zugriffssteuerung oder Access Control oder Recycling von Hardware), sodass andere Personen möglicherweise physischen Zugriff auf Laufwerke mit Kundendaten erlangen könnten. In diesem Fall eliminiert BitLocker das potenzielle Risiko für Datendiebstahl oder Offenlegung aufgrund von verloren gegangener, gestohlener oder nicht ordnungsgemäß außer Betrieb gesetzter Computer und Datenträger.

BitLocker wird mit advanced Encryption Standard (AES) 256-Bit-Verschlüsselung auf Datenträgern bereitgestellt, die Kundendaten in Exchange Online, SharePoint Online und Skype for Business. Datenträgersektoren werden mit einem Vollvolumeverschlüsselungsschlüssel (Full Volume Encryption Key, FVEK) verschlüsselt, der mit dem Volume Master Key (VMK) verschlüsselt wird, der wiederum an das vertrauenswürdige Plattformmodul (Trusted Platform Module, TPM) auf dem Server gebunden ist. Der VMK schützt das FVEK direkt, und daher wird der Schutz des VMK kritisch. Die folgende Abbildung zeigt ein Beispiel für BitLocker Schlüsselschutzkette für einen bestimmten Server (in diesem Fall mithilfe eines Exchange Online Server).

In der folgenden Tabelle wird BitLocker Schlüsselschutzkette für einen bestimmten Server beschrieben (in diesem Fall ein Exchange Online Server).

| SCHLÜSSELSCHUTZ | GRANULARITÄT | WIE GENERIERT? | WO WIRD SIE GESPEICHERT? | SCHUTZ |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Externer AES-256-Bit-Schlüssel | Pro Server | BitLocker APIs | TPM oder Secret Safe | Lockbox/Zugriffssteuerung |
|  |  |  | Postfachserverregistrierung | TPM verschlüsselt |
| 48-stelliges numerisches Kennwort | Pro Datenträger | BitLocker APIs | Active Directory | Lockbox/Zugriffssteuerung |
| X.509-Zertifikat als Datenwiederherstellungs-Agent (Data Recovery Agent, DRA) auch als Public Key Protector bezeichnet | Umgebung (z. B. Exchange Online multitenant) | Microsoft CA | Buildsystem | Kein Benutzer hat das vollständige Kennwort für den privaten Schlüssel. Das Kennwort befindet sich unter physischem Schutz. |


BitLocker Schlüsselverwaltung umfasst die Verwaltung von Wiederherstellungsschlüsseln, die zum Entsperren/Wiederherstellen verschlüsselter Datenträger in einem Microsoft-Rechenzentrum verwendet werden. Microsoft 365 speichert die Hauptschlüssel in einer gesicherten Freigabe, auf die nur Personen zugreifen können, die überprüft und genehmigt wurden. Die Anmeldeinformationen für die Schlüssel werden in einem gesicherten Repository für Zugriffssteuerungsdaten gespeichert (was wir als "geheimer Speicher" bezeichnen), für das ein hohes Maß an Erhöhungs- und Verwaltungsgenehmigungen erforderlich ist, um mithilfe eines Just-in-Time-Zugriffserweiterungstools auf den Zugriff zu zugreifen.

BitLocker unterstützt Schlüssel, die in zwei Verwaltungskategorien fallen:

- Von BitLocker verwaltete Schlüssel, die in der Regel kurzlebig sind und an die Lebensdauer einer Betriebssysteminstanz auf einem Server oder einem bestimmten Datenträger gebunden sind. Diese Schlüssel werden während der Serverneuinstallation oder der Datenträgerformatierung gelöscht und zurückgesetzt.

- BitLocker wiederherstellungsschlüssel, die außerhalb von BitLocker verwaltet werden, aber für die Datenträgerentschlüsselung verwendet werden. BitLocker verwendet Wiederherstellungsschlüssel für Szenarien, in denen ein Betriebssystem neu installiert wird, und bereits verschlüsselte Datenträger mit Daten vorhanden sind. Wiederherstellungsschlüssel werden auch von Überwachungstests für die verwaltete Verfügbarkeit in Exchange Online verwendet, in denen ein Reagierender ggf. einen Datenträger entsperren muss.

BitLocker volumes werden mit einem vollständigen Volumeverschlüsselungsschlüssel verschlüsselt, der wiederum mit einem Volumemasterschlüssel verschlüsselt wird. BitLocker verwendet FIPS-kompatible Algorithmen, um sicherzustellen, dass Verschlüsselungsschlüssel niemals gespeichert oder über den Draht gesendet werden. Die Microsoft 365-Implementierung des Schutzes von ruhenden Kundendaten weicht nicht von der BitLocker-Standardimplementierung ab.
