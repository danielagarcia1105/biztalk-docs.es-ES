---
title: Definir actividades económicas y vistas en Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating business activities
- monitoring business activities [BAM], creating business activities
ms.assetid: 000532f0-cb9a-40ac-a6c5-a8bd4e49f8d0
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61e9302d2f3178e457a5ed57353e77eac0909d32
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014141"
---
# <a name="defining-business-activities-and-views-in-excel"></a>Definición de actividades económicas y vistas en Excel
El primer paso para crear cualquier solución de BAM es identificar los datos que le interesan y la forma en que deben interpretarse. Para ello, debe usar el complemento BAM para Excel. Dicho complemento permite definir una lista de los datos de interés definiendo una actividad económica. También puede definir la forma en que los datos deben interpretarse y mostrarse a distintas categorías de usuarios empresariales.  
  
 El complemento BAM permite al usuario definir agregaciones.  
  
 También puede cambiar el nombre de los elementos de actividad; por ejemplo, en los casos en que la terminología habitual de algunos usuarios no coincida con los nombres de los elementos de datos correspondientes de la actividad. Esto podría deberse, por ejemplo, a que la vista está en otro idioma.  
  
 Una vez completada la definición de la actividad, Excel genera datos aleatorios de vista previa que pueden usarse para definir los gráficos deseados y otras formas de presentación. Para obtener más información acerca de los datos de la versión preliminar, consulte [cómo usar la tabla dinámica](../core/how-to-use-the-pivottable.md).  
  
 La definición de actividad completada define los puntos de datos y los eventos que debe recopilar cuando se ejecuta un proceso empresarial. Puede obtener el complemento BAM para Excel de diversas fuentes.  
  
 Puede instalar el XLA complemento BAM durante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación. Para obtener más información, consulte [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)  
  
 Implementación de BAM. Archivo XLA se instala en una de las siguientes ubicaciones:  
  
- Si Microsoft Office no está instalado en el equipo, el archivo BAM.xla se instalará en el BizTalk Server 20 \Program Files\Microsoft*xx*carpeta \ExcelDir\.  
  
- Si está instalado Microsoft Office, el archivo BAM.xla se instala en el \Program Files\Microsoft Office\OFFICE*xx*\Library\ carpeta.  
  
  También puede copiar el archivo BAM.xla a su equipo desde una carpeta compartida de otro equipo. Para registrar el XLA, selecciónelo en la ubicación a la que lo ha copiado.  
  
  Para habilitar el complemento de BAM en la barra de herramientas de Excel, haga clic en el **archivo** menú, a continuación, haga clic en **opciones**y, a continuación, haga clic en **Add-Ins**. Seleccione **Business Activity Monitoring**, a continuación, haga clic en **vaya**, en la ventana complementos, seleccione la casilla de verificación junto a **Business Activity Monitoring**y, a continuación, haga clic en **Aceptar**.  
  
> [!NOTE]
>  El uso del complemento BAM impide ejecutar Excel con dos instancias cargadas en el mismo proceso.  Cuando se usa el complemento, pueden darse varias instancias en el mismo proceso en las siguientes situaciones:  
>   
>  Cuando se tiene abierta una hoja de cálculo de Excel con el complemento BAM habilitado y se hace doble clic en otra hoja de cálculo de Excel; el programa intenta cargar la hoja de cálculo en la instancia actualmente en ejecución.  
>   
>  Cuando se tiene abierta una hoja de cálculo de Excel con el complemento BAM habilitado y se usa la opción de menú Archivo/Abrir para cargar otra hoja de cálculo de Excel.  
  
 En estas situaciones, el complemento no podrá usarse correctamente. Para abrir varias hojas de cálculo de Excel con el complemento BAM habilitado, debe abrir una copia nueva de Excel y cargar la hoja de cálculo en esa instancia de Excel.  
  
> [!NOTE]
>  Cuando use BAM.xla en Excel, puede obtener el error "este libro ha perdido su proyecto VBA, los controles ActiveX y otras características relacionadas con la programabilidad". Para obtener más información sobre el error, vea [solución de problemas de BAM](../core/troubleshooting-bam.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo definir una actividad económica](../core/how-to-define-a-business-activity.md)  
  
-   [Definición de una vista de BAM](../core/defining-a-bam-view.md)  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de actividades económicas con BAM](../core/monitoring-business-activities-with-bam.md)