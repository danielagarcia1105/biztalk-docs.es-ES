---
title: HelloWorld (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, messages
ms.assetid: 4416029a-ca76-45a4-b66c-b44cb71ded58
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77c9a45e6314a4fc36fca8604677d7bd4b69098
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966613"
---
# <a name="helloworld-biztalk-server-sample"></a>HelloWorld (ejemplo de BizTalk Server)
En el ejemplo HelloWorld se muestra cómo utilizar orquestaciones de BizTalk para convertir un mensaje XML (un pedido), a un tipo de mensaje (una factura) relacionado pero distinto.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo se configura el **en** carpeta como ubicación de recepción. Cuando coloca un archivo, por ejemplo, el archivo de ejemplo **SamplePOInput.xml**, en esta carpeta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa el mensaje mediante los pasos siguientes:  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera el de mensajes de pedido XML desde la carpeta de ubicación de recepción.  
  
2. La orquestación utiliza el archivo de asignación para crear una factura XML del pedido XML.  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] coloca el mensaje de factura XML resultante en el adaptador de envío **Out** carpeta.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 En un contexto de intercambio de mensajes entre empresas, a menudo es necesario convertir mensajes entrantes recibidos de los socios comerciales a un formato que puedan reconocer las aplicaciones internas. Este ejemplo utiliza un **recepción** forma, un **transformar** forma y un **enviar** forma para lograr este resultado. El **transformar** forma desempeña una función importante en este ejemplo porque es donde se produce la conversión de formato de mensaje. Arrastrar un **transformar** en la orquestación y dar forma a configurar el mensaje de origen, el nombre de mapa y el mensaje de destino para ella. Durante el tiempo de ejecución, el mensaje de origen se asigna al mensaje de destino mediante la asignación que designó.  
  
 Para obtener más información sobre la **transformar** forma, vea [cómo configurar la forma transformación](../core/how-to-configure-the-transform-shape.md). Para obtener más información sobre la creación de un mapa, consulte [crear mapas de uso del asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md).  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de la ruta de acceso*\>\Orchestrations\HelloWorld\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global. Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|HelloOrchestration.odx|Orquestación que coordina la conversión del pedido en una factura.|  
|HelloWorld.btproj HelloWorld.sln|Archivos de proyectos y de soluciones de este ejemplo.|  
|HelloWorldBinding.xml|Se usa para la instalación automatizada, como el enlace de puerto.|  
|InvoiceSchema.xsd POSchema.xsd|Esquemas para los mensajes de factura y de pedido, respectivamente.|  
|POToInvoice.btm|Asignación para convertir el pedido en una factura.|  
|SamplePOInput.xml|Archivo de entrada de ejemplo.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-helloworld-sample"></a>Para crear e iniciar el ejemplo HelloWorld  
  
1. En una ventana de comandos, desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\Orchestrations\HelloWorld  
  
2. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
   - Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta siguiente:  
  
      \<*Ejemplos de la ruta de acceso*\>\Orchestrations\HelloWorld  
  
   - Compila el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
   - Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción a la orquestación.  
  
   - Habilita la ubicación de recepción e inicia el puerto de envío. Da de alta e inicia la orquestación.  
  
> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización. Lo puede confirmar si ve sus registros de sucesos.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-helloworld-sample"></a>Para ejecutar el ejemplo HelloWorld  
  
1.  Pegue una copia del archivo SamplePOInput.xml en la **en** carpeta.  
  
2.  Observe el archivo .xml creado en el **Out** carpeta. Este archivo contiene la factura XML construida del archivo de entrada SamplePOInput.xml. El formato del nombre de este archivo es \< *MessageID*\>.xml, donde *\<MessageID\>* es el GUID generado para identificar de forma única el mensaje .  
  
## <a name="uninstalling-this-sample"></a>Desinstalar este ejemplo  
  
#### <a name="to-uninstall-the-helloworld-sample"></a>Para desinstalar el ejemplo HelloWorld  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de la ruta de acceso*\>\Orchestrations\HelloWorld\  
  
2.  Ejecute Cleanup.bat.  
  
## <a name="see-also"></a>Vea también  
 [Orquestaciones (carpetas de ejemplos de BizTalk Server)](../core/orchestrations-biztalk-server-samples-folder.md)