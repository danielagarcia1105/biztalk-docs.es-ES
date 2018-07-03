---
title: 'Escenario: Implementar una aplicación nueva | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, applications
- applications, deploying
- deploying [applications], examples
- applications, examples
- examples, deploying
ms.assetid: 6d34a626-9fd4-4c33-a067-b66333eec01f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c706e990154f43f264e3c529a8ee7ce59efcc166
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986237"
---
# <a name="scenario-deploying-a-new-application"></a>Escenario: Implementar una aplicación nueva
En este tema se describe la implementación de una aplicación en un entorno nuevo en el que no se ha implementado antes; por ejemplo, la implementación de una aplicación que se ha configurado en un entorno de ensayo en un entorno de producción.  
  
 Como se describe en [el proceso de implementación de aplicación](../core/the-application-deployment-process.md), cuando desea mover una aplicación de un entorno a otro, exporte la aplicación a un archivo MSI. Después importa el archivo .msi al grupo de BizTalk del entorno nuevo. También instala la aplicación en los equipos de dicho grupo que ejecutarán la aplicación. Antes de que pueda comenzar a funcionar, debe instalar la aplicación en cada equipo que vaya a ejecutarla y también iniciar la aplicación.  
  
 En el diagrama siguiente, la aplicación 1 se importa desde un archivo .msi en el grupo B de BizTalk.  
  
 ![Implementar una aplicación de BizTalk](../core/media/deployapplication.gif "DeployApplication")  
  
 De este modo, se importan artefactos en las distintas bases de datos de BizTalk Server como se indica a continuación:  
  
- El ensamblado de BizTalk, el ensamblado .NET, los enlaces, el archivo de enlace, la plantilla de BAM, el componente COM, el certificado y el archivo de texto se agregan todos ellos a la base de datos de administración de BizTalk.  
  
- La directiva y el vocabulario se agregan a la base de datos del motor de reglas.  
  
- La plantilla de BAM y el archivo de definición de BAM se agregan a la base de datos de importación principal de BAM.  
  
  Cada uno de estos artefactos también se asocia a la aplicación 1 en la base de datos administración de BizTalk.  
  
  La aplicación también se instala en un equipo local desde el archivo .msi. De este modo se instalan distintos artefactos incluidos en el archivo .msi, como se indica a continuación:  
  
- El directorio virtual, denominado VirtualDirectory, se crea en la metabase de Internet Information Services (IIS).  
  
- El certificado se agrega al almacén de certificados local.  
  
- El archivo de texto y el componente COM se copian en el sistema de archivos local.  
  
- El ensamblado de BizTalk y el ensamblado .NET se agregan a la caché de ensamblados global (GAC) si se ha seleccionado esta opción de implementación para ellos.  
  
- El ensamblado .NET y el componente COM se agregan al Registro de Windows si se ha seleccionado esta opción de implementación para ellos.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones y escenarios de administración](../core/application-deployment-and-management-scenarios.md)   
 [Implementación de aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)