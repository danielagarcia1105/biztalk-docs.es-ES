---
title: "Paso 5: Probar la solución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ce7edd1c1f1f8a063e2787cc2acecb3b57cca2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-test-the-solution"></a>Paso 5: Probar la solución
El objetivo de esta solución es automatizar el proceso de envío de notificaciones a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cada vez que se cierra una nueva oportunidad en Salesforce estableciendo la etapa de la oportunidad como **Closed Won**. Después de que se reciba la notificación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía una consulta a Salesforce para recuperar los detalles de los productos relacionados con la oportunidad y, a continuación, inserta la respuesta de Salesforce en una tabla de base de datos de SQL Server denominada **OrderDetails**. Por lo tanto, para probar esta solución, actualizaremos la etapa de una oportunidad para **Closed Won** y por tanto, deben insertarse los registros pertinentes en la tabla OrderDetails en la base de datos de pedidos.  
  
### <a name="to-test-the-solution"></a>Para probar la solución  
  
1.  Inicie sesión en `https://login.salesforce.com/?lt=de` con las credenciales de inicio de sesión de desarrollador de Salesforce.  
  
2.  En la barra de navegación, haga clic en **oportunidades**y, a continuación, haga clic en **oportunidad con customer1**. Se creó esta oportunidad en [paso 2: configurar el sistema Salesforce](../core/step-2-set-up-the-salesforce-system.md).  
  
3.  En el **detalle de oportunidad** sección, tome nota de los productos asociados en el **productos (estándar)** sección. Los valores que especifique en esta sección se insertarán finalmente en la base de datos de SQL Server. En el **detalle de oportunidad** sección haga clic en el **editar** botón y cambie el valor de **fase** campo **Closed Won**. Haga clic en **Guardar**.  
  
     ![Editar una oportunidad existente](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")  
  
4.  En SQL Server Management Studio, ejecutar una consulta en el **OrderDetails** tabla para seleccionar todas las filas.  
  
     ![Resultado de la consulta SQL](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")  
  
     Observe que se muestran los productos enumerados en la oportunidad para la que cambió la etapa.  
  
     ![Agregar productos a una oportunidad](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
 Puede ver que los registros se escriben en el **OrderDetails** se corresponden con la oportunidad de venta creada en Salesforce para un conjunto determinado de productos. Puede repetir estos pasos creando nuevas oportunidades y asociando nuevos productos a cada oportunidad.