---
title: 'Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec7897e9-0c77-41b2-8cc2-61745bd3b028
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3021a5e3ead821a0f3c8d0372d48ae469a834c1c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001861"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a>Lección 3: Ejecutar un procedimiento almacenado para seleccionar a nuevos empleados agregados
Antes de la descripción de las tareas realizadas en esta lección, primero debe comprender por qué se requieren estas tareas. El **empleado** tabla a la que se insertan los registros para agregar un nuevo empleado se define de tal manera que un **estado** columna siempre se establece en "0" cada vez que se agrega un nuevo empleado. Esto se hace para que pueda usar esta columna para consultar los empleados recién agregados y también recibir notificaciones. En SQL Server, podría consultar mediante la ejecución de la siguiente instrucción SQL:  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 Después de recibir la lista de recién agregado empleados, también debe actualizar el **estado** columna en "1" para que la próxima vez que se agregan nuevos empleados y ejecutar la misma consulta, no podrá obtener registros de antiguos empleados también. Para asegurarse de que la instrucción Select anterior le proporciona solo los empleados recién agregados, se actualizará la **empleado** tabla mediante la instrucción SQL siguiente:  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 Por lo tanto, el **estado** columna para los empleados antiguos se establece en "1" mientras que los empleados nuevos siempre es "0".  
  
 En esta lección, ejecutará un procedimiento almacenado, **UPDATE_EMPLOYEE**, que a su vez ejecuta las instrucciones Select y Update. Cuando haya terminado esta lección, la orquestación hará lo siguiente:  
  
1. Recibe la notificación de los cambios realizados en el **empleado** tabla.  
  
2. Extrae el mensaje de notificación que recibe el tipo de notificación.  
  
3. Si el mensaje de notificación es para una operación de inserción, la orquestación ejecuta la **UPDATE_EMPLOYEE** procedimiento almacenado.  
  
4. El procedimiento almacenado lee los registros recién introducidos en el **empleado** tabla. Después de leer los nuevos registros, el procedimiento almacenado también establece la **estado** columna para aquellos registros en "1".  
  
   Ahora ya sabe por qué necesita ejecutar el procedimiento almacenado. Ahora deberá pensar en cómo se ejecuta como parte de la orquestación. La orquestación necesita un mensaje de solicitud para el **UPDATE_EMPLOYEE** procedimiento almacenado. En este tutorial, creará una biblioteca de clases personalizadas que se creará el mensaje sobre la marcha y, a continuación, se proporcionan a la orquestación. Después de que la orquestación recibe el mensaje, enviará el mensaje a SQL Server mediante el adaptador de SQL y recibir la respuesta.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Crear el mensaje de solicitud para el procedimiento almacenado UPDATE_EMPLOYEE](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir la respuesta](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)