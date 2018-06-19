---
title: Componentes | Documentos de Microsoft
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
ms.openlocfilehash: 6ca9c5fdb04ffd182a8c51963c1a5c7cf5e7f8c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210516"
---
# <a name="components"></a>Components
Usa [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] componentes para implementar soluciones de middleware centradas en SWIFT que facilitan la comerciales relaciones, integración de aplicaciones empresariales (EAI) y aplicación y automatización del flujo de trabajo de negocios de socios comerciales. Estos componentes incluyen:  
  
-   **Esquemas de mensaje SWIFT.** Usar el lenguaje de definición de esquemas XML (XSD)-componentes de canalización compatible con esquemas para facilitar el análisis de los mensajes de archivo sin formato SWIFT nativo en XML mediante el rápido y [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución. Después de convertir datos SWIFT en XML, se utiliza una asignación para transformar en otro formato, como archivos sin formato delimitados o archivos sin formato posicionales. Esta transformación le permite usar estos archivos en las aplicaciones existentes. También puede usar los datos XML sin ninguna asignación, como para los escenarios de solo validación. Esquemas SWIFT también aplican reglas de datos y el formato definido para SWIFT. Para obtener una lista completa de los esquemas proporcionados en esta versión, consulte [admite mensajes](../../adapters-and-accelerators/accelerator-swift/supported-messages.md).  
  
-   **Las directivas de validación de SWIFT y marco de trabajo.** Usa [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] directivas del motor de reglas de negocios (BRE) para validar y aplicar reglas de datos, formato, red y uso definidas por el SWIFT. El Desensamblador SWIFT y [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] el BRE de invocación del componente de validación. Errores de validación se recopilan en los objetos de colección de errores y mensajes erróneos se marcan con propiedades promocionadas especiales antes de publicarse en la base de datos de cuadro de mensajes.  
  
-   **Componentes de canalización SWIFT.** Utilice los componentes de desensamblador y de ensamblador de canalización de BizTalk para procesar los mensajes de SWIFT. El Desensamblador SWIFT dinámicamente resuelve los tipos de mensaje SWIFT, desensambla lotes de mensajes SWIFT, analiza mensajes en XML y valida los mensajes con formatos de datos sencilla y las reglas de red y el uso. El ensamblador de SWIFT serializa datos XML en formato de archivo sin formato SWIFT.  
  
-   [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]  **Componente de validación.** La [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] ensamblado proporciona la clase aplicación interfaces de programación (API) que pueden usarse en formas de expresión de orquestación de BizTalk. Estas clases proporcionan la misma funcionalidad de validación de mensaje SWIFT realizada el Desensamblador SWIFT. Esta funcionalidad permite la validación del mensaje que se realicen en orquestaciones (por ejemplo, después de transformar o modificar un mensaje SWIFT).  
  
-   **Reparación de mensajes y nuevo envío.** Utilice la característica de reparación de mensajes y nuevo envío para reparar los mensajes que no superan la validación o que no se puede analizar el Desensamblador SWIFT, o para crear y enviar mensajes nuevos. Esta característica se implementa a través de la orquestación MrsrRepair, el sitio de SharePoint de MRSR, y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios.  
  
-   **Conciliación de respuesta FRR.** Conciliación de respuesta FRR reconcilia una respuesta FIN con el mensaje enviado originalmente por A4SWIFT, permitiendo un procesamiento personalizado del conjunto de correlación del mensaje de respuesta resultante. FRR se implementa a través de la orquestación FrrMain, la FRR ubicación de recepción y puertos de envío y el adaptador de BizTalk para MQSeries.  
  
-   **Kit de desarrollo de software (SDK).** El SDK proporciona herramientas, tutoriales y ejemplos para facilitar el desarrollo e implementación de soluciones de BizTalk basada en SWIFT. Estas soluciones incluyen:  
  
    -   [Tutorial de extremo a extremo](../../adapters-and-accelerators/accelerator-swift/end-to-end-tutorial2.md)  
  
    -   [Utilidad de implementación de BRE](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)  
  
    -   [Esquemas de finalizador y encabezado SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
-   **Documentación.** [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]Ayuda describe lo que necesita planear, desarrollar, implementar y mantener las soluciones de BizTalk basada en SWIFT.  
  
## <a name="see-also"></a>Vea también  
[En tiempo de ejecución, reparación de mensajes, respuesta FIN y de mensajería](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)