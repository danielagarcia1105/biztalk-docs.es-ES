---
title: 'Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados | Documentos de Microsoft'
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
ms.openlocfilehash: 7af49c026b443fb1ca6a0fb7f35b64cdf1e377f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222628"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a>Lección 3: Ejecutar un procedimiento almacenado para seleccionar a nuevos empleados agregados
Antes de la descripción de las tareas realizadas en esta lección, primero debe entender qué son necesarias estas tareas. El **empleado** tabla a la que se insertan los registros para agregar un nuevo empleado se define de tal manera que un **estado** columna siempre se establece en "0" cada vez que se agrega un nuevo empleado. Esto se hace para que puedan utilizar esta columna para consultar los empleados recién agregados y obtener notificaciones. En SQL Server, debería consultar ejecutando la siguiente instrucción SQL:  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 Después de recibir la lista de recién agregado empleados, también debe actualizar el **estado** columna a "1" para que la próxima vez que se agregan nuevos empleados y ejecutar la misma consulta, no obtener registros de empleados antiguos así. Para asegurarse de que la instrucción Select anterior le proporciona solo los empleados recién agregados, actualizará el **empleado** tabla utilizando la instrucción SQL siguiente:  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 Por lo tanto, la **estado** columna para los empleados anteriores se establece en "1", mientras que los empleados nuevos siempre es "0".  
  
 En esta lección, se ejecutará un procedimiento almacenado, **UPDATE_EMPLOYEE**, que a su vez ejecuta las instrucciones Select y Update. Cuando haya terminado de esta lección, la orquestación hará lo siguiente:  
  
1.  Recibe la notificación de los cambios realizados en el **empleado** tabla.  
  
2.  Extrae el tipo de notificación recibe el mensaje de notificación.  
  
3.  Si el mensaje de notificación es para una operación de inserción, la orquestación ejecuta la **UPDATE_EMPLOYEE** procedimiento almacenado.  
  
4.  El procedimiento almacenado lee los registros recién especificados en la **empleado** tabla. Después de leer los nuevos registros, el procedimiento almacenado también establece la **estado** columna para dichos registros a "1".  
  
 Ahora ya sabe por qué necesita ejecutar el procedimiento almacenado. Debe pensar en cómo se ejecuta como parte de la orquestación. La orquestación necesita un mensaje de solicitud para la **UPDATE_EMPLOYEE** procedimiento almacenado. En este tutorial, creará una biblioteca de clases personalizadas que creará el mensaje sobre la marcha y, a continuación, se proporcionan a la orquestación. Después de que la orquestación recibe el mensaje, enviará el mensaje a SQL Server mediante el adaptador de SQL y recibir la respuesta.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Crear el mensaje de solicitud de UPDATE_EMPLOYEE procedimiento almacenado](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir respuesta](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)