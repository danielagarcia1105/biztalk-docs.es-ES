---
title: "Ejecución de BizTalk no pudo ejemplo de procesamiento de ESB de enrutamiento de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2a536a0-cfc8-4ba3-adcd-2b8b580bff85
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a19f8c29c22638be97ae62dfea88d0d2feca6c55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-biztalk-failed-message-routing-esb-processing-sample"></a>Ejecución de BizTalk no pudo ejemplo de procesamiento de ESB de enrutamiento de mensajes
El ejemplo de Microsoft BizTalk no se pudo enrutamiento ESB procesamiento de mensajes muestra cómo se puede utilizar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco de administración de excepciones como un mecanismo de universal para administrar, serializar y representar las excepciones que se producen en todas las condiciones de [!INCLUDE[prague](../includes/prague-md.md)]. Esto incluye las excepciones generadas por el enrutamiento de mensajes de error de BizTalk mecanismo y error mensajes generados por el marco de administración de excepción desde una orquestación.  
  
 El mecanismo de enrutamiento de mensajes de error de BizTalk es la funcionalidad de control de errores de [!INCLUDE[prague](../includes/prague-md.md)]; gracias a ella, el diseñador puede designar un control automatizado de mensajes con errores como alternativa al tradicional comportamiento (ahora como configuración predeterminada) de colocar errores mensajes en la cola de "Suspensión". Este control automatizado enruta un mensaje de error a cualquier destino de enrutamiento de suscripción, como un puerto de envío o una orquestación. El mensaje de error es un clon del mensaje original con todas las propiedades anteriormente promocionadas degradadas y con propiedades seleccionadas relacionadas al error de mensajería específico promocionadas en el contexto del mensaje.  
  
 Para habilitar el mecanismo de enrutamiento de mensajes de error de BizTalk en un puerto de recepción o un puerto de envío, seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación, tal como se muestra en la figura 1.  
  
 ![Enrutamiento habilitado](../esb-toolkit/media/ch6-enabledrouting.gif "Ch6-EnabledRouting")  
  
 **Figura 1**  
  
 **Habilitar el mecanismo de enrutamiento de mensajes de error de BizTalk**  
  
 Sin embargo, no hay un mecanismo similar si hay errores o errores que se producen en una orquestación. En su lugar, el código en el controlador de excepciones de una orquestación puede sacar partido de la API de marco de trabajo de administración de excepciones para emular la funcionalidad del mecanismo de enrutamiento de mensajes de error de BizTalk.  
  
 En este ejemplo, la ubicación de recepción denominada EAIProcess.RequestPort_FILE recoge archivos copiados en la ubicación \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.RequestPort.  
  
 Además, hay un puerto de envío genérico llamado todos. Exceptions_FILE configurado para usar la canalización de GlobalFaultProcessor instalada como parte de la estructura de administración de la excepción. Este puerto se suscribe a todas las excepciones que se producen en el sistema, ambos BizTalk no pudo mensaje enrutamiento de mensajes y mensajes de error ESB, tal como se muestra en la figura 2.  
  
 ![Puerto de envío](../esb-toolkit/media/ch6-sendport.gif "Ch6-SendPort")  
  
 **Figura 2**  
  
 **ALL. Suscripción de puerto para todos los tipos de excepción o un error de envío de excepciones**  
  
 El marco de trabajo de administración de excepciones se normaliza todas las excepciones en un único formato y se serializa utilizando una instrucción de procesamiento de Microsoft InfoPath en la ubicación \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions.  
  
## <a name="installation"></a>Installation  
 Todos los ejemplos de administración de excepciones utilizan el mismo conjunto de servicios principales y artefactos de la aplicación de BizTalk. Por lo tanto, tendrá que instalar los artefactos de ejemplo de administración de excepción sólo una vez para poder ejecutar la excepción de todos los ejemplos de administración. Para obtener información acerca de cómo instalar los ejemplos de administración de excepciones, vea [instalar los ejemplos de administración de excepción](../esb-toolkit/installing-the-exception-management-samples.md).  
  
## <a name="running-the-sample-application"></a>Ejecutar la aplicación de ejemplo  
 **Para ejecutar el ejemplo de BizTalk no se pudo enrutamiento ESB procesamiento de mensajes**  
  
1.  Antes de ejecutar este ejemplo por primera vez, asegúrese de que la recepción dirección URL de puerto de envío y de ubicación apuntan a los directorios adecuados en la carpeta \Source\Samples\Exception Handling\Test\Filedrop. La ubicación de recepción debe especificar la carpeta EAIProcess.RequestPort y la dirección URL de puerto de envío debe especificar la carpeta All_Exceptions.  
  
2.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
3.  Copie el archivo denominado FlatFileReceive_in.txt desde la carpeta \Source\Samples\Exception Handling\Test\Data en la carpeta de ubicación de recepción denominada EAIProcess.RequestPort (en la carpeta \Source\Samples\Exception Handling\Test\Filedrop).  
  
4.  Este mensaje es un archivo de texto y producirá una excepción. Abra la carpeta denominada All_Exceptions (en la carpeta \Source\Samples\Exception Handling\Test\Filedrop) y, a continuación, haga doble clic en el mensaje de error para abrirlo en InfoPath que utiliza la plantilla adecuada. Verá que el mecanismo de control de excepciones de ESB serializa el contenido correctamente para permitir que InfoPath representarlo.  
  
5.  A continuación, copie el archivo denominado soapmessage [1] .xml desde la carpeta \Source\Samples\Exception Handling\Test\Data en la EAIProcess.RequestPort carpeta de ubicación de recepción.  
  
6.  Este mensaje es un documento XML que contiene una sección CDATA, y producirá una excepción. Abra la carpeta de salida All_Exceptions y haga doble clic en el mensaje de error para abrirlo en InfoPath. Verá que el mecanismo de control de excepciones de ESB serializa este contenido adecuadamente para permitir que InfoPath representarlo.  
  
7.  Por último, copie el archivo denominado Csqzav01.pdf desde la carpeta \Source\Samples\Exception Handling\Test\Data en la EAIProcess.RequestPort ubicación de recepción.  
  
8.  Este mensaje es un archivo PDF y producirá una excepción. Abra la carpeta de salida All_Exceptions y haga doble clic en el mensaje de error para abrirlo en InfoPath. Verá que el mecanismo de control de excepciones de ESB serializa y Base64 codifica el contenido para permitir que InfoPath representarlo.