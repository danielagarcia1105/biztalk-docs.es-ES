---
title: Archivo BTSNTSvc.exe.config | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2bb89a7-4fff-4ccf-a0a7-20ca610f2ddf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7fae2fc49487597380e6c5d04a946b1078daeeb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004821"
---
# <a name="btsntsvcexeconfig-file"></a>BTSNTSvc.exe.config (archivo)
Las propiedades de deshidratación y sus valores predeterminados se pueden configurar en [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] o como XML en el archivo de configuración de BizTalk (BTSNTSvc.exe.config o BTSNTSvc64.exe.config). Los valores del archivo de configuración de BizTalk se aplican antes. A continuación, se aplica la configuración de [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]. Las propiedades de deshidratación se leen cuando se inician todas las instancias de host que contienen una orquestación.  
  
 Este tema se centra en el archivo de configuración de BizTalk (BTSNTSvc.exe.config o BTSNTSvc64.exe.config). Muchas propiedades de deshidratación no se enumeran. Sin embargo, estas propiedades se aplican con sus valores predeterminados aunque no se especifiquen explícitamente en el archivo de configuración.  
  
 Para cambiar los valores predeterminados, debe agregarlos de forma explícita al archivo de configuración. Para obtener información acerca de cómo cambiar el comportamiento de deshidratación predeterminado, consulte [cómo modificar configuración de la limitación de orquestación](../core/how-to-modify-orchestration-throttling-settings.md). Para obtener información acerca de la limitación de memoria de orquestación, consulte [cómo modificar configuración de limitación de orquestación memoria](../core/how-to-modify-orchestration-memory-throttling-settings.md).  
  
 A continuación figura el contenido del archivo BTSNTSvc.exe.config. Este archivo siempre se encuentra en el mismo directorio que el archivo BTSNTSvc.exe, que normalmente es C:\Program Files\Microsoft BizTalk Server.  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section name="xlangs" type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
       <xlangs>  
              <Configuration>  
                     <Dehydration MaxThreshold="1800" MinThreshold="1" ConstantThreshold="-1">  
                            <VirtualMemoryThrottlingCriteria OptimalUsage="900" MaximalUsage="1300" IsActive="true" />  
                            <PrivateMemoryThrottlingCriteria OptimalUsage="50" MaximalUsage="350" IsActive="true" />  
                            <PhysicalMemoryThrottlingCriteria OptimalUsage="50" MaximalUsage="350" IsActive="false" />  
                     </Dehydration>  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Uso del panel de configuración para ajustar el rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)