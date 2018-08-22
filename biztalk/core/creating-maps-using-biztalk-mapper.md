---
title: Crear asignaciones usando el asignador de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- maps, creating
- orchestrations, maps
- translations [maps]
- maps, about maps
- transformations [maps]
- maps
ms.assetid: 265e61d8-8cff-44c9-a717-8e895cb4b9bf
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c12da6732729052119bfcc7841424db6d0dcaff9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238340"
---
# <a name="creating-maps-using-biztalk-mapper"></a>Crear asignaciones con el Asignador de BizTalk
El Asignador de BizTalk es una herramienta que se ejecuta en el entorno Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. El Asignador de BizTalk se puede usar para crear y editar asignaciones, que se utilizan para traducir o transformar mensajes xml. Las asignaciones se usan en orquestaciones, como sugiere la siguiente ilustración, y también se pueden usar para procesar los mensajes recibidos en un puerto de recepción y, a continuación, transformar los mensajes para su envío mediante puertos de envío.  
  
 ![Diagrama de procesamiento empresarial con asignaciones. ](../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")  
Asignaciones en procesamiento empresarial  
  
 Las asignaciones le permiten traducir y transformar mensajes. La traducción es el proceso por el que se convierte un mensaje de un formato en otro formato, como convertir un archivo sin formato en un archivo XML. La transformación es el proceso por el que se toma información de un mensaje y se inserta en otro. Por ejemplo, puede tomar las direcciones de envío y de facturación de un pedido e insertarlas en un documento de factura.  
  
 El Asignador de BizTalk utiliza su propio sistema gráfico de iconos y vínculos para representar la traducción y transformación de mensajes de instancia de entrada a mensajes de instancia de salida. El Asignador utiliza la misma representación gráfica de esquemas que el Editor de BizTalk. El Asignador de BizTalk almacena las asignaciones como hojas de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT).  
  
> [!NOTE]
>  El Asignador de BizTalk es compatible con XSLT 1.0. No se admite el uso de XSLT 2.0 en el Asignador de BizTalk.  
  
 Para obtener información sobre la creación de esquemas, vea [crear esquemas de uso del Editor BizTalk](../core/creating-schemas-using-biztalk-editor.md). Para obtener información sobre el uso de las asignaciones en orquestaciones, consulte [crear orquestaciones utilizando Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md).  
  
> [!NOTE]
>  El rendimiento de una asignación depende de la complejidad de la asignación: el número y el tipo de functoids, el tamaño de los esquemas de entrada y de salida, el tamaño del mensaje de entrada y el hardware.  
  
 Para obtener información sobre cómo usar métodos abreviados de teclado para el asignador de BizTalk, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Planear la creación de mapas](../core/planning-to-create-maps.md)  
  
-   [Acerca de las asignaciones](../core/about-maps.md)  
  
-   [Con el asignador de BizTalk](../core/using-biztalk-mapper.md)  
  
-   [Crear mapas](../core/creating-maps.md)  
  
-   [Compilar y probar las asignaciones](../core/compiling-and-testing-maps.md)  
  
-   [Solucionar problemas de asignaciones](../core/troubleshooting-maps.md)