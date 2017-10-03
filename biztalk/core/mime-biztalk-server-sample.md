---
title: MIME (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines, MIME/SMIME Encoder [pipeline component]
- examples, send pipelines
- MIME/SMIME Encoder [pipeline component], send pipelines
- MIME/SMIME Encoder [pipeline component], examples
- examples, MIME/SMIME Encoder [pipeline component]
ms.assetid: f76c720d-3798-4f15-a5f9-885ddf421d57
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e948aeca31d3eb9908d6933f5ac375bce206761
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mime-biztalk-server-sample"></a>MIME (ejemplo de BizTalk Server)
El ejemplo MIME muestra cómo se realiza la codificación MIME en una canalización de envío.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo configura la carpeta MIMEIn como ubicación de recepción. Cuando se coloca un archivo, como el archivo de ejemplo ImageInput.gif, en esta carpeta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa el mensaje de este archivo mediante los siguientes pasos:  
  
1.  Recuperar el archivo de mensajes de la carpeta de la ubicación de recepción MIMEIn.  
  
2.  En la canalización de recepción, pasar el mensaje sin ningún cambio.  
  
3.  En la base de datos del cuadro de mensajes, enrutar el mensaje a la canalización de envío.  
  
4.  En la canalización de envío, realizar la codificación MIME y colocar el archivo en la carpeta MIMEOut del adaptador de envío.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*> \Pipelines\MIME\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC). Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|ImageInput.GIF|Archivo de entrada de ejemplo.|  
|SampleMimeEncoding.btproj<br /><br /> SampleMimeEncoding.sln|Archivos de proyectos y de soluciones de este ejemplo.|  
|SampleMimeEncodingBinding.xml|Se utiliza para la instalación automatizada, como el enlace de puerto.|  
|SendMimePipeline.btp|Archivo de canalización de envío de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con el componente de codificador de MIME.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Utilice el siguiente procedimiento para crear e inicializar el ejemplo MIME.  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \Pipelines\MIME  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea las carpetas de entrada (MIMEIn) y de salida (MIMEOut) de este ejemplo en la carpeta:  
  
         \<*Ejemplos de ruta de acceso*> \Pipelines\MIME  
  
    -   Compila el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
    -   Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  
  
        > [!NOTE]
        >  Este ejemplo muestra la siguiente advertencia al crear y enlazar los puertos:  
  
        > [!NOTE]
        >  `Warning: Receive handler not specified for receive location "MIMEReceiveLocation"; updating with first receive handler with matching transport type.`  
  
        > [!NOTE]
        >  Puede omitir estas advertencias de forma segura. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  
  
    -   Habilita la ubicación de recepción e inicia el puerto de envío.  
  
> [!NOTE]
>  Si ejecuta este ejemplo desde una ubicación distinta de donde está instalado, primero debe agregar una referencia a la **Microsoft.BizTalk.Pipeline.Components** ensamblado.  
  
> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
> [!NOTE]
>  Si elige abrir y crear el proyecto de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar el ensamblado resultante. Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo MIME.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Guarde una copia del archivo ImageInput.gif en la carpeta MIMEIn.  
  
2.  Observe el archivo de texto creado en la carpeta MIMEOut. El nombre de este archivo de texto se basa en el GUID de Id. del mensaje. Este archivo incluye el contenido del archivo de entrada ImageInput.gif codificado con MIME.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones (carpeta de ejemplos de BizTalk Server)](../core/pipelines-biztalk-server-samples-folder.md)