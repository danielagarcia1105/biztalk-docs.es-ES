---
title: Cómo actualizar una orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef3f032f-28a1-4d52-9d85-d5748c9e9682
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edd9fa8e98b62ec92b1313cc1028efc5320ce17e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257892"
---
# <a name="how-to-upgrade-an-orchestration"></a>Cómo actualizar una orquestación
Cómo actualizar una orquestación que se ejecuta en un entorno de producción cuando la orquestación controla transacciones de larga ejecución o está esperando una respuesta desde un puerto de petición-respuesta.

## <a name="overview"></a>Información general
 Cuando una orquestación no procesa transacciones de larga ejecución, puede actualizarla como se describe en [lista de comprobación: actualizar los artefactos de una aplicación de BizTalk](../core/checklist-update-the-artifacts-in-a-biztalk-application.md). Sin embargo, si la orquestación procesa transacciones de larga ejecución, no podrá transferir inmediatamente el sistema a la versión actualizada de la orquestación. Debe dejar que la versión original termine de procesar los mensajes para que no se pierdan. Para ello, implemente la orquestación actualizada en la misma aplicación que la original. A continuación, detenga la versión original e inicie la versión actualizada de modo que reciba todos los mensajes nuevos mientras la versión anterior sigue procesando cualquier mensaje en proceso. Cuando la orquestación original termine de procesar todos los mensajes, anule su implementación desde la aplicación de BizTalk en la que se implementó.  
  
 Para obtener más información acerca de este escenario, vea [escenario: actualización de artefactos de la aplicación](../core/scenario-updating-application-artifacts.md).  
  
> [!IMPORTANT]
>  Si hay más de una orquestación enlazada al mismo puerto de recepción y cada una de ellas está iniciada o dada de alta, se insertarán mensajes duplicados en el sistema.  
  
> [!NOTE]
>  Al efectuar la actualización a una nueva orquestación, puede que algunas instancias de orquestación pasen a un estado Suspendido (reanudable) en condiciones de mucha actividad debido a la condición de anticipación de la orquestación antigua y de la orquestación nueva durante la actualización. Para reanudar manualmente estas instancias de orquestación, consulte [cómo reanudar instancias de orquestación suspendidas](../core/how-to-resume-suspended-orchestration-instances.md).

## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. La cuenta también debe tener permiso de lectura/escritura en el sistema de archivos local y la memoria caché global de ensamblados. La cuenta de administradores del equipo local cuenta con este permiso.  

Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx). 
 
## <a name="update-an-orchestration"></a>Actualizar una orquestación  
  
1.  Realice los cambios necesarios en la orquestación.  
  
2.  Incremente el número de versión del ensamblado como se indica a continuación:  
  
    1.  En el Explorador de soluciones, haga clic en el proyecto de BizTalk y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.  
  
    2.  Haga clic en el **aplicación** ficha si aún no está activo y, a continuación, haga clic en **información de ensamblado**.  
  
    3.  En el panel derecho, incremente el número de versión del ensamblado. Incremente únicamente el número principal o secundario de la versión. El número de versión principal es el primer dígito en la secuencia (**0**. 0.0.0); el número de versión secundaria es el segundo dígito en la secuencia (0. **0**. 0.0). BizTalk Server no reconocerá un cambio de número de versión que está más adelante en la secuencia, como 0,0. **0**.0 ó 0.0.0. **0**.  
  
    4.  Haga clic en **Aceptar** para cerrar el **información de ensamblado** cuadro de diálogo.  
  
    5.  Guarde el proyecto.  
  
3.  Implemente el ensamblado en una aplicación de BizTalk desde Visual Studio. Para obtener instrucciones, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md). Asegúrese de seleccionar la opción de implementación para instalar el ensamblado en la GAC.  
  
4.  Pruebe el ensamblado que contiene la orquestación.  
  
5.  Exporte el ensamblado de la aplicación en el entorno de prueba a un archivo .msi, tal y como se describe en [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
    > [!NOTE]
    >  Puede seguir los pasos siguientes para probar el ensamblado e implementarlo en el entorno de producción. Para obtener más información sobre las tareas de implementación de aplicaciones en desarrollo, prueba, ensayo y producción, consulte [tareas de implementación de aplicación](../core/application-deployment-tasks.md).  
  
6.  Importar el archivo .msi en la aplicación de BizTalk en el entorno de producción que contiene la orquestación que desea actualizar, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
7.  Enlazar la orquestación actualizada usando los mismos enlaces que la orquestación original, tal como se describe en [cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md).  
  
8.  Dé de baja la orquestación original y, a continuación, inicie la orquestación actualizada. Para evitar que se quiten mensajes, debe hacerlo mediante programación, como se describe en [implementar e iniciar una nueva versión de una orquestación mediante programación](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md). Como alternativa, puede realizar estos pasos manualmente, tal y como se describe en [cómo dar de baja una orquestación](../core/how-to-unenlist-an-orchestration.md), [cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md), y [cómo iniciar una orquestación](../core/how-to-start-an-orchestration.md).  
  
9. Supervisar el sistema para instancias de la versión original de orquestación que usan el concentrador de grupo página vista de consulta, como se describe en [cómo ver información de instancia para una orquestación](../core/how-to-view-instance-information-for-an-orchestration.md).  
  
10. Cuando se completa todas las instancias activas, deshidratadas y suspendidas, anular la implementación de la orquestación original desde la aplicación, como se describe en [cómo quitar una orquestación de una aplicación](../core/how-to-remove-an-orchestration-from-an-application.md).  
  
11. Si lo desea desinstalar la versión de ensamblado original de la GAC en cada equipo que ejecuta la aplicación, como se describe en [cómo desinstalar un ensamblado de la GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4).  
  
## <a name="see-also"></a>Vea también  
 [Actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md)   
 [Administrar orquestaciones](../core/managing-orchestrations.md)