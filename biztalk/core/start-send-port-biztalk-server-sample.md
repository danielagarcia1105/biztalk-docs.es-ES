---
title: "Iniciar puerto de envío (ejemplo de BizTalk Server) | Documentos de Microsoft"
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
- send ports, starting
ms.assetid: 84e54c9e-e9e8-4bb2-a191-20c29e127dae
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfb9db99f06e05877939631e4306be396c47ebda
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="start-send-port-biztalk-server-sample"></a>Iniciar puerto de envío (ejemplo de BizTalk Server)
El ejemplo de cómo iniciar un puerto de envío muestra cómo iniciar un puerto de envío y, opcionalmente, definir la dirección de transporte principal al utilizar el adaptador de archivo.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:  
  
-   A partir de un nombre de puerto de envío, consultar una lista de puertos de envío coincidentes.  
  
    > [!NOTE]
    >  Como norma general, sólo habrá un puerto de envío que coincide con un nombre determinado.  
  
-   Establecer la dirección de transporte principal para esos puertos de envío (con respecto a la ruta de instalación).  
  
-   Inicia esos puertos de envío.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Los archivos de ejemplo se encuentran en la siguiente ubicación de SDK:  
  
 \<*Ejemplos de ruta de acceso*> \Admin\WMI\Start enviar Port\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|En la carpeta \VBScript:<br /><br /> StartSendPort.vbs|El archivo VBScript que toma parámetros que especifican el puerto de envío que se va a utilizar y, de forma opcional, un valor nuevo para la dirección de transporte principal asociada a ese puerto.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 El ejemplo Iniciar puerto de envío consta de un archivo único VBScript que no necesita generar o inicializar.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \Admin\WMI\Start enviar Port\VBScript\  
  
2.  Ejecute el archivo StartSendPort.vbs mediante el programa cscript, de modo que se pasen los siguientes argumentos de línea de comandos, de los cuales el segundo es opcional:  
  
    -   **\<**   
         ***SendPortName* >.** El nombre del puerto de envío que se van a iniciar. Si el nombre del puerto de envío contiene espacios, enciérrelo entre comillas.  
  
    -   **\<**   
         ***PrimaryTransportAddress* >.** La dirección de transporte principal, relativa a la ubicación de instalación del producto, que puede cambiar mediante la especificación de este argumento. Si la dirección del adaptador principal contiene espacios, enciérrela entre comillas.  
  
         Por ejemplo:  
  
        ```  
        cscript StartSendPort.vbs "My Business Send Port" SDK\Samples\HelloWorld\Out\%MessageID%.xml  
        ```  
  
## <a name="comments"></a>Comentarios  
 Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.  
  
 El archivo de secuencias de comandos StartSendPort.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza. Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).  
  
## <a name="see-also"></a>Vea también  
 [WMI de administración (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)