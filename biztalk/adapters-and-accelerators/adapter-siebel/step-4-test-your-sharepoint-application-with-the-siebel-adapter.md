---
title: "Paso 4: Prueba la aplicación de SharePoint con el adaptador de Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec1392fa-fdc1-42be-b4dc-75a55d8fa400
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85cebcafcdf768686ed3f7382a0838db5062d96b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application-with-the-siebel-adapter"></a>Paso 4: Probar la aplicación de SharePoint con el adaptador de Siebel
![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **Tiempo en completarse:** 5 minutos.  
  
 **Objetivo:** después de haber agregado elementos Web en el sitio de SharePoint y crea una aplicación, debe probar la aplicación mediante la recuperación de algunos datos en el sistema Siebel. Esta sección proporciona instrucciones sobre cómo usar la aplicación para recuperar los datos en el sistema Siebel.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Deberá haber creado la página de elementos Web que contiene los elementos Web adecuado para recuperar los datos empresariales. Vea [paso 3: crear una aplicación de SharePoint para recuperar datos de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md).  
  
### <a name="to-test-the-sharepoint-application"></a>Para probar la aplicación de SharePoint  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP en la que se creó la aplicación.  
  
3.  En el panel izquierdo, haga clic en **ver todo el contenido del sitio**. En el panel derecho, haga clic en **plantillas de formulario**.  
  
4.  En el **formulario categoría** lista, haga clic en **cuenta de Siebel**. Ha especificado este nombre al crear la página de elementos Web. En la siguiente ilustración muestra la página de elementos Web que ha creado.  
  
     ![Página de elemento Web completada](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")  
  
5.  Consultar el componente de negocio de cuenta en función de una cadena de búsqueda. Por ejemplo, especifique la expresión de búsqueda `[Name] LIKE ‘W*’`. Para ello:  
  
    1.  En el **lista de cuentas de** sección, en la primera lista, seleccione **SearchExpression**y, a continuación, seleccione **es igual a**.  
  
    2.  En el campo de texto, escriba `[Name] LIKE ‘W*’`.  
  
    3.  Haga clic en **recuperar datos** vincular, o presione ENTRAR. La siguiente ilustración muestra los registros recuperados en el sistema Siebel que cumplen los criterios de búsqueda.  
  
         ![Buscar resultados en el sistema Siebel](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentar datos desde un sistema Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)