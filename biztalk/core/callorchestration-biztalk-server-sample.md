---
title: CallOrchestration (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, calling
- examples, orchestrations
ms.assetid: 0c4194f0-c1e2-419a-8a1a-a3c96e8d2667
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 614cbb4531d0d7052263e5e4c7d73ec209e9b685
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021882"
---
# <a name="callorchestration-biztalk-server-sample"></a>CallOrchestration (ejemplo de BizTalk Server)
El ejemplo de CallOrchestration muestra cómo llamar a una orquestación de BizTalk desde otra orquestación.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra una orquestación que llama a otra orquestación mediante los pasos que se indican a continuación:  
  
1.  La orquestación principal recibe un mensaje de pedido.  
  
2.  La orquestación principal llama a la secundaria para determinar el precio de envío del pedido.  
  
3.  La orquestación secundaria calcula el precio de envío solicitado y lo devuelve a la orquestación primaria.  
  
4.  La orquestación principal actualiza el mensaje de pedido con el precio de envío.  
  
5.  La orquestación principal guarda el mensaje de pedido actualizado en una carpeta para que lo inspeccione.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 El objetivo principal de este ejemplo consiste en mostrar cómo llamar a una orquestación desde otra orquestación. La posibilidad de llamar a orquestaciones permite dividir los procesos empresariales en componentes reutilizables. Puede descomponer sus procesos comunes en orquestaciones independientes para que otras personas puedan reutilizarlos.  
  
 En este ejemplo, el **orquestación de llamada** forma en receivePO.odx invoca findShippingPrice.odx y espera a que la orquestación anidada, findShippingPrice.odx, para calcular y devolver el precio de envío antes de enviar la compra orden. La orquestación findShippingPrice.odx utiliza la siguiente lógica para calcular el precio de envío:  
  
```  
If ( weight * shippingRate ) < minShippingPrice Then  
    shippingPrice = minShippingPrice  
Else  
    shippingPrice = weight * shippingRate  
End If  
```  
  
 El archivo de pedido de entrada de ejemplo, InputPO.xml, especifica un peso de 20, lo que da como resultado que el mensaje de pedido de salida haya cambiado el precio de envío de 10 a 20.  
  
> [!NOTE]
>  No puede llamar a una transacción de larga ejecución desde una orquestación atómica.  
  
> [!NOTE]
>  La diferencia entre usar el **orquestación de llamada** forma y el **Iniciar orquestación** forma es que al llamar a una orquestación, el llamador espera a que la orquestación anidada finalice antes de continuar. Al iniciar una orquestación desde una orquestación, una vez que el autor de la llamada inicia la acción, pasa al siguiente paso del flujo de procesos. La orquestación invocada por el autor de la llamada se ejecuta de forma independiente hasta que finaliza el flujo de procesos. Para obtener más información, consulte [cómo configurar la forma de orquestación llame a](../core/how-to-configure-the-call-orchestration-shape.md). Consulte también [cómo configurar la forma de orquestación de inicio](../core/how-to-configure-the-start-orchestration-shape.md).  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de la ruta de acceso*\>\Orchestrations\CallOrchestration\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|CallOrchestration.btproj, CallOrchestration.sln|Archivos de proyectos y de soluciones de este ejemplo.|  
|CallOrchestrationBinding.xml|Se usa para la instalación automatizada, como el enlace de puerto.|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global. Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|findShippingPrice.odx|La orquestación de BizTalk que sirve como orquestación secundaria llamada desde la orquestación principal, receivePO.odx.|  
|InputPO.xml|El mensaje de pedido de entrada de ejemplo que se ajusta al esquema definido en el archivo PO.xsd.|  
|PO.xsd|El esquema que define la estructura de mensajes de pedidos entrantes, como el archivo de entrada de ejemplo InputPO.xml, y define la promoción de propiedades de los tres elementos del esquema.|  
|PropertySchema.xsd|El archivo de esquema de propiedad que participa en la promoción de propiedades de los tres elementos del esquema PO.xsd.|  
|receivePO.odx|La orquestación de BizTalk que sirve como orquestación principal en este ejemplo. Recupera los mensajes de pedido de la carpeta de recepción y llama a la otra orquestación, findShippingPrice.odx, para calcular y actualizar el precio de envío.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-callorchestration-sample"></a>Para crear e iniciar el ejemplo de CallOrchestration  
  
1. En una ventana de comandos, desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\Orchestrations\CallOrchestration\  
  
2. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
   - Crea las carpetas de entrada (In) y salida (Out) de este ejemplo en la carpeta CallOrchestration.  
  
   - Compila e implementa el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] que contiene las dos orquestaciones de este ejemplo.  
  
   - Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  
  
   - Habilita la ubicación de recepción e inicia el puerto de envío.  
  
> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-callorchestration-sample"></a>Para ejecutar el ejemplo de CallOrchestration  
  
1.  Guarde una copia del archivo InputPO.xml en la carpeta In.  
  
2.  Observe el archivo de pedido XML actualizado creado en la carpeta Out. Contiene el mensaje de pedido original, modificado para incluir el costo de envío calculado del modo explicado anteriormente. El formato del nombre de este archivo es \< *MessageID*\>.xml, donde *\<MessageID\>* es el GUID generado para identificar de forma única el mensaje .  
  
## <a name="uninstalling-this-sample"></a>Desinstalar este ejemplo  
  
#### <a name="to-uninstall-the-callorchestration-sample"></a>Para desinstalar el ejemplo CallOrchestration  
  
1. En una ventana de comandos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\Orchestrations\CallOrchestration\  
  
2. Ejecute Cleanup.bat.  
  
## <a name="see-also"></a>Vea también  
 [Orquestaciones (carpetas de ejemplos de BizTalk Server)](../core/orchestrations-biztalk-server-samples-folder.md)