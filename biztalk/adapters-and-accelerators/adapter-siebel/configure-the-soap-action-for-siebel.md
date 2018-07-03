---
title: Configurar la acción SOAP para el adaptador de Siebel en BizTalk | Microsoft Docs
description: Especifique una acción de SOAP en Visual Studio, o utilizar el adaptador WCF-Custom o WCF-Siebel en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f22a4691-0355-4f08-a14e-e90a3c987ac0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb945aba089e0c57e42e846cec765ae48b10d433
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022250"
---
# <a name="configure-the-soap-action-for-siebel"></a>Configurar la acción SOAP para Siebel
Para realizar cualquier operación en el sistema de Siebel mediante basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], los usuarios de adaptador deben especificar una acción de SOAP. La acción SOAP comunica al adaptador qué acción debe realizarse. Puede especificar la acción de SOAP en tiempo de diseño o en tiempo de ejecución. Sin embargo, si se especifica la acción de SOAP tanto en tiempo de diseño y tiempo de ejecución, se invalidará la acción que ha especificado en tiempo de diseño.  
  
 Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).
  
## <a name="enter-soap-action-at-design-time"></a>Especifique la acción de SOAP en tiempo de diseño  
 Para el tiempo de diseño, debe especificar la acción SOAP como parte de la orquestación mediante la inclusión de una forma de expresión.  
  
1.  En el BizTalk orquestación incluyen una forma expresión arrastrándolo desde la **orquestación de BizTalk** cuadro de herramientas.  
  
2.  Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.  
  
3.  Especifica la acción en el Editor de expresiones de BizTalk. Por ejemplo:  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"  
    ```  
  
     Para obtener más información acerca de **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).  
  
## <a name="enter-soap-action-at-run-time"></a>Especifique la acción de SOAP en tiempo de ejecución  
 Para el tiempo de ejecución, debe especificar la acción SOAP como parte del cuadro de diálogo Propiedades de puerto de WCF-Custom o WCF-Siebel.  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>Especifique una acción de SOAP para el puerto de WCF-Custom  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.  
  
5. En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
   -   **Con el formato de acción única**. Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
       ```  
       http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
       ```  
  
   -   **Con el formato de asignación de acción**. Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación. Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para realizar una operación de inserción en el componente de negocio de cuenta) y Op2 (para realizar una operación de actualización en el componente de negocio de cuenta), se puede especificar la acción SOAP en el siguiente forma:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
       </BtsActionMapping>  
       ```  
  
        Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.  
  
        El formato de la acción SOAP es diferente para cada operación. Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).
  
#### <a name="enter-a-soap-action-for-the-wcf-siebel-port"></a>Especifique una acción de SOAP para el puerto de WCF-Siebel  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione el WCF-Siebel adaptador agregue anteriormente y, a continuación, haga clic en **configurar**.  
  
5. En el cuadro de diálogo Propiedades de puerto, haga clic en el **General** ficha.  
  
6. En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
   -   **Con el formato de acción única**. Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
       ```  
       http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
       ```  
  
   -   **Con el formato de asignación de acción**. Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación. Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para realizar una operación de inserción en el componente de negocio de cuenta) y Op2 (para realizar una operación de actualización en el componente de negocio de cuenta), se puede especificar la acción SOAP en el siguiente forma:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
       </BtsActionMapping>  
       ```  
  
        Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.  
  
        El formato de la acción SOAP es diferente para cada operación. Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)