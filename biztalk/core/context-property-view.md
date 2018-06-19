---
title: Vista propiedad de contexto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- Context Property view [Tracking Profile Editor]
- Tracking Profile Editor, Context Property view
- message schemas, XML messages
ms.assetid: 17a21b86-995c-4dc2-9a3c-1309837d0b9b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a0f3a1d507e1440f67cd5f9e4afa18bff0b52a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237884"
---
# <a name="context-property-view"></a>Vista Propiedad de contexto
La vista Propiedad de contexto muestra el esquema del mensaje XML asociado a la propiedad. La vista está disponible desde el menú contextual para algunas de las formas de la vista Programación de orquestación.  
  
## <a name="working-with-the-context-property-view"></a>Trabajar con la vista Propiedad de contexto  
 Seleccione la vista de la propiedad de contexto haciendo clic en el **Seleccionar origen de eventos** botón y haciendo clic en el **Seleccionar propiedad de contexto** elemento de menú. A continuación, seleccione una propiedad de contexto desde la lista de propiedades de contexto conocidas para cargar el esquema para esa propiedad. Una vez seleccionada la propiedad, puede arrastrar los elementos del esquema asociado a las carpetas de elementos de datos de la actividad. De esta manera, se indica que desea extraer en esta acción esos datos de la expresión XPath específica del mensaje.  
  
 Puede abrir las vistas de propiedad de contexto desde la vista de programación de orquestación al hacer clic con el botón secundario en una forma que contenga una propiedad de contexto. Se abrirá un menú contextual desde el que puede hacer clic en el **esquema de propiedades de contexto** elemento de menú para recuperar una lista de propiedades de contexto asociado a la forma.  
  
 La lista de propiedades de contexto disponibles puede ser amplia. Si conoce parte del nombre de la propiedad que está buscando, puede escribirla en el **en cadena** cuadro de texto y haga clic en el **búsqueda** botón. De este modo, se seleccionarán solo las propiedades que contengan la cadena parcial que ha escrito.  
  
> [!NOTE]
>  Cuando elige asignar desde la vista de propiedades de contexto, la lista de esquemas de propiedad es una lista completa de todos los esquemas de propiedad que se configuraron durante la instalación de BizTalk Server.  Debe tener en cuenta que los esquemas que se muestran no dependen de las características de BizTalk Server que se utilizan durante el proceso en ejecución con el que está trabajando. Por ejemplo, puede seleccionar un esquema para las propiedades SOAP de la lista de esquemas que se ofrecen cuando se realiza una asignación a partir de las propiedades de contexto, pero puede que el propio proceso en ejecución no utilice SOAP. Cualquier elemento de actividad de BAM que se haya asignado a partir de una propiedad sin usar, hace que los datos que captura BAM sean nulos o estén vacíos.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es la vista del origen de eventos?](../core/what-is-the-source-event-view.md)   
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)