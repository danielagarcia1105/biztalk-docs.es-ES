---
title: "Cómo implementar una nueva versión de una aplicación se ejecute en paralelo con una versión existente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1677c6a5-2c4c-4d70-ab83-f7e0bb3aaf6e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053145729546453b959dc35c7901932c1c8690c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-a-new-version-of-an-application-to-run-side-by-side-with-an-existing-version"></a>Cómo implementar una nueva versión de una aplicación para que se ejecute de manera simultánea con una versión existente
Cómo implementar una nueva versión de una aplicación que se ejecutará en paralelo con una versión existente. 

## <a name="overview"></a>Información general
Puede que desee hacerlo para implementar de manera gradual una actualización de una aplicación fundamental; por ejemplo, al principio podría ponerla a disposición de un subconjunto de socios comerciales, en lugar de implementarla para todos a la vez. Este enfoque permite continuar ejecutando la aplicación existente para prestar servicio a los usuarios que aún no están usando la versión nueva hasta que esté preparado para pasar totalmente a la nueva versión. Para obtener información general sobre este escenario, vea [escenario: implementar dos versiones de una aplicación](../core/scenario-deploying-two-versions-of-an-application.md).  
  
 Las versiones de aplicaciones no se crean incrementando el número de versión de la misma manera que con las versiones de ensamblados. En cambio, se crea una nueva aplicación con un nombre distinto a la aplicación original y se rellena con las nuevas versiones de los artefactos de la aplicación.  
  
 Puesto que en un mismo grupo de BizTalk pueden existir muchos tipos de artefactos, tales como ensamblados, es preciso incrementar el número de versión de todos los ensamblados que ya existan en el grupo para poder implementarlos en la nueva aplicación. Para obtener más información, consulte [artefactos que deben ser únicos en una aplicación o un grupo de](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).  

## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. La cuenta también debe tener permiso de lectura/escritura en el sistema de archivos local y la memoria caché global de ensamblados. La cuenta de administradores del equipo local cuenta con este permiso.  

Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx). 
  
## <a name="deploy-a-new-version-of-an-application"></a>Implementar una nueva versión de una aplicación  
  
1.  En Visual Studio, realice los cambios necesarios en los ensamblados que desee implementar en la nueva versión de la aplicación.  
  
2.  Incremente el número de versión de cada ensamblado, como se indica a continuación:  
  
    1.  En el Explorador de soluciones, haga clic en el proyecto de BizTalk y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.  
  
    2.  Haga clic en el **aplicación** pestaña si no está activo y, a continuación, haga clic en **información de ensamblado** botón.  
  
    3.  Aumentar el número de versión del ensamblado y, a continuación, haga clic en **Aceptar**.  
  
    4.  Guarde el proyecto.  
  
    > [!NOTE]
    >  Utilice el modelo de objetos del Diseñador de canalizaciones para evitar conflictos entre los esquemas al incrementar las versiones de los ensamblados.  
  
3.  En las propiedades de implementación de cada proyecto de la solución, haga lo siguiente:  
  
    -   Cambie el nombre de la aplicación por el nombre que desee utilizar para la nueva aplicación.  
  
    -   Asegúrese de que esté seleccionada la opción de instalación de ensamblados en la caché de ensamblados global (GAC).  
  
     Para obtener instrucciones, consulte [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md). Al implementar la solución, los ensamblados se implementarán en la nueva aplicación y se instalarán en la GAC.  
  
4.  Implemente la o las soluciones que contienen los ensamblados. Para obtener instrucciones, consulte [cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).  
  
5.  Cree un nuevo puerto de recepción y las ubicaciones de recepción necesarias especificando las nuevas direcciones URL a las que desee que los socios envíen los mensajes. Para obtener instrucciones, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md). Consulte también [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
6.  Crear los puertos de envío adecuado según sea necesario, como se describe en [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).  
  
7.  Enlace la nueva aplicación en recién creada de recepción y puertos de envío, como se describe en [cómo configurar una aplicación](../core/how-to-configure-an-application.md).  
  
8.  Exportar la aplicación a un archivo .msi desde el entorno de prueba, como se describe en [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
    > [!NOTE]
    >  Puede usar los pasos siguientes para probar la aplicación e implementarla en el entorno de producción. Para obtener más información sobre las tareas de implementación de aplicaciones en desarrollo, prueba, ensayo y producción, consulte [tareas de implementación de aplicación](../core/application-deployment-tasks.md).  
  
9. Importar el archivo .msi de aplicación en el grupo de BizTalk en el entorno de producción, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Si la aplicación requiere referencias, puede agregarlos al usar el Asistente para la importación de MSI o, más adelante tal como se describe en [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
10. Instale la nueva aplicación en cada instancia de host que se ejecutará, como se describe en [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md). Compruebe que cada ensamblado actualizado se ha instalado en la GAC de cada equipo donde se aloje el ensamblado. Si es necesario, instale los ensamblados en la GAC, como se describe en [cómo instalar un ensamblado en la GAC](../core/how-to-install-an-assembly-in-the-gac.md).  
  
11. Realizar un inicio completo de la aplicación, como se describe en [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
12. Notifique a los socios que deben comenzar a enviar los mensajes a las nuevas direcciones URL. Cuando lo hagan, la aplicación comenzará a procesar los mensajes de los socios especificados.  
  
## <a name="see-also"></a>Vea también  
 [Actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md)