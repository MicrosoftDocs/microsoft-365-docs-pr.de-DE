---
title: 'Schritt 3: Liefern von Office- und Branchen-Apps'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zum Liefern von Office- und Branchen-Apps.
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868213"
---
# <a name="step-3-office-and-lob-app-delivery"></a>Schritt 3: Liefern von Office- und Branchen-Apps

Sie sind nun bereit, Ihre Office- und Branchen-Apps zu liefern. Es gibt eine Reihe von Möglichkeiten, die zu tun, darunter auch einige interessanten neuen Optionen. Nehmen Sie sich Zeit, diese Optionen anzusehen und die besten Methoden für Ihre aktuellen Anforderungen auszuwählen.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>Schritt 3: Liefern von Office- und Branchen-Apps</strong></p>
<p>Stellen Sie sicher, dass Ihre Apps für eine automatische Installation verpackt und bereit sind. Erfahren Sie, wie Sie durch eine Klick-und-Los-Verpackung mit Office 365 ProPlus neue Optionen erhalten, um Ihre Office-Apps zu konfigurieren, zu liefern und auf dem neuesten Stand zu halten.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>Das Liefern von Office- und Branchen-Apps ist der dritte Schritt in unserem empfohlenem Bereitstellungsprozess, bei dem die Optionen für die Installation und Verwaltung von Office und Branchen-Apps behandelt werden. Um eine erfolgreiche Bereitstellung zu gewährleisten, überspringen Sie nicht den ersten und zweiten Schritt. Den vollständigen Desktopbereitstellungsprozess finden Sie im [Bereitstellungscenter für modernen Desktop](https://aka.ms/HowToShift).
>

Während einige Programme nur als eine kompilierte 32-Bit- oder 64-Bit-Version verfügbar sind, sind andere, einschließlich Office 365 ProPlus, sowohl als nativer kompilierter 32-Bit- als auch als 64-Bit-Code verfügbar. Eine der wichtigsten Entscheidungen, die Sie treffen, ist die zu bereitstellende Version. Um zusätzliche Rechenleistung und RAM auf neuen Geräten nutzen zu können, sollten Sie die 64-Bit-Version verwenden. Bevor Sie dies tun, müssen Sie jedoch ermitteln, ob es Kompatibilitätsprobleme mit Add-Ins oder Dateien geben könnte. Dazu müssen Sie möglicherweise noch einmal zu „Schritt 1: Geräte- und App-Bereitschaft“ zurückkehren.

Wenn Ihnen nichts im Wege steht, empfehlen wir Ihnen, die 64-Bit-Version aller Apps bereitzustellen, einschließlich Microsoft Office. Die nativen kompilierten 64-Bit-Apps bieten die beste Leistung und sind auf die Zukunft ausgelegt.

Es gibt viele Methoden und Modelle für die Installation von Apps unter Windows. Sehen wir uns also die Optionen an, die Ihnen für die Lieferung zur Verfügung stehen.

[Windows 10-Anwendungsmanagement](https://docs.microsoft.com/de-DE/windows/application-management/)

## <a name="msi-based-deployments"></a>MSI-basierte Bereitstellungen

Für Ihre Branchen-Apps verwenden Sie wahrscheinlich MSI-basierte Pakete oder ausführbare Dateien, und Sie installieren Apps als Teil einer Aufgabensequenz für die Betriebssystembereitstellung. In Windows 10 werden diese Pakete weiterhin verwendet.

Software-Bereitstellungstools wie System Center Configuration Manager und Microsoft Intune sind ebenfalls für die Lieferung von Apps in MSI-Paketen optimiert. Nachdem Sie Ihre Apps unter Windows 10 geprüft haben, können Sie System Center Configuration Manager (aktueller Zweig) für die App-Lieferung verwenden. Wenn Sie das Unternehmensportal in Microsoft Intune verwenden, können Sie die Auswahl der von der IT genehmigten Apps, die Ihrer Organisation zu Verfügung stehen, erweitern, sodass auch die neuesten Anwendungen enthalten sind. Benutzer können dann selbst auswählen, was sie benötigen.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>PC-Imageerstellung

Eine andere häufig verwendete Methode zum Liefern von Apps ist die PC-Imageerstellung. In diesem Fall werden Anwendungen entweder über die Aufgabensequenz oder manuell auf einem Beispiel-PC installiert. Anschließend wird ein Image des Systems mit den vorinstallierten erforderlichen Apps erfasst. Der Imageerstellungsansatz zum Erstellen und Erfassen kann beim Bereitstellen neuer PCs Zeit sparen, bedenken Sie jedoch, dass die Betriebssysteme und Apps im Image schnell veraltet sein können. Das kumulative Updatemodell in Windows 10 und Office 365 ProPlus schafft Abhilfe bei diesem Problem, kann es jedoch nicht vollständig beheben. Deshalb empfehlen wir den Thin-Image-Ansatz, bei dem die Anwendungen während der Bereitstellung außerhalb des Images installiert werden.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

Wenn Sie Office 365 ProPlus in das Image einbeziehen möchten, denken Sie daran, dass dies eine benutzerbasierte Aktivierung erfordert. Es kann nicht vom Systemadministrator bereits aktiviert werden. Verwenden Sie Office-Bereitstellungstool auf dem Gerät, von dem Sie ein Image erstellen, und überspringen Sie die Benutzeranmeldung. Benutzer können sich anmelden, ihnen kann die Aktivierung zugewiesen werden, und sie können die Vorteile anderer Funktionen nutzen, die eine Anmeldung bei der ersten Verwendung bietet.

[Erstellen einer Aufgabensequenz zum Installieren des Betriebssystems](https://docs.microsoft.com/de-DE/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

## <a name="click-to-run"></a>Klick-und-Los 

Office 365 ProPlus wird über Klick-und-Los installiert. Klick-und-Los ersetzt MSI-basierte Pakete in allen Versionen der anstehenden Office 2019-Version für Windows. Dies hat eine Reihe von Vorteilen, einschließlich eine schnellere Installation, schnellere und effizientere Aktualisierung und saubere Deinstallation.

Per Klick-und-Los gelieferte Programme werden in einer virtuellen Umgebung auf Ihrem Computer ausgeführt und existieren daher parallel mit einer anderen Anwendungen, ohne Konflikte zu verursachen. Sie nehmen auch ungefähr nur die Hälfte des Speicherplatzes ein, den sie als MSI-basiertes Paket belegen würden. Und da Klick-und-Los das Streaming von Programmen unterstützt, indem zuerst die am häufigsten verwendeten Funktionen gestreamt werden, können Benutzer Office-Anwendung bereits in nur wenigen Minuten verwenden, anstatt zuerst auf die vollständige Installation von Office warten zu müssen. Dies ist nicht nur für die erste Bereitstellung wichtig, sondern bedeutet auch, dass Updates im Hintergrund mit minimaler Auswirkung auf die Benutzer gestreamt werden können.

Wenn Sie System Center Configuration Manager verwenden, können Sie dies weiter für die allgemeine Bereitstellung von Office 365 ProPlus verwenden. System Center Configuration Manager (aktueller Zweig) hat native Unterstützung für das aktualisierte Office Customization Tool, Paketanpassung für Klick-und-Los zum Installationszeitpunkt und native Unterstützung für die Verwaltung von Software-Updates nach der Installation.

[Bereitstellungshandbuch für Office 365 ProPlus](https://docs.microsoft.com/de-DE/deployoffice/deployment-guide-for-office-365-proplus)

[Entfernen vorhandener MSI-Versionen von Office beim Upgrade auf Office 365 ProPlus](https://docs.microsoft.com/de-DE/deployoffice/upgrade-from-msi-version)

[Verwalten von Office 365 ProPlus mit Configuration Manager](https://docs.microsoft.com/de-DE/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[Zuweisen von Office 365-Apps zu Windows 10-Geräten mit Microsoft Intune](https://docs.microsoft.com/de-DE/intune/apps-add-office365)

## <a name="browser-based-apps"></a>Browserbasierte Apps

Es gibt einige Dinge zu berücksichtigen, um sicherzustellen, dass Ihre browserbasierten Anwendung weiterhin wie erwartet funktionieren. Wenn Sie über bestimmte Websites und Apps verfügen, von denen Sie wissen, dass es Kompatibilitätsprobleme mit Microsoft Edge gibt, können Sie die Enterprise Mode-Websiteliste verwenden, damit die Websites automatisch mit Internet Explorer 11 geöffnet werden.

Wenn Sie darüber hinaus wissen, dass Ihre Intranetwebsites nicht ordnungsgemäß mit Microsoft Edge funktionieren, können Sie festlegen, dass alle Intranetwebsites automatisch mit Internet Explorer 11 geöffnet werden. Dieser Vorgang verwendet eine XML-Datei, um zu bestimmen, ob IE11 für jede Website verwendet wird, wobei eine Gruppenrichtlinie zum Erzwingen der Einstellungen verwendet wird.

Bisher haben wir bekannte Bereitstellungsmethoden behandelt. Allerdings gibt es zwei neue Ansätze für die App-Bereitstellungen, die Sie möglicherweise berücksichtigen möchten.

[Der Unternehmensmodus](https://docs.microsoft.com/de-DE/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen 

Microsoft Store für Unternehmen bietet eine flexible Möglichkeit zum Finden, Erwerben, Verwalten und Verteilen von kostenlosen und kostenpflichtigen Apps für Windows 10-Geräte im großen Maßstab. Als IT-Administrator können Sie ausgewählte Microsoft Store-Apps zusammen mit Ihren eigenen Apps in einem eigenen privaten Store veröffentlichen sowie Lizenzen zuweisen und bei Bedarf wiederverwenden. Die Benutzer werden nur an diesen Store weitergeleitet und können daher nur genehmigte Apps suchen und installieren.

Store-Apps können systemeigen als UWP-Apps entwickelt sein, oder Sie können mithilfe der Desktop-Brücke vorhandene Apps für den Store packen und eine moderne Benutzeroberflächen für Windows 10 hinzufügen. Außer dem Code, mit dem Sie die Oberfläche von Windows 10 ansprechender gestalten, bleibt Ihre App unverändert und wird weiterhin im voll vertrauenswürdigen Benutzermodus ausgeführt.

## <a name="msix-containerization"></a>MSIX-Containerisierung

Eine neue Option für die Anwendungsverpackung ist MSIX. MSIX verwendet die in Windows verfügbare Containerisierungstechnologie, die die besten Aspekte von Klick-und-Los, UWP- und MSI-Paketen vereint. Durch Tools zum Migrieren von vorhandenen Installationsprogrammen, z. B. EXE, MSI, APPV und APPX, direkt in MSIX, sehen Sie, dass die MSIX-Containerisierung einen einheitlichen Pfad für die vielen Installationstechnologien bietet, die heutzutage verwendet werden. Die MSIX-Unterstützung ist in den aktuellen Versionen von Windows enthalten: Alle Geräte, die unter Windows 10 RS5 oder neueren Versionen laufen, enthalten alles, was Sie zum Installieren und Ausführen von Apps in einem MSIX-Paket benötigen. Windows 10 integriert dynamisch die MSIX-Container, die es erhält, während die Anwendung unabhängig vom Betriebssystem beibehalten werden.

Containerisierung bedeutet die saubere Deinstallation und Entfernung von Paketen, im Gegensatz zu MSI- und EXE-basierten Paketen, die möglicherweise Objekte auf dem System zurücklassen. Außerdem müssen nur standardmäßige Benutzeranmeldeinformationen zum Installieren von Anwendungen verwendet werden. Es sind keine Administratoranmeldeinformationen zum Installieren von MSIX-Containern erforderlich. MSIX-Container lassen sich außerdem effizienter aktualisieren. Wenn ein Update veröffentlicht wird, werden durch die Verwendung von Unterschieden auf Blockebene nur neue Netto-Binärdaten angewendet, sodass die Nutzlast des Updates verringert wird und so schnellere Bereitstellungen möglich sind, die weniger Netzwerkbandbreite verbrauchen.

Weitere Informationen über MSIX finden Sie auf der Website der [MSIX Tech Community](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)

## <a name="next-step"></a>Nächster Schritt

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[Schritt 4: Benutzerdateien und Einstellungen](https://aka.ms/mdd4)

## <a name="previous-step"></a>Vorheriger Schritt

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Schritt 2: Verzeichnis- und Netzwerkbereitschaft](https://aka.ms/mdd2) 