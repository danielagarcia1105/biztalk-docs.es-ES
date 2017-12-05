---
title: Escenario empresarial de ejemplo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78229d903461fe2b84033b036ef02b2838832fc0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="sample-business-scenario"></a>Escenario empresarial de ejemplo
Procesos de atención sanitaria a menudo son complejos e implican muchos sistemas. Un ejemplo es el proceso que se produce cuando un paciente introduce un hospital y un médico envía al paciente para una prueba de laboratorio. Implicadas en este procedimiento son cinco partes:  
  
-   El médico que le  
  
-   El sistema de registro de Hospital  
  
-   El sistema de entrada de pedidos clínicos  
  
-   El sistema de laboratorio  
  
-   El sistema de facturación  
  
 En este proceso, pueden producirse los siguientes pasos:  
  
1.  El médico impedimento registra al paciente.  
  
    1.  Un ADT ^ O04 mensaje de registro se difunde por el sistema de registro de Hospital.  
  
    2.  El ADT ^ O04 recibirlo por todos los departamentos que se suscriben al mensaje, incluido el sistema de entrada de pedido clínicos y el sistema de laboratorio.  
  
2.  El médico ordena un estudio de diagnóstico de la instalación de laboratorio.  
  
    1.  Un ORM ^ O01 mensaje del pedido se envía desde el sistema de entrada de pedidos clínicos, después de la validación de reglas de negocios.  
  
    2.  La ORM ^ O01 recibirlo por el sistema de laboratorio.  
  
3.  El laboratorio recibe el pedido y devuelve una confirmación.  
  
    1.  Un ORR ^ O02 mensaje de confirmación del pedido es enviado por el sistema de laboratorio, que indica que se puede ejecutar el orden.  
  
    2.  El ORR ^ O02 recibirlo por el sistema de entrada de pedidos clínicos.  
  
4.  En la realización de las pruebas, el laboratorio envía los resultados al médico y otros departamentos.  
  
    1.  Un ORU ^ R01 mensaje de resultados de pruebas se envía desde el sistema de laboratorio.  
  
    2.  El ORU ^ R01 recibirlo por el sistema de entrada de pedidos clínicos y el sistema de facturación.  
  
    3.  El motor de interfaz se envía un mensaje de correo electrónico al médico, que recibe los resultados de laboratorio en su PDA inalámbrico.  
  
## <a name="the-btahl7-solution"></a>La solución BTAHL7  
 El escenario empresarial de ejemplo que se ha descrito anteriormente es un ejemplo de un sistema de atención médica que necesita la integración. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) proporciona una solución para este escenario que ofrece la funcionalidad siguiente:  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]se integra todos los sistemas implicados en una organización de concentrador y radio. Cada sistema se comunica directamente con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. No tienen que comunicarse directamente entre ellas.  
  
2.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]controla los mensajes con codificación HL7 de forma nativa. No se requiere ningún código personalizado.  
  
3.  El ADT ^ O04 mensaje de registro se difunde a todos los sistemas que se suscriben a él. El modelo de mensajería de publicador y el suscriptor para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona flexibilidad en la configuración y mantenimiento de la lista de sistemas de suscripción al mensaje. Puede agregar sistemas o eliminarlos de la lista de suscripciones sin afectar al resto del sistema.  
  
4.  La regla de negocios que se usa para validar la ORM ^ O01 mensaje de pedido puede cambiarse dinámicamente sin afectar al resto del sistema.  
  
5.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]puede configurarse para generar automáticamente el ORR ^ O02 mensaje de confirmación del pedido (ACK).  
  
6.  Si es necesario, puede procesar por lotes cualquiera de los mensajes con otros usuarios para el envío y procesarlos en recepción desde dentro del lote.  
  
7.  Puede validar todos los mensajes en el motor y en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 esquemas X fabricado por la organización de HL7.  
  
## <a name="see-also"></a>Vea también  
 [Cómo resuelve BizTalk Server la necesidad empresarial](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)