---
title: Kit de desarrollo de software para el Acelerador para RosettaNet en BizTalk Server | Documentos de Microsoft
description: Lista de utilidades y ejemplos del SDK de BTARN de BizTalk Server
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36a1b283-26e1-407e-afc4-8879ef0d1672
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81bf0f7f0947875540d835ced3726224525f23a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="software-development-kit"></a>Kit de desarrollo de software
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] incluye un kit de desarrollo de software (SDK) que incluye la referencia y la Guía del programador completo. Además, el SDK incluye utilidades y ejemplos que pudieron realizar las operaciones y la integración de back-end sea más fácil.  
  
## <a name="utilities"></a>Utilidades  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye los siguientes ejemplos:  
  
|Utilidad|Utilice|  
|-------------|---------|  
|[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md)|Para anular la implementación de todos los [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] artefactos desde la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo del equipo host|  
|[BtarnConfig](../../adapters-and-accelerators/accelerator-rosettanet/btarnconfig.md)|Para importar o exportar datos de configuración|  
|[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)|Para importar un certificado|  
|[LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)|Para enviar un mensaje de acción o respuesta a un socio comercial|  
|[LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)|Para enviar un mensaje de acción o respuesta desde una página ASPX a un socio comercial|  
|[Bucle invertido](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)|Para generar un acuerdo de bucle invertido, establecer [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] una copia de seguridad en un único equipo|  
|[Componente de canalización del Editor de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-component.md)|Para editar automáticamente cualquier parte de un mensaje de varias partes dentro de un envío o la canalización de recepción|  
|[Componente de canalización del Inspector de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/message-inspector-pipeline-component.md)|Para examinar todas las partes de un mensaje de varias partes y el contexto del mensaje|  
|[SchemaValidator](../../adapters-and-accelerators/accelerator-rosettanet/schemavalidator.md)|Para solucionar problemas relacionados con una instancia de mensaje|  
|[TestCrypto](../../adapters-and-accelerators/accelerator-rosettanet/testcrypto.md)|Para solucionar errores de descifrado de mensajes|  
  
## <a name="samples"></a>Ejemplos  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye los siguientes ejemplos:  
  
|Ejemplo|Demostraciones|  
|------------|------------------|  
|[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)|Cómo enviar notificaciones cuando llega un mensaje|  
|[ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)|Cómo ejecutar las reglas de validación especiales en un mensaje recibido por la orquestación de socio comercial|  
|[Ejemplo de FileTransport](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md)|Cómo usar puertos de archivo, en lugar de los puertos SQL|  
|[Ejemplo de GetMessages](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)|Cómo recuperar mensajes de una de las tablas sin repudio o una de las tablas LOB en un formato legible|  
|[Ejemplo de ASPX de envío de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md)|Cómo enviar contenido de un servicio a un proceso privado|  
|[Ejemplo de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md)|Cómo mostrar el estado actual de mensajes y procesos|  
|[Orquestación de Respondedor privada de 3A4 mediante una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)|Cómo implementar un proceso de servicio de respuesta privada incorpora una regla de negocios|  
|[Orquestación PIPAutomation de acción doble](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)|Cómo implementar una orquestación para generar automáticamente las respuestas para procesos de interfaz de socio (PIP) de doble acción|  
|[Solicitud de 3A2 al ejemplo de asignación de respuesta de 3A2](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)|Cómo asignar una solicitud de 3A2 a una respuesta de 3A2|  
|[Solicitud de 3A4 al ejemplo de asignación de respuesta 3A4](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)|Cómo asignar una solicitud de 3A4 a una respuesta 3A4|  
|[Ejemplo de PrivateInitiator](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)|Cómo implementar el proceso privado del iniciador|  
|[Ejemplo de PrivateResponder](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)|Cómo implementar el proceso de servicio de respuesta privada|  
|[Ejemplo de HubScenario](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)|Cómo administrar la transmisión de mensajes en un escenario de concentrador|  
|[Canalización de envío](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md)|Cómo implementar una canalización de envío|  
|[La canalización de recepción](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md)|Cómo implementar una canalización de recepción|  
|[Ejemplo de canalización del Editor de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md)|Cómo modificar el contenido de un mensaje entrante|  
|[Ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)|Cómo modificar los esquemas|  
|[RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md)|Cómo preparar un mensaje para el procesamiento de RNIF y enviar el mensaje a la página de trabajo RNIFReceive.aspx en el servicio de respuesta|  
|[RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md)|Cómo recibir un mensaje RNIF y prepararlo para su procesamiento mediante la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proceso público|  
|[Detener e iniciar orquestaciones, puertos de envío y ubicaciones de recepción mediante programación](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)|Cómo detener e iniciar estos artefactos dinámicamente|  
  
## <a name="see-also"></a>Vea también  
 [Lo que agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [Ejemplos](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)