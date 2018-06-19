---
title: Configurar la acción SOAP para Oracle E-Business Suite en BizTalk Server | Documentos de Microsoft
description: Especifique una acción de SOAP en Visual Studio, o usar el adaptador de WCF-Custom o WCF-OracleEBS en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca799d96-66e4-4d4e-a632-cb5505e999b4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c29cb5ce17f0a80e42ceae908639bed48e99e3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218284"
---
# <a name="configure-the-soap-action-for-oracle-e-business-suite"></a>Configurar la acción SOAP para Oracle E-Business Suite
Para realizar cualquier operación en Oracle E-Business Suite con basadas en WCF [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe especificar una acción de SOAP. La acción SOAP comunica con el adaptador de la acción que debe realizarse. Puede especificar la acción SOAP de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Sin embargo, si especifica la acción de SOAP en ambas ubicaciones, la acción especificado de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se invalida.  
  
 Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío de WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).  
  
## <a name="enter-soap-action-from-visual-studio"></a>Especifique la acción de SOAP desde Visual Studio  
 De [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar la acción SOAP como parte de la orquestación mediante un **expresión** forma.  
  
1.  En la orquestación de BizTalk, incluya una **expresión** forma arrastrándolo desde el **orquestación de BizTalk** cuadro de herramientas.  
  
2.  Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.  
  
3.  Especifica la acción en el Editor de expresiones de BizTalk. Por ejemplo:  
  
    ```  
    OutboundMessage(WCF.Action)="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY"  
    ```  
  
     Para obtener más información sobre la **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a>Especifique la acción de SOAP de administración de BizTalk Server  
 Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar la acción SOAP como parte de la configuración del puerto WCF-Custom o WCF-OracleEBS.  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>Especifique una acción de SOAP para el puerto de WCF-Custom  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3.  En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
4.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.  
  
5.  En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
    -   **Con el formato de acción única**. Utilice este formato si WCF-Custom puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
        ```  
        InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
        ```  
  
    -   **Con el formato de asignación de acción**. Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación. Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para insertar registros en la tabla GL_ALLOC_HISTORY) y Op2 (para actualizar registros en la tabla GL_ALLOC_HISTORY), la acción SOAP puede especificarse de la siguiente manera:  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
          <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
        </BtsActionMapping>  
        ```  
  
         El método de asignación de acción proporciona mayor flexibilidad en cuanto a especificar un conjunto de acciones y, por lo tanto, lo que permite los mensajes que pertenecen a los tipos de acción diferentes atraviese el mismo puerto.  
  
         El formato de la acción SOAP es diferente para cada operación. Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje para el adaptador de Oracle EBS](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).
  
#### <a name="enter-a-soap-action-for-the-wcf-oracleebs-port"></a>Especifique una acción de SOAP para el puerto de WCF-OracleEBS  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Agregar el adaptador de WCF-OracleEBS a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).  
  
3.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4.  En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione el WCF-OracleEBS adaptador agrega anteriormente y, a continuación, haga clic en **configurar**.  
  
5.  En el cuadro de diálogo Propiedades de transporte, haga clic en el **General** ficha.  
  
6.  En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
    -   **Con el formato de acción única**. Utilice este formato si WCF-OracleEBS puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
        ```  
        InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
        ```  
  
    -   **Con el formato de asignación de acción**. Utilice este formato si un único puerto de WCF-OracleEBS envía y recibe mensajes de más de una operación. Por ejemplo, si un único puerto de WCF-OracleEBS envía y recibe mensajes de Op1 (para insertar registros en la tabla GL_ALLOC_HISTORY) y Op2 (para actualizar registros en la tabla GL_ALLOC_HISTORY), la acción SOAP puede especificarse de la siguiente manera:  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
          <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
        </BtsActionMapping>  
        ```  
  
         El método de asignación de acción proporciona mayor flexibilidad en cuanto a especificar un conjunto de acciones y, por lo tanto, lo que permite los mensajes que pertenecen a los tipos de acción diferentes atraviese el mismo puerto.  
  
         El formato de la acción SOAP es diferente para cada operación. Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje para el adaptador de Oracle EBS](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).
  
## <a name="see-also"></a>Vea también  
 [Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)