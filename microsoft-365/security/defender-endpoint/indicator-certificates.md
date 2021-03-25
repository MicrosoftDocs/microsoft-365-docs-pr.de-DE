---
title: Erstellen von Indikatoren basierend auf Zertifikaten
ms.reviewer: ''
description: Erstellen Sie Indikatoren basierend auf Zertifikaten, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: ioc, Zertifikat, Zertifikate, verwalten, zulässig, blockiert, blockieren, sauber, schadhaft, Dateihash, IP-Adresse, URLs, Domäne
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164681"
---
# <a name="create-indicators-based-on-certificates"></a>Erstellen von Indikatoren basierend auf Zertifikaten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Sie können Indikatoren für Zertifikate erstellen. Einige häufige Verwendungsfälle sind:

- Szenarien, in denen Sie Blockierungstechnologien bereitstellen müssen, z. B. Regeln zur Reduzierung der Angriffsfläche und kontrollierten Ordnerzugriff, jedoch Verhalten von signierten Anwendungen zulassen müssen, indem Sie das Zertifikat in der Liste der zulässigen Anwendungen hinzufügen. [](attack-surface-reduction.md) [](controlled-folders.md)
- Blockieren der Verwendung einer bestimmten signierten Anwendung in Ihrer Organisation. Durch das Erstellen eines Indikators zum Blockieren des Zertifikats der Anwendung verhindert Windows Defender AV Dateiausführungen (Blockieren und Bereinigung), und die automatische Untersuchung und Korrektur verhält sich gleich.


### <a name="before-you-begin"></a>Vorbereitung

Es ist wichtig, die folgenden Anforderungen zu verstehen, bevor Sie Indikatoren für Zertifikate erstellen:

- Dieses Feature ist verfügbar, wenn Ihre Organisation Windows Defender Antivirus und cloudbasierter Schutz aktiviert ist. Weitere Informationen finden Sie unter [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
- Die Antischalwareclientversion muss 4.18.1901.x oder höher sein.
- Unterstützt auf Computern unter Windows 10, Version 1703 oder höher, Windows Server 2016 und 2019.
- Die Viren- und Bedrohungsschutzdefinitionen müssen auf dem neuesten Stand sein.
- Dieses Feature unterstützt derzeit die Eingabe von . CER oder . PEM-Dateierweiterungen.

>[!IMPORTANT]
> - Ein gültiges Blattzertifikat ist ein Signaturzertifikat, das über einen gültigen Zertifizierungspfad verfügt und an die von Microsoft vertrauenswürdige Stammzertifizierungsstelle (Root Certificate Authority, CA) verkettet werden muss.  Alternativ kann ein benutzerdefiniertes (selbst signiertes) Zertifikat verwendet werden, solange es vom Client als vertrauenswürdig eingestuft wird (Das Zertifikat der Stammzertifizierungsstelle wird unter dem lokalen Computer "Vertrauenswürdige Stammzertifizierungsstellen" installiert).
>- Die untergeordneten Oder übergeordneten der IoCs für das Zulassen/Blockieren von Zertifikaten sind nicht in der Allow/Block-IoC-Funktionalität enthalten, sondern nur Blattzertifikate werden unterstützt.
>- Von Microsoft signierte Zertifikate können nicht blockiert werden.

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Erstellen Sie auf der Einstellungsseite einen Indikator für Zertifikate:

>[!IMPORTANT]
> Es kann bis zu 3 Stunden dauern, bis ein Zertifikat ioC erstellt und entfernt wird.

1. Wählen Sie im Navigationsbereich **Einstellungsindikatoren**  >  **aus.**  

2. Wählen Sie die **Registerkarte Zertifikat** aus.

3. Wählen **Sie Indikator hinzufügen aus.**

4. Geben Sie die folgenden Details an:
   - Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.
   - Aktion – Geben Sie die zu ergreifende Aktion an, und geben Sie eine Beschreibung an.
   - Bereich : Definieren Sie den Bereich der Computergruppe.

5. Überprüfen Sie die Details auf der Registerkarte Zusammenfassung, und klicken Sie dann auf **Speichern**.

## <a name="related-topics"></a>Verwandte Themen
- [Erstellen von Indikatoren](manage-indicators.md)
- [Erstellen von Indikatoren für Dateien](indicator-file.md)
- [Erstellen von Indikatoren für IPs und URLs/Domänen](indicator-ip-domain.md)
- [Verwalten von Indikatoren](indicator-manage.md)
