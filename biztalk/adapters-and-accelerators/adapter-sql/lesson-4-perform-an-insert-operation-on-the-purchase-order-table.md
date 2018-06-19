---
title: 'Lección 4: Realizar una operación de inserción en la tabla de orden de compra | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66fc64c5-a3da-4014-8545-f34e6577bd73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c966e3c10f18424b2cfb1fde0235caedbb5f58f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222692"
---
# <a name="lesson-4-perform-an-insert-operation-on-the-purchase-order-table"></a>Lección 4: Realizar una operación de inserción en la tabla de orden de compra
En [lección 3: ejecutar un procedimiento almacenado que seleccione a nuevos empleados agregar](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md), que ha ejecutado el **UPDATE_EMPLOYEE** procedimiento almacenado y recibe un mensaje de respuesta que contiene los detalles de la recién Inserta el registro del empleado. En esta lección, se basan en la lección anterior y actualizar la orquestación para llevar a cabo los pasos siguientes:  
  
1.  En la orquestación, se genera el mensaje para realizar una operación de inserción en el **Purchase_Order** tabla. Este paso es similar a [paso 1: crear el mensaje de solicitud para el procedimiento almacenado de UPDATE_EMPLOYEE](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).  
  
2.  Después de crear el mensaje de solicitud, asignar el mensaje de respuesta de la **UPDATE_EMPLOYEE** procedimiento almacenado para el mensaje de solicitud para la operación de inserción en el **Purchase_Order** tabla. Mediante la asignación de los mensajes, pasar los valores procedentes de los mensajes de respuesta al mensaje de solicitud para la operación de inserción.  
  
3.  Enviar el mensaje para insertar un registro en el **Purchase_Order** de tabla y recibir una respuesta.  
  
4.  Enviar la respuesta a un puerto de envío.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)  
  
-   [Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE insertar el mensaje de solicitud de operación](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)  
  
-   [Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)  
  
-   [Paso 4: Generar el proyecto](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)