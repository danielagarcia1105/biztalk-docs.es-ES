---
title: "Dimensión de progreso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], progress dimensions
- Progress dimension [BAM]
ms.assetid: 472fcbf6-502f-4c81-bf48-f7eec98e391b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2e4764071beb2aa94aac738e8f1cec2377dd1d8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="progress-dimension"></a>Dimensión de progreso
Use una dimensión de progreso para agrupar las actividades de BAM por hitos conseguidos. A continuación se incluye ejemplo ilustrativo.  
  
 Tomemos la orquestación del Tutorial 1 que procesa solicitudes de elementos. (Consulte [Tutorial 1: integración de aplicaciones empresariales](../core/tutorial-1-enterprise-application-integration.md) para obtener más información acerca de esta orquestación.) La orquestación contiene una forma de decisión seguida de dos ramas. En [Tutorial 4: Business Activity Monitoring](http://msdn.microsoft.com/library/81d5e768-f8a6-4eb0-8e6c-64db47455476) se asigna el hito económico denegadas a una forma de la rama que representa la solicitud se deniega, y asigne el hito económico aprobadas a una forma de la rama que representa la solicitud de aprobación. A continuación, puede crear una dimensión de progreso que incluya los hitos económicos Aprobadas y Denegadas. Si usa la dimensión de progreso en una tabla dinámica, puede mostrar las actividades de BAM agrupadas en aprobadas y denegadas. Observe la siguiente imagen:  
  
 ![Tabla dinámica con columnas para aprobado y denegado](../core/media/bts-view-with-approved-denieds.gif "bts_view-con-approved-denieds")  
  
 También puede definir hitos secundarios dentro del hito Denegadas, aunque esta acción no se incluya en los tutoriales. Por ejemplo, si la orquestación identifica motivos de denegación, puede crear los hitos secundarios Crédito insuficiente y Existencias agotadas dentro del hito Denegadas. Si usó la dimensión de progreso en una tabla dinámica, puede desglosar el hito Denegadas para ver las actividades de BAM que han alcanzado el hito Crédito insuficiente y las que han alcanzado el hito Existencias agotadas.  
  
 Dimensiones de progreso de BAM constan de *hitos de progreso* y *fases de progreso*. Un hito de progreso representa una clasificación, una forma de agrupar actividades de BAM. Por ejemplo, Aprobadas y Denegadas son hitos de progreso, ya que las actividades de solicitud se clasifican en aprobadas y denegadas.  
  
> [!NOTE]
>  El uso de la palabra “hito” para dos conceptos no es muy acertado. A *hito económico* es un elemento de actividad de una actividad de BAM representa la fecha y hora en que se produjo un evento de la aplicación. A *hito de progreso* es una manera de agrupar instancias de actividad. Cada hito de progreso corresponde a un hito económico. Para minimizar la confusión, considere la opción de usar el mismo nombre para el hito de progreso y el hito económico al que corresponde.  
  
 Una fase de progreso es un grupo de hitos del mismo nivel. Nuestro ejemplo con hitos secundarios incluye dos fases de progreso. La primera fase de progreso consta de los hitos de progreso Aprobadas y Denegadas. La segunda fase de progreso consta de los hitos de progreso Crédito insuficiente y Existencias agotadas.  
  
 Una dimensión de progreso empieza con un hito de progreso raíz. A menudo, este hito de progreso representa el mensaje original que se recibe. Cada hito de progreso puede contener una fase de progreso y varios hitos de progreso. Todos los hitos de progreso de una fase de progreso deben excluirse mutuamente. En la imagen siguiente, Disposición y Motivo son fases de progreso, mientras que Recibidas, Aprobadas, Denegadas, Crédito insuficiente y Existencias agotadas son hitos de progreso.  
  
 ![Definir un dos &#45; el nivel de dimensión de progreso](../core/media/bts-progress-dimension-two-levelss.gif "bts_progress-dimension-two-levelss")  
  
## <a name="how-to-create-progress-dimensions"></a>Creación de dimensiones de progreso  
 Antes de usar el Asistente para vistas de BAM para crear la dimensión de progreso, diséñela. En la tabla siguiente se identifica el proceso de diseño de una dimensión de progreso y se incluyen ejemplos de cada paso.  
  
|Procesar|Ejemplo|  
|-------------|-------------|  
|Dibuje la jerarquía de categorías y subcategorías sobre las que desea informar.<br /><br /> Estos niveles serán los hitos de progreso.|Recibidas:<br /><br /> -Aprobado<br /><br /> -Denegado<br /><br /> -Crédito insuficiente<br /><br /> -Out de papel|  
|Para cada grupo de categorías del mismo nivel, elija un nombre que las represente.<br /><br /> Estos nombres serán las fases de progreso.|El nivel que contiene los hitos de progreso Aprobadas y Denegadas se denomina “disposición”.<br /><br /> El nivel que contiene los hitos de progreso Crédito insuficiente y Existencias agotadas se denomina “motivo”.|  
|Identifique el hito económico que representa cada hito de progreso.<br /><br /> **Nota:** la actividad de BAM debe incluir un elemento de actividad para cada uno de estos hitos económicos.|Recibido: recibido<br /><br /> Aprobado: aprobado<br /><br /> Denegado: denegar<br /><br /> Crédito insuficiente: Denegado por crédito insuficiente<br /><br /> Agotados: Denegado fuera-existencias|  
  
 Use estos hitos de progreso, fases e hitos económicos para crear la dimensión de progreso.  
  
> [!NOTE]
>  El procedimiento siguiente arranca en el punto de creación de la dimensión. Previamente, debe haber creado actividades de BAM y haber empezado a crear una vista de BAM.  
  
#### <a name="to-create-a-progress-dimension"></a>Procedimiento para crear una dimensión de progreso  
  
1.  Haga clic en el **Add-Ins** pestaña y, a continuación, seleccione **vista de SAE** desde el **BAM** la lista desplegable en el **comandos de menú** grupo.  
  
2.  En el Asistente para vistas de BAM, haga clic en **siguiente** hasta que vea el **nueva vista de SAE: agregación dimensiones y medidas** página.  
  
3.  Haga clic en **nueva dimensión**.  
  
4.  En el **nueva dimensión** cuadro de diálogo, escriba un nombre para la dimensión en la **nombre de la dimensión** cuadro y, a continuación, seleccione **dimensión de progreso** desde el **dimensión tipo** lista desplegable.  
  
5.  Haga clic en **nuevo hito**.  
  
6.  En el **hito de progreso** cuadro de la **nuevo hito de progreso** diálogo cuadro, escriba el nombre del hito de progreso en el nivel superior de la jerarquía que ha diseñado. En este ejemplo, escribiría `Received`.  
  
7.  Seleccione el hito económico correspondiente al hito de progreso y, a continuación, haga clic en **Aceptar**. En este ejemplo, seleccionaría **recibidos (\<nombre de la actividad\>)**.  
  
8.  En el **nueva dimensión** cuadro de diálogo, haga clic en **nueva fase**.  
  
9. En el **fase de progreso** cuadro de la **nueva fase de progreso** cuadro de diálogo, escriba el nombre de la fase de nivel superior y, a continuación, haga clic en **Aceptar**.  En este ejemplo, escribiría **disposition**.  
  
10. En el **nueva dimensión** cuadro de diálogo, haga clic en **nuevo hito**.  
  
11. En el **hito de progreso** cuadro de la **nuevo hito de progreso** diálogo cuadro, escriba el nombre de uno de los hitos de primer nivel. Por ejemplo, estamos usando, debería escribir `Approved`.  
  
12. En el **hito económico** cuadro de lista desplegable, seleccione el hito económico correspondiente al hito de progreso y, a continuación, haga clic en **Aceptar**. En este ejemplo, seleccionaría **aprobado (\<nombre de la actividad\>)**.  
  
13. Repita los tres pasos anteriores para agregar otros hitos de la misma fase de progreso.  
  
14. Si un hito económico contiene hitos secundarios, seleccione el hito principal en el **nueva dimensión** cuadro de diálogo, haga clic en **nueva fase**y, a continuación, repita los cinco pasos anteriores para definir la fase secundaria y su hitos.  
  
     La siguiente ilustración muestra la **nueva dimensión** cuadro de diálogo después de haber creado la dimensión de progreso de ejemplo.  
  
     ![Definir un dos &#45; el nivel de dimensión de progreso](../core/media/bts-progress-dimension-two-levelss.gif "bts_progress-dimension-two-levelss")  
  
## <a name="see-also"></a>Vea también  
 [Definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md)   
 [Dimensión de datos](../core/data-dimension.md)   
 [Dimensión de tiempo](../core/time-dimension.md)   
 [Dimensión de rango numérico](../core/numeric-range-dimension.md)   
 [Definir dimensiones](../core/defining-dimensions.md)