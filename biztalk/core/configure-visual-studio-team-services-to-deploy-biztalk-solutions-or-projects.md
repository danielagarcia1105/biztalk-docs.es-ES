---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: Configurar Visual Studio Team Services para implementar soluciones de BizTalk Server o proyectos | Microsoft Docs
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
ms.openlocfilehash: 8b13ef6f56e892bb3598096272d876c5f0a865f3
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826308"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a>Configurar Visual Studio Team Services para implementar proyectos o soluciones de BizTalk Server
Configurar VSTS para implementar automáticamente [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proyectos. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , puede generar automáticamente su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] soluciones mediante Visual Studio Team Services (VSTS). 

Este tema muestra cómo instalar y configurar Visual Studio Team Service (VSTS) para usar la implementación automática de BizTalk. 

> [!IMPORTANT]
> El agente VSTS solo puede instalarse en uno [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo. 

## <a name="prerequisites"></a>Requisitos previos

* Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* Algo de experiencia y conocimientos sobre crear y trabajar con definiciones en VSTS. Si está familiarizado con VSTS, pueden ser buenos recursos: 

  [Información general de Visual Studio Team Services](https://www.visualstudio.com/docs/overview)  
  [CI/CD para principiantes](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a>Crear una cuenta de VSTS y crear una definición

1. En un explorador web, vaya a su [perfil de Visual Studio online](https://app.vsaex.visualstudio.com/go/profile), inicie sesión y seleccione un **crear nueva cuenta**:

    ![Crear nueva cuenta](../core/media/create-a-new-account.png)

2. Escriba un nombre para la cuenta, seleccione el repositorio de código fuente preferido y seleccione **continuar**:

    ![Crear un nuevo proyecto](../core/media/create-a-new-project.png)

3. Se crea la nueva cuenta y un sitio similar a `https://YourAccountName.visualstudio.com/MyFirstProject` se abre.
    
4. Instalar el [servicios de implementación de la aplicación BizTalk](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application) a la cuenta que acaba de crear.

    ![Crear nueva versión](../core/media/build-new-release.png)

5. Puede obtener algunas solicitudes. Confirmar para continuar. Asegúrese de que ha iniciado sesión el proyecto en VSTS.

6. Seleccione **compilación y versión**y crear un **New** definición de compilación:

    ![Seleccione la compilación y versión](../core/media/select-build-and-release.png)

    > [!TIP]
    > Asegúrese de estar en `https://YourAccountName.visualstudio.com/MyFirstProject`. En caso contrario, el **New** o **nueva definición** botones no pueden estar allí. 
    
7. Seleccione el **Visual Studio** plantilla y seleccione **siguiente**:

    ![Seleccione visual studio y haga clic en siguiente](../core/media/select-visual-studio-and-click-next.png)

8. Revise la configuración y seleccione **crear**.

9. Eliminar los pasos que no es necesario. Para este tutorial, puede eliminar lo siguiente: 
10. Restauración de NuGet
11. Ensamblados de prueba
12. Publicar ruta de acceso de símbolos 

      ![Eliminar los pasos que no sea necesarios](../core/media/delete-steps-not-needed.png)

13. **Opcional**. Si desea habilitar la integración continua (CI), seleccione **desencadenadores** en el menú y verificación **integración continua (CI)**.

A continuación, instale el agente en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

## <a name="install-the-agent"></a>Instalar el agente

Para que funcione la solución, habilite a un agente privado de Windows en el equipo local. Recuerde, **el agente debe instalarse en una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo**. 

1. En la definición, seleccione el **General** pestaña (en la parte superior).
2. Para el **cola de agentes predeterminada** propiedad, seleccione el **predeterminado** agente desde la lista. 
3. Seleccione **administrar** junto a la **cola de agentes predeterminada** propiedad. Se abre una nueva pestaña del explorador.

    ![Crear a nuevo agente de administración](../core/media/create-new-management-agent.png)

4. En el panel izquierdo, se selecciona la cola predeterminada. Si un agente ya está activa y en línea, a continuación, ya ha terminado. Tiene un agente instalado y ejecutándose. 

    Si un agente no aparece, seleccione **descargar agente**y continuar con la instalación en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. **Vaya a [implementar un agente en Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows) para conocer los pasos completos** para instalar el agente e iniciar un agente. 

    > [!IMPORTANT]
    > Siga los pasos descritos en [implementar un agente en Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows). No omita este paso. 

5. Con el agente de forma predeterminada **Online**, vuelva a la **General** pestaña en la definición y confirme **predeterminada** está seleccionada para la **cola de agentes predeterminada**.
6. **Guardar** y **poner nueva compilación en cola**.

A continuación, cree la definición de implementación de aplicación de BizTalk Server.

## <a name="create-the-biztalk-deployment-definition"></a>Crear la definición de implementación de BizTalk

1. Seleccione el **compilaciones** ficha, seleccione **todas las definiciones de**y seleccione **New**:

    ![Crear nueva definición de versión](../core/media/create-new-release-definition.png)

2. Seleccione el **vacía** plantilla y seleccione **siguiente**:

    ![Crear nueva definición de una plantilla vacía](../core/media/create-new-definition-from-an-empty-template.png)

3. Seleccione su **repositorio** origen y **rama** para la definición.
4. **Opcional**. Seleccione **integración continua**.
5. Seleccione el **predeterminado** agente desde la lista de la cola y seleccione **crear**.
6. **Agregar paso de compilación**, seleccione el **implementación de aplicación de BizTalk Server** de tareas y seleccione **agregar**. **Cerrar** el catálogo de tareas.

    ![Agregar definición puede implementar](../core/media/add-new-deploy-definition.png)

7. Seleccione el **nombre de la operación** que desea usar:

    * **Crear nueva aplicación de BizTalk** implementa una nueva aplicación. Si la aplicación ya existe, se desinstala las aplicaciones actuales (detención completa) y se instala la nueva aplicación. Si está habilitada la integración continua, lo automáticamente vuelve a implementar la aplicación cuando se actualizan en el repositorio.
    * **Actualizar una aplicación de BizTalk existente** anexa los cambios, como **esquemas** a una aplicación ya se está ejecutando. No se requiere una reimplementación completa de la aplicación.

8. Escriba el **nombre de la aplicación** en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno.
9. En **ruta de acceso de paquete de implementación**, seleccione la ruta de acceso al archivo zip del repositorio.
10. Seleccione **desencadenadores** en el menú, habilitar **integración continua**y seleccione el valor correcto **rama** para la compilación.
11. Seleccione **guardar**:

    ![Guarde la nueva definición de compilación](../core/media/save-the-new-build-definition.png)

12. El nombre del nuevo **definición**y establezca la ruta de acceso correcta. 
13. Una vez que se guarda la definición, seleccione **poner en cola la nueva compilación**. A continuación, seleccione el **agente cola**y agregue un comentario a la confirmación.
