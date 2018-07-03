---
title: Cómo definir una actividad empresarial | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business activities, creating [Excel add-in]
- monitoring business activities [BAM], creating business activities [Excel add-in]
- monitoring business activities [BAM], Excel add-in
ms.assetid: 305e3718-46b4-45df-bd52-f7ae36621576
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3252d7a96b06da3590b4c823e150366e6ba24168
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983365"
---
# <a name="how-to-define-a-business-activity"></a>Definición de actividades económicas
Para indicar los datos que necesita recopilar para informes, debe definir una actividad de BAM. Dicha actividad contiene una lista de los elementos de datos e hitos importantes sobre los que BAM debe realizar un seguimiento. Use el complemento BAM para Excel a fin de crear una actividad como la que se muestra en el siguiente procedimiento.  
  
> [!NOTE]
>  Una vez implementada una actividad, las acciones que puede realizar sobre ella están restringidas. Específicamente, no puede eliminar elementos de una actividad a menos que esté dispuesto a que su administrador anule la implementación de toda la actividad de BAM y sus conjuntos de vista y los vuelva a implementar. Esto puede provocar una interrupción de la visibilidad y pérdidas de datos a menos que el administrador haga una copia de seguridad de los datos y los restaure.  
  
### <a name="to-create-a-business-activity"></a>Procedimiento para crear una actividad económica  
  
1.  Abra Microsoft Excel.  
  
2.  En la barra de herramientas del menú, haga clic en el **BAM** elemento de menú y haga clic en **actividad de BAM**.  
  
     El **Asistente para actividad de supervisión de la actividad económica** aparece.  
  
3.  Haga clic en **nueva actividad**.  
  
     El **nueva actividad** aparece el cuadro de diálogo.  
  
4.  Escriba un nombre descriptivo para la actividad en el **nombre de la actividad** cuadro de texto.  
  
> [!NOTE]
>  Una actividad debe contener al menos un elemento de actividad.  
  
#### <a name="to-create-a-new-item"></a>Procedimiento para crear un nuevo elemento  
  
1. Haga clic en **nuevo elemento**.  
  
2. En el **nuevo elemento de actividad** cuadro de diálogo el **nuevo elemento de actividad** , escriba un nombre descriptivo para el elemento de actividad.  
  
3. Desde el **tipo de elemento** menú desplegable, seleccione un tipo para este elemento. Los valores posibles incluyen:  
  
   |Tipo de elemento|Descripción|  
   |---------------|-----------------|  
   |Hito económico|Un valor de fecha y hora. Por ejemplo, la fecha de aprobación de un pedido de compra.|  
   |Datos económicos: texto|Cadena que contiene cualquier carácter alfanumérico. Por ejemplo, enviar: código de ciudad, estado o provincia y código Postal.|  
   |Datos económicos: Integer|Valor numérico entero. Por ejemplo el número total de compras.|  
   |Datos económicos: decimal|Valor decimal. Por ejemplo el importe total del pedido de compra.|  
  
    Si selecciona el elemento de tipo "Datos de económicos: Text", debe especificar el número máximo de caracteres de la cadena en el **longitud máxima** cuadro.  
  
   > [!NOTE]
   >  Para obtener más información sobre la creación de estos elementos, consulte "Partner Management and Business Activity Monitoring" ("Supervisión de la administración de socios comerciales y la actividad económica") en el tutorial de Microsoft BizTalk Server.  
  
4. Repita los pasos 1 a 3 para agregar tantos elementos como necesite a esta actividad.  
  
5. Una vez completado el Asistente para actividad de Supervisión de la actividad económica, se inicia automáticamente el Asistente para vistas de Supervisión de la actividad económica.  
  
   Para obtener más información sobre cómo usar este asistente, consulte [definir una vista de BAM](../core/defining-a-bam-view.md).  
  
## <a name="see-also"></a>Vea también  
 [Definir una vista BAM](../core/defining-a-bam-view.md)   
 [Definición de actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md)