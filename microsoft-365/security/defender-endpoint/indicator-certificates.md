---
title: Erstellen von Indikatoren basierend auf Zertifikaten
ms.reviewer: ''
description: Erstellen Sie Indikatoren basierend auf Zertifikaten, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: iOC, Zertifikat, Zertifikate, verwalten, zulässig, blockiert, blockieren, sauber, bösartig, Dateihash, IP-Adresse, URLs, Domäne
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
ms.openlocfilehash: b75a8cf1d2681281555a3b7bb80deadfc11ee44c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845450"
---
# <a name="create-indicators-based-on-certificates"></a>Erstellen von Indikatoren basierend auf Zertifikaten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Sie können Indikatoren für Zertifikate erstellen. Einige häufige Anwendungsfälle sind:

- Szenarien, in denen Sie Blockierungstechnologien bereitstellen müssen, z. B. Regeln zur Verringerung der [Angriffsfläche](attack-surface-reduction.md) und [kontrollierter Ordnerzugriff,](controlled-folders.md) aber Verhaltensweisen von signierten Anwendungen zulassen müssen, indem Sie das Zertifikat in der Zulassungsliste hinzufügen.
- Blockieren der Verwendung einer bestimmten signierten Anwendung in Ihrer Organisation. Durch das Erstellen eines Indikators zum Blockieren des Zertifikats der Anwendung verhindert Windows Defender AV Dateiausführungen (blockieren und korrigieren), und die automatische Untersuchung und Korrektur verhält sich identisch.


### <a name="before-you-begin"></a>Bevor Sie beginnen

Es ist wichtig, die folgenden Anforderungen zu verstehen, bevor Sie Indikatoren für Zertifikate erstellen:

- Dieses Feature ist verfügbar, wenn Ihre Organisation Windows Defender Antivirus verwendet und der cloudbasierte Schutz aktiviert ist. Weitere Informationen finden Sie unter [Verwalten des cloudbasierten Schutzes.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)
- Die Antischadsoftware-Clientversion muss 4.18.1901.x oder höher sein.
- Unterstützt auf Computern mit Windows 10, Version 1703 oder höher, Windows Server 2016 und 2019.
- Die Viren- und Bedrohungsschutzdefinitionen müssen auf dem neuesten Stand sein.
- Dieses Feature unterstützt derzeit die Eingabe. CER oder . PEM-Dateierweiterungen.

>[!IMPORTANT]
> - Ein gültiges Blattzertifikat ist ein Signaturzertifikat, das über einen gültigen Zertifizierungspfad verfügt und mit der Von Microsoft vertrauenswürdigen Stammzertifizierungsstelle verkettet werden muss.  Alternativ kann ein benutzerdefiniertes (selbstsigniertes) Zertifikat verwendet werden, solange es vom Client als vertrauenswürdig eingestuft wird (Das Stammzertifizierungsstellenzertifikat wird unter dem lokalen Computer "Vertrauenswürdige Stammzertifizierungsstellen" installiert).
>- Die untergeordneten elemente oder übergeordneten Elemente der Allow/Block-Zertifikat-IOCs sind nicht in der Allow/Block-IoC-Funktion enthalten, es werden nur untergeordnete Zertifikate unterstützt.
>- Von Microsoft signierte Zertifikate können nicht blockiert werden.

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Erstellen Sie auf der Einstellungsseite einen Indikator für Zertifikate:

>[!IMPORTANT]
> Es kann bis zu 3 Stunden dauern, bis ein Zertifikat-IoC erstellt und entfernt wird.

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Indikatoren** aus.  

2. Wählen Sie die Registerkarte **"Zertifikat"** aus.

3. Wählen Sie **"Indikator hinzufügen" aus.**

4. Geben Sie die folgenden Details an:
   - Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.
   - Aktion – Geben Sie die auszuführende Aktion an, und geben Sie eine Beschreibung an.
   - Bereich: Definieren Sie den Bereich der Computergruppe.

5. Überprüfen Sie die Details auf der Registerkarte "Zusammenfassung", und klicken Sie dann auf **"Speichern".**

## <a name="related-topics"></a>Verwandte Themen
- [Indikatoren erstellen](manage-indicators.md)
- [Erstellen von Indikatoren für Dateien](indicator-file.md)
- [Erstellen von Indikatoren für IPs und URLs/Domänen](indicator-ip-domain.md)
- [Indikatoren verwalten](indicator-manage.md)
