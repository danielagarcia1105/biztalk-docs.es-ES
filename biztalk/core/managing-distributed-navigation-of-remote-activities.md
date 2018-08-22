---
title: Administrar la exploración distribuida de actividades remotas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cf6e0c2-ea72-4621-9ca7-fa43e404ec46
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be784f72fe5c027f1a481335579ca77bfbea4a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009925"
---
# <a name="managing-distributed-navigation-of-remote-activities"></a>Administrar la exploración distribuida de actividades remotas
La exploración distribuida de actividades remotas es el proceso por el que un usuario empresarial explora y ve actividades existentes en bases de datos de BAM diferentes. Cuando configura la infraestructura de BAM para proporcionar la exploración distribuida, el usuario empresarial puede obtener acceso a la actividad remota en el portal de BAM. Cuando el usuario hace clic en la actividad, la actividad se abre en el portal de BAM remoto. Llegados a este punto, el usuario se ha transferido de forma clara y eficaz al portal remoto de BAM y puede explorar la búsqueda de actividades, las agregaciones y la administración de alertas para la actividad como si la actividad existiera en el almacén de datos principal del usuario.  
  
## <a name="why-use-distributed-navigation-of-activities-and-documents"></a>¿Por qué se utiliza la exploración distribuida de actividades y documentos?  
 La exploración distribuida permite a las organizaciones a mantener el control de bases de datos departamentales de BAM sin tener que acordar una única ubicación para las actividades. Esto también permite un mejor rendimiento de las bases de datos BAM al distribuir la carga del sistema de las actividades en todo el entorno.  
  
 La ilustración siguiente muestra un escenario en que la exploración distribuida cubre las necesidades del usuario empresarial para que pueda obtener acceso fácilmente a las actividades que administran departamentos diferentes de una empresa. Los administradores de estos departamentos conservan el control del proceso empresarial específico de ese departamento.  
  
 En este escenario existen los siguientes accionistas:  
  
- Un administrador que es propietario de la infraestructura del departamento de ventas. El administrador es responsable únicamente de la disponibilidad y seguridad de los datos del departamento.  
  
- Un administrador que es propietario de la infraestructura del departamento de envíos. Es responsable de satisfacer las necesidades de las ventas.  
  
- Un usuario empresarial del departamento de ventas. El usuario empresarial ve subconjuntos de datos de ventas que están incluidos en las vistas en las que se ha agregado al cliente. Las vistas las crea el administrador que concede al usuario empresarial acceso a la vista. La vista principal del usuario empresarial del negocio es la actividad de pedido en la que participa. Este usuario está configurado para ver la página principal del portal de BAM que mantiene el administrador del departamento de ventas.  
  
  **Usar la exploración distribuida en BAM**  
  
  ![Escenario de navegación distribuida. ](../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")  
  
  Los administradores quieren configurar sus servidores para que sean lo más independientes posible, como se muestra a continuación:  
  
- El administrador del departamento de ventas no quiere que se detenga la aceptación de pedidos ni que la funcionalidad de consulta para sus usuarios empresariales se vea afectada si la estructura del departamento de envíos está inactiva.  
  
- El administrador del departamento de envíos no quiere que su departamento se vea afectado por los problemas de rendimiento del departamento de ventas. Quiere que sus usuarios empresariales puedan seguir el proceso de los envíos, incluso si el departamento de ventas no está disponible.  
  
  El objetivo de la exploración distribuida es proporcionarle al usuario empresarial final el acceso a cada vista de la que tienen permisos.  
  
  Por ejemplo, las vistas A y B se definen en la base de datos de ventas. El departamento de envíos definen la vista C. El usuario empresarial tiene permisos para verlas todas y acceso al portal de BAM específico del departamento de ventas. Que permite al usuario empresarial acceso a las vistas A, B y C en el **Mis vistas** marco del portal se logra mediante el establecimiento de al menos una confianza unidireccional desde la base de datos de ventas a la base de datos de trasvase de registros.  
  
> [!NOTE]
>  El usuario empresarial con poderes, como el administrador o el analista, define los permisos de cada categoría de usuarios empresariales que puede ver datos específicos. Los administradores solo agregan usuarios a los grupos existentes o a las vistas de BAM.  
  
 La exploración distribuida de actividades de BAM también permite que el usuario vea y tenga acceso a las relaciones de actividades distribuidas. Cuando existen instancias de actividad en dos bases de datos de BAM diferentes que han estado relacionadas entre sí mediante exploración distribuida, la actividad remota relacionada se muestra como una actividad relacionada en los detalles de actividad de la instancia de actividad local. Si hace clic en la actividad relacionada, se abre la página de detalles de la actividad para la actividad en el portal remoto. Para obtener más información acerca de las actividades relacionadas de la página de resultados de búsqueda de actividad en el portal BAM, una, consulte [actividades relacionadas](../core/related-activities.md).  
  
> [!IMPORTANT]
>  Para que los usuarios de cada equipo vean las actividades relacionadas que se encuentran en diferentes bases de datos de BAM, debe habilitar la exploración distribuida bidireccional entre todas las bases de datos de BAM.  
  
 Si habilita la exploración distribuida unidireccional entre dos bases de datos de importación principal cuando configura la exploración distribuida, los usuarios tendrán una experiencia asimétrica durante la exploración.  
  
 La experiencia del usuario será tal que éste verá las diferentes actividades. Sin embargo, cuando el usuario obtiene los detalles de los datos de nivel de instancia, la sección en la que se muestran las instancias relacionadas estará vacía. Para solucionar este problema, debe volver a configurar la ruta de exploración distribuida para el usuario como la del servidor de portal de BAM principal.  
  
 Por ejemplo, observe el siguiente caso:  
  
- Tiene un Equipo 1 en el que tiene una actividad denominada Purchase Order y una vista denominada SalesManager.  
  
- Tiene un Equipo 2 en el que tiene una actividad denominada Shipping Order y una vista denominada SalesManager.  
  
- Agrega una actividad denominada PO_1 al Purchase Order en el Equipo 1  
  
- Agrega una actividad denominada SO_1 a Shipping Order en el Equipo 2  
  
- En el Equipo 2 agrega la relación: SO_1 a la actividad PurchaseOrder PO_1 en Shipping Order  
  
- Cuando un usuario obtiene detalles de la actividad SO_1 del Equipo 1, la actividad SO_1 es reconocible  
  
- Si el usuario obtiene detalles de SO_1 en el Equipo 2, la actividad PO_1 no está visible  
  
  Para rectificarlo, será necesario agregar la relación en el Equipo 1.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo configurar la exploración entre actividades distribuidas](../core/how-to-configure-navigation-between-distributed-activities.md)  
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)