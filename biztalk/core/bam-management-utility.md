---
title: "Utilidad de administración de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c55aabe2-f38b-4917-863c-b408a4eef98e
caps.latest.revision: "50"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be7c36900c39f46f636077c5c9d0cb630265cc80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-management-utility"></a>Utilidad de administración de BAM
Los administradores de definiciones de Supervisión de la actividad económica (BAM) utilizan la utilidad de administración de BAM para administrar y mantener todos los aspectos de la infraestructura de BAM.  
  
 Puede usar la utilidad de BAM para realizar las tareas siguientes:  
  
-   Utilizar definición de BAM y XML de configuración de BAM como entrada. Los archivos XML o XLS de definición de BAM establecen los datos que se van a agregar y de los que se va a realizar el seguimiento, así como la vista de los datos de seguimiento del usuario empresarial final. El XML de configuración de BAM dicta dónde implementar la infraestructura, como el nombre del servidor, nombre de la base de datos y otra configuración de base de datos.  
  
-   Implemente la infraestructura en tiempo de ejecución en el servidor, que incluye la base de importación principal de BAM, la base de datos de esquema de estrella de BAM, la base de datos de análisis de BAM y los paquetes correspondientes de Servicios de transformación de datos (DTS). Se crean los elementos siguientes en este paso:  
  
    -   Base de datos de importación principal de BAM  
  
    -   Base de datos de esquema de estrella de SAE  
  
    -   Base de datos de archivo SAE  
  
    -   Base de datos de análisis de BAM  
  
> [!NOTE]
>  La configuración local del equipo donde se está ejecutando la utilidad de administración de BAM debe ser la misma que la configuración regional utilizada para crear la definición de BAM que se implementa para que los comandos de BAM funcionen correctamente. Por ejemplo, si ejecuta el **get-views** comando en un equipo configurado con una configuración regional en inglés configuración en una base de datos en un equipo con una configuración regional en francés no podrá usar el nombre de vista devuelta a menos que restablezca su configuración regional del equipo en francés.  
  
 Puede utilizar la utilidad de administración de BAM para generar e implementar su configuración de seguimiento en un servidor. La utilidad de administración de BAM es una herramienta de línea de comandos situada en \< *ruta de acceso de instalación*> \Program BizTalk Server \<versión > \Tracking\BM.exe.  
  
> [!IMPORTANT]
>  Para ejecutar la utilidad de administración de BAM, debe ser miembro de la **db_owner** rol de base de datos de SQL Server en las bases de datos de importación principal de BAM, esquema de estrella de BAM y archivo de BAM. También debe tener permisos de sysadmin en las bases de datos de alertas de BAM si realiza las actualizaciones relacionadas con las alertas de BAM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
## <a name="bam-management-utility-commands"></a>Comandos de la utilidad de administración de BAM  
 Las descripciones de comando usan estas convenciones:  
  
-   Los corchetes ([]) indican un parámetro opcional.  
  
-   Los corchetes angulares (<>) indican un parámetro requerido.  
  
-   Las llaves ({}) indican que ese elemento se debe seleccionar en la lista enumerada.  
  
-   Una cuenta de seguridad puede ser un grupo de NT o una cuenta individual de usuarios NT.  
  
-   Un archivo de definición de BAM puede ser un archivo XML o un archivo de libro de Excel (.xls) de BAM.  
  
-   Si no se proporciona el archivo de configuración de BAM, se predetermina un archivo BamConfiguration.xml en la carpeta actual.  
  
 Las descripciones de comandos individuales se incluyen en los siguientes temas:  
  
-   [Comandos de base de datos](../core/database-commands.md)  
  
-   [Implementación de comandos (modelo de observación) de definición de BAM](../core/deployment-of-bam-definition-observation-model-commands.md)  
  
-   [Comandos de administración de infraestructura](../core/infrastructure-management-commands.md)  
  
-   [Comandos de administración de la actividad](../core/activity-management-commands.md)  
  
-   [Comandos de administración de vista](../core/view-management-commands.md)  
  
-   [Comandos de administración de alertas](../core/alert-management-commands.md)  
  
-   [Comandos de administración de usuario](../core/user-management-commands.md)  
  
-   [Comandos de administración de la suscripción de alerta](../core/alert-subscription-management-commands.md)  
  
-   [Comandos de administración de interceptor](../core/interceptor-management-commands.md)  
  
## <a name="displaying-the-bam-management-utility-help"></a>Mostrar la Ayuda de la utilidad de administración de BAM  
 ¿Usa el **/?** o **ayuda de la utilidad de administración de BAM** comando para mostrar el archivo de Ayuda de la utilidad de administración de BAM.  
  
#### <a name="to-display-the-help-file-for-the-bam-management-utility"></a>Para mostrar el archivo de Ayuda de la utilidad de administración de BAM  
  
1.  Desde un símbolo del sistema, vaya al siguiente directorio: C:\Program Files\Microsoft BizTalk Server \<versión > \Tracking\\.  
  
2.  Tipo de **bm** o **ayuda bm**.  
  
3.  Presione ENTRAR.