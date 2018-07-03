---
title: 'Paso 1: Generar el esquema para las operaciones | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63218a5e-9af2-40af-9992-ac5e204d2832
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eb6de636ba2ee587fa1da3720c38ef517f0ba01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997861"
---
# <a name="step-1-generate-schema-for-operations"></a>Paso 1: Generar el esquema para las operaciones
![Paso 1 de 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, se genera esquemas para las operaciones que se realizan en la base de datos de SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para este tutorial, debe generar el esquema para lo siguiente:  
  
-   **Notificación** (operación de entrada).  
  
-   **UPDATE_EMPLOYEE** (operación de salida) de procedimiento almacenado.  
  
-   **Insertar** operación en el **Purchase_Order** (operación de salida) de la tabla.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de continuar con el tutorial, asegúrese de que:  
  
-   Debe haber completado los pasos descritos en [antes de que desarrollar aplicaciones de BizTalk](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6).  
  
-   Debe iniciar sesión como miembro del grupo Administradores de BizTalk Server.  
  
### <a name="to-generate-schema-for-operations"></a>Para generar el esquema para las operaciones  
  
1. Crear un nuevo proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Para este tutorial, denomine el proyecto como `Employee_PurchaseOrder`.  
  
2. Conectarse a la base de datos de SQL Server de ADAPTER_SAMPLES mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Para obtener instrucciones sobre cómo conectarse mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [conectar con SQL Server en Visual Studio utilizando Consume Adapter Service complemento](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).  
  
   > [!NOTE]
   >  También puede conectarse a SQL Server mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Sin embargo, para este tutorial usará el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
3. Genere el esquema para el **notificación** operación entrante.  
  
   1. Después de conectarse a la base de datos ADAPTER_SAMPLES, en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], desde el **seleccione el tipo de contrato** , seleccione **(operaciones de entrada) de servicio**.  
  
   2. Desde el **seleccionar una categoría** cuadro, haga clic en el nodo raíz (**/**).  
  
   3. Desde el **operaciones y categorías disponibles** cuadro, seleccione **notificación** y haga clic en **agregar**. El **notificación** operación aparece ahora en el **agregar categorías y operaciones** cuadro. Haga clic en **Aceptar**.  
  
4. Genere el esquema para el **UPDATE_EMPLOYEE** procedimiento almacenado y la operación de inserción en **Purchase_Order** tabla.  
  
   1. Repita el paso 2 para conectarse a la base de datos ADAPTER_SAMPLES en SQL Server mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
      > [!NOTE]
      >  No se puede generar el esquema para las operaciones de entrada y salidas al mismo tiempo. Por lo tanto, en el paso 3, tras hacer clic en **Aceptar** para generar el esquema para **notificación** operación, el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] se cierra. Debe volver a conectarse a la base de datos de SQL Server para generar el esquema para las operaciones de salida.  
  
   2. Desde el **seleccione el tipo de contrato** , seleccione **Client (Outbound operations)**.  
  
   3. Desde el **seleccionar una categoría** cuadro, haga clic en el **Strongly-Typed procedimientos** nodo. Desde el **categorías disponibles y operación**cuadro, seleccione **UPDATE_EMPLOYEE**y, a continuación, haga clic en **agregar**.  
  
      > [!IMPORTANT]
      >  El **UPDATE_EMPLOYEE** también está disponible en el procedimiento almacenado la **procedimientos** nodo. Sin embargo, si genera el esquema para el procedimiento almacenado en el **procedimientos** nodo, el esquema de mensaje de respuesta no está disponible en tiempo de diseño, pero se recibe el mensaje de respuesta después de ejecutar el procedimiento almacenado.  
      >   
      >  En este tutorial, asignará el esquema de respuesta del procedimiento almacenado para el esquema de entrada de la operación de inserción en el **Purchase_Order** tabla. Por lo tanto, necesitará el esquema para el **UPDATE_EMPLOYEE** procedimiento almacenado en tiempo de diseño y debe seleccionar el procedimiento almacenado en el **Strongly-Typed procedimientos**. Al hacerlo, obtendrá el esquema del procedimiento almacenado en tiempo de diseño.  
  
   4. Desde el **seleccionar una categoría** , expanda el **tablas** nodo y haga clic en el nodo de **Purchase_Order** tabla. Desde el **categorías disponibles y operación**cuadro, seleccione **insertar**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, se generan esquemas para **notificación** (operación de entrada), **UPDATE_EMPLOYEE** procedimiento almacenado, y **insertar** operación en el  **Purchase_Order** tabla. Después de generar el esquema, el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] agrega los siguientes archivos al proyecto de BizTalk:  
  
- Archivos XSD que contienen el esquema del mensaje de solicitud invocar operaciones en SQL Server.  
  
- Archivos de enlace XML que puede usar para crear el envío de WCF-Custom y los puertos de recepción [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
  Para obtener más información sobre la generación de esquemas, vea [examinar, buscar y obtener metadatos para operaciones de SQL mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear mensajes en el proyecto de BizTalk para los esquemas de [paso 2: creación de mensajes para orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).  
  
## <a name="see-also"></a>Vea también  
 [Lección 1: Generar esquemas y crear mensajes](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)