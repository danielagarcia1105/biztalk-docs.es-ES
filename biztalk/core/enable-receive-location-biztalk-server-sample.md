---
title: "Habilitar (ejemplo de BizTalk Server) de la ubicación de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99923c3029b72dae660bee4b4089336e90e2e4e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enable-receive-location-biztalk-server-sample"></a>Habilitar recepción ubicación (ejemplo de BizTalk Server)
El ejemplo para habilitar ubicación de recepción muestra cómo se habilita una ubicación de recepción y como se establece, de forma opcional, la dirección URL de transporte de entrada para la ubicación de recepción.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 La secuencia de comandos de Microsoft Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:  
  
-   A partir de un nombre de puerto de recepción y una ubicación de recepción, consultar una lista de ubicaciones de recepción coincidentes.  
  
-   Establecer la dirección URL de transporte de entrada para una ubicación de recepción (con respecto a la ruta de instalación).  
  
-   Habilitar una ubicación de recepción.  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de ruta de acceso*> \Admin\WMI\Enable recibir Location\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|En la carpeta \VBScript:<br /><br /> EnableRecLoc.vbs|El archivo VBScript que toma parámetros que especifican la ubicación de recepción que se va a habilitar y, de forma opcional, un valor nuevo para la dirección URL de transporte de entrada asociada a la ubicación de recepción.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 El ejemplo para habilitar ubicación de recepción consta de un archivo único VBScript que no necesita generar o inicializar.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \Admin\WMI\Enable recibir Location\VBScript\  
  
2.  Ejecute el archivo EnableRecLoc.vbs mediante el programa cscript, de modo que se pasen los siguientes argumentos de línea de comandos, de los cuales el tercero es opcional:  
  
    -   **\<**   
         ***ReceivePortName* >.** El nombre del puerto de recepción que contiene la ubicación de recepción que se va a habilitar. Si el nombre del puerto de recepción contiene espacios, enciérrelo entre comillas.  
  
    -   **\<**   
         ***ReceiveLocationName* >.** El nombre de la ubicación de recepción en el puerto de recepción especificado que se va a habilitar. Si el nombre de la ubicación de recepción contiene espacios, enciérrelo entre comillas.  
  
    -   **\<**   
         ***InboundTransportURI* >.** Un URI del adaptador de recepción, relativo a la ubicación de instalación del producto, que se puede cambiar mediante la especificación de este argumento. Si el URI del adaptador de entrada contiene espacios, enciérrelo entre comillas.  
  
         Por ejemplo:  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         -OR-  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a>Comentarios  
 Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.  
  
 El archivo de secuencias de comandos EnableRecLoc.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza.  
  
 Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).  
  
## <a name="see-also"></a>Vea también  
 [WMI de administración (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)