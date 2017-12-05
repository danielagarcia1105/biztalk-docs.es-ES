---
title: "Detener la orquestación (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, stopping
ms.assetid: 83be44e9-819d-4ac5-8b75-84c23e6b5ba2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0c88bdeb85b8ad493b85d2569061c35bd516e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="stop-orchestration-biztalk-server-sample"></a>Detener la orquestación (ejemplo de BizTalk Server)
El ejemplo Detener una orquestación muestra cómo detener una orquestación de BizTalk Server y, de forma opcional, darla de baja.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:  
  
-   A partir de un nombre de orquestación y de ensamblado, consultar una orquestación de BizTalk Server implementada.  
  
-   Detener esa orquestación.  
  
-   Dar de baja esa orquestación (opcional).  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Los archivos de ejemplo se encuentran en la siguiente ubicación de SDK:  
  
 \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Stop Orchestration\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|En la carpeta \VBScript:<br /><br /> StopOrch.vbs|El archivo VBScript que toma parámetros para especificar una orquestación que se va a detener y, de forma opcional, que se va a dar de baja.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 El ejemplo Detener orquestación consta de un archivo único VBScript que no necesita generar o inicializar.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Stop Orchestration\VBScript\  
  
2.  Ejecute el archivo StopOrch.vbs mediante el programa cscript, de modo que se pasen los siguientes argumentos de línea de comandos, de los cuales el tercero es opcional:  
  
    -   **\<** ***OrchestrationName* \>.** El nombre de la orquestación de BizTalk Server que se va a detener y, de forma opcional, a dar de baja.  
  
    -   **\<** ***AssemblyName* \>.** El nombre del ensamblado de BizTalk en el que se ha especificado la orquestación. Si el nombre del ensamblado contiene espacios, enciérrelo entre comillas.  
  
    -   **Dar de baja.** Una cadena opcional y literal que se utiliza para indicar que la orquestación especificada debe darse de baja además de detenerse.  
  
         Por ejemplo:  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         -OR-  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a>Comentarios  
 Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante el uso de secuencias de comandos que tienen acceso al modelo de objetos WMI de Windows.  
  
 El archivo de secuencias de comandos StopOrch.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza. Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).  
  
## <a name="see-also"></a>Vea también  
 [Admin\WMI (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)