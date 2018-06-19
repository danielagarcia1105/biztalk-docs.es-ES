---
title: Opciones de menú del TPE | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, menu options
- activities [BAM], importing
- activities [BAM], definitions
ms.assetid: 5179fcb5-6dab-481d-ad89-3868c8b07383
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e04d2dfcd6d7f34b0a60a450b64e217b02390a6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010629"
---
# <a name="tpe-menu-options"></a>Opciones de menú del TPE
En este tema se describen las opciones de menú del Editor de perfiles de seguimiento (TPE). Los menús principales incluyen Archivo, Herramientas y Ayuda.  
  
 La funcionalidad adicional específica de la intercepción de mensajería se expone en el menú contextual de elementos mostrados en la vista Actividad, en el panel izquierdo de la aplicación.  
  
## <a name="file-menu"></a>Menú Archivo  
 El menú Archivo contiene las opciones siguientes:  
  
-   **Nueva** : crea un nuevo perfil de seguimiento. Esta opción siempre está disponible.  
  
-   **Abra** : abre un perfil de seguimiento existente. Esta opción siempre está disponible.  
  
-   **Guardar** – guarda el perfil de seguimiento que actualmente se está editando. Si no se edita ningún perfil de seguimiento, esta opción no está disponible.  
  
-   **Guardar como** – guarda el perfil de seguimiento que actualmente se está editando con un nombre que especifique. Si no se edita ningún perfil de seguimiento, esta opción no está disponible.  
  
-   **Importar definición de actividad de BAM** – importa una definición de actividad que se ha aplicado. Este elemento de menú tiene la misma funcionalidad que el vínculo de marca de agua del marco izquierdo, lo que significa que el usuario puede iniciar esta acción desde cualquier lugar (la marca de agua es un tipo de sugerencia de utilidad). Esta opción siempre está disponible cuando se encuentra una conexión a la base de datos de administración de BizTalk y a la base de datos de importación principal de BAM.  
  
-   **Salida** : cierra el TPE. Si sale durante una edición activa invoca Guardar o Guardar como estándares de Windows. Esta opción siempre está disponible.  
  
### <a name="new-profile"></a>Nuevo perfil  
 El **nuevo perfil** opción de menú abre un espacio en blanco seguimiento de archivo de código fuente de perfil no tienen contenidos en un archivo BTT vacío (archivo de perfil de seguimiento). El nombre predeterminado del nuevo perfil es TrackingProfile1 (…2, 3, etc.).  
  
> [!NOTE]
>  De forma predeterminada, la base de datos de administración de BizTalk está configurada como la base de datos de administración de BizTalk del grupo de BizTalk. Para cambiar la base de datos de administración, use la **establecer base de datos Mgmt** opción el **herramientas**. La configuración de la base de datos de administración de BizTalk se conserva entre sesiones.  
  
### <a name="open"></a>Abrir  
 El **abiertos** opción de menú permite al usuario buscar y seleccionar un perfil único con el que se va a trabajar. Los perfiles dependen de los ensamblados con respecto a los que se crearon y que están disponibles para presentar y validar el perfil.  
  
 Si el ensamblado implementado original ya no está disponible o si necesita cambiar el ensamblado al que está asociado el perfil, tiene la opción de invocar explícitamente el **establecer base de datos Mgmt** acción para actualizar este vínculo. También puede modificar el perfil y aplicarlo.  
  
### <a name="save"></a>Guardar  
 El **guardar** opción guarda el perfil de seguimiento que actualmente se está editando. La primera vez que se selecciona Guardar de nuevo un perfil de seguimiento, la opción invoca el **Guardar como** cuadro de diálogo.  
  
### <a name="save-as"></a>Guardar como  
 El **Guardar como** opción le permite especificar la carpeta y el nombre del perfil de seguimiento. La extensión predeterminada para el archivo de perfil de seguimiento es .btt.  
  
### <a name="import-bam-activity-definition"></a>Importar definición de actividad de BAM  
 El **Importar definición de actividad de BAM** opción abre el cuadro de diálogo Importar definición de actividad de BAM que se rellena con una lista de definiciones de actividad BAM se encuentra en la base de datos de importación principal de BAM.  
  
 Esta característica también se invoca haciendo clic en **haga clic aquí para seleccionar un vínculo de la definición de actividad de BAM** en la vista de actividad de un nuevo perfil de seguimiento.  
  
 **Recuperar casilla de verificación de perfil existente**  
  
 Esta casilla de verificación le permite extraer e incluir asignaciones de perfiles de seguimiento existentes de la definición de actividad.  La casilla de verificación no está activada de forma predeterminada.  
  
