---
title: 'Paso 3: crear las definiciones de compilación y la versión | Documentos de Microsoft'
description: En VSTS, cree una definición de compilación para compilar los proyectos en el repositorio TFS o git, a continuación, crear una definición de la versión para implementar la aplicación de BizTalk Server
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ce84071fbc105fd9faddd794792273aae2e76b9
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="step-3-create-the-build-and-release-definition"></a>Paso 3: Crear la compilación y la versión de definición

Las definiciones de compilación y la versión son tareas de Visual Studio Team Services y probablemente deben hacerse mediante un administrador de VSTS. La definición de compilación compila el proyecto en el repositorio git y las definiciones de versión lo implementa en el entorno de BizTalk Server. 

## <a name="before-you-begin"></a>Antes de empezar
Completa [paso 2: símbolo (token) de VSTS crear e instalar el agente](feature-pack-create-vsts-token.md).

## <a name="add-the-build-tasks"></a>Agregue las tareas de compilación
1. En el proyecto, seleccione **de compilación y la versión**. Se abre la pestaña de compilaciones. Crear un **New** definición:

    ![Nueva definición de compilación](../core/media/vsts-new-definition.png)

2. Seleccione el **vacía** plantilla y seleccione **aplicar**:  

    ![Seleccione la plantilla vacía](../core/media/vsts-emtpy-template.png)
 
3. Establecer el **cola del agente** valores predeterminados: 

    ![Elija la cola de forma predeterminada](../core/media/vsts-select-agent-queue.png)

4. En **fase 1**, agregue una tarea, seleccione **Visual Studio Build**y seleccione **agregar**:

    ![Agregar la que tarea de compilación de VS](../core/media/vsts-add-visual-studio-task.png)

5. Haga clic en la tarea de compilación de Visual Studio que acaba de agrega y establezca las siguientes propiedades:  

    | Propiedad | Establecer en |
    | --- | --- | 
    | Nombre para mostrar | *NombreDeProyecto* compilar solución **\*.sln | 
    | Versión de Visual Studio | Visual Studio 2015 | 
    | Arquitectura de MSBuild | MSBuild x86 | 

6. En **fase 1**, agregue una tarea, seleccione **publicar artefactos de compilación**y seleccione **agregar**: 

    ![Agregar la que tarea de compilación de VS](../core/media/vsts-add-publish-build-task.png)

7. Seleccione el **publicar artefacto** de tareas y escriba su preferido **nombre para mostrar**. Para **ruta de acceso para publicar**, seleccione la **...**  botón y elija la carpeta de proyecto de aplicación (por ejemplo, appProjectHelloWorld). Seleccione **Aceptar**.

8. El **nombre del artefacto** puede ser cualquier cosa que desee. Seleccione **guardar**. 

9. Vaya a **desencadenadores**y establezca el **desencadenar estado** a **habilitado**:  

    ![Agregar la que tarea de compilación de VS](../core/media/vsts-continuous-integration.png)

10. **Guardar y poner en cola** para probar la definición de compilación. Cuando pone en cola, se le solicitará la cola del agente y la bifurcación. Seleccione el **predeterminado** agente de cola y elija la bifurcación. Seleccione **cola**.  

11. Se inicia una nueva compilación, y puede seleccionarlo para comprobar si un éxito o error. 

## <a name="add-the-release-tasks"></a>Agregue las tareas de versión

Cuando la compilación se realiza correctamente, la definición de la versión implementa la aplicación en el servidor BizTalk Server. 

1. Seleccione el **versiones** ficha, seleccione **nueva definición**. 

2. Seleccione el **vacía** plantilla y seleccione **aplicar**:

    ![Agregar plantilla vacía](../core/media/vsts-empty-release-template.png)

3. Cambiar el **nombre del entorno** a **Dev**, o todo lo que desees para que se llame. 

4. Seleccione **agregar artefactos**, seleccione el proyecto, la definición de compilación y seleccione **agregar**: 

5. Vaya a la **tareas** ficha, agregue una nueva tarea: 

    ![Agregar la tarea de liberación](../core/media/vsts-new-release-tasks.png)

6. En la lista, filtrar los resultados, seleccione la **implementación de aplicación de BizTalk Server** de tareas y seleccione **agregar**:  

    ![Agregar tareas de implementación de BizTalk](../core/media/vsts-biztalk-application-deployment-task.png)

    Si **implementación de aplicación de BizTalk Server** ins't en la lista, vuelva a instalarlo después en [implementar aplicación de BizTalk](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application).

7. Seleccione el **implementar** , escriba los valores y de la tarea: 

    **Nombre de la operación**: las opciones: * **crear nueva aplicación de BizTalk**: implementa una nueva aplicación. Si la aplicación ya existe, desinstala las aplicaciones actuales (detención completa) e instala la nueva aplicación. Si está habilitada la integración continua, lo automáticamente vuelve a implementar la aplicación cuando se actualiza en el repositorio. 
        * **Actualizar una aplicación de BizTalk existente**: anexa los cambios, como esquemas, a una aplicación ya se está ejecuta. No se requiere una nueva implementación completa de la aplicación.
        * **Instalar la aplicación de BizTalk Server**: [instalar las aplicaciones](../core/how-to-install-a-biztalk-application.md), y escriba el nombre del equipo de administración de BizTalk y la ruta de acceso del paquete de implementación.

        ![Deploy operations](../core/media/vsts-deploy-operations.png)

    **Nombre de la aplicación**: el texto que escriba será el nombre de aplicación de administración de BizTalk. Hacer **no** escriba BizTalk Application 1.

    **Paquete de implementación**: seleccione el archivo zip en el proyecto de aplicación y seleccione **Aceptar**. 

8. Seleccione el **fase agente** tarea. Seleccione el **predeterminado** cola del agente. **Guardar** los cambios.

9. Seleccione **versión** > **crear versión**:  

    ![La versión, crear versión](../core/media/vsts-create-release.png)

10. Seleccione **cola**. Compruebe el estado haciendo clic en el vínculo de la versión. Si se produce un error, se muestra el error. Si se realiza correctamente, la aplicación se agrega a la consola de administración de BizTalk. 

## <a name="what-you-did"></a>Lo que hizo

En VSTS, ha creado una definición de compilación que compile su aplicación en Git o Team Foundation Version Control (lo que ha elegido). Cuando se realizan cambios en el control de código fuente, los cambios se detectan automáticamente y puede insertarlas. Una vez finalizada la compilación, se crea una definición de la versión que implementa la aplicación en BizTalk Server, que puede ver en administración de BizTalk Server. 

## <a name="next-step"></a>Paso siguiente
En este paso, ha terminado. Si lo prefiere, puede crear tokens medioambientales dentro del archivo de enlace XML de BizTalk y crear variables del sistema en VSTS que coinciden con los tokens de entorno. Vea [configurar tokens de entorno y variables](configure-environmental-tokens-and-variables-for-automatic-deployment.md) para obtener los detalles. 