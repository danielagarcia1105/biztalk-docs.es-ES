---
title: Informe de estado de lote | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04dad016-e7bb-45cd-b36a-a9c83d073501
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c033f58432c8ae5a2d87b87b56223b8f64a7201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231804"
---
# <a name="batch-status-report"></a>Informe de estado de lotes
Este informe muestra la actividad de instancias de la orquestación por lotes. Cada fila del informe indica el estado de los lotes que se van a procesar mediante una única instancia de la orquestación por lotes.  
  
 No se notifica el estado de los lotes conservados en el informe de estado de lotes, pero se notifica en el informe de estado de confirmación o de intercambio.  
  
## <a name="fields-in-the-status-report"></a>Campos del informe de estado  
 El informe de estado de lotes muestra la siguiente información para los intercambios por lotes:  
  
-   Estado del lote  
  
-   Nombre de lote  
  
-   Nombre de entidad de destino  
  
-   Hora de activación  
  
-   Repeticiones de lotes  
  
-   Tipo de codificación EDI  
  
-   Tipo de lote  
  
-   Destino de lote  
  
-   Número de elementos de lote: el número de elementos por lotes ha acumulado la instancia de orquestación de procesamiento por lotes  
  
-   Número de elementos rechazados  
  
-   Última acción: Puede ser lote activado, lanzamiento programado, lanzamiento basado en el recuento, lanzamiento de invalidación Manual, lanzamiento detenido/terminado del lote, elemento agregado o versión externo  
  
-   Número de Control de intercambio  
  
-   Fecha y hora de intercambio  
  
-   Tamaño del lote (en caracteres) (no se muestra de forma predeterminada)  
  
## <a name="view-related-interchanges-status-reports"></a>Ver informes de estado de intercambios relacionados  
 Si hace clic con el botón secundario en un intercambio o confirmación que se enumera en el informe de estado de lotes, puede visualizar los detalles sobre los intercambios relacionados con el lote.  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>Campos de Expresión de consulta para el informe de estado  
 Para personalizar el informe de estado de lotes, cambie los campos de la expresión de consulta que determina los datos que se muestran. Están disponibles los campos siguientes:  
  
|||||  
|-|-|-|-|  
|Campo Expresión de consulta|Operadores potenciales|Valores potenciales|¿Incluido de forma predeterminada?|  
|Buscar|Es igual a|Estado del lote|Sí (obligatorio)|  
|Estado del lote|Es igual a<br /><br /> No es igual a|Define: La instancia de proceso por lotes está configurada pero fecha y hora de inicio es posterior a la hora de la fecha actual.<br /><br /> Activo (predeterminado): la instancia de lotes se configura y recopilan conjuntos de transacciones para un lote. La fecha y hora de inicio es anterior a las actuales.<br /><br /> Fecha de publicación: Se ha cumplido los criterios de lanzamiento y se ha enviado el lote o que la orquestación del lote se ha detenido antes de procesar los mensajes.<br /><br /> Completado: Se ha cumplido los criterios de versión, pero no se ha enviado el lote.<br /><br /> Todo: Mostrar cualquier instancia de lotes que se encuentra en uno de los estados anteriores.|Sí|  
|N.º máximo de coincidencias|Es igual a|Entero (predeterminado de 50)|Sí|  
|Fecha y hora de activación|Menor o igual que<br /><br /> Mayor o igual que|Fecha/hora<br /><br /> Hoy<br /><br /> Hoy en día - 5|No<br /><br /> Nota: se puede incluir más de una vez en la expresión de consulta.|  
|Nombre de lote|Es igual a|Todo (predeterminado)<br /><br /> Nombre de lote específico|No|  
|Entidad de destino|Es igual a|All (valor predeterminado)<br /><br /> Nombre de entidad específico|No|  
|Tipo de codificación EDI|Es igual a|X12<br /><br /> EDIFACT<br /><br /> All (valor predeterminado)|No|  
  
