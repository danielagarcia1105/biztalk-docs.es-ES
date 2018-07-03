---
title: Cómo crear una consulta en búsqueda de actividad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query Builder [BAM portal], creating queries
- queries [BAM], saving
- queries [BAM], creating
- queries [BAM], executing
- Query Builder [BAM portal], executing queries
- Query Builder [BAM portal], opening queries
- Query Builder [BAM portal], saving queries
- queries [BAM], opening
ms.assetid: 7940e47d-10e4-4eb1-b4e6-a8b98461e3a8
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd89ec71319a70c0330ebef80c7c8165cacf6c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989753"
---
# <a name="how-to-create-a-query-in-activity-search"></a>Cómo crear una consulta en Búsqueda de actividad
Los usuarios empresariales finales que necesiten recibir notificaciones de eventos y estados relativos a su actividad empresarial deben utilizar consultas para crear búsquedas de actividad en las que basar las alertas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe tener una vista implementada.  
  
### <a name="to-open-a-query"></a>Para abrir una consulta  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **sitio Web de Portal de BAM**.  
  
2. En el **Mis vistas** marco del portal, haga clic en una vista existente para expandir los menús disponibles en esa vista.  
  
3. Haga clic en **búsqueda de actividad** para expandir la lista de actividades disponibles para la vista.  
  
4. Haga clic en una actividad de la lista. Esto cargará la página Búsqueda de actividad de la actividad seleccionada.  
  
5. En el marco de contenido en la parte superior de la página, haga clic en el **examinar** botón para abrir el **Elegir archivo** cuadro de diálogo.  
  
6. Vaya a la carpeta donde ha guardado consultas anteriormente.  
  
7. Haga clic en una operación de Guardar consulta.  
  
8. Haga clic en el **abierto** botón. Esto cargará la ruta de acceso a la consulta en el cuadro de texto a la izquierda de la **examinar** botón. También puede escribir la ruta de la consulta directamente en el cuadro de texto.  
  
9. Haga clic en el **Abrir consulta** situado a la derecha de la **examinar** botón.  
  
### <a name="to-construct-a-query"></a>Procedimiento para generar una consulta  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **sitio Web de Portal de BAM**.  
  
2. En el **Mis vistas** marco del portal actualmente no hay una lista de las vistas configuradas. Debajo de cada vista se muestran tres tareas que se pueden realizar en dicha vista. Si la vista está contraída, haga clic en ella para expandir la lista de tareas.  
  
3. Haga clic en **búsqueda de actividad** para expandir la lista de actividades disponibles para la vista.  
  
4. Haga clic en una actividad de la lista. Esto cargará la página Búsqueda de actividad de la actividad seleccionada.  
  
5. En el marco de contenido en el **consulta** , seleccione un campo desde el **datos empresariales** lista desplegable que se usará para una comparación en la consulta.  
  
6. Desde el **operador** lista desplegable, seleccione el operador de comparación a usar.  
  
7. En el **valor** , escriba el valor para comparar. Solo podrá escribir un valor adecuado para el campo con el que está comparando. (Si el elemento de datos económicos es un campo de fecha, los datos de comparación son una fecha o una fecha y hora con el formato correspondiente a su configuración regional).  
  
8. Si tiene más cláusulas que agregar a la consulta, haga clic en el **agregar** situado a la derecha del cuadro de consulta. Esto agregará una línea nueva para la siguiente cláusula. Puede especificar si las cláusulas deben unirse utilizando AND u OR.  
  
   > [!NOTE]
   >  No puede agrupar cláusulas para formar consultas más complejas. Una consulta es un conjunto sencillo de cláusulas combinadas mediante un operador AND u OR.  
  
   > [!NOTE]
   >  Si hace clic en el botón Atrás durante estos procedimientos y recibe una "Advertencia: la página ha caducado" puede presionar F5 para regresar el contenido original. Es posible que tenga que presionar F5 varias veces.  
  
9. En el selector de columnas, seleccione los datos o hitos de la **datos e hitos disponibles** cuadro de lista para la consulta se devuelven como datos. Puede seleccionar varios elementos presionando la tecla MAYÚS mientras hace clic en el primer y último elemento del grupo que desea que se devuelva. También puede seleccionar varios elementos individuales de la lista presionando la tecla CTRL mientras selecciona los elementos que desea obtener.  
  
10. Use la **>>** botón para mover los elementos seleccionados a la **elementos para mostrar** cuadro de lista. Se pueden quitar elementos de esta lista seleccionándolos y usando el **<<** botón para volver al cuadro de lista datos e hitos.  
  
11. Una vez seleccionados todos los elementos que debe devolver la consulta, puede reorganizar los resultados para determinar el orden de aparición de las columnas. Para mover una columna a la primera posición en el conjunto de datos devuelto, selecciónela haciendo clic en ella y haciendo clic en el **Subir** botón hasta que esté en la parte superior de la lista de elementos. De forma similar, para mover un elemento a una posición posterior en el conjunto de datos devuelto, seleccione el elemento haciendo clic en él y, a continuación, haciendo clic en el **Bajar** botón hasta que se encuentra en la posición en la que desea mostrar.  
  
### <a name="to-save-a-query"></a>Para guardar una consulta  
  
1.  En el marco de contenido en la parte superior de la página, haga clic en el **Guardar consulta** botón para abrir el **Guardar archivo** cuadro de diálogo.  
  
2.  En el **de descarga del archivo** cuadro de diálogo, haga clic en el **guardar** botón.  
  
3.  Desplácese hasta la ubicación en que desea guardar la consulta.  
  
4.  Puede aceptar el nombre predeterminado proporcionado para la consulta o puede escribir un nombre nuevo en el **nombre de archivo** cuadro de texto.  
  
5.  Haga clic en el **guardar** botón.  
  
### <a name="to-execute-a-query"></a>Para ejecutar una consulta  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **sitio Web de Portal de BAM**.  
  
2. En el **Mis vistas** marco del portal, haga clic en una vista existente para expandir los menús disponibles en esa vista.  
  
3. Haga clic en **búsqueda de actividad** para expandir la lista de actividades disponibles para la vista.  
  
4. Haga clic en una actividad de la lista. Esto cargará la página Búsqueda de actividad de la actividad seleccionada.  
  
5. Abra una consulta existente o cree una nueva.  
  
6. En el marco de contenido del portal, haga clic en el **Ejecutar consulta** botón.  
  
## <a name="see-also"></a>Vea también  
 [Búsquedas de actividad del portal de BAM](../core/activity-searches-in-the-bam-portal.md)