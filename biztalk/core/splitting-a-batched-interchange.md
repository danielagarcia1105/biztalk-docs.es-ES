---
title: Dividir un intercambio por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e67bef19-77fb-47a9-88f3-ee20043b3691
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 745f94d4ec56222d3c1d3e03c0817933248f4b8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="splitting-a-batched-interchange"></a>Dividir un intercambio por lotes
En este tema se describe cómo se configura un acuerdo para procesar un intercambio EDI por lotes mediante la división de los conjuntos de transacciones que componen el intercambio.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-receive-a-split-edi-interchange"></a>Para recibir un intercambio EDI dividido  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo. En el **entidades y perfiles empresariales** página, haga clic en la entidad que tenga el acuerdo que resolverá el intercambio por lotes entrante. En el **acuerdo** sección de la página, haga clic en el acuerdo y haga clic en **propiedades**. En el **propiedades del acuerdo de** cuadro de diálogo, en la ficha de acuerdo unidireccional (a la que se resolverá el intercambio por lotes entrante), haga lo siguiente:  
  
    1.  En el **identificadores** página, asegúrese de escribir los valores correctos para que el intercambio por lotes entrante resuelva este acuerdo.  
  
        -   En caso de **X12**: establezca ISA5, ISA6, ISA7 e ISA8.  
  
        -   En caso de **Edifact**: establezca UNB2.1, UNB2.2, UNB3.1 y UNB3.2.  
  
    2.  En el **configuración de Host Local** página (en **configuración de intercambio**), en **configuración del receptor** sección, para el **opción de procesamiento por lotes de entrada** , seleccione una de las siguientes opciones:  
  
        -   **Dividir intercambio como conjuntos de transacciones: suspender conjuntos de transacciones en caso de Error** : seleccione esta opción para especificar que BizTalk Server debe analizar cada conjunto de transacciones en un intercambio en un documento XML independiente. Después, BizTalk Server aplicará el sobre adecuado al conjunto de transacciones y enrutará el documento de este conjunto al cuadro de mensajes. Con esta opción, si uno o varios conjuntos de transacciones del intercambio no superan la validación, BizTalk Server suspenderá solo esos conjuntos de transacciones.  
  
        -   **Dividir intercambio como conjuntos de transacciones: suspender intercambio en caso de Error** : seleccione esta opción para especificar que BizTalk Server debe analizar cada conjunto de transacciones en un intercambio en un documento XML independiente. Después, BizTalk Server aplicará el sobre adecuado al conjunto de transacciones y enrutará el documento de este conjunto al cuadro de mensajes. Con esta opción, si uno o varios conjuntos de transacciones en el intercambio no superan la validación, BizTalk Server suspenderá el intercambio completo.  
  
2.  Cree un proyecto de Visual Studio para el lote conservado, como se indica a continuación:  
  
    1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree un proyecto de BizTalk y agregue los esquemas de todos los mensajes del lote.  
  
    2.  Compile e implemente el proyecto.  
  
3.  En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un puerto de envío para enviar lotes divididos, de la siguiente manera:  
  
    1.  Establecer la canalización de envío **EdiSend** o **AS2EdiSend**.  
  
    2.  Establezca el filtro del puerto de envío en el valor necesario para recoger cada conjunto de transacciones, por ejemplo como BTS.MessageType.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de lotes de EDI](../core/configuring-edi-batches.md)   
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)