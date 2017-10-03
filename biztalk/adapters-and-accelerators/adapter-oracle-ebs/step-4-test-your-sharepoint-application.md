---
title: "Paso 4: Probar la aplicación de SharePoint | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a859044e-a28e-477e-a20b-f9bb3c9f7405
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 427235d27e4e783111ccdb60f799c228737cd008
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application"></a>Paso 4: Probar la aplicación de SharePoint
![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** después de haber agregado elementos Web en el sitio de SharePoint y crea una aplicación, debe probar la aplicación al recuperar algunos datos de Oracle E-Business Suite. Este tema proporciona instrucciones sobre cómo usar la aplicación para recuperar los datos de Oracle E-Business Suite.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Deberá haber creado la página de elementos Web que contiene los elementos Web adecuado para recuperar los datos empresariales. Vea [paso 3: crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a>Escenario 1: Para probar la aplicación de SharePoint creado mediante el elemento de Web de lista de datos económicos  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP en la que se creó la aplicación.  
  
3.  En el panel izquierdo, haga clic en **ver todo el contenido del sitio**. En el panel derecho, haga clic en **plantillas de formulario**.  
  
4.  En el **formulario categoría** lista, haga clic en **MS_SAMPLE_EMPLOYEE**. Ha especificado este nombre cuando creaste la página de elementos Web en [escenario 1: mostrar datos mediante el elemento web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).  
  
5.  Búsqueda de empleados basada en una cadena de búsqueda. Por ejemplo, para buscar todos los empleados, escriba  **%**  en el cuadro de texto y haga clic en **recuperar datos**. La siguiente ilustración muestra los archivos recuperados de Oracle E-Business Suite:  
  
     ![Resultado de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")  
  
6.  También puede buscar un empleado concreto mediante la especificación de su nombre o apellido:  
  
    -   Para buscar mediante el nombre, escriba las letras iniciales de un nombre de empleado seguido por el  **%**  símbolos para devolver registros de todos los empleados que cumpla los criterios de búsqueda.  
  
    -   Para buscar con el apellido, escriba  **%**  seguido por el apellido del empleado.  
  
    > [!NOTE]
    >  La cadena de búsqueda distingue mayúsculas de minúsculas.  
  
     ![Buscar por nombre de un empleado](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a>Escenario 2: Para probar la aplicación de SharePoint creado para realizar una búsqueda de texto completo  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP en la que se creó la aplicación.  
  
3.  En el panel izquierdo, haga clic en **ver todo el contenido del sitio**. En el panel derecho, haga clic en **plantillas de formulario**.  
  
4.  En el **formulario categoría** lista, haga clic en **MS_SAMPLE_EMPLOYEE_Search**. Ha especificado este nombre cuando creaste la página de elementos Web en [escenario 2: realizar una búsqueda mediante el elemento Web de cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md) en [escenario 2: realizar una búsqueda mediante el elemento Web de cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).  
  
5.  La página MS_SAMPLE_EMPLOYEE_Search muestra el cuadro de búsqueda que puede realizar una búsqueda de texto completo en la tabla de empleados de MS_SAMPLE. Por ejemplo, si desea buscar todos los empleados que viven en Nueva York, escriba `New York` en el cuadro de búsqueda y presione ENTRAR.  
  
     ![Especifique un parámetro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")  
  
6.  Aparece una página con los resultados de búsqueda. Cada registros coincidentes se muestra como un vínculo en la página de resultados de búsqueda.  
  
     ![Resultados de la búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")  
  
7.  Haga clic en un vínculo en el resultado de la búsqueda para ver el registro de empleado correspondiente.  
  
     ![Registro de empleado detallado](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")  
  
## <a name="summary"></a>Resumen  
 En este tutorial, ha creado un servicio WCF para los artefactos de Oracle E-Business Suite que desea tener acceso desde un SharePoint Portal. También se crea una definición de aplicación para los artefactos de Oracle E-Business Suite que se importa en un portal de SharePoint para crear elementos Web para presentar y buscar datos en Oracle E-Business Suite.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)