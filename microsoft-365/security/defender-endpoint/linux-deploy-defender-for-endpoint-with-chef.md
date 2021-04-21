---
title: Bereitstellen von Defender for Endpoint unter Linux mit Chef
description: Erfahren Sie, wie Sie Defender for Endpoint unter Linux mit Chef bereitstellen
keywords: microsoft, defender, atp, linux, scans, antivirus, microsoft defender for endpoint (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa699aae24b1e6383f5a2afbe7fce31e0f53805c
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903928"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Microsoft Defender für Endpunkt unter Linux mit Chef bereitstellen

Bevor Sie beginnen:

- Installieren Sie entpacken, wenn es noch nicht installiert ist. Die Chef-Komponenten sind bereits installiert, und es ist ein Chefrepository vorhanden (chef generate repo), um das Rezeptbuch zu speichern, das für die Bereitstellung in Defender for Endpoint auf von Chef verwalteten <reponame> Linux-Servern verwendet wird.

Sie können ein neues Rezeptbuch in Ihrem vorhandenen Repository erstellen, indem Sie den folgenden Befehl im Ordner "Rezeptbücher" ausführen, der sich im Chefrepository befindet:</br>
`chef generate cookbook mdatp`

Mit diesem Befehl wird eine neue Ordnerstruktur für das neue Rezeptbuch mdatp erstellt.  Sie können auch ein vorhandenes Rezeptbuch verwenden, wenn Sie bereits über ein Rezept verfügen, zu dem Sie die MDE-Bereitstellung hinzufügen möchten.
Erstellen Sie nach dem Erstellen des Kochbuchs einen Ordner mit Dateien innerhalb des Gerade erstellten Kochbuchordners:

`mkdir mdatp/files`

Übertragen Sie die Zip-Datei für das Linux Server-Onboarding, die aus dem Microsoft Defender Security Center-Portal heruntergeladen werden kann, in diesen neuen Dateiordner.

Navigieren Sie auf der Chef Workstation zum Ordner mdatp/recipes. Dieser Ordner wird erstellt, wenn das Rezeptbuch generiert wurde. Verwenden Sie ihren bevorzugten Texteditor (z. B. vi oder nano), um die folgenden Anweisungen am Ende der Datei "default.rb" hinzuzufügen:
-   include_recipe '::onboard_mdatp'
- include_recipe '::install_mdatp'

Speichern und schließen Sie dann die Datei default.rb.
Erstellen Sie als Nächstes eine neue Rezeptdatei namens install_mdatp.rb im Ordner "Rezept", und fügen Sie der Datei diesen Text hinzu:

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

Sie müssen version number, distribution und repo name so ändern, dass sie der Version entsprechen, in der Sie bereitstellen, und dem Kanal, den Sie bereitstellen möchten.
Als Nächstes sollten Sie eine onboard_mdatp.rb-Datei im Ordner mdatp/recipies erstellen.  Fügen Sie der Datei den folgenden Text hinzu:

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

Achten Sie darauf, den Pfadnamen auf den Speicherort der Onboardingdatei zu aktualisieren.
Führen Sie einfach aus, um die Bereitstellung auf der Chef-Arbeitsstation zu ``sudo chef-client -z -o mdatp`` testen.
Nach der Bereitstellung sollten Sie das Erstellen und Bereitstellen einer Konfigurationsdatei auf den Servern basierend auf  [Set preferences for Microsoft Defender for Endpoint unter Linux in](/linux-preferences.md)Betracht ziehen.  
Nachdem Sie die Konfigurationsdatei erstellt und getestet haben, können Sie sie in den Ordner cookbook/mdatp/files platzieren, in dem Sie auch das Onboardingpaket platziert haben.  Anschließend können Sie eine datei settings_mdatp.rb im Ordner mdatp/recipies erstellen und diesen Text hinzufügen:

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

Wenn Sie diesen Schritt als Teil des Rezepts hinzufügen möchten, fügen Sie einfach include_recipe ":: settings_mdatp" zur Datei default.rb im Rezeptordner hinzu.
Sie können auch crontab verwenden, um automatische Updates zu planen Planen eines Updates von [Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).

Deinstallieren des MDATP-Kochbuchs:

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

