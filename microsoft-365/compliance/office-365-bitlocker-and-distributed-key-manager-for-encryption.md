---
title: BitLocker für die Verschlüsselung
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
description: 'Zusammenfassung: Informationen zu BitLocker für die Verschlüsselung in der Cloud.'
ms.openlocfilehash: 5596848e392736e20e8c796e6fd409b9c43235d4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637351"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker und Distributed Key Manager (DKM) für die Verschlüsselung

Microsoft-Server verwenden BitLocker zum Verschlüsseln der Datenträgerlaufwerke, die Kundendaten im Ruhezustand auf Volumen Ebene enthalten. BitLocker-Verschlüsselung ist eine Datenverschlüsselungsfunktion, die in Windows integriert ist. BitLocker ist eine der Technologien, die zum Schutz vor Bedrohungen verwendet werden, falls andere Prozesse oder Steuerelemente hinfällig werden (z. B. Zugriffssteuerung oder Access Control oder Recycling von Hardware), sodass andere Personen möglicherweise physischen Zugriff auf Laufwerke mit Kundendaten erlangen könnten. In diesem Fall eliminiert BitLocker das potenzielle Risiko für Datendiebstahl oder Offenlegung aufgrund von verloren gegangener, gestohlener oder nicht ordnungsgemäß außer Betrieb gesetzter Computer und Datenträger.

BitLocker wird mit AES 256-Bit-Verschlüsselung (Advanced Encryption Standard) auf Datenträgern mit Kundendaten in Exchange Online, SharePoint Online und Skype for Business bereitgestellt. Datenträgersektoren werden mit einem vollständigen Volume Encryption Key (FVEK) verschlüsselt, der mit dem Volume Master Key (VMK) verschlüsselt wird, der wiederum an das TPM (Trusted Platform Module) auf dem Server gebunden ist. Das VMK schützt das FVEK direkt und daher wird der Schutz der VMK kritisch. Die folgende Abbildung zeigt ein Beispiel für die BitLocker-Schlüsselschutz Kette für einen bestimmten Server (in diesem Fall mit einem Exchange Online Server).

In der folgenden Tabelle wird die BitLocker-Schlüsselschutz Kette für einen bestimmten Server (in diesem Fall ein Exchange Online Server) beschrieben.

| Tasten Schutz | Granularität | wie generiert? | wo wird es gespeichert? | Schutz |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Externer AES-Schlüssel 256-Bit | Pro Server | BitLocker-APIs | TPM oder geheimer Tresor | Lockbox/Zugriffssteuerung |
|  |  |  | Post Fach Server-Registrierung | TPM verschlüsselt |
| 48-stelliges numerisches Kennwort | Pro Datenträger | BitLocker-APIs | Active Directory Domain Services | Lockbox/Zugriffssteuerung |
| X. 509-Zertifikat als Daten Wiederherstellungs-Agent (DRA), auch Public Key Protector genannt | Umgebung (z. b. Exchange Online Multimandanten) | Microsoft-Zertifizierungsstelle | Erstellungs System | Ein Benutzer hat nicht das vollständige Kennwort für den privaten Schlüssel. Das Kennwort ist unter physischem Schutz. |


Die BitLocker-Schlüsselverwaltung umfasst die Verwaltung von Wiederherstellungsschlüsseln, die zum Entsperren/Wiederherstellen verschlüsselter Datenträger in einem Microsoft-Rechenzentrum verwendet werden. Microsoft 365 speichert die Hauptschlüssel in einer gesicherten Freigabe, nur für Personen zugänglich, die geprüft und genehmigt wurden. Die Anmeldeinformationen für die Schlüssel werden in einem gesicherten Repository für Zugriffssteuerungsdaten gespeichert (was wir als geheimer Speicher bezeichnen), was eine hohe Höhe der Höhen-und Verwaltungs Genehmigungen erfordert, um mithilfe eines Just-in-Time-Zugriffs Ansichts Tools auf den Zugriff zuzugreifen.

BitLocker unterstützt Schlüssel, die in zwei Verwaltungskategorien fallen:

- Von BitLocker verwaltete Schlüssel, die in der Regel kurzlebig sind und an die Lebensdauer einer auf einem Server oder einem bestimmten Datenträger installierten Betriebssysteminstanz gebunden sind. Diese Schlüssel werden gelöscht und während der Server Neuinstallation oder der Datenträgerformatierung zurückgesetzt.

- BitLocker-Wiederherstellungsschlüssel, die außerhalb von BitLocker verwaltet werden, aber für die Datenträger Entschlüsselung verwendet werden. BitLocker verwendet Wiederherstellungsschlüssel für das Szenario, in dem ein Betriebssystem neu installiert wird, und es sind bereits verschlüsselte Datenträger vorhanden. Wiederherstellungsschlüssel werden auch von Überwachungstests für verwaltete Verfügbarkeit in Exchange Online verwendet, in denen ein Responder möglicherweise einen Datenträger entsperren muss.

Mit BitLocker geschützte Volumes werden mit einem vollständigen Verschlüsselungsschlüssel verschlüsselt, der wiederum mit einem Volumen Hauptschlüssel verschlüsselt wird. BitLocker verwendet FIPS-konforme Algorithmen, um sicherzustellen, dass Verschlüsselungsschlüssel nie im Klartext gespeichert oder über den Draht gesendet werden. Die Microsoft 365-Implementierung von Kundendaten-at-Rest-Protection weicht nicht von der BitLocker-Standardimplementierung ab.
