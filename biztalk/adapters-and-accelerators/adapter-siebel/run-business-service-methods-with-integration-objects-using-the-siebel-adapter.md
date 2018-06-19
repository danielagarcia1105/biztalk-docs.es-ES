---
title: Invocar métodos de servicio de negocio con objetos de integración con el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- integration objects
- how to, invoke business service methods with integration objects
- business service methods, invoking with integration objects
ms.assetid: ac0fa80a-3451-436e-8a1a-b6b5e93081e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 132c269d347f67cbad3038bcbbb8e62d29112b6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962850"
---
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a>Invocar métodos de servicio de negocio con objetos de integración con el adaptador de Siebel
El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes de adaptador invocar métodos de servicio de negocio que funcionan con objetos de integración. Estos servicios empresariales suelen tienen IN, OUT, o en los parámetros de datos de "jerarquía" escriba para enviar o recibir datos de objetos de integración.  
  
 La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone estos tipos jerárquicos como cadenas. Estos valores de cadena son básicamente una cadena XML que se encapsulan en una sección CDATA XML. La cadena XML es compatible con el esquema XML del objeto de integración que del cliente de adaptador está intentando enviar o recibir.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, SiebelAdapterIntegrationObjects, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a>Crear una orquestación para invocar métodos de servicio de negocio con objetos de integración  
 Crear una orquestación para invocar un método de servicio de negocios que toma parámetros de objetos de integración es similar a la orquestación para invocar cualquier otro servicio de negocio, como se describe en [invocar Business servicio métodos mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).  
  
 La diferencia radica en el mensaje de solicitud que se quita de la orquestación. Esta diferencia es por los motivos siguientes:  
  
-   El esquema del mensaje de solicitud es diferente porque invocar un servicio empresarial diferente.  
  
-   El mensaje de solicitud contiene la cadena XML para el objeto de integración. Este código XML se encapsula en una sección CDATA. Debe generar primero el esquema para el objeto de integración y, a continuación, crear un XML que se ajusta al esquema. Este código XML debe pasarse en la sección CDATA del mensaje de solicitud que se envía al adaptador.  
  
 Una vez que haya generado el XML que se ajusta al esquema de objetos de integración e incluido en el mensaje de solicitud, debe quitar el mensaje de solicitud en una ubicación de archivos, al igual que haría para cualquier otra orquestación. Busque el mensaje de respuesta en la ubicación del archivo.  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a>Mensajes de solicitud y respuesta para invocar el servicio de negocio con objetos de integración  
 Como se mencionó antes, la única diferencia para invocar un servicio de negocios que toma parámetros de objetos de integración es el mensaje de solicitud enviado al adaptador. Esta sección proporciona instrucciones sobre los pasos que debe seguir para crear el mensaje de solicitud.  
  
 Para obtener más información, tomar un servicio de negocios de Siebel 'Adaptador de Siebel de EAI' como un ejemplo. El servicio de negocio 'Adaptador de Siebel de EAI' funciona en un objeto de la integración de Siebel, "Cuenta de ejemplo". Debe realizar las siguientes tareas para crear el mensaje de solicitud para invocar un método expuesto por el servicio de negocio "Adaptador de Siebel de EAI":  
  
-   **Generar el esquema para el servicio de adaptador de Siebel EAI empresarial**. Debe usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Una vez generado el esquema, generar el XML que se ajusta al esquema.  
  
-   **Generar el esquema para el objeto de integración**. Utilice las herramientas de Siebel para generar el esquema de un objeto de integración. Desde la interfaz de las herramientas de Siebel, seleccione el objeto de integración, por ejemplo, la cuenta de ejemplo y haga clic en **generar esquema**. Al generar el esquema, asegúrese de que:  
  
    -   El **seleccione un servicio empresarial de la lista** lista desplegable tiene el valor "Generador de EAI XML XSD".  
  
    -   El **seleccione un tipo de sobre de la lista** lista desplegable tiene el valor "Siebel sobre del mensaje".  
  
     Para obtener más información, consulte la documentación de Siebel.  
  
-   **Crear un mensaje XML que se ajusta al esquema del objeto integración**. Un mensaje XML de ejemplo generado por el objeto de integración 'Cuenta de ejemplo' tiene el siguiente aspecto:  
  
    ```  
    <?xml version="1.0" encoding="UTF-16"?>  
    <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
      <ListOfSampleAccount>  
        <Account>  
          <CurrencyCode>USD</CurrencyCode>  
          <Location>Redmond</Location>  
          <Name>IntegrationObjectTest</Name>  
        </Account>  
      </ListOfSampleAccount>  
    </SiebelMessage>  
    ```  
  
-   **Pase este mensaje XML como el valor para el elemento CDATA en el mensaje de solicitud para el método de servicio de negocio**. Un mensaje de solicitud de ejemplo que contiene el mensaje XML anterior dentro de un elemento CDATA es similar a la siguiente. Esta solicitud de ejemplo es invocar el método de inserción para el servicio de negocio "Adaptador de Siebel de EAI".  
  
    ```  
    <Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
      <InsertRequestRecord />   
      <InsertInOutRecord>  
        <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
          <![CDATA[ <?xml version="1.0" encoding="UTF-16"?>  
            <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
              <ListOfSampleAccount>  
                <Account>  
                  <CurrencyCode>USD</CurrencyCode>  
                  <Location>Redmond</Location>  
                  <Name>IntegrationObjectTest</Name>  
                </Account>  
              </ListOfSampleAccount>  
            </SiebelMessage>  
          ]]>   
         </SiebelMessage>  
      </InsertInOutRecord>  
    </Insert>  
    ```  
  
     La respuesta de Siebel para el mensaje de solicitud anterior es similar al siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <InsertResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
      <InsertResult>  
        <ErrorCode xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">0x0</ErrorCode>   
        <ErrorContextIntComp xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <ErrorContextSearchSpec xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <ErrorSymbol xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <OMErrorCode xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <OMErrorSymbol xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <PrimaryRowId xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">1-6SPSJ</PrimaryRowId>   
      </InsertResult>  
      <InsertInOutRecord>  
        <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
          <![CDATA[ <?xml version="1.0" encoding="UTF-16"?>  
            <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
              <ListOfSampleAccount>  
                <Account>  
                  <CurrencyCode>USD</CurrencyCode>  
                  <Location>Redmond</Location>  
                  <Name>IntegrationObjectTest</Name>  
                </Account>  
              </ListOfSampleAccount>  
            </SiebelMessage>  
          ]]>   
         </SiebelMessage>  
      </InsertInOutRecord>  
    </InsertResponse>  
    ```  
  
 Usar las características de BizTalk, los clientes de adaptador también pueden realizar una validación adicional del integración parámetro del objeto de entrada y salida con respecto al esquema de objetos de integración (obtenido a partir de las herramientas de Siebel).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)    
[Desarrollar aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)