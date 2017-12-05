---
title: "VisualStudioHostRestart (ejemplo de implementación de aplicaciones) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0b82627-1552-479d-a083-cdc9fe4843c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d98a3a5e497a4476de897c8008f3a9976812209a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a>VisualStudioHostRestart (ejemplo de implementación de aplicaciones)
En este tema se explica como utilizar la secuencia de comandos de ejemplo VisualStudioHostRestart para reiniciar una instancia de host que se ejecuta en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo local. Puede utilizar esta secuencia de comandos a la hora de volver a implementar ensamblados en Visual Studio, de manera que el tiempo de ejecución de BizTalk Server adopta los cambios de forma inmediata. Como alternativa, puede usar la opción para reiniciar instancias de host que puede establecer en las propiedades de implementación del proyecto. Para obtener más información, consulte [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Esta secuencia de comandos de ejemplo lleva a cabo las siguientes acciones en este orden:  
  
1.  Detener todas las instancias de host en curso en el equipo local.  
  
2.  Iniciar todas las instancias de host en curso en el equipo local.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] carpeta de instalación, como se indica a continuación:  *\<ruta de ejemplos\>*\Application Deployment\VisualStudioHostRestart.  
  
 En el ejemplo se incluye el archivo siguiente:  
  
-   RestartBizTalkHostInstances.vbs  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Utilice los procedimientos que se exponen a continuación para ejecutar el ejemplo.  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
-   Ejecute el archivo RestartBizTalkHostInstances.vbs.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [Implementación de aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)