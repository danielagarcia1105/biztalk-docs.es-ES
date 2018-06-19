---
title: 'Paso 4: Probar la aplicación de SharePoint 1 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7ded5a5-88d5-40aa-814b-70bc0a7dcfa3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b8be51df02bd9796b41201c0495758c281e8f14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216636"
---
# <a name="step-4-test-your-sharepoint-application"></a>Paso 4: Probar la aplicación de SharePoint
![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** después de haber agregado elementos Web en el sitio de SharePoint y crea una aplicación, debe probar la aplicación mediante la recuperación de algunos datos desde el sistema SAP. Este tema proporciona instrucciones sobre cómo usar la aplicación para recuperar los datos desde el sistema SAP.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Deberá haber creado la página de elementos Web que contiene los elementos Web adecuado para recuperar los datos empresariales. Vea [paso 3: crear una aplicación de SharePoint para recuperar datos de SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md).  
  
### <a name="to-test-the-sharepoint-application"></a>Para probar la aplicación de SharePoint  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP en la que se creó la aplicación.  
  
3.  En el panel izquierdo, haga clic en **ver todo el contenido del sitio**. En el panel derecho, haga clic en **plantillas de formulario**.  
  
4.  En el **formulario categoría** lista, haga clic en **Customer_SalesOrders**. Ha especificado este nombre cuando creaste la página de elementos Web. En la siguiente ilustración muestra la página de elementos Web que ha creado.  
  
     ![Página de elemento Web completada](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")  
  
5.  Buscar los clientes basándose en una cadena de búsqueda. Por ejemplo, buscar los clientes cuyo nombre empieza por "John E". Para ello:  
  
    1.  En la sección de la lista de clientes, en la primera lista, haga clic en **CustomerName**.  
  
    2.  En la segunda lista, haga clic en **comienza con**.  
  
    3.  En el cuadro de texto, escriba **John E**.  
  
    4.  Haga clic en el **recuperar datos** vincular o presione ENTRAR. La siguiente ilustración muestra los registros recuperados desde el sistema SAP que cumplen los criterios de búsqueda.  
  
         ![Buscar resultados en el sistema SAP](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")  
  
6.  Ahora puede ver los detalles de cualquier cliente en la lista y los pedidos de venta asociados con los clientes, en su caso. Para ello, haga clic en el botón de opción en un número de cliente. Actualice la página para mostrar los detalles y los pedidos de venta para un cliente específico de los elementos Web correspondientes.  
  
     ![Datos SAP presentados en SharePoint](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")  
  
     Si los detalles de los clientes y el pedido de venta asociado se muestran correctamente, ha completado correctamente el tutorial. Si no hay ningún o datos incorrectos se muestran, compruebe con cuidado el trabajo para asegurarse de que ha realizado correctamente todas las tareas.  
  
## <a name="summary"></a>Resumen  
 En este tutorial ha creado un servicio WCF para los artefactos SAP que desea tener acceso desde un SharePoint Portal. También se crea una definición de aplicación para los artefactos SAP que se importa en un portal de SharePoint para crear elementos Web para presentar los datos de un sistema SAP.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentar datos desde un sistema SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)