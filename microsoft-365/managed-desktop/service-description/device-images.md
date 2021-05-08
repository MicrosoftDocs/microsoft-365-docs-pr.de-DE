---
title: Gerätebilder
description: Imageanforderungen bei der Bestellung neuer Geräte oder bei der Erneutvernendung vorhandener Geräte
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 00943eb85abbfd2d237ae5544eb69d3ec4d9f875
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245504"
---
# <a name="device-images"></a>Gerätebilder


Unabhängig davon, ob [](#existing-devices) Sie [neue Geräte bestellen](#new-devices) oder vorhandene geräte wiederverwenden, haben Sie mehrere Optionen, um sicherzustellen, dass das Bild auf dem Gerät unsere [Geräteanforderungen erfüllt.](device-requirements.md#check-hardware-requirements)

## <a name="new-devices"></a>Neue Geräte
Wenn Sie ein neues Gerät bei einem genehmigten Hersteller [bestellen,](device-requirements.md#minimum-requirements)führen Sie die folgenden Schritte aus, um sicherzustellen, dass geräte mit der richtigen Microsoft Managed Desktop und Softwarekonfiguration versandt werden.

### <a name="dell"></a>Dell
Arbeiten Sie direkt mit dem Dell-Vertriebsmitarbeiter zusammen, der dafür sorgt, dass das von Microsoft Managed Desktop genehmigte Bild auf Geräte für Ihre Bestellung angewendet wird. Weitere Fragen zu Dell-Geräten, dem Bild und dem Bestellvorgang finden Sie unter MMD_at_dell@dell.com.

### <a name="hp"></a>HP 
Wenn Sie neue Geräte bei HP bestellen, verwenden Sie unbedingt die spezifische SKU, die im Abschnitt Zusätzliche Anforderungen für jedes Modell auf der Website [Geschäft Windows 10 Pro](https://www.microsoft.com/windowsforbusiness/view-all-devices) Geschäftsgeräte aufgeführt ist (filtern Sie die Ansicht, um Microsoft Managed Desktop anzeigen).

Wenn Sie ein Gerät von HP bestellen, [](customizing.md) das als Ausnahme genehmigt wurde, aber derzeit nicht auf der Seite Geräteliste aufgeführt ist, müssen Sie die SKU für Ihr Modell anfordern. Wir arbeiten mit HP zusammen, um Diese Informationen mithilfe Ihrer Ausnahmeanforderung zu erhalten. Sie können hp auch direkt kontaktieren, wenn Sie Fragen zu Geräten und Anweisungen zur Gerätebestellung erhalten, indem Sie die folgenden Adressen verwenden:
 
- Amerika: mmd-americas@hp.com
- Europa/Naher Osten/Afrika: mmd-emea@hp.com
- Asien-Pazifik/Japan: mmd-apj@hp.com
- Global: mmd@hp.com

### <a name="lenovo"></a>Lenovo
Wenn Sie Geräte von Lenovo für die Verwendung in Microsoft Managed Desktop bestellen, müssen Sie eine bestimmte Teilnummer angeben, die im Rahmen der Bestellung enthalten ist. Wenden Sie sich an Ihren Lenovo Vertriebsmitarbeiter oder Lenovo Channel Partner, und bitten Sie ihn, ein *spezielles* Angebotsmodell mit einem System zu erstellen, das unsere [Geräteanforderungen erfüllt.](device-requirements.md#minimum-requirements) Bitten Sie den Vertriebsmitarbeiter, auf "System *building block part number SBB0Q94938 – MMD Enablement"* zu verweisen, um ein mit Microsoft Managed Desktop kompatibles vorab geladenes Bild zu verwenden.

Die folgenden Produkte sind derzeit für den Microsoft Managed Desktop aktiviert:

- L13 Gen 1
- L13-Yoga Gen 1
- L14 Gen 1 (Intel)
- L14 Gen 1 (AMD)
- L15 Gen 1 (Intel)
- L15 Gen 1 (AMD)
- X1 Carbon Gen 8
- X1-Gen 5 für "X1"
- T14 Gen 1 (Intel)
- T14 Gen 1 (AMD)
- T15 Gen 1
- X13 Gen 1 (Intel)


### <a name="microsoft"></a>Microsoft
Alle Microsoft-Geräte, die Geräteanforderungen erfüllen, verfügen über ein Bild, das mit Microsoft Managed Desktop. Es sind keine weiteren Schritte erforderlich.

Um das neueste Bild, das in der Fabrik auf einem Microsoft-Gerät verfügbar ist, zu erhalten, arbeiten Sie mit Ihrem Surface-Spezialisten zusammen, um den Surface "Pegged PO"-Prozess zu verwenden.

## <a name="existing-devices"></a>Vorhandene Geräte

Sie können vorhandene Geräte wiederverwenden, solange sie sowohl die [Geräteanforderungen als](device-requirements.md#minimum-requirements) auch die [Softwareanforderungen erfüllen.](device-requirements.md#installed-software) Führen Sie die für Ihren Hersteller relevanten Schritte aus.

Sie können Geräte entweder mit einem Bild des Herstellers oder mithilfe der Microsoft Managed Desktop "universelles Bild" nachbilden. Um ein entsprechendes Herstellerimage zu erhalten, können Sie mindestens ein [neues](#new-devices) Gerät des Modells bestellen, das Sie erneut verwenden. Anschließend können Sie das Bild von diesem Gerät abrufen und auf andere Geräte desselben Modells anwenden.

> [!NOTE]
> Sie sind dafür verantwortlich, Bilder zu erstellen, zu testen und zu bereitstellen. Es wird auch empfohlen, nach Möglichkeit geeignete Bilder des Herstellers anstelle von benutzerdefinierten Bildern zu verwenden , einschließlich des "universellen Bilds".

### <a name="hp"></a>HP

Hp Commercial PCs, die mit dem HP Corporate Ready Image ausgeliefert werden, enthalten einen . WIM-Datei für die Wiederherstellung. Sie können dieses Bild verwenden, um das Werkswiederherstellungsimage auf andere Geräte desselben Modells anzuwenden.

Mit diesen Schritten werden alle Daten auf dem Gerät entfernt. Daher sollten Sie vor dem Starten alle Daten sichern, die Sie behalten möchten.

1. [Erstellen Sie ein startbares USB-Laufwerk](https://docs.microsoft.com/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) mit WinPE.
2. Kopieren Sie diese Dateien aus C: \\ SOURCES auf das USB-Laufwerk:
    - Die FACTORY-Wiederherstellungs-WIM-Datei (z. B. HP \_ EliteBook \_ 840 \_ G7 \_ Notebook PC CR \_ \_ \_ 2004.wim)
    - DEPLOY. CMD
    - ReCreatePartitions.txt
3. [Starten des Geräts zu WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB-Laufwerk.
4. Führen Sie in einer Eingabeaufforderung [Diskpart.exe](https://docs.microsoft.com/windows-server/administration/windows-commands/diskpart#additional-references)aus.
5. Führen Sie in Diskpart , und notieren Sie dann die primäre Datenträgernummer (in der Regel `list disk` Datenträger 0).
6. Beenden Sie Diskpart, indem Sie `exit` eingeben.
7. Führen Sie in der Eingabeaufforderung aus, wobei sys_disk die Datenträgernummer des primären Speicherdatenträgers ist, den Sie gerade ermittelt haben, und recovery_wim ist der `deploy.cmd <sys_disk> <recovery_wim>` Dateiname der .   ZUVOR kopierte WIM-Datei.
8. Entfernen Sie das USB-Laufwerk, und starten Sie das Gerät neu.

### <a name="microsoft"></a>Microsoft 

Microsoft Surface geräte enthalten "Bare Metal [Recovery"-Bilder,](https://support.microsoft.com/en-us/surfacerecoveryimage) die für jedes Modell spezifisch sind. Sie können diese Bilder verwenden, um Geräte neu zu abbilden.

Diese Bilder verwenden die Windows Recovery Environment (WinRE), und dies ist ein manueller Prozess (nicht automatisiert). Führen Sie die Schritte unter [Erstellen und Verwenden eines USB-Wiederherstellungslaufwerks für Surface aus.](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)


### <a name="universal-image"></a>Universelles Bild
Microsoft Managed Desktop hat ein Bild mit Windows 10 Pro und Microsoft 365 Apps für Enterprise erstellt, das Sie mit Microsoft Managed Desktop. Es ist jedoch am besten, bilder zu verwenden, die Microsoft Managed Desktop vom Hersteller bereitgestellt werden, wann immer möglich, auch wenn dies eine ältere Windows-Version bedeutet, die nach der Benutzera0 aktualisiert werden muss. Die Verwendung Microsoft Managed Desktop Universelles Bild sollte eine letzte Option sein.

- Wir aktualisieren das Bild mit den neuesten Windows monatlichen Qualitätsupdates alle 30-60 Tage und Microsoft 365 Apps für Enterprise mindestens zweimal pro Jahr.
- Das Bild enthält ein Wiederherstellungsbereitstellungspaket, um sicherzustellen, Microsoft 365 Apps wiederhergestellt Enterprise wiederhergestellt Windows Wiederherstellungsszenarien.
- Sie können das Image mit USB-Laufwerken bereitstellen. Es enthält einen skriptbaren Prozess zum Einfügen von Treibern (in der Im Bild enthaltenen Dokumentation beschrieben).
- Sie können die enthaltenen Skripts und Ordner für die Verwendung mit anderen Anpassungen ändern, z. B. das Hinzufügen bestimmter kumulativer Updates, Dateikopiencode oder andere Prüfungen.
- Treiber und Qualitätsupdates werden Windows Bereitstellung über das USB-Laufwerk hinzugefügt.

> [!NOTE]
> Es liegt in Ihrer Verantwortung, alle erforderlichen Treiber hinzuzufügen, alle Tests durchzuführen und sicherzustellen, dass keine Probleme mit dem endgültigen bereitgestellten Image auftreten. Wir stellen das universelle Bild "as-is" zur Verfügung, stellen jedoch technische Anleitungen zur Verfügung und beantworten Fragen. Kontakt MMDImage@microsoft.com.

Senden Sie Anforderungen für den Inhalt und die Dokumentation des universellen Bilds, indem Sie eine Änderungsanforderung im [Administratorportal erstellen.](../get-started/access-admin-portal.md)


