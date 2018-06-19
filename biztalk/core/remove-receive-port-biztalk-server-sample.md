---
title: Quitar (ejemplo de BizTalk Server) del puerto de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d15442da8afd4829245b742bdd45af8f7d1f832
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971778"
---
# <a name="remove-receive-port-biztalk-server-sample"></a>Quitar (ejemplo de BizTalk Server) del puerto de recepción
El ejemplo para quitar puerto de recepción demuestra cómo quitar uno o varios puertos de recepción.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:  
  
-   A partir de un nombre de puerto de recepción, consultar una lista de puertos de recepción coincidentes.  
  
    > [!NOTE]
    >  Como norma general, sólo habrá un puerto de recepción que coincide con un nombre determinado.  
  
-   Quitar estos puertos de envío.  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Estos ejemplos se encuentran en la siguiente ubicación de SDK:  
  
 \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Remove Port\ de recepción  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|En la carpeta \VBScript:<br /><br /> RemoveReceivePort.vbs|El archivo VBScript que toma un parámetro que especifica uno o más puertos de recepción que se van a quitar.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 El ejemplo para quitar puerto de recepción consta de un archivo único VBScript que no necesita generar o inicializar.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Remove Port\VBScript\ de recepción  
  
2.  Ejecute el archivo RemoveReceivePort.vbs mediante el programa cscript, de modo que se pase el siguiente argumento de línea de comandos:  
  
     **\<** ***ReceivePortName* \>** . El nombre de los puertos de recepción que se van a quitar. Si el nombre del puerto de recepción contiene espacios, enciérrelo entre comillas.  
  
     Por ejemplo:  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a>Comentarios  
 Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.  
  
 El archivo de secuencias de comandos RemoveReceivePort.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza. Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).  
  
## <a name="see-also"></a>Vea también  
 [Admin\WMI (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)