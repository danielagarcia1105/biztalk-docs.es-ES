---
title: Ejemplo de escenario empresarial | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b88bd76a1fac2ebfa5c2f75a6abbf78aab75b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966909"
---
# <a name="sample-business-scenario"></a>Ejemplo de escenario empresarial
Los procesos de atención médica a menudo son complejos e implican muchos sistemas. Un ejemplo es el proceso que se produce cuando un paciente entra en un hospital y un médico envía al paciente para una prueba de laboratorio. Implicados en este procedimiento son cinco partes:  
  
- El informe del médico  
  
- El sistema de registro de Hospital  
  
- El sistema de entrada de pedidos clínica  
  
- El sistema de laboratorio  
  
- El sistema de facturación  
  
  En este proceso, podrían producirse los siguientes pasos:  
  
1.  El médico de asistir a registra al paciente.  
  
    1.  Un ADT ^ O04 mensaje de registro se difunde por el sistema de registro del Hospital.  
  
    2.  El ADT ^ O04 recibirlo por todos los departamentos que se suscriben al mensaje, incluido el sistema de entrada de orden clínicos y el sistema de laboratorio.  
  
2.  El médico pedidos de un estudio de diagnóstico desde la instalación de laboratorio.  
  
    1.  Un ORM ^ O01 mensaje del pedido se envía desde el sistema de entrada de pedidos clínicos, después de la validación de reglas de negocios.  
  
    2.  El ORM ^ O01 recibirlo por el sistema de laboratorio.  
  
3.  El laboratorio recibe el pedido y devuelve una confirmación.  
  
    1.  Un ORR ^ O02 mensaje de confirmación del pedido se envía por el sistema de laboratorio, que indica que se puede ejecutar el orden.  
  
    2.  El ORR ^ O02 recibirlo por el sistema de entrada de pedidos clínicos.  
  
4.  En la realización de las pruebas, el laboratorio envía los resultados para el médico y otros departamentos.  
  
    1.  Un ORU ^ R01 mensaje de resultados de pruebas se envía desde el sistema de laboratorio.  
  
    2.  El ORU ^ R01 recibirlo por el sistema de entrada de pedidos clínicos y el sistema de facturación.  
  
    3.  El motor de la interfaz envía un mensaje de correo electrónico al médico, que recibe los resultados de laboratorio en sus PDA inalámbrico.  
  
## <a name="the-btahl7-solution"></a>La solución BTAHL7  
 El escenario empresarial de ejemplo descrito anteriormente es un ejemplo de un sistema de atención médica que necesita la integración. Servidor MicrosoftBizTalk con acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) proporciona una solución para este escenario que incluye la funcionalidad siguiente:  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se integra todos los sistemas implicados en una organización de concentrador y radio. Cada sistema se comunica directamente con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. No tienen que comunicarse directamente entre sí.  
  
2. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] controla los mensajes codificados en HL7 de forma nativa. No se requiere ninguna codificación personalizada.  
  
3. El ADT ^ O04 mensaje de registro se difunde a todos los sistemas que se suscriban a ella. El modelo de mensajería de publicación-suscripción para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona flexibilidad en la configuración y mantenimiento de la lista de sistemas de suscripción al mensaje. Puede agregar a los sistemas o eliminarlos de la lista de suscripciones sin afectar al resto del sistema.  
  
4. La regla de negocios que se utiliza para validar el ORM ^ O01 mensaje de pedido puede cambiarse dinámicamente sin afectar al resto del sistema.  
  
5. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede configurarse para generar automáticamente el ORR ^ O02 mensaje de confirmación del pedido (ACK).  
  
6. Si es necesario, cualquiera de los mensajes con otros usuarios para el envío de lote y procesarlos en la recepción desde dentro del lote.  
  
7. Puede validar todos los mensajes en el motor y contra el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 esquemas X publican por la organización de HL7.  
  
## <a name="see-also"></a>Vea también  
 [Cómo resuelve BizTalk Server la necesidad empresarial](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)