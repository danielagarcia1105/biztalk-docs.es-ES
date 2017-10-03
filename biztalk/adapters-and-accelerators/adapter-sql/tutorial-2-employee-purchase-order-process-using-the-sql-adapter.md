---
title: 'Tutorial 2: Empleado: proceso de pedido de compra con el adaptador de SQL | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fca0c11aeb1f84a5e9f05a4df4f995b7c2b52e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a>Tutorial 2: Empleado: proceso de pedido de compra con el adaptador de SQL
En este tutorial, va a automatizar el proceso donde el departamento de compras que coloca un equipo solicitar cada vez que la organización une a un nuevo empleado. Detalles de los empleados y los detalles de pedido de compra se mantienen en **empleado** y **Purchase_Order** respectivamente, las tablas en una base de datos de SQL Server. El departamento de compras se informa mediante la actualización de la tabla Purchase_Order en la base de datos de SQL Server y envíe un correo electrónico. Dentro del proceso, se producen las siguientes acciones:  
  
1.  El adaptador recibe una notificación cada vez que la **empleado** se actualiza la tabla. El adaptador, a continuación, envía una notificación a la orquestación de BizTalk.  
  
2.  La orquestación de BizTalk averigua si la notificación es para un nuevo registro que se inserta en la **empleado** tabla. Si la notificación es para ninguna otra operación en el **empleado** tabla, la orquestación no realiza ninguna operación.  
  
3.  Si la notificación es para una operación de inserción en el **empleado** tabla, le notifica que se ha agregado un nuevo registro de empleado, la orquestación utiliza el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para leer los detalles del nuevo registro.  
  
4.  La orquestación recibe una respuesta que contiene los detalles del nuevo registro de empleado agregado. Las asignaciones de orquestación la **Id_Empleado** y **designación** campos en la respuesta al mensaje de solicitud para la operación de inserción en el **Purchase_Order** tabla.  
  
5.  La orquestación, a continuación, usa el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar una operación de inserción en el **Purchase_Order** tabla. La respuesta para la operación de inserción se envía al departamento de compras como un correo electrónico.  
  
## <a name="about-the-database-objects-used-in-this-sample"></a>Acerca de los objetos de base de datos utilizados en este ejemplo  
 Este tutorial usa los objetos de base de datos creados por la secuencia de comandos SQL incluido con los ejemplos. Para obtener más información acerca de la secuencia de comandos y los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md). Los objetos de base de datos que va a utilizar en este tutorial son:  
  
-   **ADAPTER_SAMPLES** base de datos.  
  
-   **Empleado** y **Purchase_Order** tablas.  
  
-   **UPDATE_EMPLOYEE** procedimiento almacenado.  
  
 Estos objetos de base de datos se crean al ejecutar el script SQL proporcionado con el ejemplo. Asegúrese de que se ejecute el script antes de empezar con el tutorial.  
  
## <a name="sample-based-on-this-tutorial"></a>Ejemplo basado en este Tutorial  
 Obtener un ejemplo, **Employee_PurchaseOrder**, que se basa en este tutorial también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
 Se recomienda que seguir el tutorial completamente para aprender a crear proyectos de BizTalk con el adaptador y, a continuación, examine el ejemplo como referencia.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Lección 1: Generar esquemas y crear mensajes](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [Lección 2: Recibir y filtrar notificaciones](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [Lección 3: Ejecutar un procedimiento almacenado para seleccionar a nuevos empleados agregados](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [Lección 4: Realizar una operación de inserción en la tabla de orden de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [Lección 5: Implementar la solución](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)