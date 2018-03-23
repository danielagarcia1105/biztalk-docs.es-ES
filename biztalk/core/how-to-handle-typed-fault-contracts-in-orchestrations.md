---
title: Los contratos de cómo tratar con tipos erróneos en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- typed fault contracts [orchestrations]
- WCF services, orchestrations
- orchestrations, typed fault contracts
- orchestrations, WCF services
ms.assetid: 5a1a7d22-b0ff-4d09-bebf-4995229784b0
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a7643c4a39785018368572d721eed3ef6545c6b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a>Cómo controlar los contratos con tipos erróneos en orquestaciones
En este tema se explica cómo controlar los contratos con tipos erróneos al consumir servicios WCF desde las orquestaciones. Para controlar las excepciones de tipo erróneo en orquestaciones, los servicios WCF que va a consumir deben tener la **FaultContractAttribute** aplica a las operaciones de servicio; por lo tanto, los errores se pueden iniciar mediante el uso de  **FaultException**\<T\> donde T puede ser cualquier contrato de datos válido o un tipo serializable de los servicios WCF.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a>Para controlar los contratos con tipo erróneo en orquestaciones  
  
1.  En la Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el Explorador de soluciones, haga clic en el proyecto, haga clic en **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el **agregar elementos generados - \< ***nombre del proyecto*** \>**  cuadro de diálogo, en la **plantillas** sección, seleccione **consumir WCF Servicio**y, a continuación, haga clic en **agregar**.  
  
3.  En el **éste es el Asistente para consumición de servicio de BizTalk WCF** página, haga clic en **siguiente**.  
  
4.  En el **origen de metadatos** página, seleccione **punto de conexión de intercambio de metadatos (MEX)**y, a continuación, haga clic en **siguiente**.  
  
5.  En el **extremo de metadatos** página, especifique la dirección URL para el servicio en ejecución que proporciona metadatos para su descarga mediante WS-Metadata Exchange o Http-Get — por ejemplo, http://localhost: 8005. Para obtener el documento de metadatos de la dirección URL, haga clic en **obtener**. Si el servicio en ejecución requiere una credencial de usuario con el esquema de autenticación básica, haga clic en **editar** para abrir el **Asistente de consumición de servicio WCF de BizTalk** cuadro de diálogo en el que puede proporcionar el nombre de usuario y contraseña que se utilizará al obtener acceso a lo servicio en ejecución. Haga clic en **Siguiente**.  
  
6.  En el **Importar resumen de metadatos de servicio de WCF** página, revise la configuración. Puede hacer clic en **volver** realizar ningún cambio. A continuación, haga clic en **importación** para crear los artefactos de BizTalk y los tipos que se usará para utilizar el servicio WCF.  
  
7.  En el **completar el Asistente para consumición de servicio de BizTalk WCF** página, haga clic en **finalizar**.  
  
8.  Supongamos que el Servicio WCF que va a consumir inicia la siguiente excepción de error:  
  
    ```  
    throw new FaultException<MyOperationException>(divideException);  
    ```  
  
     La operación errónea en el puerto de envío espera un mensaje de tipo **MyOperationException**, pero el mensaje de respuesta WCF contiene el cuerpo de error completo. Por lo tanto, debe extraer el **MyOperationException** parte del mensaje mediante la configuración de la **cuerpo del mensaje entrante de BizTalk** opción en el cuadro de diálogo de propiedades de transporte. Por ejemplo,  
  
    -   Seleccione **ruta--contenido ubicado por la ruta de cuerpo**.  
  
    -   Establezca la expresión de ruta del cuerpo a continuación:  
  
        ```  
        /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
        ```  
  
    -   Seleccione **Xml** desde el **codificación de nodo** lista desplegable.  
  
9. En la orquestación, será necesario agregar un ámbito y dos controladores de excepción. Es un controlador de excepción para la operación de error similar al **MyOperationException** se muestra en el ejemplo anterior; el otro controlador de excepciones es para capturar genérico **SOAPExceptions**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)   
 [Cómo usar el servicio de WCF de BizTalk consumiendo Asistente para consumir un servicio WCF](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)