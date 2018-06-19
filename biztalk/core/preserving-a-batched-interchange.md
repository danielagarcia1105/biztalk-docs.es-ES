---
title: Conservar un intercambio por lotes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 907e07f3-1f3e-485e-a82d-b28eb7658e0a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e7ea2bdef1fe2b2c3db92421d610b0b889e0460
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265348"
---
# <a name="preserving-a-batched-interchange"></a>Conservar un intercambio por lotes
En este tema se describe cómo se configura un acuerdo para procesar un intercambio EDI por lotes como un solo documento sin dividir los conjuntos de transacciones que componen el intercambio.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a>Para configurar los elementos de recepción y de envío de un lote conservado  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo. En el **entidades y perfiles empresariales** página, haga clic en la entidad que tenga el acuerdo que resolverá el intercambio por lotes entrante. En el **acuerdo** sección de la página, haga clic en el acuerdo y haga clic en **propiedades**. En el **propiedades del acuerdo de** cuadro de diálogo, en la ficha de acuerdo unidireccional (a la que se resolverá el intercambio por lotes entrante), haga lo siguiente:  
  
    1.  En el **identificadores** página, escriba los valores de escriba valores para ISA5, ISA6, ISA7 e ISA8. Asegúrese de escribir los valores correctos, para que el intercambio por lotes entrante resuelva este acuerdo.  
  
    2.  En el **configuración de Host Local** página (en **configuración de intercambio**), en **configuración del receptor** sección, para el **opción de procesamiento por lotes de entrada** , seleccione una de las siguientes opciones:  
  
        -   **Conservar intercambio: suspender intercambio en caso de Error** : seleccione esta opción para especificar que BizTalk Server debe dejar el intercambio intacto y crear un documento XML para todo el intercambio por lotes. Con esta opción, si uno o varios conjuntos de transacciones en el intercambio no superan la validación, BizTalk Server suspenderá el intercambio completo.  
  
        -   **Conservar intercambio: suspender conjuntos de transacciones en caso de Error** : seleccione esta opción para especificar que BizTalk Server debe dejar el intercambio intacto y crear un documento XML para todo el intercambio por lotes. Con esta opción, si uno o más conjuntos de transacciones del intercambio no superan la validación, BizTalk Server suspenderá solo esos conjuntos de transacciones, continuando procesar todos los demás conjuntos de transacciones.  
  
        > [!NOTE]
        >  Si selecciona cualquiera de las dos opciones mencionadas arriba, no se aplican las propiedades de intercambio, grupo y transacción (que determinan cómo BizTalk Server creará los encabezados de ISA, GS y ST de un intercambio saliente). Los encabezados de intercambios, grupos y conjuntos de transacciones que existen en el intercambio que se conserva quedan retenidos cuando la canalización de envío lo procesa para su envío. Sin embargo, si no desea usar los valores especificados para el intercambio en el acuerdo, establezca la propiedad de contexto `EDI.PopulateInterchangeValues` en true.  
  
2.  Cree un proyecto de Visual Studio para el lote conservado, como se indica a continuación:  
  
    1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree un proyecto de BizTalk y agregue los esquemas de todos los mensajes del lote.  
  
    2.  Compile e implemente el proyecto.  
  
3.  En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un puerto de envío para enviar los lotes conservados de la siguiente manera:  
  
    1.  Establecer la canalización de envío **EdiSend** o **AS2EdiSend**.  
  
    2.  Establezca el filtro del puerto de envío en la propiedad de contexto `EDI.ReuseEnvelope == True`.  
  
        > [!NOTE]
        >  Al definir este filtro se asegura de que el puerto de envío se suscribirá a todos los intercambios de procesamiento por lotes que se hayan conservado. La canalización de recepción EdiReceive promociona la propiedad de contexto `EDI.ReuseEnvelope` para identificar que el intercambio se conserva.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de lotes de EDI](../core/configuring-edi-batches.md)   
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)