---
title: Samples3 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SDK samples
- examples, developing
- developing, examples
ms.assetid: b940111e-4f71-494b-b7a3-d2e8310bea51
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f509668bb8da8021b14a7252a3902cb01da9fd5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006117"
---
# <a name="samples"></a>Ejemplos
Esta sección describen los ejemplos incluidos en el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Kit de desarrollo de Software (SDK). Esta sección proporciona información detallada sobre cada ejemplo, incluido cómo generar el ejemplo, cómo ejecutarlo y los resultados que se esperan.  

 Los ejemplos se incluyen en el \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador de la carpeta RosettaNet\SDK\.  

## <a name="in-this-section"></a>En esta sección  

- Carpeta de ejemplos de adaptador  

  -   [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md). Muestra cómo incluir un mecanismo de notificación de mensaje.  

  -   [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md). Muestra cómo ejecutar las reglas de validación especiales en un mensaje.  

- Carpeta de ejemplos de mensajería  

  -   [Ejemplo de FileTransport](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md). Muestra cómo configurar BTARN para usar puertos de archivo.  

  -   [Ejemplo de GetMessages](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md). Muestra cómo recuperar mensajes desde cualquiera de las tablas de rechazo o una de las tablas de línea de negocio (LOB).  

  -   [Ejemplo ASPX de envío del mensaje](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md). Proporciona código .aspx de ejemplo para enviar contenido a un proceso privado del servicio. También proporciona el HTML para enviar un mensaje de acción de proceso de interfaz de socio (PIP) a ese contenido de servicio.  

  -   [Ejemplo de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md). Proporciona código .aspx de ejemplo para ver el estado de los mensajes enviados y recibidos con BTARN.  

- Carpeta de ejemplos de orquestación  

  -   [Orquestación del Respondedor privado 3A4 mediante una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md). Muestra cómo automatizar un proceso empresarial que implican PIP mediante un mapa de transformar un mensaje de solicitud a un mensaje de respuesta.  

  -   [Orquestación PIPAutomation de acción doble](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md). Muestra cómo automatizar un proceso empresarial, con determinación automática del tipo de mensaje de respuesta según el tipo de mensaje entrante.  

  -   [Solicitud de 3A2 al ejemplo de asignación de respuesta de 3A2](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md). Muestra cómo asignar un esquema de solicitud de 3A2 a un esquema de respuesta de 3A2.  

  -   [Solicitud de 3A4 al ejemplo de asignación de respuesta de 3A4](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md). Muestra cómo asignar un esquema de solicitud de 3A4 a un esquema de respuesta de 3A4.  

  -   [Ejemplo de PrivateInitiator](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md). Muestra cómo crear una orquestación de procesos privado del iniciador.  

  -   [Ejemplo de PrivateResponder](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md). Muestra cómo crear una orquestación de proceso privado del Respondedor.  

  -   [Ejemplo de HubScenario](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md). Muestra cómo transformar un mensaje enviado a un concentrador intermediario, en un mensaje que se enviará al destinatario final.  

- Carpeta de ejemplos de canalización  

  - [Canalización de envío](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md). Muestra cómo procesar mensajes XML salientes en mensajes RNIF equivalentes mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalizaciones.  

  - [Canalización de recepción](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md). Muestra cómo procesar los mensajes entrantes de RNIF en mensajes XML equivalentes mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalizaciones.  

  - [Ejemplo de canalización del Editor de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md). Muestra cómo crear un componente de canalización personalizado para modificar los mensajes entrantes.  

- Carpeta de ejemplos de esquema  

  -   [Ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md). Describe los esquemas de ejemplo proporcionados en el SDK, incluidos los esquemas XML de PIP, esquemas de próxima generación de RosettaNet y esquemas RNIF. Incluye punteros a los procedimientos para usar estos esquemas.  

- Carpeta de ejemplo de aplicación Web  

  -   [RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md). Muestra cómo personalizar la página ASPX que envía mensajes de RNIF del iniciador para el servicio de respuesta.  

  -   [RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md). Muestra cómo personalizar la página ASPX que recibe los mensajes RNIF en el servicio de respuesta.  

- [Detener e iniciar orquestaciones, puertos de envío y ubicaciones de recepción mediante programación](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md). Muestra cómo detener e iniciar todas las orquestaciones, puertos de envío y recibir ubicaciones, como un grupo o de forma individual.
