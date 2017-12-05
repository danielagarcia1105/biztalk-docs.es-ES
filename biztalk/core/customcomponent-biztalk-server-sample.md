---
title: CustomComponent (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- messages, streamed
- pipeline components [custom], configuring
ms.assetid: ed0da9f5-8cc7-4528-be8c-35b80744fd38
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fd774848dec1ae54541e749a0cc551bf7c42d49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="customcomponent-biztalk-server-sample"></a>CustomComponent (ejemplo de BizTalk Server)
El ejemplo CustomComponent muestra cómo crear y utilizar un componente de canalización personalizado que modifique un mensaje transmitido. También muestra la configuración de un componente de canalización personalizado en el Diseñador de canalizaciones.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo implementa un componente de canalización personalizado que puede agregar cadenas como prefijo o como anexo al mensaje de entrada. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]procesa el mensaje en el modo, lo que significa que nunca se carga el mensaje completo en la memoria de streaming. El componente de canalización personalizado se demuestra con la siguiente secuencia de pasos:  
  
1.  BizTalk recupera un mensaje de texto de un archivo en una carpeta determinada.  
  
2.  El mensaje de texto se envía a través de una canalización de recepción que contiene el componente personalizado FixMsg. Este componente se configura para insertar una cadena al comienzo del mensaje.  
  
3.  El mensaje de texto que se obtiene como resultado se envía a través de una canalización de envío con el componente personalizado FixMsg. Este componente se configura para agregar una cadena al final del mensaje.  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escribe el mensaje de texto que se obtiene como resultado en un archivo en una carpeta determinada.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*\>\Pipelines\CustomComponent\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC). Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|Input.txt|Archivo de entrada de ejemplo.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|En la carpeta \FixMsg:<br /><br /> AssemblyInfo.cs, FixMsg.csproj, FixMsg.sln|Archivos de información de proyecto, de solución y de ensamblado para la parte del componente de canalización personalizado de este ejemplo.|  
|En la carpeta \FixMsg:<br /><br /> FixMsg.cs|Implementa las interfaces del componente de canalización.|  
|En la carpeta \FixMsg:<br /><br /> FixMsgStream.cs|Implementa un contenedor para la **System.IO.Stream** (clase), habilitar el procesamiento de flujo de datos.|  
|En la carpeta \FixMsg:<br /><br /> FixMsgDescription.cs|Proporciona métodos para obtener acceso y representar recursos de interfaz de usuario de componentes en el Diseñador de canalizaciones.|  
|En la carpeta \FixMsg:<br /><br /> FixMsg.resx|Contiene descripciones de propiedad, un icono y mensajes de error.|  
|En la carpeta \PipelineComponentSample:<br /><br /> PipelineComponentSample.btproj, PipelineComponentSample.sln|Archivos de proyecto y de solución para la parte de proyecto de BizTalk de este ejemplo.|  
|En la carpeta \PipelineComponentSample:<br /><br /> PipelineComponentSampleBinding.xml|Se utiliza para la instalación automatizada, como el enlace de puerto.|  
|En la carpeta \PipelineComponentSample:<br /><br /> FixMsgReceivePipeline.btp, FixMsgSendPipeline.btp|Canalizaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contienen el componente de canalización personalizado FixMsg, para las canalizaciones de recepción y de envío, respectivamente.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-customcomponent-sample"></a>Para crear e inicializar el ejemplo CustomComponent  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Pipelines\CustomComponent  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta:  
  
         \<*Ejemplos de ruta de acceso*\>\Pipelines\CustomComponent  
  
    -   Compila e implementa los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
    -   Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  
  
        > [!NOTE]
        >  Este ejemplo muestra las siguientes advertencias al crear y enlazar los puertos:  
        >   
        >  `Warning: Receive handler not specified for receive location "PCReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "CustomComponent"; updating with first available host.`  
        >   
        >  Puede omitir estas advertencias de forma segura. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  
  
    -   Habilita la ubicación de recepción e inicia el puerto de envío.  
  
> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
> [!NOTE]
>  Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice que este par de claves se usa para firmar los ensamblados resultantes.  
  
> [!NOTE]
>  Para deshacer los cambios realizados por Setup.bat, debe detener y reiniciar, en primer lugar, la instancia de host de la consola MMC de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. A continuación, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-customcomponent-sample"></a>Para ejecutar el ejemplo CustomComponent  
  
1.  Pegue una copia del archivo de texto Input.txt en la carpeta In.  
  
2.  Observe el archivo de texto que se ha creado en la carpeta Out. Este archivo incluye el contenido del archivo Input.txt con texto adicional insertado al principio (por la canalización de recepción) y al final (por la canalización de envío). El formato del nombre de este archivo es \< *MessageID*\>.xml, donde  *\<MessageID\>*  es el GUID generado para identificar de forma única el mensaje .  
  
## <a name="comments"></a>Comentarios  
 Puede ver las canalizaciones preconfiguradas en el Diseñador de canalizaciones mediante los pasos que se indican a continuación:  
  
1.  En el Explorador de soluciones, haga doble clic en ReceivePipeline.btp para abrir la canalización de recepción en el Diseñador de canalizaciones. Observe que el componente FixMsg se encuentre en el **validar** fase de la canalización de recepción.  
  
2.  Haga clic en el componente FixMsg en la **validar** fase en la superficie de diseño. En la ventana Propiedades, puede ver las propiedades de configuración del componente de canalización. Observe que la **PrependData** propiedad está establecida en **cadenas de canalización de recepción de datos que se va a anteponer en**.  
  
3.  En el Explorador de soluciones, haga doble clic en SendPipeline.btp para abrir la canalización de envío en el Diseñador de canalizaciones. Observe que el componente FixMsg se encuentre en el **preensamblar** fase de la canalización de envío.  
  
4.  Haga clic en el componente FixMsg en **preensamblar** fase en la superficie de diseño. Tenga en cuenta que la **AppendData** propiedad está establecida en **cadenas de canalización de envío de datos que se va a anexar en**.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones (carpeta de ejemplos de BizTalk Server)](../core/pipelines-biztalk-server-samples-folder.md)