> [!NOTE]
>  Cuando se importan definiciones de actividad de BAM con sus configuraciones de seguimiento, las asignaciones existentes se validan con respecto a los ensamblados, orquestaciones, esquemas y puertos en la base de datos de administración de BizTalk seleccionada actualmente. Si las asignaciones no son válidas con respecto a la base de datos, aparecerá un icono de error al lado de la asignación no válida. Las instancias donde se podría producir esto son un perfil de seguimiento que se implementó antes de que se anulara la implementación de un ensamblado, o cuando varios grupos o varias bases de datos de administración de BizTalk comparten la base de datos de importación principal de BAM. En el último caso, aparecerán los iconos de error si el perfil de seguimiento se implementó desde un grupo y si se importó desde otro grupo.  
  
### <a name="exit"></a>Salir  
 El **Exit** opción cierra el TPE. Si ha habido una modificación del perfil de seguimiento, se le pedirá que guarde el perfil al cerrarse el Editor de perfiles de seguimiento.  
  
## <a name="tools-menu"></a>Menú Herramientas  
 El menú Herramientas contiene las opciones siguientes:  
  
-   **Aplicar perfil de seguimiento** : almacena el perfil en la base de datos de importación principal de BAM.  
  
-   **Quitar perfil de seguimiento** : quita el seguimiento de asignaciones de la base de datos de importación principal de BAM de perfil.  
  
-   **Establecer base de datos de administración** – establece la base de datos de administración que funciona con el TPE.  
  
-   **Opciones de** – le permite establecer opciones del TPE.  
  
### <a name="apply-tracking-profile"></a>Aplicar perfil de seguimiento  
 El **aplicar perfil de seguimiento** opción de menú almacena el perfil de seguimiento de asignación en el ensamblado especificado, así como para las orquestaciones y puertos correspondientes. Todos los artefactos a los que se hace referencia en el perfil de seguimiento deberían estar disponibles en una base de datos de administración de BizTalk determinada. Todas las instancias nuevas de los servicios más importantes utilizan el perfil de seguimiento nuevo al iniciar.  
  
 Puede trabajar al mismo tiempo con varios ensamblados. No funciona simultáneamente con los ensamblados, pero se puede tener el acceso a varios ensamblados en una sesión única de edición con respecto a cualquier definición  única de actividad de BAM  Es decir, si importa una definición de actividad de BAM y si a continuación, selecciona tres ensamblados desde los que trazar elementos de los que se ha realizado un seguimiento, el perfil que crea el TPE se aplica a varios perfiles que están asociados a las orquestaciones y puertos que se utilizan en el perfil de seguimiento. El perfil de seguimiento siempre contiene información sobre todos los ensamblados asociados a cualquier definición dada de actividad de BAM.  
  
> [!CAUTION]
>  En BizTalk Server, cada actividad de BAM sólo puede tener un perfil de seguimiento que se implementan en el mismo. Es decir, si implementa un perfil que tiene asignada una actividad a una orquestación, y si implementa posteriormente un perfil diferente que tiene asignada la misma actividad a una orquestación diferente, el primer perfil implementado se sobrescribe.  
  
### <a name="remove-tracking-profile"></a>Quitar perfil de seguimiento  
 El **quitar perfil de seguimiento** opción de menú quita el perfil de seguimiento para la definición de actividad carga y sus correspondientes orquestaciones y puertos. Se le pedirá que confirme antes de que se finalice esta acción.  
  
### <a name="set-management-database"></a>Configurar la base de datos de administración  
 El **establecer base de datos de administración** opción de menú especifica la base de datos de administración de BizTalk desde que la asignación se pueden elegir orígenes y, a través de la que BAM se encuentran las definiciones de actividad. De forma predeterminada, el perfil de seguimiento está establecido como la base de datos de administración de BizTalk que determinó durante la configuración.  
  
 Las cadenas de conexión de SQL pueden especificarse en uno de dos maneras:  
  
-   Puede especificar únicamente el nombre del servidor, y el Editor de perfiles de seguimiento (TPE) se conectará al puerto predeterminado.  
  
-   Puede especificar un nombre de servidor y número de puerto del par, ServerName, el puerto. El Editor de perfiles de seguimiento se conectará al equipo que ejecuta el servidor SQL Server que utiliza el puerto especificado.  
  
## <a name="help-menu"></a>Menú Ayuda  
 El menú Ayuda contiene las opciones siguientes:  
  
-   **Ayuda de BizTalk Server** : abre el archivo de Ayuda de BizTalk Server.  
  
-   **Ayuda del Editor de perfiles de seguimiento** – abre la sección del TPE en el archivo de Ayuda de BizTalk Server.  
  
-   **El servidor BizTalk Server en línea** -abre la Ayuda en línea del servidor BizTalk Server.  
  
-   **Editor de perfiles de seguimiento** : muestra la información estándar acerca.  
  
## <a name="see-also"></a>Vea también  
 [Componentes del TPE](../core/components-of-the-tpe.md)   
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)