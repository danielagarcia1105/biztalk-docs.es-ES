---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: Configurar Visual Studio Team Services para implementar soluciones de BizTalk Server o los proyectos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2555712a-dfe4-420e-9a61-1d1a6d98c322
caps.latest.revision: 6
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 95d8e9fc274793471335fc03bc38c82c1b3e3469
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054588"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a>Configurar Visual Studio Team Services para implementar soluciones de BizTalk Server o los proyectos
Configurar VSTS para implementar automáticamente [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proyectos. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , puede generar automáticamente su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] soluciones mediante Visual Studio Team Services (VSTS). 

En este tema se muestra cómo instalar y configurar Visual Studio Team Service (VSTS) para usar la implementación automática de BizTalk. 

> [!IMPORTANT]
> El agente VSTS solo puede instalarse en uno [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo. 

## <a name="prerequisites"></a>Requisitos previos

* Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* Algunos experiencia y conocimientos de crear y trabajar con definiciones de VSTS. Si está familiarizado en VSTS, puede tratarse de buenos recursos: 

  [Introducción a Visual Studio Team Services](https://www.visualstudio.com/docs/overview)  
  [Elemento de configuración/CD para principiantes](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a>Cree una cuenta VSTS y crear una definición

1. En un explorador web, vaya a su [perfil en línea de Visual Studio](https://app.vsaex.visualstudio.com/go/profile), inicie sesión y seleccione un **crear nueva cuenta**:

    ![Crear nueva cuenta](../core/media/create-a-new-account.png)

2. Escriba un nombre para la cuenta, seleccione el repositorio de código fuente preferida y seleccione **continuar**:

    ![Crear un nuevo proyecto](../core/media/create-a-new-project.png)

3. Se crea la nueva cuenta y un sitio similar a `https://YourAccountName.visualstudio.com/MyFirstProject` se abre.
    
4. Instalar el [servicio de implementar la aplicación de BizTalk](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application) a la cuenta que acaba de crear.

    ![Nueva versión de compilación](../core/media/build-new-release.png)

5. Es posible que obtenga algunos mensajes. Confirmar para continuar. Asegúrese de que ha iniciado sesión el proyecto en VSTS.

6. Seleccione **compilación y versión**y crear un **New** definición de compilación:

    ![Seleccione la compilación y versión](../core/media/select-build-and-release.png)

    > [!TIP]
    > Asegúrese de que está en `https://YourAccountName.visualstudio.com/MyFirstProject`. En caso contrario, el **New** o **nueva definición** botones no pueden estar no existe. 
    
7. Seleccione el **Visual Studio** plantilla y seleccione **siguiente**:

    ![Seleccione visual studio y haga clic en siguiente](../core/media/select-visual-studio-and-click-next.png)

8. Revise la configuración y seleccione **crear**.

9. Eliminar los pasos que no es necesario. Para este tutorial, se pueden eliminar los siguientes: 
* Restauración de NuGet
* Ensamblados de prueba
* Publicar la ruta de acceso de símbolos 

    ![Eliminar los pasos que no sea necesarios](../core/media/delete-steps-not-needed.png)

10. **Opcional**. Si desea habilitar la integración continua (CI), seleccione **desencadenadores** en el menú y verificación **integración continua (CI)**.

A continuación, instale el agente en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

## <a name="install-the-agent"></a>Instalar el agente

Para que funcione la solución, habilitar a un agente de Windows privada en el equipo local. Recuerde que **el agente debe instalarse en una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo**. 

1. En la definición, seleccione la **General** pestaña (en la parte superior).
2. Para el **cola predeterminada del agente** propiedad, seleccione la **predeterminado** agente desde la lista. 
3. Seleccione **administrar** junto a la **cola predeterminada del agente** propiedad. Se abre una nueva pestaña de explorador.

    ![Crear a nuevo agente de administración](../core/media/create-new-management-agent.png)

4. En el panel izquierdo, está seleccionada la cola de forma predeterminada. Si un agente ya está lista y, a continuación, en línea, a continuación, ha terminado. Tiene un agente instalado y ejecutándose. 

    Si no se incluye un agente, a continuación, seleccione **descargar agente**y continuar con la instalación en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. **Vaya a [implementar un agente en Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows) para todos los pasos** para instalar el agente e iniciar un agente. 

    > [!IMPORTANT]
    > Siga los pasos descritos en [implementar un agente en Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows). No omita este paso. 

5. Con el agente predeterminado **en línea**, vuelva a la **General** pestaña en la definición y confirme **predeterminado** está seleccionada para el **cola predeterminada del agente**.
6. **Guardar** y **poner nueva compilación en cola**.

A continuación, cree la definición de la implementación de aplicación de BizTalk Server.

## <a name="create-the-biztalk-deployment-definition"></a>Crear la definición de la implementación de BizTalk

1. Seleccione el **compilaciones** ficha, seleccione **todas las definiciones de**y seleccione **New**:

    ![Crear definición de la nueva versión](../core/media/create-new-release-defintion.png)

2. Seleccione el **vacía** plantilla y seleccione **siguiente**:

    ![Crear nueva definición de una plantilla vacía](../core/media/create-new-defintion-from-an-empty-template.png)

3. Seleccione el **repositorio** origen y **bifurcación** para la definición.
4. **Opcional**. Seleccione **integración continua**.
5. Seleccione el **predeterminado** agente en la lista de la cola y seleccione **crear**.
6. **Agregar el paso de compilación**, seleccione la **implementación de aplicación de BizTalk Server** de tareas y seleccione **agregar**. **Cerrar** el catálogo de la tarea.

    ![Agregar nuevo implementar definición](../core/media/add-new-deploy-definition.png)

7. Seleccione el **nombre de la operación** que desea usar:
    * **Crear nueva aplicación de BizTalk** implementa una nueva aplicación. Si la aplicación ya existe, desinstala las aplicaciones actuales (detención completa) e instala la nueva aplicación. Si está habilitada la integración continua, lo automáticamente vuelve a implementar la aplicación cuando se actualiza en el repositorio.
    * **Actualizar una aplicación de BizTalk existente** anexa los cambios, como **esquemas** a una aplicación ya se está ejecuta. No se requiere una nueva implementación completa de la aplicación.
8. Escriba el **nombre de la aplicación** en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno.
9. En **ruta de acceso de paquete de implementación**, seleccione la ruta de acceso al archivo zip en el repositorio.
10. Seleccione **desencadenadores** en el menú, habilitar **integración continua**y seleccione el valor correcto **bifurcación** para la compilación.
11. Seleccione **guardar**:

    ![Guarde la nueva definición de compilación](../core/media/save-the-new-build-definition.png)

12. Nombre de la nueva **definición**y establezca la ruta de acceso correcta. 
13. Una vez que se guarda la definición, seleccione **la nueva compilación en cola**. A continuación, seleccione la **agente cola**y agregar un comentario a la confirmación.
