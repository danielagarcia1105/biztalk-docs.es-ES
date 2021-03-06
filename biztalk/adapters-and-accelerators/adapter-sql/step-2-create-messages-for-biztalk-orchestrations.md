---
title: 'Paso 2: Crear mensajes para orquestaciones de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47a4fb98-6085-4aeb-ab39-2f2c3858d4e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bad2f052efa561020ba04060a8290137a08f542
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995365"
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a>Paso 2: Crear mensajes para orquestaciones de BizTalk
![Paso 2 de 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, podrá agregar una orquestación al proyecto de BizTalk y crear mensajes para los esquemas que generó en [paso 1: generar el esquema para las operaciones](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 1: generar el esquema para las operaciones](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).  
  
### <a name="to-create-messages-in-an-orchestration"></a>Para crear mensajes en una orquestación  
  
1. Agregar una orquestación de BizTalk para el proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:  
  
   1.  Desde el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
   2.  En el **Agregar nuevo elemento** cuadro de diálogo desde el **categorías** cuadro, haga clic en **archivos de orquestación**. Desde el **plantillas** cuadro, haga clic en **orquestación de BizTalk**.  
  
   3.  Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**. Para este tutorial, escriba el nombre `EmployeeOrch.odx`.  
  
2. Abra el **Vista orquestación** ventana del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
3. Agregar mensajes a la orquestación.  
  
   1.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
   2.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
   3.  En el **propiedades** panel **Message_1**, realice lo siguiente:  
  
       |Use|Para|  
       |--------------|----------------|  
       |Identificador|Tipo `NotifyReceive`.|  
       |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione **Employee_PurchaseOrder.Notification**, donde Employee_PurchaseOrder es el nombre de su proyecto de BizTalk. Notificación es el esquema generado para el **notificación** operación.|  
  
   4.  Repita el paso anterior para agregar cuatro nuevos mensajes, un mensaje de solicitud y respuesta establecida para invocar el update_employee al procedimiento almacenado y establece otro mensaje de solicitud y respuesta para llevar a cabo la **insertar** operación en  **Purchase_Order** tabla.  
  
       |Identificador de conjunto para|Establecer el tipo de mensaje en|  
       |-----------------------|-------------------------|  
       |UpdateEmployee|*Employee_PurchaseOrder.TypedProcedure_dbo. UPDATE_EMPLOYEE*, donde TypedProcedure_dbo. UPDATE_EMPLOYEE es que el esquema para el update_employee al procedimiento almacenado.|  
       |UpdateEmployeeResponse|*Employee_PurchaseOrder.TypedProcedure_dbo. UPDATE_EMPLOYEEResponse*|  
       |InsertPO|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*, donde TableOperation_dbo_Purchase_Order.Insert es el esquema para la operación de inserción en la tabla Purchase_Order.|  
       |InsertPOResponse|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*|  
  
   5.  Guarde el archivo de orquestación y proyecto de BizTalk.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha creado los mensajes para invocar la realización de operaciones de entrada y salida en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="next-steps"></a>Pasos siguientes  
 Agregar formas de orquestación para recibir una notificación de SQL Server y filtrar notificaciones para la operación de inserción, como se describe en [lección 2: recibir notificaciones de filtro y](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).  
  
## <a name="see-also"></a>Vea también  
 [Lección 1: Generar esquemas y crear mensajes](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)   
 [Paso 1: Generar el esquema para las operaciones](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)