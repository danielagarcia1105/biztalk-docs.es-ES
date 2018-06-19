---
title: Importar o exportar la configuración de BizTalk mediante BTSTask | Documentos de Microsoft
description: Usar comandos ImportSettings o ExportSettings BTSTask para mover la configuración de un entorno a otro en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3fdd8c9-3534-4c11-8acc-6cb6f5bf0989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99aecaea767133fc5f3cb77d38dc174b09733674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255148"
---
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a>Utilizar BTSTask para importar o exportar la configuración de BizTalk

## <a name="overview"></a>Información general
Mediante la utilidad de línea de comandos BTSTask, se puede exportar la configuración de un entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e importarla en otro entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], lo que reduce el tiempo general necesario para implementar la solución. Esto es especialmente práctico en aquellas situaciones en las que los administradores intentan mejorar el rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de ensayo y, una vez obtenidos los resultados deseados, pueden importar la configuración en un entorno de producción. 

En este tema se enumera los pasos para importar o exportar la configuración de BizTalk Server de un entorno a otro mediante **BTSTask.exe**.  


## <a name="import-biztalk-settings"></a>Importar configuración de BizTalk 
> [!IMPORTANT]
>  Para importar la configuración de BizTalk desde un entorno concreto, debe haber exportado y guardado esa configuración a un archivo XML. Para obtener más información acerca de cómo exportar la configuración, consulte [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) o **exportar la configuración de BizTalk usar BTSTask** (en este tema).  
  
 Al importar el archivo XML, se puede replicar la configuración de BizTalk Server necesaria en el equipo de destino. Mediante el **BTSTask.exe**, puede importar la configuración de grupo, Host e instancia de Host y asignar las propiedades de uno a otro. Las hipótesis necesarias para importar la configuración son:  
  
-   La configuración de BizTalk Server se puede importar a través de topologías similares.  
  
-   Debería poder asignar las instancias de host y el host de origen a sus equivalentes en el destino.  
  
-   El entorno de destino tiene un hardware similar (si no idéntico) al entorno de origen. Esto es esencial, ya que algunas de las configuraciones dependen del hardware subyacente.  
  
### <a name="importsettings-command"></a>Comando ImportSettings 
 Puede usar el **ImportSettings** comandos de BTSTask para importar la configuración de BizTalk Server desde el entorno de origen al entorno de destino. Vea [comando ImportSettings](../core/importsettings-command.md) para obtener detalles específicos.  
  
 Puede definir la asignación de un host de origen a un host de destino o de una instancia de host de origen a una instancia de host de destino de este modo:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SettingsMap>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerApplication">  
  <DestinationHosts>BizTalkServerApplication</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerIsolatedHost">  
  <DestinationHosts>BizTalkServerIsolatedHost</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host1">  
  <DestinationHosts>Host2</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host2">  
  <DestinationHosts>Host1;Host3;Host4;Host5</DestinationHosts>   
  </SourceHost>  
  </HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostInstanceMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="BizTalkServerApplication:COMPUTER_NAME1">  
  <DestinationHostInstances>BizTalkServerApplication:COMPUTER_NAME2</DestinationHostInstances>   
  </SourceHostInstance>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="Host1:COMPUTER_NAME1">  
  <DestinationHostInstances>Host2:COMPUTER_NAME2;Host3:COMPUTER_NAME3;Host4:COMPUTER_NAME4;Host5:COMPUTER_NAME5</DestinationHostInstances>   
  </SourceHostInstance>  
  </HostInstanceMappings>  
  </SettingsMap>  
  
```  
  
 En un archivo de asignación, especifique una instancia de host como 'Hostname: MachineName'. Por ejemplo: "Host1:Server1" hace referencia a la instancia de host 'Host1' qué se está ejecutando (o presente) en el equipo 'Server1'.  
  
 Para especificar el origen de 1: n las asignaciones de destino, utilice una lista separada por punto y coma. Por ejemplo:  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 Solo se pueden asignar los host-instancias para los que también se haya creado la asignación de host correspondiente. Si 'SourceHost1' se ha asignado a 'DestinationHost1' en las asignaciones de host, las instancias (si existen) de 'DestinationHost1' solo se pueden asignar a las instancias (si existen) de 'SourceHost1'. La interfaz de usuario del Asistente para importar se encarga de esta restricción. Debe escribirlo explícitamente en el archivo de asignación.  


## <a name="export-biztalk-settings"></a>Exportar la configuración de BizTalk  

Hay un par de formas para exportar la configuración de BizTalk: 

1. Use la **ExportSettings** comandos de BTSTask para exportar la configuración de BizTalk Server al entorno de origen a un archivo XML. Vea [comando ExportSettings](../core/exportsettings-command.md) para obtener más detalles.  

2.  Utilice el panel de configuración de administración de BizTalk Server. Vea [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) para conocer los pasos.

 
> [!TIP]
>  Para obtener información sobre cómo se aplica la configuración de BizTalk Server en un archivo XML para el entorno de destino, vea [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md). 
  
## <a name="see-also"></a>Vea también  
 [Automatizar el servidor BizTalk Server ajuste del rendimiento](../core/automating-biztalk-server-performance-tuning.md)