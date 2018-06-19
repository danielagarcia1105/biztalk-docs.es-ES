---
title: Enumerar, buscar y ordenar los mensajes de error | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 850b9682-8eba-4a3f-8508-d3eefcd715b7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768dd7f51ff09bad76115f8a7e2a95a11ce47981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294644"
---
# <a name="listing-searching-and-sorting-fault-messages"></a>Enumerar, buscar y ordenar los mensajes de error
Puede usar la página de inicio del Portal de administración de ESB para obtener una vista general del estado de las aplicaciones que se ejecutan en Microsoft BizTalk Server. La página de errores se puede usar para consultar los mensajes de error, en función de un intervalo de criterios.  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a>Para ver una descripción general del estado de las aplicaciones actuales de BizTalk Server  
  
1.  Abra la [página principal del Portal](../esb-toolkit/portal-home-page.md). Esta página muestra el estado general de la aplicación, un resumen de errores, solicitudes recientes para el registro de Universal Description, Discovery y Integration (UDDI) y gráficos que muestren un desglose de errores por tipo y por la aplicación.  
  
2.  Para seleccionar las aplicaciones para el que desea ver la información, haga clic en el **seleccionar aplicaciones** vincular por encima del primer gráfico y, a continuación, active o desactive las casillas de verificación en la lista de aplicaciones instaladas de BizTalk Server que aparece.  
  
3.  Para cambiar el período para el que el portal muestra información, seleccione **hora, día, semana, mes, trimestre, año,** o **todos los** en la lista desplegable situada encima del primer gráfico.  
  
4.  Para cambiar la configuración predeterminada utilizada en la página principal de la lista de aplicaciones y el período de presentación, modifique la configuración en el [página de configuración de Portal de mi](../esb-toolkit/portal-my-settings-page.md).  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a>Para obtener una lista, buscar y ordenar los mensajes en el Portal de administración de ESB de error  
  
1.  Abra la [página Configuración de error](../esb-toolkit/fault-settings-page.md). Esta página muestra una lista de propiedades para cada error truncada y admite el análisis de errores de una gama de criterios.  
  
2.  Para filtrar la lista de errores que se muestra en la página, use las listas desplegables y cuadros de texto situado encima de la lista de errores. Puede filtrar las filas mostradas por aplicación, período, número de código de error, nombre de la categoría de error, el texto del tipo de error y gravedad de error mínimo o máximo. Deje cualquiera de los controles en blanco para recuperar todos los mensajes independientemente de su valor para este criterio.  
  
3.  Haga clic en **aplicar filtros** para ver la lista de errores de coincidencia. Tenga en cuenta que el filtrado en las bases de datos de errores muy grandes puede tardar unos segundos para mostrar los resultados.  
  
4.  Para mostrar más o menos filas en la página, seleccione el valor adecuado en el **registros por página** lista desplegable.  
  
5.  Para ordenar la lista de mensajes de error, haga clic en un encabezado de columna. Para ordenar las filas en orden inverso, haga clic en la misma columna de encabezado de nuevo.  
  
6.  Haga clic en **exportar a Excel** para descargar la lista completa de los mensajes de error en un formato que se puede ver en Microsoft Excel.