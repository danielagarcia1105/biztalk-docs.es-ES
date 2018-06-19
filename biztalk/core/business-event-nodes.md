---
title: Nodos de eventos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, Tracking Profile Editor
- events, date specific
- events, time specific
- Tracking Profile Editor, node descriptions
- Business Event nodes [Tracking Profile Editor]
- Tracking Profile Editor, events
ms.assetid: 177bc3c4-e762-42fe-80bc-edede5cd4fcd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44c3d06e553f129abb36eb53c4dde9c5ab9c25f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230908"
---
# <a name="business-event-nodes"></a>Nodos de eventos empresariales
Los nodos de hitos o eventos empresariales definen eventos que son específicos de la fecha o la hora. Las carpetas de hito o evento empresarial predefinidas existen en la definición de actividad que importa del usuario empresarial final y no las puede eliminar sin tener que volver a importar el archivo de definición de actividad.  
  
## <a name="working-with-business-event-nodes"></a>Trabajar con nodos de eventos empresariales  
 Puede arrastrar formas a la carpeta Eventos empresariales desde la orquestación para realizar el seguimiento de aquellos eventos a medida que se completa la ejecución de las formas.  
  
 TPE utiliza el nombre de la forma para el nombre de la carpeta de evento y esta carpeta tendrá un icono único. Por ejemplo, en el caso del ejemplo de proceso de préstamo, TPE los denomina según el evento, como Aprobado o Denegado. solo debería realizar el seguimiento de eventos empresariales una vez por proceso empresarial cuando el proceso empresarial abarque varios perfiles de seguimiento. Si tiene una ruta condicional en su orquestación, puede seleccionar el evento empresarial de ambas rutas, ya que solo uno de ellos se ejecutará. No debería seleccionar una forma dentro de un bucle.  
  
> [!NOTE]
>  Aunque no puede eliminar carpetas sin tener que volver a importar la definición de actividad, puede eliminar formas (eventos).  
  
## <a name="see-also"></a>Vea también  
 [Nodos de vista de actividad TPE](../core/tpe-activity-view-nodes.md)