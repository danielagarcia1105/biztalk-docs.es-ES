---
title: "Quitar puerto de envío (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, deleting
- deleting, send ports
ms.assetid: e6643525-fa9f-4d39-880f-314749a68471
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8b82af2be42342d51429e42d1952816ee0dd07a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="remove-send-port-biztalk-server-sample"></a>Quitar puerto de envío (ejemplo de BizTalk Server)
El ejemplo para quitar puerto de envío muestra cómo dar de baja y quitar uno o varios puertos de envío.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:  
  
-   A partir de un nombre de puerto de envío, consultar una lista de puertos de envío coincidentes.  
  
    > [!NOTE]
    >  Como norma general, sólo habrá un puerto de envío que coincide con un nombre determinado.  
  
-   Dar de baja los puertos de envío.  
  
-   Eliminar los puertos de envío.  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Remove enviar Port\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|En la carpeta \VBScript:<br /><br /> RemoveSendPort.vbs|El archivo VBScript que toma un parámetro que especifica uno o más puertos de envío que se van a dar de baja y quitar.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 El ejemplo para quitar puerto de envío consta de un archivo único VBScript que no necesita generar o inicializar.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-remove-send-port-sample"></a>Para ejecutar el ejemplo para quitar puerto de envío  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Remove Port\VBScript\ de recepción  
  
2.  Ejecute el archivo RemoveSendPort.vbs mediante el programa cscript, de modo que se pase el siguiente argumento de línea de comandos:  
  
     **\<** ***SendPortName* \>.** El nombre de los puertos de envío que se van a quitar. Si el nombre del puerto de envío contiene espacios, enciérrelo entre comillas.  
  
     Por ejemplo:  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a>Comentarios  
 Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.  
  
 El archivo de secuencias de comandos RemoveSendPort.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza. Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).  
  
## <a name="see-also"></a>Vea también  
 [Admin\WMI (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)