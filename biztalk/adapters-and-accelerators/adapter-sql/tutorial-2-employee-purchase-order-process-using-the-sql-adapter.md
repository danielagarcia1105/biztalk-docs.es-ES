---
title: 'Tutorial 2: Empleado: proceso de pedido de compra mediante el adaptador de SQL | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d14008611bfb22bf39e446e72ecb3bba4571761
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010781"
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a>Tutorial 2: Empleado: proceso de pedido de compra mediante el adaptador de SQL
En este tutorial, va a automatizar el proceso donde el departamento de compras que coloca un equipamiento solicitar cada vez que un nuevo empleado incorpora a la organización. Detalles de los empleados y los detalles de pedido de compra se mantienen en **empleado** y **Purchase_Order** tablas respectivamente, en una base de datos de SQL Server. Se informa al departamento de compras mediante la actualización de la tabla Purchase_Order en la base de datos de SQL Server y enviando un correo electrónico. Dentro del proceso, se producen las siguientes acciones:  
  
1. El adaptador recibe una notificación cada vez que el **empleado** se actualiza la tabla. El adaptador, a continuación, envía una notificación a la orquestación de BizTalk.  
  
2. La orquestación de BizTalk averigua si la notificación es para inserta un nuevo registro en el **empleado** tabla. Si la notificación es para ninguna otra operación en el **empleado** tabla, la orquestación no realiza ninguna operación.  
  
3. Si la notificación es para una operación de inserción en el **empleado** tabla, que le notifica que se ha agregado un nuevo registro de empleado, la orquestación utiliza el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para leer los detalles del nuevo registro.  
  
4. La orquestación recibe una respuesta que contiene los detalles del nuevo registro de empleado agregado. La orquestación se asigna el **Id_Empleado** y **designación** campos en la respuesta al mensaje de solicitud para la operación de inserción en el **Purchase_Order** tabla.  
  
5. La orquestación, a continuación, usa el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar una operación de inserción en el **Purchase_Order** tabla. La respuesta para la operación de inserción se envía al departamento de compras como un correo electrónico.  
  
## <a name="about-the-database-objects-used-in-this-sample"></a>Acerca de los objetos de base de datos utilizados en este ejemplo  
 Este tutorial usa los objetos de base de datos creados por la secuencia de comandos SQL incluido con los ejemplos. Para obtener más información acerca de la secuencia de comandos y los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md). Los objetos de base de datos que va a utilizar en este tutorial son:  
  
- **ADAPTER_SAMPLES** base de datos.  
  
- **Empleado** y **Purchase_Order** tablas.  
  
- **UPDATE_EMPLOYEE** procedimiento almacenado.  
  
  Todos estos objetos de base de datos se crean al ejecutar el script SQL proporcionado con el ejemplo. Asegúrese de que ejecutar el script antes de empezar con el tutorial.  
  
## <a name="sample-based-on-this-tutorial"></a>Ejemplo basado en este Tutorial  
 Un ejemplo, **Employee_PurchaseOrder**, que se basa en este tutorial también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
 Se recomienda que recorra el tutorial completamente para aprender a crear proyectos de BizTalk con el adaptador y, a continuación, examine el ejemplo como referencia.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Lección 1: Generar esquemas y crear mensajes](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [Lección 2: Recibir y filtrar notificaciones](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [Lección 4: Realizar una operación de inserción en la tabla de pedidos de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [Lección 5: Implementar la solución](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)