---
title: Configurar la acción SOAP para el sistema SAP en BizTalk | Microsoft Docs
description: Especifique una acción de SOAP en forma de expresión, o utilizar el adaptador WCF-Custom o WCF-SAP en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76084bc5-7a10-4c4c-be22-bee83779a011
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c4b3c8d8287b430774813487e924837880a01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004877"
---
# <a name="configure-the-soap-action-for-the-sap-system"></a>Configurar la acción SOAP para el sistema SAP
Para realizar cualquier operación en el sistema SAP mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], los usuarios de adaptador deben especificar una acción de SOAP. La acción SOAP comunica al adaptador qué acción debe realizarse. Puede especificar la acción de SOAP en tiempo de diseño o en tiempo de ejecución. Sin embargo, si se especifica la acción de SOAP tanto en tiempo de diseño y tiempo de ejecución, se invalidará la acción que ha especificado en tiempo de diseño.  
  
 Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).
  
## <a name="enter-soap-action-at-design-time"></a>Especifique la acción de SOAP en tiempo de diseño  
 Para el tiempo de diseño, debe especificar la acción SOAP como parte de la orquestación mediante la inclusión de una forma de expresión.  
  
 
1.  En la orquestación de BizTalk, incluya una forma expresión arrastrándolo desde la **orquestación de BizTalk** cuadro de herramientas.  
  
2.  Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.  
  
3.  Especifica la acción en el Editor de expresiones de BizTalk. Por ejemplo:  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET"  
    ```  
  
     Para obtener más información sobre la **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).
  
## <a name="enter-soap-action-at-run-time"></a>Especifique la acción de SOAP en tiempo de ejecución  
 Para el tiempo de ejecución, puede especificar la acción SOAP como parte de la configuración del puerto WCF-Custom o WCF-SAP.  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>Especifique una acción de SOAP para el puerto de WCF-Custom  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.  
  
5. En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
   -   **Con el formato de acción única**. Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   **Con el formato de asignación de acción**. Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación. Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para invocar RFC RFC_CUSTOMER_GET) y Op2 (para invocar BAPI BAPI_SALESORDER_CREATEFROMDAT2), se puede especificar la acción SOAP de la siguiente manera:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.  
  
        El formato de la acción SOAP es diferente para cada operación. Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).
  
### <a name="enter-a-soap-action-for-the-wcf-sap-port"></a>Especifique una acción de SOAP para el puerto de SAP de WCF  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
5. En el cuadro de diálogo Propiedades de transporte, haga clic en el **General** ficha.  
  
6. En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
   -   **Con el formato de acción única**. Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   **Con el formato de asignación de acción**. Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación. Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para invocar RFC RFC_CUSTOMER_GET) y Op2 (para invocar BAPI BAPI_SALESORDER_CREATEFROMDAT2), se puede especificar la acción SOAP de la siguiente manera:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.  
  
        El formato de la acción SOAP es diferente para cada operación. Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)