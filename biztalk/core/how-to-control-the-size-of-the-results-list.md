---
title: Cómo controlar el tamaño de la lista de resultados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- results list [Orchestration Debugger], deleting columns
- results list [Orchestration Debugger], limiting list size
- Orchestration Debugger, results list
- results list [Orchestration Designer]
- results list [Orchestration Debugger], adding columns
ms.assetid: 4d41003f-5ea9-4599-8ec0-737c342ffdbd
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80787e4c7dbac57aca9c787943846e924a1a7870
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249740"
---
# <a name="how-to-control-the-size-of-the-results-list"></a>Cómo controlar el tamaño de la lista Resultados
En el **concentrador de grupo** página de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, los resultados de consulta panel contiene tantas columnas de información que tenga que desplazarse para verlas. Puede agregar o quitar columnas del panel para mostrar únicamente la información que necesite. Para agregar o quitar columnas, haga clic en cualquier parte del panel de resultados de consulta y haga clic en **agregar o quitar columnas** en el menú contextual.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-add-or-remove-columns-in-the-results-list"></a>Procedimiento para agregar o quitar columnas en la lista de resultados  
  
1.  Haga clic en cualquier celda de la **resultados de la consulta** lista y, a continuación, haga clic en **agregar o quitar columnas** en el menú contextual.  
  
    > [!NOTE]
    >  Elementos que ya están presentes en la lista de resultados aparecen en la parte derecha debajo **columnas mostradas**. Elementos que no están presentes en la lista de resultados aparecen en el lado izquierdo en **columnas disponibles**.  
  
2.  Para agregar una columna, seleccione uno de los elementos de **columnas disponibles** y haga clic en **agregar** para mover dicha columna a la lista de **columnas mostradas**.  
  
3.  Para quitar una columna, seleccione uno de los elementos de **columnas mostradas** y haga clic en **quitar** para mover dicha columna a la lista de **columnas disponibles**.  
  
 Puede controlar el número de resultados que devuelve la consulta usando los filtros que se proporcionan al crear o ejecutar una consulta.  
  
## <a name="columns-in-the-query-results-list"></a>Columnas de la lista Resultados de la consulta  
 Los resultados de la consulta se muestran en el panel Resultados de la consulta, en la parte inferior de la vista que originó la consulta. No se puede obtener acceso directamente a la lista de resultados. El menú contextual muestra todas las acciones que puede realizar en el registro seleccionado desde la vista activa. Por ejemplo, si el registro contiene un Id. de instancia de servicio, se mostrarán las acciones relativas a dicho servicio. Si existe un Id. de mensaje, aparecerán las acciones relativas al mensaje.  
  
 Es posible que no necesite toda la información contenida en la lista, de modo que puede seleccionar solo las columnas que desea ver, o volver a seleccionar columnas que haya quitado previamente. Al ordenar la lista de resultados por hora, las instancias se ordenan por milisegundos, aunque no aparezcan los milisegundos en la lista. Si vuelve a usar una consulta guardada, los resultados mostrarán solo las columnas seleccionadas cada vez que se ejecute la consulta.  
  
 En la tabla siguiente se muestra una lista completa de los elementos que aparecen en la lista de resultados.  
  
|||  
|-|-|  
|**Campo de mensaje o servicio**|**Description**|  
|Nombre de servicio|Nombre de la instancia de servicio.|  
|Tipo de evento|Tipo de servicio. Por ejemplo, mensajería (aparece como “canalización” en el informe), orquestación, adaptador de transporte.|  
|Descripción del error|Descripción del error si se ha producido uno.|  
|State|Estado de la operación cuando se ejecutó la consulta.|  
|Código de error|Código del error si se ha producido uno.|  
|Certificado de descifrado|Muestra la información del certificado relativa al mensaje o servicio.|  
|Duración|Tiempo para que finalice la operación.|  
|Nombre de puerto|Puerto implicado en el flujo de la instancia.|  
|Signature|Información de firma digital del mensaje.|  
|Tamaño|Tamaño del mensaje en bytes.|  
|Start Time|Tiempo de la operación iniciada.|  
|Hora de finalización|Hora en que la operación ha finalizado.|  
|Número de partes|Número de partes del mensaje|  
|Party|Identificador de la entidad que inició la operación.|  
|URI|URI de la entidad iniciadora.|  
|TimeStamp|Tiempo de la operación iniciada.|  
|Host|Nombre de host de BizTalk que ejecuta la instancia de servicio.|  
|Nombre de ensamblado|Nombre del ensamblado de .NET que implementa la instancia de servicio.|  
|Versión del ensamblado|Número de versión del ensamblado asociado.|  
|Tiempo de implementación|Hora de implementación de la instancia de servicio en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|Id. de actividad|Identifica la actividad de la instancia de servicio exclusiva (por ejemplo, mensajes enviados o recibidos por la canalización u orquestación tienen el mismo identificador).|  
|Id. de instancia de servicio|Identificador único global (GUID) que identifica una ejecución de una instancia de servicio.|  
|Id. de instancia de mensaje|Identificador único global (GUID) que identifica una instancia de mensaje.|  
|Id. de servicio|Identificador único global (GUID) que identifica un servicio.|  
|Servicio (clase)|Tipo de clase (canalización u orquestación).|  
|Id. de clase de servicio|GUID de servicio independiente que identifica un servicio (por ejemplo, una orquestación).|  
|Icono|Icono de la fila de resultados.|  
|Adaptador|Adaptador usado en la operación.|