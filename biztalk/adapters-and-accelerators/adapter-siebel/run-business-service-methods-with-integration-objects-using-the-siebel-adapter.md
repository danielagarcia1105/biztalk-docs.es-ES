---
title: Invocar métodos de servicio empresarial con objetos de integración mediante el adaptador de Siebel | Microsoft Docs
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
ms.openlocfilehash: 40add1c72dabfd8648d1fa33e968cb26e98c11c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996917"
---
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a>Invocar métodos de servicio empresarial con objetos de integración mediante el adaptador de Siebel
El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes del adaptador invocar métodos de servicio empresarial que trabajan con objetos de integración. Estos servicios empresariales suelen tienen IN, OUT, o escriba los parámetros IN OUT de datos "jerarquía" para enviar o recibir datos de objetos de integración.  
  
 La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone estos tipos jerárquicos como cadenas. Estos valores de cadena son básicamente una cadena XML que se encapsula en una sección XML CDATA. La cadena XML es compatible con el esquema XML del objeto de integración que el cliente de adaptador está intentando enviar o recibir.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, SiebelAdapterIntegrationObjects, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a>Creación de una orquestación para invocar métodos de servicio empresarial con objetos de integración  
 Creación de una orquestación para invocar un método de servicio de negocio que toma los parámetros de objetos de integración es similar a la orquestación para invocar cualquier otro servicio de negocio, como se describe en [invocar Business Service métodos mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).  
  
 La diferencia reside en el mensaje de solicitud que quita de la orquestación. Esta diferencia es debido al siguiente:  
  
- El esquema del mensaje de solicitud es diferente porque invocar un servicio empresarial diferente.  
  
- El mensaje de solicitud contiene la cadena XML para el objeto de integración. Este XML se encapsula en una sección CDATA. Debe generar primero el esquema para el objeto de integración y, a continuación, crear un XML que se ajusta al esquema. Este XML debe pasarse en la sección CDATA del mensaje de solicitud enviado al adaptador.  
  
  Después de haber generado el XML que se ajusta al esquema de objetos de integración y lo incluye en el mensaje de solicitud, debe quitar el mensaje de solicitud en una ubicación de archivos, igual que haría para cualquier otra orquestación. Busque el mensaje de respuesta en la ubicación del archivo.  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a>Mensajes de solicitud y respuesta para invocar el servicio de negocio con objetos de integración  
 Como se mencionó antes, la única diferencia para invocar un servicio empresarial que toma los parámetros de objetos de integración es el mensaje de solicitud enviado al adaptador. Esta sección proporciona instrucciones sobre los pasos que debe realizar para crear el mensaje de solicitud.  
  
 Para comprender mejor, tomar un servicio de negocio de Siebel 'Adaptador de Siebel EAI' como un ejemplo. El servicio de negocio 'Adaptador de Siebel de EAI' funciona en un objeto de la integración de Siebel, "Cuenta de ejemplo". Debe realizar las tareas siguientes para crear el mensaje de solicitud para invocar un método expuesto por el servicio de negocio 'Adaptador de Siebel de EAI':  
  
- **Generar el esquema para el servicio de adaptador de Siebel EAI business**. Debe usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Cuando genere el esquema, generar el XML que se ajusta al esquema.  
  
- **Generar el esquema para el objeto de integración**. Use las herramientas de Siebel para generar el esquema de un objeto de integración. Desde la interfaz de las herramientas de Siebel, seleccione el objeto de integración, por ejemplo, la cuenta de ejemplo y haga clic en **generar esquema**. Al generar el esquema, asegúrese de que:  
  
  - El **seleccione un servicio empresarial en la lista** desplegable tiene el valor "EAI XML XSD Generator".  
  
  - El **seleccione un tipo de sobre de la lista** desplegable tiene el valor "Siebel sobre del mensaje".  
  
    Para obtener más información, consulte la documentación de Siebel.  
  
- **Crear un mensaje XML que se ajusta al esquema del objeto integración**. Un mensaje XML de ejemplo generado para el objeto de integración 'Cuenta de ejemplo' tiene el siguiente aspecto:  
  
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
  
- **Pase este mensaje XML como el valor para el elemento CDATA en el mensaje de solicitud para el método de servicio empresarial**. Un mensaje de solicitud de ejemplo que contiene el mensaje XML anterior dentro de un elemento CDATA es similar a la siguiente. Esta solicitud de ejemplo consiste en invocar el método de inserción para el servicio de negocio 'Adaptador de Siebel de EAI'.  
  
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
  
  Uso de las características de BizTalk, los clientes del adaptador también pueden realizar una validación adicional la integración de entrada y salida del parámetro de objeto con respecto al esquema de objetos de integración (obtenido a partir de las herramientas de Siebel).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)    
[Desarrollar aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)