---
title: "Configurar los tokens de entorno y variables para la implementación automática | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 7d148f79fceb68b24feb45882ab89767369ed7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a>Configurar los tokens de entorno y variables para la implementación automática
Usar variables de Visual Studio Team Services (VSTS) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] archivos de enlace.

## <a name="overview"></a>Información general
En un entorno de VSTS, puede agregar las variables y establecerlos en un valor. Por ejemplo, puede crear un *sendPortPath* variable y establezca su valor en una carpeta física en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

En el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] archivo de enlace de la aplicación, las variables configurables pueden ser cualquier elemento dentro de una etiqueta XML, como el nombre de la ubicación de recepción, host, URI del puerto de envío y así sucesivamente. 

Estas variables son específicas de su entorno de VSTS y puede utilizarse para implementar la misma aplicación para varios [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos. 

En este tema, se muestra cómo se agrega la variable VSTS en el archivo de enlace y cómo crear la variable dentro de VSTS. 

## <a name="configure-the-variables-in-your-biztalk-binding-file"></a>Configurar las variables en el archivo de enlace de BizTalk

El ejemplo siguiente es una parte de una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] el archivo de enlace y muestra cómo aplicar los tokens.

1. Abra el archivo de enlace de la aplicación:

    ![Paquete de características de BizTalk 1 enlace 1](../core/media/biztalk-feature-pack-1-binding-1.png)

2. Busque el elemento que desea cambiar:

    ![Paquete de características de BizTalk 1 enlace 2](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. Quitar el valor rellenado y reemplazarlo con usted variables: `$(YourValue)`. Por ejemplo, escriba `$(SendPort1)`: 

    ![Paquete de características de BizTalk 1 enlace 3](../core/media/biztalk-feature-pack-1-binding-3.png)


4. Cuando haya terminado, guarde el archivo de enlace y aplicarlo a la plantilla de compilación JSON.
5. Inicie sesión la solución de Visual Studio Team Service y seleccione **de compilación y la versión**.
6. Vaya a **versión**. Seleccione el **definición de la versión**, o cree uno nuevo.
7. En **entornos**, seleccione **agregar un nuevo entorno**, o cambiar a un entorno existente: 

    ![Agregar un nuevo entorno](../core/media/add-a-new-environment.png)

8. Haga clic en el botón de puntos suspensivos y seleccione **configurar variables**:

    ![configurar variables](../core/media/configure-variables.png)

9. Mediante la adición de las variables para cada entorno, mediante los nombres de token que creó en el archivo de enlace, puede implementar las aplicaciones en varios entornos con distintos valores:

    ![variables de entorno específicas](../core/media/environment-specific-variables.png)
    
10. Seleccione **Aceptar** para guardar las nuevas variables.
11. Una vez que se inicia la compilación, se agregan los valores del archivo de enlace.

## <a name="next-step"></a>Paso siguiente
[Agregar una aplicación de BizTalk a VSTS](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)