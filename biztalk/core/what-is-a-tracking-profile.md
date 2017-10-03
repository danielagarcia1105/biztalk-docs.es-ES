---
title: "¿Qué es un perfil de seguimiento? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking profiles, about tracking profiles
- tracking profiles, Tracking Profile Editor
- Tracking Profile Editor, tracking profiles
- tracking profiles
ms.assetid: b579bdc4-7c69-4fa0-bbc1-f98170c13d4f
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da032fb6063d81cedca9f21899c5e2bbe6eca947
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-a-tracking-profile"></a>¿Qué es un perfil de seguimiento?
Un perfil es un conjunto de características que definen un proceso empresarial. Un perfil de seguimiento contiene la asignación de estas características de una actividad a orquestaciones y puertos. Un perfil de seguimiento es un archivo con extensión .btt de nombre de archivo.  
  
## <a name="using-tracking-profiles-in-the-tpe"></a>Utilizar perfiles de seguimiento en el TPE  
 Los usuarios del TPE crean una asignación, o perfil de seguimiento, entre elementos de una actividad de BAM y los orígenes de solución de BizTalk Server para aquellos elementos. Las actividades de BAM constan de los hitos y de los datos contextuales que forman la “lista de visibilidad”, y definen en la empresa una unidad de trabajo por la que se guía el perfil de seguimiento. Para obtener más información acerca de las actividades, consulte [implementar actividades de BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md).  
  
 Cuando se crea un perfil de seguimiento utilizando el TPE, se utilizan los objetos siguientes:  
  
-   Actividades de BAM  
  
-   Orquestaciones de BizTalk en ensamblados implementados  
  
-   Puertos de envío y recepción.  
  
-   Esquemas de mensaje en ensamblados implementados  
  
-   Propiedades de contexto  
  
-   Base de datos de importación principal de BAM  
  
-   Base de datos de administración de BizTalk  
  
-   Base de datos de seguimiento de BizTalk  
  
 Para definir la extracción de datos desde una orquestación, coloque los elementos de esquemas de mensaje, formas de orquestación y propiedades de contexto en las carpetas de hitos económicos (evento) y de elementos de datos.  
  
 Por ejemplo, considere una actividad de BAM que incluya un hito llamado Pedido recibido y que tenga un puerto de mensajería por el que fluyen los pedidos para iniciar el procesamiento. Los programadores pueden asociar el hito `PO Received` a una propiedad de mensajería de BizTalk denominada `PortEndTime` para el puerto en su solución. Semánticamente, indica que el Pedido se recibe satisfactoriamente cuando el puerto de recepción concluye su acción y rellena la propiedad `PortEndTime`. El programador realiza ésta y otras asignaciones para completar el perfil de seguimiento. Se asignarán todos los elementos de la actividad siempre que tengan un origen de BizTalk Server. Por el contrario, si el origen de los datos o eventos es un proceso externo al tiempo de ejecución de BizTalk Server, los elementos se dejarán sin asignar, para ser completados directamente por llamadas de API.  
  
 Aunque cada panel o vista del TPE dispone de una función exclusiva, todas las vistas y carpetas tienen características de exploración similares para ayudarle a buscar y controlar la información.  
  
## <a name="who-uses-tracking-profiles-and-the-tpe"></a>¿Quién utiliza los perfiles de seguimiento y el TPE?  
 Los usuarios implicados en el desarrollo de integración empresarial utilizan los perfiles de seguimiento y el TPE para asignar orígenes de eventos de BizTalk Server a actividades de destino de BAM. El archivo .btt resultante se entrega a la implementación de TI para su implantación.  
  
 Por lo general, los usuarios de implementación de TI aplicarán los perfiles de seguimiento utilizando herramientas de línea de comandos (BTTDeploy). El usuario de TI también puede utilizar el TPE directamente para aplicar el perfil de seguimiento.  
  
 Los usuarios de operaciones de TI pueden ser responsables de las actualizaciones periódicas de los perfiles de seguimiento de forma programada (incluidas las operaciones de bases de datos como copia de seguridad y restauración), especialmente como resultado de cambios en los requisitos empresariales.  
  
## <a name="see-also"></a>Vea también  
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)