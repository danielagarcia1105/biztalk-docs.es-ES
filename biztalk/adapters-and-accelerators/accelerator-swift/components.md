---
title: Componentes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, components
ms.assetid: 8793534f-5bd7-4cd3-9a42-8f0895f91007
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c8595aafb14b42240a5f781faf481977be2b821
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014685"
---
# <a name="components"></a>Components
Utilice Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] relaciones, integración de aplicaciones empresariales (EAI) y aplicación y automatización de flujo de trabajo de negocio de componentes para implementar soluciones de software intermedio centrado en SWIFT que facilitan el comercio asociado. Estos componentes incluyen:  
  
- **Esquemas de mensaje SWIFT.** Usar lenguaje de definición de esquema XML (XSD)-componentes de canalización compatible con esquemas para facilitar el análisis de los mensajes de archivo sin formato SWIFT nativo en XML con SWIFT y [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución. Después de convertir datos SWIFT en XML, utilice un mapa de transformarlo en otro formato, como archivos sin formato delimitados o archivos sin formato posicionales. Esta transformación permite usar estos archivos en las aplicaciones existentes. También puede usar los datos XML sin ninguna asignación, por ejemplo, para escenarios de solo validación. Esquemas de SWIFT también aplican reglas de datos y el formato definido por el SWIFT. Para obtener una lista completa de los esquemas que se proporcionan en esta versión, consulte [admite mensajes](../../adapters-and-accelerators/accelerator-swift/supported-messages.md).  
  
- **Las directivas de validación de SWIFT y marco de trabajo.** Usa [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] directivas del motor de reglas de negocios (BRE) para validar y aplicar reglas de formato, datos, red y uso definidas en SWIFT. El Desensamblador de SWIFT y [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] componente de validación de invocar el BRE. Errores de validación se recopilan en los objetos de colección de errores y mensajes erróneos se marcan con propiedades promocionadas especiales antes de que se publican en la base de datos de cuadro de mensajes.  
  
- **Componentes de canalización de SWIFT.** Utilice los componentes de desensamblador y ensamblador de canalización de BizTalk para procesar los mensajes de SWIFT. El Desensamblador de SWIFT dinámicamente resuelve los tipos de mensaje SWIFT, Desensambla los lotes de mensajes SWIFT, analiza los mensajes en XML y valida los mensajes con respecto a los formatos de datos SWIFT y reglas de red y el uso. El ensamblador de SWIFT serializa los datos XML en formato de archivo sin formato SWIFT.  
  
- [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]  **Componente de validación.** El [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] ensamblado proporciona la clase application interfaces de programación (API) que se pueden usar en formas de expresión de orquestación de BizTalk. Estas clases proporcionan la misma funcionalidad de validación de mensaje SWIFT que realiza el Desensamblador SWIFT. Esta funcionalidad permite la validación de mensajes que tienen lugar en orquestaciones (por ejemplo, después de transformar o modificación de un mensaje SWIFT).  
  
- **Reparación de mensajes y nuevo envío.** Use la característica de reparación de mensajes y nuevo envío para reparar los mensajes que no superan la validación o que no se puede analizar el Desensamblador de SWIFT, o para crear y enviar mensajes nuevos. Esta característica se implementa a través de la orquestación MrsrRepair, sitio de SharePoint de MRSR, y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios.  
  
- **Conciliación de respuestas de FRR.** Conciliación de respuestas de FRR reconcilia una respuesta FIN con el mensaje que se envió originalmente por A4SWIFT, habilitar el procesamiento personalizado del conjunto resultante de correlación de mensajes de solicitud-respuesta. FRR se implementa a través de la orquestación FrrMain, la FRR ubicación de recepción y puertos de envío y el adaptador de BizTalk para MQSeries.  
  
- **Kit de desarrollo de software (SDK).** El SDK proporciona herramientas, tutoriales y ejemplos para facilitar el desarrollo e implementación de soluciones de BizTalk basado en SWIFT. Estas soluciones se incluyen:  
  
  -   [Tutorial integral](../../adapters-and-accelerators/accelerator-swift/end-to-end-tutorial2.md)  
  
  -   [Utilidad de implementación de BRE](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)  
  
  -   [Esquemas de finalizadores y encabezados de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
- **Documentación.** [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Ayuda describe lo que necesita para planear, desarrollar, implementar y mantener las soluciones de BizTalk basado en SWIFT.  
  
## <a name="see-also"></a>Vea también  
[Tiempo de ejecución, reparación de mensajes, respuesta FIN y mensajería](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)